<template>
	<div>
		<form @submit.prevent="addBook">
			<input type="text" name="title" v-model="title" placeholder="Add book title">
			<button type="submit">Add book</button>
		</form>
	</div>
</template>

<script>
export default {
	name: 'AddBookItem',
	data() {
		return {
			title: ''
		}
	},
	methods: {
		addBook() {
			const newBook = {
				title: this.title
			};
			if (newBook.title !== '') {
				this.$emit('add-book-event', newBook);
			}
			this.title = ''
		}
	}
}
</script>