<template>
    <div>
      <ul class="list">
        <li class="content"
            v-for="item of letters" :key="item"
            @click="handleClick"
            @touchstart.prevent="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
            :ref="item"
        >{{item}}</li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    city: Object
  },
  data () {
    return {
      touching: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.city) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleClick (e) {
      this.$emit('change', e.target.innerText)
      // console.log(e.target.innerText)
    },
    handleTouchStart () {
      this.touching = true
    },
    handleTouchMove (e) {
      if (this.touching) {
        if (this.timer) { clearTimeout(this.timer) }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          console.log(touchY)
          const index = Math.floor((touchY - this.startY) / 20)
          if (index >= 0 && index < this.letters.length) { this.$emit('change', this.letters[index]) }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touching = false
    }
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
