<template>
  <div>
    <!---using the data passed from the app.vue todos here-->
    <p>{{ todoArray.completed }}</p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  components: {},
  //   props: {
  //     todoArray: String,
  //   },

  //data from the app.vue sent to todolist.vue now to todoitem component prop drilling data from grandmother to mother to child
  //
  props: ["todoArray"],
};
</script>

<style>
</style>