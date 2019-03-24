<template>
  <div>
    <div class="search">
      <input
        type="text"
        placeholder="输入城市名/拼音"
        class="searchInput"
        v-model="keyword"
      />
    </div>
    <div class="item-list" ref="search" v-show="this.keyword">
      <ul>
        <li class="item-content border-bottom" v-for="item of list" :key="item.id">
          {{item.name}}
        </li>
        <li class="item-content border-bottom" v-show="hasNoWord">
          没有找到匹配数据
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      list: [],
      keyword: '',
      timer: null
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      setTimeout(() => {
        const result = []
        // console.log(this.cities)
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (
              value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1
            ) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  computed: {
    hasNoWord () {
      return !this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.search
  height :.72rem
  background:$bgColor
  padding :0 .1rem
  .searchInput
    box-sizing: border-box
    height :.62rem
    line-height :.62rem
    text-align :center
    width :100%
    border-radius :.06rem
    color :#666
    padding :0 .1rem
.item-list
  z-index :1
  overflow :hidden
  position :absolute
  top:1.58rem
  right :0
  left:0
  bottom:0
  background :#eee
  .item-content
   line-height :.62rem
   padding-left :.2rem
   color :#666
   background :#ffffff
</style>
