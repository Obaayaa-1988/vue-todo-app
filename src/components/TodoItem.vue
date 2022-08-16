<template>
  <div>
    <!---using the data passed from the app.vue todos here-->
    <div class="bg-blue-700 w-2/4 pb-7 pt-7 " >
      <div >
        <p class="bg-white h-2/4 w-2/4 py-2  rounded  " >{{ todoArray.task }} </p>
  
      </div>

    </div>
 
  </div>
</template>

<script>

export default {
  name: "TodoItem",
  components: {
   
  },
  
  //data from the app.vue sent to todolist.vue now to todoitem component prop drilling data from grandmother to mother to child
  //
  props: ["todoArray"],
};
</script>

<style>
</style>