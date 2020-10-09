<template>
  <div class="wrapper">
    <swiper :options="swiperOptions">
    <swiper-slide class="problem_part" v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOptions: {
        pagination: {
          el: '.swiper-pagination'
        },
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: '//imgs.qunarzz.com/vs_ceph_vcimg/b8c4527c41649814cc4cf86880abba54.jpeg'
      }, {
        id: '0002',
        imgUrl: '//imgs.qunarzz.com/vs_ceph_vcimg/7176acd77332a433af9636eb9a2c338c.jpeg'
      }]
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
