<!-- Demo 9 -->
<!-- Watchers -->

<script setup>
import { ref, watch } from 'vue'

const todoId = ref(1)
const todoData = ref(null)

async function fetchData() {
  todoData.value = null
  const res = await fetch(
    `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
  )
  todoData.value = await res.json()
}

fetchData()

/**
watch(count, (newCount) => {
 console.log(`new count is: ${newCount}`)
 fetchData()
})
/**/
watch(todoId,fetchData)//watch parameter 1, do function in parameter 2
</script>

<template>
  <h1>Watchers</h1>
  <p>Todo id: {{ todoId }}</p>
  <button @click="todoId++">Fetch next todo</button>
  <p v-if="!todoData">Loading...</p>
  <pre v-else>{{ todoData }}</pre>
</template>