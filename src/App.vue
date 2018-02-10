<template>
  <div id="app">
      <Headerview :msg="title"></Headerview>
    <img src="./assets/logo.png">
    <Listview @myMsg="getData"></Listview>
  </div>
</template>

<script>
  //import HelloWorld from './components/HelloWorld'
  import Listview from './components/List'
  import Headerview from './components/Header'

  //組件溝通父傳子props

  export default {
    name: 'App',
    components: {
      Listview,
      Headerview
    },
    data() {
      return {
        title: "來覆蓋一張牌吧少年"
      }
    },
    methods: {
      getData(msg) {
        console.log("App.vue組件:" + msg);
        this.title = "你剛剛輸入了:" + msg;
      }
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
