<!-- Form Bindings -->
<!-- combining bindings -->
<script setup>
  import {ref} from 'vue'
  
  const text = ref('')
  
  function onInput(e){
	  text.value = e.target.value;
  }
</script>

<template>
  <h1>Form Bindings</h1>
  <input :value="text" @input="onInput" placeholder="Type here">
  <p>This is the same as the following:</p>
  <input v-model="text" placeholder="Type here">
  <p>{{text}}</p>
</template>