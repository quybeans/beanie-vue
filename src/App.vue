<template>
  <div id="app">
    <LoginForm/>
  </div>
</template>

<script>
import { default as LoginForm } from "./components/LoginForm";
export default {
  name: 'app',
  components: {
    LoginForm
  }
}
</script>

<style>
@import url('https://unpkg.com/papercss/dist/paper.min.css');
@import url('https://unpkg.com/tachyons@4.9.1/css/tachyons.min.css');
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
