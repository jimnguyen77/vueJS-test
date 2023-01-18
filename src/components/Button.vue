<template>
	<button @click="onClick()" :style="{ background: color }" class="btn">{{ text }}</button>
</template>

<script>
export default {
	name: 'Button',
	props: {
		text: String,
		color: String
	},
	methods: {
		onClick() {
			this.$emit('btn-click')
		},
	}
}
</script>

<style scoped>
button {
	font-size:1.25em;
	font-weight:900;
	padding:5px 10px;
}
</style>
