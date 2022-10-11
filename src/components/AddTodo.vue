<template>
  <div>
    <div class="bg-red-200 pb-16 w-2/4 rounded-lg ml-auto mr-auto mb-12 md">
      <h2 class="text-center text-white text-3xl pt-8 font-mono font-extrabold">
        TODO APP
      </h2>

      <form  class="ml-40 pt-16 md" >
        <input
          type="text"
          placeholder="add a todo"
          v-model="task"
          name="task"
          class="h-12 w-2/3 rounded md outline-none pl-2"
        />
        <button type="submit" class="bg-red-400 text-white py-3 px-8 rounded" v-bind:disabled="!task" @click="addTodos">Add</button>
      </form>
      
    </div>
  </div>
</template>

<script>

import { v4 as uuidv4 } from "uuid";
import axios from "axios";

export default {
  name: "AddTodo",
  

  data() {
    return {
      id: '',
      task: "",


      // newTask: {
      //    id: uuidv4(),
      //   task: this.task,
      //   completed: false,

      // }
    };
  },

  methods: {
    // addTask(e) {
    //   e.preventDefault();
    //   const newTask = {
    //     id: uuidv4(),
    //     task: this.task,
       
    //   };
      


   
    addTodos(e){
      e.preventDefault();
      axios.post("http://localhost:7576/api/task", {
         id: uuidv4(),
        task: this.task,
        completed: false
      
      })
     
      .then(async (response) => {
         console.log ("ashbella",response)
          console.log("amaa", response.data)
        if(response){
         
          this.task = await response.data
           this.task = " ";
          
        }
      })
      .catch((err) => {
        console.log(err)
      })

      this.$emit("add-todo", ); //sending out data to the parent component by creating a custome event
     
    },


 
  },
      
 

}






//addtodo component was separately created for adding new todo and new Task ="" added in data and addTask method function was
//was also implemented. The addTask method is now added to the the form tag and newTask(task) added to the input field using v-model directive
//the addTask method was then emitted and a custom event created for it, addTodo component is then imported to the grandparent component app.vue, the emmited data(event) is now bind to the
//addTodo component as an event
//a new addTask method is created inside app.vue and the array of object(existing data) spread, opened to add the new tasks to it, the array of objects, the new addTask is added to the v-on in the addTodo component
//
</script>

<style>
</style>