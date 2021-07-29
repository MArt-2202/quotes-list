<template>
	<div>
		<div class="row">
			<Quote
				v-for="(quote, index) in quotes"
				:key="index"
				@click.native="$emit('deleteQuote', index)"
			>
				{{ quote }}
			</Quote>
		</div>
	</div>
</template>

<script>
	/*
		@click.native
		Иногда нужно подписаться на нативные события браузера на корневом элементе компонента.
		В таких случаях можно применять модификатор .native для v-on
	*/
	import Quote from '@/components/Quote';

	export default {
		name: 'QuoteGrid',
		components: {
			Quote,
		},
		props: {
			quotes: {
				type: Array,
				required: true,
			},
		},
		data() {
			return {};
		},
	};
</script>
