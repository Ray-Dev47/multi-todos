<template>
  <div>
      <div>
         <h2>Todo List</h2>
         <!-- <div  v-for="todoEntry in todoEntries" :key="todoEntry.id">   -->
            <!-- <h4 >{{todoEntry}}</h4> -->
            <!-- <p>{{todoEntry.completed}}</p> -->
             <!-- <div v-bind:class="{'completed': todoEntry.completed}">
                <p @click="completedTask">{{todoEntry.title}}</p>
             -->
                   <!-- </div> -->
                   <ul v-for="todoEntry in todoEntries" :key="todoEntry.id">
                       <li>
                          <!-- <TodoList :todoEntry="todoEntry" /> -->
                          <TodoList>{{todoEntry.title}} </TodoList>
                       </li>
                   </ul>
             
       
         <!-- </div> -->
      </div>
  </div>
</template>

<script>
import TodoList from './TodoList.vue'

export default {
    name: 'Todos',
    props : ['todoEntries'],
    component: {TodoList},
    
    data(){
        return{
            
        }
    },
    // methods: {
    //     completedTask(){
    //         this.todoEntries.completed = !this.todoEntries.completed
    //         console.log('clicked')
    //     }
    // }

}
</script>

<style>
p{
    cursor: pointer;
}
.completed {
        text-decoration: line-through;
      }
</style>