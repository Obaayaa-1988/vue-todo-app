<template>
  <div id="app">
    <!----This where we are transferring the todos array data to the Todolist Component and then transfer to the todoItem component-->
    <div class="bg-red-300 w-screen min-h-screen overflow-hidden">
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
// import axios from "axios"
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
        { id: 1, task: "Visit Germany and visit friends", completed: false },
        { id: 2, task: "Visit Canada and visit friends", completed: false },
        { id: 3, task: "Visit Armsterdam", completed: false },
        { id: 4, task: "Visit USA", completed: false },
        { id: 5, task: "Visit Norway", completed: false },
      ],
    };
  },
  methods: {
    addTask(newTask) {
      this.todosArray = [...this.todosArray, newTask]; //newTask parameter is from the parameter passed for the event(emit) in addTodo Component
      // console.log("jsjjdjjdjjj", newTask);
    },

    deleteTask(taskId) {
      this.todosArray = this.todosArray.filter((todo) => todo.id !== taskId);
      console.log("mmdmdmmaaamm", taskId)
    },

    
  },

  


};
</script>