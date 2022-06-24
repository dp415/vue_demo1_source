<!--attribute bindings-->
<!-- v-bind -->
<script setup>
import { ref } from 'vue'

const titleClass = ref('title')

</script>

<template>
  <h1>Attribute Bindings</h1>
  <h1 :class="titleClass">Make Me Red</h1>
</template>

<style>
  .title{
	  color: red;
  }
</style>