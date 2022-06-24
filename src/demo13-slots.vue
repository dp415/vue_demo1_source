<!-- Demo 13 -->
<!-- Slots -->
<!-- Send text from parent page to child page -->

<script setup>
import { ref } from 'vue'
import ChildComp from './ChildCompDemo13.vue'

const msg = ref('from parent')
</script>

<template>
  <h1>Slots</h1>
  <ChildComp>Message: {{ msg }}</ChildComp>
</template>