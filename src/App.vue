<script setup>
import Greeting from './components/Greeting.vue'
import CreateTodo from './components/CreateTodo.vue'
import TodosList from './components/TodosList.vue'

import { ref, computed } from 'vue'

const todos = ref([])
const addTodo = newTodo => {
	if (newTodo.title.trim() === '' || newTodo.type === null) {
		return
	}
	todos.value.push(newTodo)
}
const removeTodo = todo => {
	todos.value = todos.value.filter(t => t.id !== todo.id)
}

const todoAsc = computed(() => todos.value.sort((a, b) => {
	return b.id - a.id
}))
</script>

<template>
	<main class="main">
		<Greeting class="greeting-section" />
		<CreateTodo @create="addTodo" class="create-to-do-section" />
		<TodosList @remove="removeTodo" class="todos-list" :todos="todoAsc" />
	</main>
</template>

<style scoped>
.greeting-section {
	margin-top: 1.2rem;
}
.create-to-do-section,
.todos-list {
	margin-top: 1.5rem;
}
</style>
