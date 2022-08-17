<template>
  <div>
    <div class="bg-purple-300 pb-16 w-2/4 rounded-lg ml-auto mr-auto">
      <h2 class="text-center text-white">My Todolist</h2>

      <form @submit="addTask" class="ml-40 pt-16 md">
        <input
          type="text"
          placeholder="add a todo"
          v-model="task"
          name="task"
          class="h-10 w-2/4 rounded"
        />
        <button type="submit" class="bg-pink-700 text-white py-3 px-8 rounded">
          Add
        </button>
      </form>
      <!-- <p>{{listTodo.task}}</p> -->
    </div>
  </div>
</template>

<script>
// import uuid from "uuid";

export default {
  name: "AddTodo",
  //  props: ["listTodo"],

  data() {
    return {
      task: "",
    };
  },

  methods: {
    addTask(e) {
      e.preventDefault();
      const newTask = {
        // id: uuid.v4(),
        task: this.task,
        completed: false,
      };
      this.$emit("add-task", newTask);//sending out data to the parent component by creating a custome event
      this.task = " ";
    },
  },
};
</script>

<style>
</style>