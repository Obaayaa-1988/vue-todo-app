<template>
  <div id="app">
    <!----This where we are transferring the todos array data to the Todolist Component and then transfer to the todoItem component-->
    <div class="bg-red-300 w-screen min-h-screen overflow-hidden">
      <NavBar />
      <AddTodo v-on:add-todo="addTodos" />
      <TodoLists v-on:delete-task="deleteTask" />
      
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
      
    };
  },
  methods: {
    addTodos() {
      this.todosArray = [...this.todosArray, ]; //newTask parameter is from the parameter passed for the event(emit) in addTodo Component
      // console.log("jsjjdjjdjjj", newTask);
    },

    deleteTask(taskId) {
      this.todosArray = this.todosArray.filter((todo) => todo.id !== taskId);
      console.log("mmdmdmmaaamm", taskId)
    },


    
  },

  


};
</script>