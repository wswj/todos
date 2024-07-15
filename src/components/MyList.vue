<template>
    <div>
        <ListItem v-for="item in todos" :key="item.id" @click="deleteMyItem(item.id)"></ListItem>
    </div>
</template>

<script>
import ListItem from './components/ListItem.vue';
export default {
    props: {
        todos: {
            type: Array,
            required: true
        },
        deleteItem: {
            type: Function,
            required: true
        }
    },
    components: {
        ListItem
    },
    methods: {
        deleteMyItem(id) {
            this.deleteItem(id);
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