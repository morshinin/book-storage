<template>
  <div id="app">
    <AddBookItem @add-book-event="addBook" />
    <Books :books="books" />
  </div>
</template>

<script>
import Books from './components/Books.vue';
import AddBookItem from './components/AddBookItem.vue';

export default {
  name: 'App',
  components: {
    Books,
    AddBookItem
  },
  data() {
    return {
      books: []
    }
  },
  methods: {
    addBook(newBook) {
      this.books = [...this.books, newBook]
    }
  },
  watch: {
    books: {
      handler() {
        localStorage.setItem('books', JSON.stringify(this.books))
      },
      deep: true
    }
  },
  mounted() {
    if (localStorage.getItem('books')) {
      this.books = JSON.parse(localStorage.getItem('books'))
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
