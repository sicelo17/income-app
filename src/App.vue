<template>
  <Header />
  <router-view/>
</template>
<script>

import Header from "./components/Header"
export default {
  name: "app",
  components: {
    Header
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

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #eee;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: #007cc7;
  text-decoration: underline;
}
</style>
