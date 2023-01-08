<template>
  <div>
    <form @submit.prevent="addNewtodo">
        <div class="input-wrapper">
            <input type="text" v-model="title"  name="title"/>
             <button type="submit">Submit</button>
        </div>
      
    </form>
  </div>
</template>



<script>
import { v4 as uuidv4 } from "uuid";

//  A UUID (Universal Unique Identifier) is a 128-bit value used to uniquely identify an object or entity an npm package was installed for this
//  the UUid helps us to generate id for every new todo created
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addNewtodo() {
      let newTodoObj = {
        id: uuidv4(),
        title: this.title,
        completed: false,
      };
        // we use event to pass the new entry to the parent component 
     this.$emit('newEmitpassed', newTodoObj),
     this.title = ''
    },

  
  },
};
</script>

<style scoped>


button {
	margin: 0;
	padding: 0;
	border: 0;
	background:red;
	font-size: 100%;
	vertical-align: baseline;
	font-family: inherit;
	font-weight: inherit;
	color: inherit;
	-webkit-appearance: none;
	appearance: none;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
}
</style>