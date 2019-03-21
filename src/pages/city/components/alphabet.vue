<template>
    <div>
      <ul class="list">
        <li class="content">A</li>
        <li class="content">A</li>
        <li class="content">A</li>
        <li class="content">A</li>
        <li class="content">A</li>
        <li class="content">A</li>
        <li class="content">A</li>
        <li class="content">A</li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'CityAlphabet'
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
