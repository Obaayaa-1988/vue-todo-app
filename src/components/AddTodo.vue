<template>
  <div>
    <div class="bg-black h-2/4 w-2/4 rounded-lg ml-auto mr-auto text-white">
      <h2 class="text-center">My Todolist</h2>

      <form @submit="addTask" class="ml-40 pt-16">
        <input
          type="text"
          placeholder="add a todo"
          v-model="task"
          name="task"
          class="h-10 w-2/4 rounded"
        />
        <button type="submit" class="bg-blue-700 text-white py-3 px-8 rounded">
          Add
        </button>
        <h2>helooooooo</h2>
        <h2>helooooooo</h2>
        <h2>helooooooo</h2>
        <h2>helooooooo</h2>
        <h2>helooooooo</h2>
      </form>
    </div>
  </div>
</template>

<script>
import uuid from "uuid";

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
        id: uuid.v4(),
        task: this.task,
        completed: false,
      };
      this.$emit("add-task", newTask);
      this.task = "";
    },
  },
};
</script>

<style>
</style>