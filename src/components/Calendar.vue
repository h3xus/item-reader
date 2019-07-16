<template>
    <div class="calendar">
     <div class="container">
      <h2> july 2019</h2>
      <div class="day day-weekend">S</div>
      <div class="day day-weekend">M</div>
      <div class="day day-weekend">T</div>
      <div class="day day-weekend">W</div>
      <div class="day day-weekend">T</div>
      <div class="day day-weekend">F</div>
      <div class="day day-weekend">S</div>      
      <div class="day day-current-month">1</div>
      <div class="day day-current-month">2</div>
      <div class="day day-current-month">3</div>
      <div class="day day-current-month">4</div>
      <div class="day day-current-month">5</div>
      <div class="day day-current-month">6</div>
      <div class="day day-current-month">7</div>
      <div class="day day-current-month">8</div>
      <div class="day day-current-month">9</div>
      <div class="day day-current-month">10</div>
      <div class="day day-current-month">11</div>
      <div class="day day-current-month">12</div>
      <div class="day day-current-month">13</div>
      <div class="day day-current-month">14</div>
      <div class="day day-current-month">15</div>
      <div class="day day-current-month">16</div>
      <div class="day day-current-month">17</div>
      <div class="day day-current-month">18</div>
      <div class="day day-current-month">19</div>
      <div class="day day-current-month">20</div>
      <div class="day day-current-month">21</div>
      <div class="day day-current-month">22</div>
      <div class="day day-current-month">23</div>
      <div class="day day-current-month">24</div>
      <div class="day day-current-month">25</div>
      <div class="day day-current-month">26</div>
      <div class="day day-current-month">27</div>
      <div class="day day-current-month">28</div>
      <div class="day day-current-month">29</div>
      <div class="day day-current-month">30</div>
      <div class="day day-current-month">31</div>
      <div class="day day-another-month">1</div>
      <div class="day day-another-month">2</div>
      <div class="day day-another-month">3</div>
      <div class="day day-another-month">4</div>
    </div>
    </div>
</template>

<script>
import RoundButton from '@/components/RoundButton.vue'

export default {
  name: 'Calendar',
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
  
  },
  mounted () {
  }
}
</script>

<style lang="scss">

.container {
  background: #fff;
  box-shadow: 0 0 30px rgba(0,0,0,.5);
  color: #333;
  display: grid;
  grid-gap: 10px;
  grid-template: 60px repeat(6, 40px) / repeat(7, 1fr);
  margin: 0 auto 0;
  max-width: 490px;
  padding: 30px;
  & > .day-current-month {
    background: #eee;
  }
}
.day {
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid transparent;
  transition: border 0.2s ease;
  &:hover {
    border: 1px solid #aaa;
    transition: border 0.2s ease;
    cursor: pointer;
  }
  &.day-another-month {
    color: #ccc
  }
  &.day-weekend {
    border: none;
    font-weight: 700;
    &:hover {
      border: none;
      cursor: initial;
    }
  }
  &.day-current {
    border: 3px solid #d2232a;
    background: #fff;
    color: #d2232a;
    font-weight: 700;
  }
}
h2 {
  grid-column: 1 / -1 /*or span 7*/;
  text-align: center;
  border: 1px solid #888;
  margin: 0;
}

</style>
