<template>
  <div id="app">
    <Todos :todoEntries="todoEntries" />
    <AddTodo @newEmitpassed="addtodoItemToParent" />
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo.vue";


export default {
  name: "App",
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todoEntries: [
        {
          id: 1,
          title: "Lorem One",
          completed: true,
        },
        {
          id: 2,
          title: "Lorem Two",
          completed: true,
        },
        {
          id: 3,
          title: "Lorem Three",
          completed: true,
        },
      ],
    };
  },
  methods: {
     addtodoItemToParent(newTodo){
         this.todoEntries = [...this.todoEntries, newTodo]
         
     }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
