<template>
  <div>
       <div v-bind:class="{ 'completed' : todoEntry.completed }">
        <p @click="markComplete">{{ todoEntry.title }}</p>
        hello test
      </div>
  </div>
</template>

<script>

export default {
    name: 'TodoList',
    props: ['todoEntry'],

      methods: {
    markComplete(){
      this.todoEntry.completed = !this.todoEntry.completed
    }
  }

}
</script>

<style>
.completed{
    text-decoration: line-through;
}

</style>