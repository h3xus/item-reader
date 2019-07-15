<template>
  <div id="app">
    <div class="bar"></div>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <div class="app-contanier">
      <router-view/>
    </div>
  </div>
</template>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 auto;
}
.bar{
  background: linear-gradient(141deg, #48ded4 0%, #a026bf 51%, #e82c75 75%);
  width: 100%;
  height: 20px;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
.app-contanier {
 height: 100vh;
 display: grid;
 margin: 0 auto;
 max-width: 640px;
 align-content: center;
 padding: 0 16px;
}
</style>
