<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id: </label>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <label for="password">pw: </label>
      <input id="password" type="text" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
// npm i axios
import axios from 'axios';

export default {
  data: function() {
    return {
      username: '', 
      password: '',
    }
  }, 
  methods: {
    submitForm: function() {
      // event.preventDefault(); // JS로 새로고침 막기
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username, 
        password: this.password
      }
      axios.post(url, data)
        .then(function(response) {
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  }
}
</script>

<style>

</style>