<script setup>
import { ref, watch, onMounted } from 'vue'
import MyInputName from './UI/MyInputName.vue'

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
				<MyInputName placeholder="Name here" type="text" v-model="name" />
			</h2>
		</div>
	</section>
</template>

<style scoped>
.title {
	display: flex;
	gap: .5rem;
}
</style>
