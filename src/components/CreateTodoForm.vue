<template>
	<form @submit.prevent="createTodo">
		<h4>What's on your todo list?</h4>
		<MyInput
			type="text"
			placeholder="a.g. make a website"
			v-model="todo.title"
		/>
		<h4>Pick a category</h4>
		<div class="options">
			<label>
				<MyInput
					type="radio"
					name="category"
					value="business"
					v-model="todo.type"
				/>
				<span class="bubble business"></span>
				<div>Business</div>
			</label>

			<label>
				<MyInput
					type="radio"
					name="category"
					value="personal"
					v-model="todo.type"
				/>
				<span class="bubble personal"></span>
				<div>Personal</div>
			</label>
		</div>

		<MyInput
			class="button-submit"
			:class="todo.type"
			type="submit"
			value="AddTodo"
		/>
	</form>
</template>
<script setup>
import MyInput from './UI/MyInput.vue'
import { ref, defineEmits } from 'vue'

const emit = defineEmits(['create'])

const todo = ref({
	title: '',
	type: null,
})

const createTodo = () => {
	const newTodo = { ...todo.value, id: new Date().getTime() }
	emit('create', newTodo)

	todo.value.title = ''
}
</script>
<style scoped>
.options {
	display: grid;
	grid-template-columns: repeat(2, 1fr);
	grid-gap: 1rem;
	margin-bottom: 1.5rem;
	color: var(--dark);
}
.options label {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	padding: 1.5rem;
	background-color: #fff;
	border-radius: 0.5rem;
	box-shadow: var(--shadow);
	cursor: pointer;
}
.button-submit.business {
	box-shadow: var(--business-glow);
	background-color: var(--business);
}
</style>
