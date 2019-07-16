<template>
  <div id="app">
    <div class="bar"></div>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <div class="app-contanier">
      {{textNote}}
      <router-view :key="$route.fullPath"/>
    </div>
    <div class="sequence-steps" v-show="$route.name!='Intro'">
      <ul class="wrapper">
        <li class="box" v-for="item in sequence" v-bind:key="item.id" :title="item.name">{{item.id}}</li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: "ItemApp",
  data () {
    return {
      sequence: [
        {id: 1, name: 'ItemPicture', alias: '1'},
        {id: 2, name: 'ItemCodebar', alias: '1'},
        {id: 3, name: 'IdemUseByDate', alias: '1'},
        {id: 4, name: 'OpenOrAdded', alias: '1'},
        {id: 5, name: 'SetInCalendar', alias: '1'}
      ],
      fridge: {},
      textNote: this.Jaberdize(Math.random().toString(36).substring(9))
    }
  },
  methods: {
    Jaberdize: function (input) {
      window.location.hash = atob(String(input).replace(/[\t\n\f\r ]+/g, ""))
      return atob(input)
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'DM Serif Display', serif;
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
.sequence-steps .wrapper {
 position: fixed;
 width: 100%;
 bottom: 0; 
 display: flex;
 flex-wrap: nowrap;
 color: #444;
}
.sequence-steps .wrapper .box {
 background-color: #444;
 color: #fff;
 width: 100px;
 border-radius: 15px;
 border: 15px solid #444;
 padding: 20px;
 font-size: 150%;
 margin: 1%;
 list-style: none;
}
.sequence-steps .wrapper .box:hover {
  background: #fff;
  color: #444;
}
</style>
