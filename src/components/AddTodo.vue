<template>
  <div>
    <div class="bg-red-200 pb-16 w-2/4 rounded-lg ml-auto mr-auto mb-12 md">
      <h2 class="text-center text-white text-3xl pt-8 font-mono font-extrabold">
        TODO APP
      </h2>

      <form @submit="addTask" class="ml-40 pt-16 md" >
        <input
          type="text"
          placeholder="add a todo"
          v-model="task"
          name="task"
          class="h-12 w-2/3 rounded md outline-none pl-2"
        />
        <button type="submit" class="bg-red-400 text-white py-3 px-8 rounded" v-bind:disabled="!task">Add</button>
      </form>
      
    </div>
  </div>
</template>

<script>

import { v4 as uuidv4 } from "uuid";

export default {
  name: "AddTodo",
  

  data() {
    return {
      task: "",
    };
  },

  methods: {
    addTask(e) {
      e.preventDefault();
      const newTask = {
        id: uuidv4(),
        task: this.task,
        completed: false,
      };
      this.$emit("add-task", newTask); //sending out data to the parent component by creating a custome event
      this.task = " ";
    },
  },
};
</script>

<style>
</style>