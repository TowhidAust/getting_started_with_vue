<template>
  <div>
      <div v-for="(todo, index) in todos" v-bind:key="index">
          <TodoItem v-bind:todo="todo"/>
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