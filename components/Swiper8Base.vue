<template>
<div ref="swiper" class="swiper">
  <div class="swiper-wrapper">
    <div class="swiper-slide">Slide 1</div>
    <div class="swiper-slide">Slide 2</div>
    <div class="swiper-slide">Slide 3</div>
  </div>
  <div ref="prev" class="swiper-button-prev"></div>
  <div ref="next" class="swiper-button-next"></div>
  <div ref="pagination" class="swiper-pagination"></div>
</div>
</template>

<script>
import Swiper from 'swiper8/swiper-bundle.min'
import 'swiper8/swiper.min.css'

export default {
  name: 'Swiper8Base',
  data(){
    return {
      swiper: null,
    }
  },
  mounted(){
    this.swiperInit()
  },
  methods:{
    swiperInit(){
      this.$nextTick(() => {
        this.swiper = new Swiper(this.$refs.swiper, {
          loop: false,
          pagination: {
            el: this.$refs.pagination,
          },
          navigation: {
            prevEl: this.$refs.prev,
            nextEl: this.$refs.next,
          },
        })
      })
    },
  }
}
</script>

<style lang="css" scoped>
.swiper {
  width: 800px;
  height: 300px;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
