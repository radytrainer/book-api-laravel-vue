<template>
  <div class="card-container" v-if="books.length > 0">
    <FormView @addBook="addNewBook"/>
    <card-view v-for="(book, index) in books" :key="index" :book="book" @deleteBook="deleteBook" />
  </div>
</template>

<script>
import axios from "axios";
import FormView from './components/FormView.vue';
import CardView from './components/CardView.vue';
export default {

  components: {
    "card-view": CardView,
    FormView
},
data() {
  return {
    apiURL: "http://localhost:81/api/books/",
    books: []
  }
},
methods: {
  getBook() {
    axios.get(this.apiURL)
    .then(response => {
      this.books = response.data;
    })
  },
  addNewBook(object) {
    axios.post(this.apiURL, object)
    .then(res => {
      console.log(res.data);
    });
  },
  deleteBook(id) {
    axios.delete(this.apiURL + id)
    .then(res=> {
      console.log(res.data);
    })
  }
},
mounted() {
  this.getBook();
}
}
</script>

<style>
#app {
  font-family: sans-serif;
  width: 40%;
  margin: auto;
}
</style>
