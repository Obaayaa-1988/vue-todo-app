<template>
  <div>
    <div>
      <div class="bg-white h-2/4 w-2/4 py-3 rounded m-auto mb-7 md">
        {{ todoArray.task }}

        <div class="float-right mb-">
          <button class="bg-pink-700 text-white py-3 px-8 rounded"> Update</button>
          <button class="bg-pink-700 text-white py-3 px-8 rounded ml-3">Delete</button>
        </div>
      </div>
    </div>

    <!---using the data passed from the app.vue todos here-->
    <!-- <div class="bg-white w-2/4 pt-4 pb-4 ml-auto mr-auto md shadow-md">
      
    </div> -->
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  components: {},

  //data from the app.vue sent to todolist.vue now to todoitem component prop drilling data from grandmother to mother to child
  //
  props: ["todoArray"],
};
</script>

<style>
</style>