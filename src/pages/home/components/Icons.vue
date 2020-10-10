<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img">
                        <img class="icon-img-content" :src="item.imgUrl">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '0001',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/69e8b07cb2d438c5530aebd4c8e3abd3.png',
        desc: '一日游'
      }, {
        id: '0002',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/5ffcd4a916f764f678263b27c1e2e00c.png',
        desc: '动植物园'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
        desc: '横店梦外滩'
      }, {
        id: '0004',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/d266ef09a4f19a45a566b1108392255e.png',
        desc: '横店梦溪谷'
      }, {
        id: '0005',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/e261a830727b7ffde3ce391190644204.png',
        desc: '横店影视城'
      }, {
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
        desc: '梦泉谷'
      }, {
        id: '0007',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/50e2841850ed7891d9bcb676f5ee9c54.png',
        desc: '亲子游'
      }, {
        id: '0008',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/b7a5e6b1774eda4fc9e32588f1d00c94.png',
        desc: '踏青赏花'
      }, {
        id: '0009',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png',
        desc: '景点门票'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.icons >>> .swiper-container
 height: 0
 padding-bottom: 50%
.icons
 margin-top: .1rem
 .icon
  position: relative
  overflow: hidden
  float: left
  width: 25%
  height: 0
  padding-bottom: 25%
  .icon-img
   position: absolute
   top: 0
   left: 0
   right: 0
   bottom: .44rem
   box-sizing: border-box
   padding: .1rem
   .icon-img-content
    display: block
    margin: 0 auto
    height: 100%
  .icon-desc
    position: absolute
    left: 0
    right: 0
    bottom: 0
    height: .44rem
    line-height: .44rem
    text-align: center
    color: $darkTextColor
    ellipsis()
</style>
