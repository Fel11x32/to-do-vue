<template>
	<section>
		<div class="container">
			<h3>TODO LIST</h3>

			<div v-if="todos.length > 0">
				<TodoItem
					v-for="todo in todos"
					:todo="todo"
					:key="todo.id"
				/>
			</div>
			<h2 v-else style="color: red">There are no todos</h2>
		</div>
	</section>
</template>

<script setup>
import TodoItem from './TodoItem.vue';

defineProps({
	todos: {
		type: Array,
		required: true,
	},
})
</script>

<style scoped></style>
