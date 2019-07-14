<template>
    <div>
        <div class="camera-comp ele-video" v-if="!shot">
            <video id="video" width="640" height="480" autoplay></video>
        </div>
        <div class="camera-comp ele-buttons">
            <button v-on:click="makeAshot">Snap Photo</button>
        </div>
        <div class="camera-comp ele-images" >
            <canvas id="canvas" width="640" height="480"></canvas>
        </div>
        <div class="camera-comp ele-retake"  v-if="shot">
            <button v-on:click="Retake"> Retake</button>
        </div>
    </div>
</template>

<script>
var video = document.getElementById('video')
var canvas = document.getElementById('canvas')
var context = canvas.getContext('2d')
var mediaConfig = { video: true }

export default {
  name: 'CameraComp',
  data () {
    return {
      shot: false
    }
  },
  methods: {
    prevCamera: function () {
      if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
        // Not adding `{ audio: true }` since we only want video now
        navigator.mediaDevices.getUserMedia(mediaConfig).then(function (stream) {
        //   video.src = window.URL.createObjectURL(stream);
          video.srcObject = stream
          video.play()
        })
      }
    },
    makeAshot: function () {
      context.drawImage(video, 0, 0, 640, 480)
      this.shot = true
    },
    Retake: function () {
      this.shot = false
    }
  },
  created: {
  },
  mounted () {
    this.prevCamera()
  }
}
</script>

<style lang="css">
body {
    margin:0;
    padding: 0;
}
</style>
