<template>
    <div class="search">
      <input type="text" placeholder="输入城市名/拼音" class="searchInput">
    </div>
</template>

<script>
export default {
  name: 'CitySearch'
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
</style>
