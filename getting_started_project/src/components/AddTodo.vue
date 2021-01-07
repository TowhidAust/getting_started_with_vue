<template>
  <div>
      <form @submit="addTodo">
          <input type="text" name="title" placeholder="Add Todo" v-model="title">
          <input class="btn" type="submit" value="submit" placeholder="Add Todo">
      </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
export default {
    name: "AddTodo",
    data() {
        return{
            title: ''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false
            }
            // send up to paren
            this.$emit('add-todo', newTodo);
            this.title = '' //form input texts clear
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
    }

    input[type="text"]{
        flex: 10;
        padding: 5px;
    }
    input[type="submit"]{
        flex: 2;
    }
</style>