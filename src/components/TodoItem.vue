<template>
	<div class="todo">
		<div class="todo__body">
			<span class="bubble" :class="todo.type"></span>
			<div class="todo__title">{{ todo.title }}</div>
		</div>

		<MyButton @click="$emit('remove', todo)" class="delete">Delete</MyButton>
	</div>
</template>

<script setup>
import MyButton from './UI/MyButton.vue'
import MyInput from './UI/MyInput.vue'

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
	justify-content: space-between;
	background-color: #fff;
	padding: 1rem;
	border-radius: 0.5rem;
	box-shadow: var(--shadow);
	color: var(--dark);
	margin-bottom: 1rem;
}
.todo__body {
	display: flex;
	align-items: center;
}
.todo__title {
	margin-left: 0.5rem;
}
.delete {
	background-color: var(--danger);
}
</style>
