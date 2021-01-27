<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"  />  
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo
  },
  data(){
    return{
      todos:[]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      //push de gegeven todo in de todos array
      this.todos = [...this.todos, newTodo];
    }
    
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  background-color: #f4f4f4;
  max-width: 50%;
  margin: 2em auto;
}

.btn{
  width: 25px;
  height: 25px;
  border: none;
  background: #333;
  color:#fff;
  cursor: pointer;
  margin: .6em 0 0 -2.6em;
}

.btn:hover{
  background: #555;
}
</style>
