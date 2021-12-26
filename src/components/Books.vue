<template>
	<div>
		<h1>
			Books List
		</h1>
		<div v-for="(book, i) in books" :key="i">
			<BookItem :book="book" />
		</div>
	</div>
</template>

<script>
import BookItem from './BookItem.vue';

export default {
	name: 'Books',
	props: {
		books: {
			type: Array,
			required: true
		}
	},
	components: {
		BookItem
	}
}
</script>