<template>
	<div class="history__item item-history">
		<div class="item-history__color"></div>
		<div class="item-history__content">{{name}}: {{value}} ({{percent}})</div>
	</div>
</template>

<script>
export default {
	props: {
		color: {
			type: String,
			required: true
		},
		value: {
			type: Number,
			required: true
		},
		name: {
			type: String,
			required: true
		},
		percent: {
			type: String,
			required: true
		}
	}
}
</script>

<style lang="scss">
.history {
		&__item {
		}
}
.item-history {
	display: flex;
	gap: 10px;
	justify-content: center;
		&__color {
			background: v-bind(color);
			width: 15px;
			height: 15px;
			border-radius: 15px;
		}
		&__content {
		}
}

</style>