<template>
  <div id="app">
    <!----This where we are transferring the todos array data to the Todolist Component and then transfer to the todoItem component-->
      <TodoLists :todosArray="todosArray"/>
  </div>
</template>

<script>
import TodoLists from "./components/TodoLists.vue";
export default {
  name: "app",
  components: {
    TodoLists,
    // register component
  },
  data (){
    return{
      todosArray: [
        { id: 1,
          task: "Go to Australia",
          completed: false

        },
        { id: 2,
          task: "Go to Canada",
          completed: false

        },
        { id: 3,
          task: "Go to Armsterdam",
          completed: false

        },
        { id: 4,
          task: "Go to USA",
          completed: false

        },
        { id: 5,
          task: "Go to Norway",
          completed: false

        },
        
      ]
    }
  }
};
</script>