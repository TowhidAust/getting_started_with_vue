<template>
  <div>
      <div class="todo-item" v-bind:class="{'is-complete': todo.completed}">
        <h3>
            <input type="checkbox" v-on:change="$emit('complete-todo', todo.id)">
              {{todo.title}}
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </h3>
      </div>
  </div>
</template>

<script>
export default {
    name: "TodoItem", // this component name,
    props: ["todo"],
    methods: {
        
    }
}
</script>

<style scoped>
    .todo-item{
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #cccccc;
        margin: 5px;
    }


    .todo-item h3{
         display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .is-complete{
        text-decoration: line-through;
    }

    .del{
        background: red;
        border: none;
        color: #f4f4f4;
        padding: 3px;
        border-radius: 3px;
        cursor: pointer;
        height: 25px;
        width: 25px;
    }
</style>