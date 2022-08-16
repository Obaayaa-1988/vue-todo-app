<template>
  <div class="hello">
    <!-----since we have received the todos array data from app.vue we loop through it to get each item in the array, we can now send eact item as prop to the
    the todoItem component the :todoTask is just the variable name for the prop, todoArray is representing each todo item inside the todoArray-->

    <div>
      <ul>
        <li v-for="todo in todosArray" :key="todo.id" class="text-red-500">
          <TodoItem :todoArray="todo" />
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

  // props: {
  //   todosArray: Array,
  // },

  props: ["todosArray"],
};
</script>

<style>
</style>