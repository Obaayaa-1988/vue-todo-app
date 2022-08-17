<template>
  <div>
    <div v-bind:class="{'completed': todoArray.completed}" >
      <div class="bg-white h-2/4 w-2/4 py-3 rounded m-auto mb-7 md pl-8">
       <div class="cursor-pointer float-left" v-on:click="markTodo">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 mr-7 text-green-400"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                fillRule="evenodd"
                d="M6.267 3.455a3.066 3.066 0 001.745-.723 3.066 3.066 0 013.976 0 3.066 3.066 0 001.745.723 3.066 3.066 0 012.812 2.812c.051.643.304 1.254.723 1.745a3.066 3.066 0 010 3.976 3.066 3.066 0 00-.723 1.745 3.066 3.066 0 01-2.812 2.812 3.066 3.066 0 00-1.745.723 3.066 3.066 0 01-3.976 0 3.066 3.066 0 00-1.745-.723 3.066 3.066 0 01-2.812-2.812 3.066 3.066 0 00-.723-1.745 3.066 3.066 0 010-3.976 3.066 3.066 0 00.723-1.745 3.066 3.066 0 012.812-2.812zm7.44 5.252a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                clipRule="evenodd"
              />
            </svg>
          </div> 
        {{ todoArray.task }}

        <div class="float-right flex justify-center">
          
          <div class="cursor-pointer">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 mr-12 text-red-400"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              strokeWidth="{2}"
            >
              <path
                strokeLinecap="round"
                strokeLinejoin="round"
                d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>


  </div>
</template>

<script>
export default {
  name: "TodoItem",
  components: {},

  //data from the app.vue sent to todolist.vue now to todoitem component prop drilling data from grandmother to mother to child
  //
  props: ["todoArray"],
  data() {
    return {
      tasks: this.todoArray,
    };
  },

  methods: {
    markTodo() {
      this.tasks.completed = !this.tasks.completed;//method for updating the todo from imcompleted to completed by striking through
    },
  },
};
</script>

<style scoped>
.completed {
    text-decoration: line-through;
  }

</style>