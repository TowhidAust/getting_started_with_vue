<template>
  <div id="app">
    <Header/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" v-on:complete-todo="completedTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos';
import Header from './components/layout/Header';
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
      todos: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo Two",
          completed: false
        },
        {
          id: 3,
          title: "Todo Three",
          completed: false
        },
        
      ]
    }
  },
  methods: {
    deleteTodo(id){
      // delete from the array
      this.todos = this.todos.filter(todo=> todo.id !== id)
    },
    completedTodo(id){
      // mark as completed if checked.
      let todos = this.todos;
      for(let index in todos){
        let todoId = todos[index].id;
        if(id === todoId){
          this.todos[index].completed = !this.todos[index].completed
        }
      }
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo];
    }
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;

  }

  .btn{
    display: inline-block;
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
