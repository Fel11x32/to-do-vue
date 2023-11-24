<template>
	<div class="todo">
		<span class="bubble" :class="todo.type"></span>
		<div class="todo__title">{{ todo.title }}</div>
	</div>
</template>

<script setup>
import MyInput from './UI/MyInput.vue';

defineProps({
	todo: {
		type: Object,
		required: true,
	},
})
</script>

<style scoped>
.todo {
	display: flex;
	align-items: center;
	background-color: #fff;
	padding: 1rem;
	border-radius: 0.5rem;
	box-shadow: var(--shadow);
	color: var(--dark);
	margin-bottom: 1rem;
}

.todo__title {
	margin-left: .5rem;
}
</style>
