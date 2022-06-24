<!-- Declarative Rendering -->
<!-- Text Interpolation -->
<!--
import { createApp } from 'vue'

const app = createApp({
	/* root component options */
})
-->

<!-- TEXT INTERPOLATION -->
<script setup>
/**/
import { reactive, ref} from 'vue'

const counter = reactive({count: 0})
const message = ref('Hello World')
/**/
</script>

<script>
// finished options example //
export default {
	data() {
		return {
			message2: 'hello world: using options',
			counter2: {
				count: 0
			}
		}
	}
}
</script>

<template>
  <h1>Declarative Rendering</h1>
  <h1>{{message}}</h1>
  <p>count is: {{counter.count}}</p>
  <h1>message 2: {{message2}}</h1>
  <p>count is {{counter2.count}}</p>
</template>

<!-- options outline -->