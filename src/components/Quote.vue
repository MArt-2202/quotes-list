<template>
	<div class="col-sm-6 col-md-4 col-lg-3">
		<div class="panel-body quote">
			<slot></slot>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Quote',
		data() {
			return {};
		},
	};
</script>

<style lang="scss">
	.panel-body {
		margin-bottom: 20px;
		padding: 10px 15px;
		font-size: 1.4rem;
		font-family: 'Arizonia', sans-serif;
		color: #fff;
		background-color: #00b2b2;
		border-radius: 6px;
		box-shadow: 1px 1px 10px rgba(0, 158, 158, 0.25);
	}

	.quote {
		cursor: pointer;
		transition: all 0.3s ease-in-out;

		&:hover {
			background-color: #009e9e;
		}
	}
</style>
