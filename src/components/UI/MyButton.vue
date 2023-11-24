<template>
	<button>
		<slot></slot>
	</button>
</template>

<script setup></script>

<style scoped>
button {
	display: block;
	padding: 0.5rem;
	border-radius: 0.25rem;
	color: #FFF;
	cursor: pointer;
	transition: 0.2s ease-in-out;
}
button :hover{
	opacity: 0.75;
}
</style>
