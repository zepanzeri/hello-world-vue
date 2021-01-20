<template>
  <div id="app">
    <Header />
    <AddBook v-on:add-book="addBook" />
    <Books v-bind:books="books" v-on:del-book="deleteBook" />
  </div>
</template>

<script>
import Books from "./components/Books.vue";
import Header from "./components/layout/Header.vue"
import AddBook from "./components/AddBook.vue"

export default {
  name: 'App',
  components: {
    Books,
    Header,
    AddBook
  },
  data(){
    return {
      books:[{
        id:1,
        title:"The Hobbit"
      },
      {
        id:2,
        title:"Alice in Wonderland"
      },
      {
        id:3,
        title:"Fahrenheit 451"
      }]
    }
  },
  methods:{
    deleteBook(id){
      this.books=this.books.filter(book=>book.id !== id);
    },
    addBook(newBook){
      this.books=[...this.books,newBook];
    }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding:0;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn{
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover{
    background: #666;
  }
</style>
