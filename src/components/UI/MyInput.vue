<template>
	<input
		:type="type"
		:name="name"
		:placeholder="placeholder"
		:value="modelValue"
		@input="$emit('update:modelValue', $event.target.value)"
	/>
</template>

<script setup>
defineProps({
	modelValue: {
		modelValue: [String, Number],
	},
	name: {
		type: String,
	},
	type: {
		type: String,
		required: true,
	},
	placeholder: {
		type: String,
	}
})
defineEmits(['update:modelValue'])
</script>

<style scoped>
input[type="text"] {
	display: block;
	width: 100%;
	font-size: 1.125rem;
	padding: 1rem 1.5rem;
	color: var(--white);
	background-color: #FFF;
	border-radius: 0.5rem;
	box-shadow: var(--shadow);
	margin-bottom: 1.5rem;
	color: var(--dark);
}

input[type="radio"],
input[type="checkbox"] {
	display: none;
}

input[type="submit"] {
	display: block;
	width: 100%;
	font-size: 1.125rem;
	padding: 1rem 1.5rem;
	color: #FFF;
	background-color: var(--primary);
	border-radius: 0.5rem;
	box-shadow: var(--personal-glow);
	cursor: pointer;
	transition: 0.2s ease-in-out;
}
</style>
