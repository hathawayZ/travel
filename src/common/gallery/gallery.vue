<template>
    <div class="container" @click="handleGalleryClick">
      <div class="gallery-wrapper">
        <swiper :options="swiperOptions">
          <!-- slides -->
          <swiper-slide v-for="(item,key) in imgs" :key="key">
            <img class="img" :src="item">
          </swiper-slide>
          <!-- Optional controls -->
          <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
      </div>
    </div>
</template>

<script>
export default {
  name: 'commonGallery',
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  methods: {
    handleGalleryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
.container>>>.swiper-container
 overflow :inherit
/*.gallery-wrapper>>>.swiper-slide*/
 /*box-sizing :border-box*/
 /*width :100%*/
 /*padding-bottom :100%*/
 /*height :0*/
.container
  z-index :99
  display: flex
  flex-direction :column
  justify-content : center
  position :fixed
  left:0
  top:0
  bottom:0
  right :0
  background :#000
  .gallery-wrapper
   width :100%
   height :0
   padding-bottom :66.4%
   .img
    width :100%
    /*position :absolute*/
    /*top:0*/
    /*bottom :0*/
    /*left:0*/
    /*right :0*/
    /*margin :auto*/
   .swiper-pagination
    color :#ffffff
    bottom :-1rem
</style>
