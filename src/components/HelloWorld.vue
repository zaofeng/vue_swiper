<template>
  <vue-swiper :show-index.sync="showIndex" loop indicators uselazyload :preload="1" :auto="5000" class="swiper_img" @slide-change="slideChange">
    <vue-swiper-slide class="swiper-item" :key="index" v-for="(item, index) in bannerList">
        <div class="item">
            <div class="c-default-bg img-wrap">
                <img class="lazy" :data-src="item.url">
            </div>
        </div>
    </vue-swiper-slide> 
  </vue-swiper>
</template>

<script>
    import vueSwiper from './vue-swiper.vue'
    import vueSwiperSlide from './vue-swiper-slide.vue'
    export default {
      props: ['bannerList'],
      components: {
        vueSwiper,
        vueSwiperSlide
      },
      data () {
        return {
          showIndex: 0
        }
      },
      methods: {
        slideChange (index, oldIndex) {
          console.log('showIndexChange:', index, oldIndex)
        }
      }
    }
</script>
<style>
  .swiper,.swiper-track {
    height:160px
  }

</style>

