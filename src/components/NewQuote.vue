<template>
	<div class="row mt-5 mb-5">
		<div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
			<form action="/">
				<label for="quote">Quote:</label>
				<textarea
					name="quote"
					class="form-control mb-4"
					:disabled="disabled"
					v-model="quote"
				></textarea>
				<div>
					<button class="btn btn-primary" :disabled="disabled" @click.prevent="createNew">
						Add quote
					</button>
				</div>
			</form>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'NewQuote',
		props: ['disabled'],
		data() {
			return {
				quote: '',
			};
		},
		methods: {
			createNew() {
				if (this.quote !== '') {
					this.$emit('quoteAdded', this.quote);
					this.quote = '';
				}
			},
		},
	};
</script>
