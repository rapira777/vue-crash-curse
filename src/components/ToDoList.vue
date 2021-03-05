<template>
    <div>
        <ul>
            <ToDoItem
                v-for="todo of todos" :key="todo.id"
                v-bind:todo="todo"
                v-on:remove-todo="removeTodo"
            />
        </ul>
    </div>
</template>

<script>
import ToDoItem from './ToDoItem'
export default {
    props: ['todos'],
    components: {
    ToDoItem
  }  ,
  methods: {
      removeTodo(id,title) {
         console.log('ToDoList -',id,title);
         this.$emit('remove-todo',id);
      }
  }  
}
</script>

<style scoped>


</style>