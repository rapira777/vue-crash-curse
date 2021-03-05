<template>
 <div id="app">
   <h1>Ежедневник</h1>
   <AddTodo @add-todo="addTodo"
   />
   <hr>
   <ToDoList 
      v-bind:todos="todos" 
      @remove-todo="removeTodo" 
    
   />
   </div>
</template>
// https://www.youtube.com/watch?v=OlnwgS-gk8Y
<script>
import ToDoList from './components/ToDoList'
import AddTodo from './components/AddTodo'

export default {
  name: 'App',
  data() {
    return {
      todos:[
          {id: 1, title: 'Купить хлеб', completed: false},
          {id: 2, title: 'Купить масло', completed: false},
          {id: 3, title: 'Купить сыр', completed: false},
      ]
    }
  },
   methods: {
    removeTodo(id) {
      console.log('App - удаляю id = ',id);
      this.todos = this.todos.filter(t=> t.id !== id)
    },
    
    addTodo(todo) {
      this.todos.push(todo)
    },
  },
  components: {
    ToDoList,AddTodo
  },
 
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
