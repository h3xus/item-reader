<template>
    <div class="intro">
        <div class="splash">
            <div class="motto">
                <h1>Make your stupid fridge smart again</h1>
            </div>
        </div>
        <router-link to="/">
          <RoundButton title="Begin"></RoundButton>
        </router-link>
    </div>
</template>

<script>
import RoundButton from '@/components/RoundButton.vue'

export default {
    name: "Intro",
    data() {
        return {
            
        }
    },
    methods: {
        
    },
    components: {
        RoundButton
    }
}
</script>

<style>
.intro {
}
.intro .splash {
  position: fixed;
  top:0;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(141deg, #48ded4 0%, #a026bf 51%, #e82c75 75%);
  padding: 5%;
}
.intro .splash .motto {
    color: #fff;
    width: 40%;
    font-size: 3rem;
    margin: 0 auto;
}
</style>
