<template>
  <div id="app">
    <Header/>
    <AddTodo/>
    <Todos v-bind:todos="todos" v-on:del-todo2="deleteTodo"/>            
  </div>
</template>

<script>
import Header from './components/layaout/Header';
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
      todos:[
        {
          id: 1,
          title: 'Todo One',
          completed: true
        },
        {
          id: 2,
          title: 'Todo Two',
          completed: true
        },
        {
          id: 3,
          title: 'Todo Three',
          completed: false
        }
      ],
      a:3
    }
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn{
  font-family: Arial, Helvetica, sans-serif;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover{
  background: #666;
}
</style>
