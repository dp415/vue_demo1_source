<!-- Demo 7 -->
<!-- Computed Property -->
<script setup>
import { ref, computed } from 'vue'

const hideCompleted = ref(false);

let id=0;
const newTodo=ref('');
const todos=ref([
	{id:id++,text:'Learn HTML', done:true},
	{id:id++,text:'Learn Javascript', done:true},
	{id:id++,text:'Learn Vue', done:false}
])

const filteredTodos = computed(() => {
	// return filtered todos based on
	// `todos.value` & `hideCompleted.value`
	
	//if hideCompleted == true
		//return a list/array copy of todos filtered to remove what is done (done==true should not be in the new list)
	
	//test if following code is the issue
	/**/
	if(hideCompleted.value)
		return todos.value.filter(removeCompleted);
	else
		return todos.value;
	function removeCompleted(item){
		return item.done==false;
	}
	/**/
	/**
	return hideCompleted.value
	    ? todos.value.filter((t) => !t.done)
	    : todos.value
	/**/
})

function addTodo(){
	todos.value.push({id:id++,text:newTodo.value, done:false});
	newTodo.value='';
}
function removeTodo(todo){
	/**/
	todos.value=todos.value.filter(removeItem);
	function removeItem(item){
		return item != todo;
	}
	/**/
	//more efficient
	/**
	todos.value = todos.value.filter((t) => t !== todo)
	/**/
}
</script>

<template>
	<h1>Computed Property</h1>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>{{newTodo}}
  </form>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
	  <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
</template>

<style>
.done {
	text-decoration: line-through;
}
</style>