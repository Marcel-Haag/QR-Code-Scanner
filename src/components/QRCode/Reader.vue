<template>
  <div class="flex h-screen" id="qr-stream">
    <div class="m-auto">
      <qrcode-stream @decode="decode" :track="drawOutline"></qrcode-stream>
    </div>
  </div>
</template>

<script>

import {QrcodeStream} from 'vue-qrcode-reader'

export default {
  name: 'Reader',
  components: {
    QrcodeStream
  },
  methods: {
    decode (decodedString) {
      console.info(decodedString)
      alert('Scanned Value: \n\n' + decodedString)
    },

    drawOutline (decodedData, context) {
      var points = decodedData[0].cornerPoints

      context.lineWidth = 6
      context.strokeStyle = '#41B883'

      context.beginPath()
      context.moveTo(points[0].x, points[0].y)

      for (const {x, y} of points) {
        context.lineTo(x, y)
      }

      context.lineTo(points[0].x, points[0].y)
      context.closePath()
      context.stroke()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

#qr-stream {
  width: 100%;
  height: 100%;
}
</style>
