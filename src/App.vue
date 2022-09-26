<template>
  <div id="app">
    <!----This where we are transferring the todos array data to the Todolist Component and then transfer to the todoItem component-->
    <div class="bg-red-300 w-screen min-h-screen overflow-hidden">
      <NavBar />
      <AddTodo v-on:add-task="addTask" />
      <TodoLists :todosArray="todosArray" v-on:delete-task="deleteTask" />
      <!-- <TodoLists :todosArray="todosArray" v-on:delete-task="deleteTask" v-on:edit-task="editTask"/> -->
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
        { id: 3, task: "Go to Armsterdam", completed: false },
        { id: 4, task: "Go to USA", completed: false },
        { id: 5, task: "Go to Norway", completed: false },
      ],
    };
  },
  methods: {
    addTask(newTask) {
      this.todosArray = [...this.todosArray, newTask]; //newTask parameter is from the parameter passed for the event(emit) in addTodo Component
      console.log("jsjjdjjdjjj", newTask);
    },

    deleteTask(taskId) {
      this.todosArray = this.todosArray.filter((todo) => todo.id !== taskId);
      console.log("mmdmdmmaaamm", taskId)
    },

    // editTask(){
    //   this.todosArray = [...this.todosArray]
    // }
  },

  mounted () {
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => (this.info = response))
  }


};
</script>