<!-- Demo 6 -->
<!-- List Rendering -->
<script setup>
import { ref } from 'vue'

let id=0;
const newTodo=ref('');
const todos=ref([
	{id:id++,text:'Learn HTML'},
	{id:id++,text:'Learn Javascript'},
	{id:id++,text:'Learn Vue'}
])

function addTodo(){
	todos.value.push({id:id++,text:newTodo.value});
}
function removeTodo(todo){
	todos.value=todos.value.filter(removeItem);
	function removeItem(item){
		return item != todo;
	}
}
</script>

<template>
  <h1>List Rendering</h1>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>{{newTodo}}
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>