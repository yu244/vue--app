<template>
  <div class="wrapper">
    <swiper :options="swiperOptions" v-if="showSwiper">
    <swiper-slide class="problem_part" v-for="item of list" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOptions: {
        autoplay: {
          delay: 2000
        },
        loop: true,
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
 background-color: #fff
.wrapper
 overflow: hidden
 width: 100%
 height: 0
 padding-bottom: 30.46%
 background-color: #fff
 .problem_part
  touch-action: none
  .swiper-img
   width: 100%
</style>
