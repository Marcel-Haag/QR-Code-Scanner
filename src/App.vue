<template>
  <div id="app">
    <Home/>
    <QRCodeScanner/>
  </div>
</template>

<script>

import Home from './components/Home'
import QRCodeScanner from './components/QRCode/QRCodeScanner'

export default {
  name: 'App',
  components: {
    Home,
    QRCodeScanner
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
