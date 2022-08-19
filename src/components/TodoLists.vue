<template>
  <div class="hello">
    <!-----since we have received the todos array data from app.vue we loop through it to get each item in the array, we can now send eact item as prop to the
    the todoItem component the :todoTask is just the variable name for the prop, todoArray is representing each todo item inside the todoArray-->

    <div>
      <ul>
        <li v-for="todo in todosArray" :key="todo.id">
          <TodoItem
            :todoArray="todo"
            v-on:delete-task="$emit('delete-task', todo.id)"
          
          />
          <!-- <TodoItem
            :todoArray="todo"
            v-on:delete-task="$emit('delete-task', todo.id)"
            v-on:edit-task="$emit('edit-task', todo.id)"
          /> -->
        </li>
      </ul>
      <p v-if="todosArray.length === 0" class="text-center text-white" >No Todos To Display</p>
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

  // props: {
  //   todosArray: Array,
  // },

  props: ["todosArray"],
};
</script>

<style>
</style>