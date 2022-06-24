<!-- Demo 11 -->
<!-- Props -->
<!-- Use a variable from the child in the parent -->

<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue'

const greeting = ref('Hello from parent')
</script>

<template>
  <h1>Props</h1>
  <ChildComp />
  <ChildComp :msg="greeting" />
</template>