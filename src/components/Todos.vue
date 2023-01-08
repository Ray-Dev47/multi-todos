<template>
  <div class="wrapper" v-cloak>
    <h2>ToDos</h2>
    <table>
      <tr v-for="(todo, i) in sortedToDos" :key="i">
        <td>
          <span :class="{ todoDone: todo.done }">{{ todo.text }}</span>
        </td>
        <td>
          <button @click="toggleDone(todo)">
            <span v-if="todo.done"> Incomplete </span><span v-else> Done </span>
          </button>
        </td>
      </tr>
    </table>
    <p>
      <input type="text" v-model="todoText" />
      <button @click="saveToDo">Save ToDo</button>
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      todoText: "",
    };
  },

  methods: {
    saveToDo() {
      if (this.todoText === "") return;
      this.todos.unshift({
        text: this.todoText,
        done: false,
      });
      this.todoText = "";
    },
    toggleDone(todo) {
      todo.done = !todo.done;
    },
  },
  computed: {
    sortedToDos() {
      return this.todos.slice().sort((a, b) => {
        if (!a.done && b.done) return -1;
        if (a.done && b.done) return 0;
        if (a.done && !b.done) return 1;
      });
    },
  },
};
</script>

<style scoped>
[v-cloak] {display: none}

.todoDone {
  color:#c0c0c0;
  text-decoration: line-through;
}
.wrapper{
    border: 1px solid black
}
</style>