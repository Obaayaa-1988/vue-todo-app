<template>
  <div id="app">
      <TodoLists />
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
};
</script>