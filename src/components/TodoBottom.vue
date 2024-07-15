<template>
    <div class="todo-header">
        <h1>{{ title }}</h1>
        <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new todo">
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: 'Todo App',
            newTodo: ''
        };
    },
    methods: {
        addTodo() {
            if (this.newTodo.trim() !== '') {
                // Add your logic to add the new todo here
                console.log('New todo:', this.newTodo);
                this.newTodo = '';
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