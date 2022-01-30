<template>
  <div class="scanner">
    <h1> {{ msg }} </h1>
    <div id="reader">
      <Reader/>
    </div>
    <!-- Display Demo QR Code -->
    <img id="image" v-bind:src="qrCode" alt="QR Code (demo)">
  </div>
</template>

<script>

import Reader from './Reader'

export default {
  name: 'QRCodeScanner',
  data () {
    return {
      msg: 'QR Code Scanner',
      qrCode: require('../../assets/qr_code.jpg')
    }
  },
  components: {
    Reader
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-size: 2rem;
  font-weight: normal;
}

#image {
  width: 25%;
  height: 25%;
}

#reader {
  margin: auto;
  width: 50%;
  padding-bottom: 2rem;
}
</style>
