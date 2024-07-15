<template>
  <div id="app">
    <TodoHeader :addTodo="addTodo" />
    <MyList :todos="todos" :deleteItem="deleteItem"/>
    <TodoBottom />
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue';
import TodoBottom from './components/TodoBottom.vue';
import MyList from './components/MyList.vue';

export default {
  name: 'App',
  components: {
    TodoHeader,
    TodoBottom,
    MyList
  },
  data() {
    return {
      todos:[]
    };
  },
  methods:{
    addTodo(newTodo){
      if(newTodo.trim() !== ''){
        this.todos.push(newTodo);
      }
    },
    deleteItem(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    doneItem(id){
      this.todos = this.todos.map(todo => {
        if(todo.id === id){
          todo.done = !todo.done;
        }
        return todo;
      });
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
