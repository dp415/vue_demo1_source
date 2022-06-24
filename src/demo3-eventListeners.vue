<!-- DOM Events -->
<script setup>
//v-on for dom events
//shortcut is @
//@click="functionName();"
import {ref} from 'vue'

const count=ref(0)

function increment(){
	count.value++
}
</script>

<template>
  <h1>Event Listeners</h1>
  <h2>Counting</h2>
  <button @click="increment">Increase</button> Count is: {{count}}
</template>