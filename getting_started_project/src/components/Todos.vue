<template>
  <div>
      <div v-for="(todo, index) in todos" v-bind:key="index">
          <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" v-on:complete-todo="$emit('complete-todo', todo.id)"/>
      </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem"
export default {
    name: "Todos", // this component name,
    props: ["todos"],
    components: {
        TodoItem
    }
}
</script>

<style scoped>

</style>