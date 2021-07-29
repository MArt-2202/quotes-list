<template>
	<div>
		<div class="progress">
			<div
				class="progress-bar progress-bar-striped"
				role="progressbar"
				:style="progressBarWidth"
			>
				{{ quoteCount }} / {{ maxQuotes }}
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Header',
		props: ['quoteCount', 'maxQuotes'],
		computed: {
			progressBarWidth() {
				return { width: (this.quoteCount / this.maxQuotes) * 100 + '%' };
			},
		},
	};
</script>

<style scoped lang="scss">
	.progress {
		height: 1.75rem;
	}
</style>
