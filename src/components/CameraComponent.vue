<template>
    <div class="camera">
      <p>{{$route.params.name}}</p>
        <div class="camera-comp ele-video" v-show="!shot">
            <video id="video" width="640" height="480" autoplay></video>
        </div>
        <div class="camera-comp ele-buttons" v-if="!shot">
          <div class="btn wrapper" @click="makeAshot()">
            <RoundButton  title="Snap Photo"></RoundButton>
          </div>
        </div>
        <div class="camera-comp ele-images" v-show="shot">
            <canvas id="canvas" width="640" height="480"></canvas>
        </div>
        <div class="camera-comp ele-retake"  v-if="shot">
            <!-- <button v-on:click="Retake"> Retake</button> -->
            <div class="btn wrapper" @click="Retake()">
              <RoundButton title="Retake"></RoundButton>
            </div>
            <div class="btn wrapper" @click="Ok()">
              <RoundButton title="Ok"></RoundButton>
            </div>
        </div>
    </div>
</template>

<script>
import RoundButton from '@/components/RoundButton.vue'

export default {
  name: 'CameraComp',
  data () {
    return {
      shot: false,
      stepName: this.$route.params.name
    }
  },
  components: {
    RoundButton
  },
  methods: {
    prevCamera: function () {
      var video = document.getElementById('video')
      var mediaConfig = { video: true }
      if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
        // Not adding `{ audio: true }` since we only want video now
        navigator.mediaDevices.getUserMedia(mediaConfig).then(function (stream) {
        //   video.src = window.URL.createObjectURL(stream);
          video.srcObject = stream
          video.play()
        })
      }
    },
    token: function (val) {
      if (val) {
        localStorage.setItem('item-reader-food-item', val)
      } else {
        return localStorage.getItem('item-reader-food-itemoken') || 0
      }
    },
    makeAshot: function () {
      var video = document.getElementById('video')
      var canvas = document.getElementById('canvas')
      var context = canvas.getContext('2d')
          context.drawImage(video, 0, 0, 640, 480)
      this.token(canvas.toDataURL('image/png'))
      this.shot = true
    },
    Retake: function () {
      this.shot = false
    },
    Ok: function () {
      this.$router.push('category')
    }
  },
  mounted () {
    this.prevCamera()
  }
}
</script>

<style lang="css">
body, * {
  margin:0;
  padding: 0;
  box-sizing: border-box;
}
.camera {
 border: 1px dotted transparent;
}
video, .camera-comp.ele-images {
  border: 1px solid #000;
}
.camera-comp {
  width: 640px;
  height: 480px;
}
.camera-comp.ele-retake, .camera-comp.ele-buttons  {
  width: 200px;
  margin: 0 auto;
}
.camera-comp.ele-retake .btn.wrapper, .camera-comp .btn.wrapper {
  /* float: left; */
  margin: 10px auto;
  /* widows: 50px; */
}
</style>
