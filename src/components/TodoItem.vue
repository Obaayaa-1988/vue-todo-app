<template>
  <div>
    <!---using the data passed from the app.vue todos here-->
    <div class="bg-pink-400 w-2/4 pt-4 pb-4 ml-auto mr-auto md" >
      <div >
        <p class="bg-gray-300 h-2/4 w-2/4 py-2  rounded ml-12 " >{{ todoArray.task }} </p>
  
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