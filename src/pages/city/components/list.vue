<template>
  <div>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper"  v-for="item of cityList" :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
        </div>

      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
          <div class="itemList">
            <div class="item border-bottom">
              阿尔及利亚
            </div>
            <div class="item border-bottom">
              阿尔及利亚
            </div>
            <div class="item border-bottom">
              阿尔及利亚
            </div>
          </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="itemList">
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="itemList">
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="itemList">
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="itemList">
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="itemList">
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
          <div class="item border-bottom">
            阿尔及利亚
          </div>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  data () {
    return {
      cityList: [
        {
          id: '001',
          name: '北京'
        },
        {
          id: '002',
          name: '北京'
        },
        {
          id: '003',
          name: '北京'
        },
        {
          id: '004',
          name: '北京'
        },
        {
          id: '005',
          name: '北京'
        },
        {
          id: '006',
          name: '北京'
        }
      ]
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
.list
  position :absolute
  top:1.56rem
  left:0
  right :0
  bottom:0
  overflow :hidden
  .border-topbottom
   &:before
    border-color :#ccc
   &:after
    border-color :#ccc
  .border-bottom
    &:before
      border-color :#ccc
  .title
    background :#eee
    height :.54rem
    line-height :.54rem
    padding-left :.2rem
    color :#666
    font-size :.26rem
  .button-list
    padding:.1rem .6rem .1rem .1rem
    display :flow-root
    .button-wrapper
     float:left
     width:33.33%
     .button
      text-align :center
      margin :.1rem
      padding :.1rem 0
      border:solid .02rem #ccc
      border-radius :.06rem
  .item
    height :.76rem
    line-height :.76rem
    padding-left :.2rem
</style>
