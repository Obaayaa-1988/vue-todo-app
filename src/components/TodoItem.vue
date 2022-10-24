<template>
  <div>
    <div :class="{'completed': diners.completed}">
      <div class="bg-white h-2/4 w-2/4 py-3 rounded m-auto mb-7 md pl-8">
        <div class="cursor-pointer float-left" @click="markTodo(diners._id)">
        <!-- <div class="cursor-pointer float-left" @click="markTodos(diners._id)"> -->
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
        {{ diners.task }}

        <div class="float-right flex justify-center">
          <div class="cursor-pointer">
            <!-- <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mr-8 text-yellow-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth={2}>
         <path strokeLinecap="round" strokeLinejoin="round" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" />
          </svg> -->
          </div>

          <div class="cursor-pointer" @click="deleteATodo(diners._id)">
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
import axios from "axios";

export default {
  name: "TodoItem",
  components: {},

  //data from the app.vue sent to todolist.vue now to todoitem component prop drilling data from grandmother to mother to child
  //
  props: ["diners"],
  data() {
    return {
      completed: false,
      id: '',
      // tasks: this.todoArray,//placed todoArray prop inside an object in data function to prevent mutation of the prop, then we use the key os the object which is
      
    };
  },

  mounted(){
    this.todoTask = this.diners// to correct prop mutation error

  },

  methods: {
    markTodo(id) {
      axios.get(`http://localhost:7576/api/task/${id}`, {
          completed: false, 
        }).then( (response) => {  
          if (response) {
            this.todoTask.completed = !this.todoTask.completed  
          } else {
            console.log('hi there')
               
          }
        }) .catch((err) => {
          console.log(err);
        });
    },

    // markTodos(id){
    //  this.$emit("markTask", id); 
  
    // },


    deleteATodo(id) {
      this.$emit("deleteTask", id);
    },
  },
};

//for delete todo we create a custom event for it inside todoItem component where we have access to each single todo in our array, we give the name of the event and use the
//prop todoArray.id since we are deleting by using each id of the todo, the event is then sent to the parent component Todolist and bindand emit on the todoItem component
//it is then forwarded to the grandparent component app.vue again as an event v-on, a delete method is implemented inside tha app.vue
//the existing data todosArray is then filtered and a condition giving to meet which todo to delete
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>