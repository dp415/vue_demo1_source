<!-- Demo 12 -->
<!-- Emits -->
<!-- Use a function from the child in the parent -->

<script setup>
import { ref } from 'vue'
import ChildComp from './ChildCompDemo12.vue'

const childMsg = ref('No child msg yet')
</script>

<template>
	<h1>Emits</h1>
  <ChildComp @response="(msg) => childMsg = msg + ', other info'+', next variable'"></ChildComp>
  <!-- The structure of an emits function is @emitFunctionName="(anyNameIs1stParam,anyNameIs2ndParam...) => refVarInParentPage = anyNameIs1stParam" -->
  <p>{{ childMsg }}</p>
</template>