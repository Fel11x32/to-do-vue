<template>
	<section>
		<div class="container">
			<h3>CREATE A TO-DO</h3>
			<CreateTodoForm @create="addTodo" />
		</div>
	</section>
</template>

<script setup>
import CreateTodoForm from './CreateTodoForm.vue'
import { defineEmits } from 'vue'

const emit = defineEmits(['create'])

const addTodo = newTodo => {
	emit('create', newTodo)
}
</script>

<style scoped></style>
