<template>
    <div>
      <ul class="list">
        <li class="content"  v-for="(item,key) of city" :key="key">{{key}}</li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    city: Object
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.list
  position :absolute
  top:1.56rem
  right:0
  bottom :0
  width :.4rem
  display :flex
  flex-direction :column
  justify-content: center
  .content
    color :$bgColor
    text-align :center
    line-height :.4rem
</style>
