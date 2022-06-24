<!-- Demo 8 -->
<!-- Lifecycle and Template Refs -->

<script setup>
import { ref, onMounted } from 'vue'

const p = ref(null)

onMounted(() => {
  p.value.textContent = 'mounted!'
})
</script>

<template>
  <h1>Lifecycle And Template Refs</h1>
  <p ref="p">hello</p>
</template>