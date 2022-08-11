<template>
  <div class="hello">
    <!-----since we have received the todos array data from app.vue we loop through it to get each item in the array, we can now send eact item as prop to the
    the todoItem component the :todoTask is just the variable name for the prop, todoArray is representing each todo item inside the todoArray-->
    <NavBar />

    <div>
      <h2>My todolist</h2>
      <ul>
        <li v-for="todo in todosArray" :key="todo.id" class="text-red-500">
          <TodoItem :todoArray="todo" />
        </li>
      </ul>
    </div>
    <!-- <div class="bg-image-backs w-screen h-screen bg-no-repeat bg-center bg-cover" >
        
    <div class="pt-40">

        <div class=" bg-red-200 h-2/4 w-3/6 rounded-lg ml-auto mr-auto  text-white py-8">

            
          <input type="text" placeholder="add a todo" class="text-black"/>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
          <h1>heloooooo hellllooo</h1>
        </div>
    </div>
      
    </div> -->
  </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import TodoItem from "./TodoItem.vue";
export default {
  name: "TodoList",
  components: {
    NavBar,
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