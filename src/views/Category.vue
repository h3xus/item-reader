<template>
    <div>
        <img :src="imgSrc" alt="">
    </div>
</template>

<script>
export default {
  name: 'Category',
  data () {
    return {
      id: Number,
      imgSrc: Object
    }
  },
  methods: {
    getPicture: function () {
      this.imgSrc = localStorage.getItem('item-reader-food-itemoken')
    }
  },
  created () {
    this.getPicture()
  },
  mounted () {
    this.getPicture()
  }
}
</script>

<style>

</style>
