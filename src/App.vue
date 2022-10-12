<template>
  <div id="app">
    <!----This where we are transferring the todos array data to the Todolist Component and then transfer to the todoItem component-->
    <div class="bg-red-300 w-screen min-h-screen overflow-hidden">
      <NavBar />
      <AddTodo @addTodo="addTodos" />
      <TodoLists :diners="diners" @deleteTask="deleteATodo" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { v4 as uuidv4 } from "uuid";
import NavBar from "./components/NavBar.vue";
import TodoLists from "./components/TodoLists.vue";
import AddTodo from "./components/AddTodo.vue";
// import axios from "axios"
export default {
  name: "App",
  components: {
    NavBar,
    TodoLists,
    AddTodo,
    // register component
  },

  data() {
    return {
      diners: [],
    };
  },
  methods: {
    addTodos(task) {
      console.log(task);
      axios
        .post("http://localhost:7576/api/task", {
          id: uuidv4(),
          task: task,
          completed: false,
        })

        .then( (response) => {
          if (response) {
            this.task = " ";
            this.diners = response.data;
            this.fetchingTodos();
          }
        })
        .catch((err) => {
          console.log(err);
        });
    },

    async fetchingTodos() {
      try {
        const response = await axios({
          method: "GET",
          url: "http://localhost:7576/api/task",
        });
        if (response) {
          this.diners = response.data;
        } else {
          console.log("no data");
        }
      } catch (error) {
        console.log(error);
      }
    },
    async deleteATodo(id) {
      try {
        const response = await axios({
          method: "DELETE",
          url: `http://localhost:7576/api/task/${id}`,
        });
        if (response) {
          this.diners = this.diners.filter((todo) => todo._id !== id);
        } else {
          console.log("no data");
        }
      } catch (error) {
        console.log(error);
      }
    },
  },
  mounted() {
    this.fetchingTodos();
  },
};
</script>