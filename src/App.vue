<template>
  <div id="app" class="container">
    <div class="page-header">
      <h1>Vue.js 2 & Firebase <small>Firebase Sample App</small></h1>
    </div>
    <div class="panel panel-default">
      <div class="panel-heading">
        <h3 class="panel-title">Add New Books</h3>
      </div>
      <div class="panel-body">
        <form id="form" class="form-inline" v-on:submit.prevent="addBook">
          <div class="form-group">
            <label for="bookTitle">Title:</label>
            <input type="text" id="bookTitle" class="form-control" v-model="newBook.title">
          </div>
          <div class="form-group">
            <label for="bookAuthor">Author:</label>
            <input type="text" id="bookAuthor" class="form-control" v-model="newBook.author">
          </div>
          <div class="form-group">
            <label for="bookUrl">Url:</label>
            <input type="text" id="bookUrl" class="form-control" v-model="newBook.url">
          </div>
          <input type="submit" class="btn btn-primary" value="Add Book">
        </form>
      </div>
    </div>
    <div class="panel panel-default">
      <div class="panel-heading">
        <h3 class="panel-title">Book List</h3>
      </div>
      <div class="panel-body">
        <table class="table table-striped">
          <thead>
          <tr>
            <th>Title</th>
            <th>Author</th>
            <th></th>
          </tr>
          </thead>
          <tbody>
          <tr v-for="book in books">
            <td><a v-bind:href="book.url">{{book.title}}</a></td>
            <td>{{book.author}}</td>
            <td><span class="glyphicon glyphicon-trash" aria-hidden="true" v-on:click="removeBook(book)"></span></td>
          </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
  import jQuery from 'jquery'
  global.jQuery = jQuery

  import Hello from './components/Hello'

  import Firebase from 'firebase'

  import toastr from 'toastr'

  let config = {
    apiKey: '...',
    authDomain: '...',
    databaseURL: 'https://vuejs-firebase-01-45ad6.firebaseio.com/',
    storageBucket: '...',
    messagingSenderId: '...'
  }

  let app = Firebase.initializeApp(config)
  let db = app.database()

  let booksRef = db.ref('books')

  export default {
    name: 'app',

    firebase: {
      books: booksRef
    },

    data () {
      return {
        newBook: {
          title: '',
          author: '',
          url: 'http://'
        }
      }
    },

    methods: {
      addBook: function () {
        booksRef.push(this.newBook)
        this.newBook.title = ''
        this.newBook.author = ''
        this.newBook.url = 'http://'
      },
      removeBook: function (book) {
        booksRef.child(book['.key']).remove()
        toastr.success('Book removed successfully')
      }
    },

    components: {
      Hello
    }
  }
</script>

<style lang="scss" scoped>

  $icon-font-path: "../node_modules/bootstrap-sass/assets/fonts/bootstrap/";
  @import "../node_modules/bootstrap-sass/assets/stylesheets/bootstrap";

  #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 20px;
  }
</style>
