<template>
  <div id="app">
    <div id="homepage">
      <home-page/>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import HomePage from './components/HomePage'

export default {
  name: 'App',
  components: {
    HelloWorld,
    HomePage
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto+Condensed&subset=vietnamese');
  @import url('https://fonts.googleapis.com/css?family=Roboto');
  * {
    box-sizing: border-box;
  }
  body {
    font-family: 'Roboto Condensed', sans-serif;
  }
  #homepage {
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-image: url('./assets/background.svg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 50%;
    overflow: hidden;
    min-height: 100vh;
    user-select: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
  }
</style>

