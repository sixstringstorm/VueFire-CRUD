<template>
  <div id="app" class="container">
    <div class="page-header">
      <h1>Vue JS & Firebase</h1>

    </div>
    <div class="panel panel-default">
      <div class="panel-heading">
        <h3>Books List</h3>
      </div>
      <div class="panel-body">
        <table class="table table-striped">
          <thead>
            <tr>
              <th>Title</th>
              <th>Author</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="book in books">
              <td><a v-bind:href="book.url">{{book.title}}</a></td>
              <td>{{book.author}}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
import Firebase from 'firebase'

let config = {
  apiKey: "AIzaSyBpyDOKKjzz6BmNgTuK1LwW3KoCwEpCDHM",
  authDomain: "vue-events-f5262.firebaseapp.com",
  databaseURL: "https://vue-events-f5262.firebaseio.com",
  projectId: "vue-events-f5262",
  storageBucket: "vue-events-f5262.appspot.com",
  messagingSenderId: "785499685027"
}

let app = Firebase.initializeApp(config);
let db = app.database();

let booksRef = db.ref('books');

export default {
  name: 'app',
  firebase: {
    books: booksRef
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
