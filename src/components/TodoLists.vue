<template>
  <div class="hello">
    <!-----since we have received the todos array data from app.vue we loop through it to get each item in the array, we can now send eact item as prop to the
    the todoItem component the :todoTask is just the variable name for the prop, todoArray is representing each todo item inside the todoArray-->

    <div>
      <ul>
        <li v-for="todo in diners" :key="todo.id">
          <TodoItem
            :diners="todo"
            v-on:delete-task="$emit('delete-task', todo.id)"
          
          />
        </li>
      </ul>
      
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
import axios from "axios";
export default {
  name: "TodoList",
  components: {
    TodoItem,
  },

 



data() {
        return {
            diners: new Array(),
        }
    },


    methods: {
        // diners: new Array(),


        async geting() {
            try {
                const response = await axios({
                    method: 'GET',
                    url: 'http://localhost:7576/api/task'
                })
                if (response) {
                    this.diners = response.data

                    console.log('heee', response.data)
                   

                    console.log(this.diners)



                } else {
                    console.log('no data')
                }
                //    const data = response.data
                //    console.log(data)
            } catch (error) {
                console.log(error)
            }
        }
    },
    mounted() {
      
        console.log('ToDoComponent mounted.');
        this.geting();
    }
}







</script>

<style>
</style>