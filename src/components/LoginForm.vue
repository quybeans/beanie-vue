<template>
  <div class="form-group"> <div class="mw6 center">
      <h2 class="mb0 pt6">
        Welcome to <span class="blue">eurame</span> crawler
      </h2>
      <h5 class="tc alert alert-secondary ma0" v-if="errorMsg.length > 0">
        {{ errorMsg }}
      </h5>
    </div>
    <div class="mw5 center pt3">
      <div class="flex mt2">
        <label for="username" class="mr2">Username: </label>
        <input id="username" v-model="username" type="text" v-on:keyup.enter="callLogin" />
      </div>
      <div class="flex mt2">
        <label for="password" class="mr2">Password: </label>
        <input id="password" v-model="password" type="password" v-on:keyup.enter="callLogin" />
      </div>
      <div class="mt2">
        <button class="btn-block" v-on:click="callLogin()" > Login </button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'LoginForm',
    data: function() {
      return {
        errorMsg: { default: '', type: String },
        username: '',
        password: ''
      }
    },
    methods: {
      callLogin: function() {
        if (this.validateLogin()) {
          console.log('Sending ' + this.username + ' ' + this.password)
        }
      },
      validateLogin: function() {
        if (this.username.length <= 0 || this.password <= 0) {
          this.errorMsg = 'Username or password shouldnot be empty..'
          return false;
        }
        this.errorMsg = '';
        return true;
      }
    }
  }
</script>
