<template>
	<div>
		<h2>
			{{ book.title }}
		</h2>
	</div>
</template>

<script>
export default {
	name: 'BookItem',
	props: {
		book: {
			type: Object,
			required: true,
			default: function() {
				return {
					title: 'Sample book title',
					description: 'Here goes the book description',
					author: 'Solomon Ghandi'
				}
			}
		}
	}
}
</script>

<style lang="stylus" module>
	
</style>