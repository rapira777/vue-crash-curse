<template>
    <div>
        <ul>
            <ToDoItem
                v-for="todo in todos"
                v-bind:todo="todo"
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
  }    
}
</script>

<style scoped>


</style>