<template>
  <div>
    <form @submit="addTask">
      <input type="text" placeholder="add a todo" v-model="task" name="task" />
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import uuid from 'uuid'

export default {
  name: "AddTodo",
  data(){
    return{
      task:"",

    }
  },

  methods:{
    addTask(e){
      e.preventDefault();
      const newTask = {
        id: uuid.v4(),
        task: this.task,
        completed: false

      }
      this.$emit('add-task', newTask);
      this.task = '';


    }

  }

};
</script>

<style>
</style>