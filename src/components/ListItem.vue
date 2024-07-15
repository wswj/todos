<template>
    <div class="item">
        <input type="checkbox" :checked="todo.done">
    </div>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        }
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
.item {
    display: flex;
    justify-content: start;
    align-items: center;
}
</style>