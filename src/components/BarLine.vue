<template>
	<div class="bar-line"></div>
</template>

<script>
export default {
	props: {
		color: {
			type: String,
			required: true
		},
		width: {
			type: String,
			required: true
		},
		height: {
			type: String,
			required: true
		}
	}
}
</script>

<style lang="scss">
	.bar-line {
		background: v-bind(color);
		width: v-bind(width);
		height: v-bind(height);
		border-radius: 5px;
	}
</style>