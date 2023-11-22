<template>
	<input
		:type="type"
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
	type: {
		type: String,
		required: true,
	},
	placeholder: {
		type: String,
	},
})
defineEmits(['update:modelValue'])
</script>

<style scoped>
input {
	color: var(--light);
	font-size: 1.5rem;
	font-weight: 700;
}
</style>
