<template>
  <div id="app">
    <!----This where we are transferring the todos array data to the Todolist Component and then transfer to the todoItem component-->
    <div class="bg-red-300 w-screen h-screen">
      <NavBar />
      <AddTodo v-on:add-task="addTask" />
      <TodoLists :todosArray="todosArray" v-on:delete-task="deleteTask" />
    </div>
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import TodoLists from "./components/TodoLists.vue";
import AddTodo from "./components/AddTodo.vue";
export default {
  name: "app",
  components: {
    NavBar,
    TodoLists,
    AddTodo,
    // register component
  },
  data() {
    return {
      todosArray: [
        { id: 1, task: "Go to Australia and visit friends", completed: false },
        { id: 2, task: "Go to Canada and visit friends", completed: false },
        // { id: 3, task: "Go to Armsterdam", completed: false },
        // { id: 4, task: "Go to USA", completed: false },
        // { id: 5, task: "Go to Norway", completed: false },
      ],
    };
  },
  methods: {
    addTask(newTask) {
      this.todosArray = [...this.todosArray, newTask];
    },

    deleteTask(taskId) {
      this.todosArray = this.todosArray.filter(todo => todo.id !== taskId);
    },
  },
};
</script>