<template>
  <div>
    <div class="bg-red-200 pb-16 w-2/4 rounded-lg ml-auto mr-auto mb-12 ">
      <h2 class="text-center text-white text-3xl pt-8 font-mono font-extrabold">
        TODO APP
      </h2>

      <form class="ml-40 pt-16 md">
        <input
          type="text"
          placeholder="add a todo"
          v-model="task"
          name="task"
          class="h-12 w-2/3 rounded md outline-none pl-2"
        />
        <button
          type="submit"
          class="bg-red-400 text-white py-3 px-8 rounded"
          v-bind:disabled="!task"
          @click.prevent="addTodos"
        >
          Add
        </button>
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name: "AddTodo",

  props: ["getTasks"], //gettasks 

  data() {
    return {
      id: "",
      task: "",
    };
  },

  methods: {   
    addTodos() {
      this.$emit("addTodo", this.task); //sending out data to the parent component by creating a custome event
      this.task =""                      //sending this add todos function to app.vue in the form of(addTodo parameter) because we to add the todos at the parent component
    },
  },
};

//addtodo component was separately created for adding new todo and new Task ="" added in data and addTask method function was
//was also implemented. The addTask method is now added to the the form tag and newTask(task) added to the input field using v-model directive
//the addTask method was then emitted and a custom event created for it, addTodo component is then imported to the grandparent component app.vue, the emmited data(event) is now bind to the
//addTodo component as an event
//a new addTask method is created inside app.vue and the array of object(existing data) spread, opened to add the new tasks to it, the array of objects, the new addTask is added to the v-on in the addTodo component
//
</script>

<style>
</style>