<template>
    <div class="todo-header">
        <input v-model="newTodo" @keyup.enter="addNewTodo" placeholder="Add a new todo">
    </div>
</template>

<script>
export default {
    props: {
        addTodo: {
            type: Function,
            required: true
        }
    },
    data() {
        return {
            newTodo: ''
        };
    },
    methods: {
        addNewTodo() {
            if (this.newTodo.trim() !== '') {
                var newTodo = {
                    id: Date.now(),
                    title: this.newTodo,
                    done: false
                };
                this.addTodo(newTodo);
            }
        }
    }
};
</script>

<style scoped>
.todo-header {
    padding: 20px;
    background-color: #f2f2f2;
}
</style>