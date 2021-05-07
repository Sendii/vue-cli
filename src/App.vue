<template>
  <div id="app">
    <Header />
  <router-view/>
  </div>
</template>

<script>
  import Header from './components/layouts/Header'
  export default{
    name: "App",
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
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
.card{
  margin: 15px 20px 20px 20px;
  padding: 5px;
  border-radius: 10px;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}
</style>
