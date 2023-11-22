<script setup>
import { ref, watch, onMounted } from 'vue'
import MyInput from './UI/MyInput.vue'

const name = ref('')

watch(name, newVal => {
	localStorage.setItem('name', newVal)
})
onMounted(() => {
	name.value = localStorage.getItem('name') || ''
})
</script>

<template>
	<section>
		<div class="container">
			<h2 class="title">
				What's up,
				<MyInput placeholder="Name here" type="text" v-model="name" />
			</h2>
		</div>
	</section>
</template>

<style scoped>
.title {
	display: flex;
	gap: .5rem;
}
section {
	margin-top: 1.2rem;
}
</style>
