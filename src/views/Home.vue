<template>
  <div class="home">
    <CameraComponent>
    </CameraComponent>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/>s -->
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import CameraComponent from '@/components/CameraComponent.vue'

export default {
  name: 'home',
  components: {
    CameraComponent
  }
}
</script>
