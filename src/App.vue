<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <p>{{ fullName }}</p>
  <hr />
  <HelloWorld msg="Welcome to Your Vue.js App" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() {
    return {
      lastName: "Igiraneza",
      firstName: "Honorine"
    }
  },
  methods: {

  },
  // Return methods as necessary only when the properties in computed are updated
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName.toUpperCase()}`
    }
  },
  components: {
    HelloWorld
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
  margin-top: 60px;
}
</style>
