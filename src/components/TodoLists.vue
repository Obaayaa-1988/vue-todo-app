<template>
  <div class="hello">
    <!-----since we have received the todos array data from app.vue we loop through it to get each item in the array, we can now send eact item as prop to the
    the todoItem component the :todoTask is just the variable name for the prop, todoArray is representing each todo item inside the todoArray-->

    <div>
      <ul>
        <li v-for="todo in diners" :key="todo.id">
          <TodoItem :diners="todo" @deleteTask="deleteATodo"  />
          <!-- <TodoItem :diners="todo" @deleteTask="deleteATodo" @markTask="markTodos" /> -->
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "TodoList",
  components: {
    TodoItem,
  },

  props: ["diners"],

  methods: {

    //  markTodos(id){
    //  this.$emit("markTask", id); 
  
    // },

    deleteATodo(id) {
      this.$emit("deleteTask", id);
    },

   
  },
};
</script>

<style>
</style>