<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-buttom">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1905/44/44c6db1f35f281f6a3.water.jpg_200x200_c654b8a4.jpg',
        title: '横店影视城',
        desc: '扬名中外的“东方好莱坞”'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/50/5020c11e7dde947390.water.jpg_200x200_a7b59471.jpg',
        title: '清水湾沁温泉',
        desc: '清水湾沁温泉，以温泉为特色，以量大质优而著称'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1901/4b/4b36f3ba52bbddcba3.water.jpg_200x200_c2209195.jpg',
        title: '诸葛八卦村',
        desc: 'AAAA级国家旅游景区,是迄今发现的诸葛亮后裔的最大聚居地'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .title
    margin-top: .2rem
    line-height: .6rem
    background: #eee
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        ellipsis()
        line-height: .54rem
        font-size: .32rem
      .item-desc
        ellipsis()
        line-height: .4rem
        color: #ccc
      .item-buttom
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
