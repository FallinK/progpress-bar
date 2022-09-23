<template>
	<div class="progressBar" ref="progressBar">
		<div class="progress-bar__line">
			<bar-line
				v-for="item in itemsArr"
				:key="item.id"
				:color="item.color"
				:height="height + 'px'"
				:width="width + 'px'"
			/>
		</div>
		<div class="progress-bar__history">
			<bar-history
				v-for="item in items"
				:key="item.name"
				:color="item.color"
				:name="item.name"
				:value="item.value"
				:percent="(item.value / sumValue * 100).toFixed(1) + '%'"
			/>
		</div>
	</div>
</template>

<script>
import BarLine from '@/components/BarLine.vue';
import BarHistory from '@/components/BarHistory.vue';
export default {
  components: { BarLine, BarHistory },
	props: {
		items: {
			type: Array,
			required: true
		},
		width: {
			type: Number,
			required: true
		},
		height: {
			type: Number,
			required: true
		}
	},
	data() {
		return {
			sumValue: 0,
			countBarLines: 0,
			barLineValue: 0,
			itemsArr: [],
		}
	},
	methods: {
		genNewArr() {
			let id = 0;
			this.items.forEach(item => {
				if(item.value > 0) {
					for (let j = 0; j < Math.ceil(item.value/this.barLineValue); j++) {
						this.itemsArr.push({...item, id: id});
						id++;
					}
				}
			});
		}
	},
	mounted() {
		this.items.forEach(item => {
			this.sumValue+= item.value;
		});
		this.countBarLines = Math.round(this.$refs.progressBar.offsetWidth / (this.width + 2));
		this.barLineValue = Math.round(this.sumValue / this.countBarLines);
		this.genNewArr();
	}
}
</script>

<style lang="scss">
.progress-bar {
	&__line {
		display: flex;
		justify-content: space-between;
	}
	&__history {
		margin: 10px 0 0 0;
		display: flex;
		justify-content: space-around;
	}
}
</style>