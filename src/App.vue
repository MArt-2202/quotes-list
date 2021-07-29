<template>
	<div>
		<Header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></Header>
		<NewQuote @quoteAdded="quoteAdded" :disabled="disabled"></NewQuote>
		<QuoteGrid :quotes="quotes" @deleteQuote="deleteQuote"></QuoteGrid>
		<div class="row mt-5 mb-2">
			<div class="col-sm-12 text-center">
				<div class="alert alert-info">Info: Click on a quote to delete it</div>
			</div>
		</div>

		<template v-if="dangerInfo">
			<div class="row">
				<div class="col-sm-12 text-center">
					<div class="alert alert-danger">Danger: Please delete quotes first!</div>
				</div>
			</div>
		</template>
	</div>
</template>

<script>
	import Header from '@/components/Header';
	import QuoteGrid from '@/components/QuoteGrid';
	import NewQuote from '@/components/NewQuote';

	export default {
		name: 'App',
		components: {
			Header,
			QuoteGrid,
			NewQuote,
		},
		data() {
			return {
				quotes: ['Default quotes'],
				maxQuotes: 10,
				dangerInfo: false,
				disabled: false,
			};
		},
		methods: {
			quoteAdded(quote) {
				if (this.quotes.length < this.maxQuotes) {
					this.quotes.push(quote);
				} else {
					this.dangerInfo = true;
					this.disabled = true;
				}
			},
			deleteQuote(index) {
				this.dangerInfo = false;
				this.disabled = false;
				this.quotes.splice(index, 1);
			},
		},
	};
</script>

<style lang="scss"></style>
