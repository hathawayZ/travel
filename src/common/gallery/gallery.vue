<template>
    <div class="container">
      <div class="wrapper">
        <swiper >
          <!-- slides -->
          <swiper-slide >
            <img class="img" src="http://img1.qunarzz.com/sight/p0/1603/17/170481fb9caf500790.water.jpg_r_800x800_15271965.jpg">
          </swiper-slide>
          <swiper-slide >
            <img class="img" src="http://img1.qunarzz.com/sight/p0/201405/15/4b16c55b620218c786d0ed33e92b8b80.jpg_r_800x800_dbb543d6.jpg">
          </swiper-slide>
          <!-- Optional controls -->
          <!--<div class="swiper-pagination"  slot="pagination"></div>-->
        </swiper>
      </div>
    </div>
</template>

<script>
export default {
  name: 'commonGallery'
}
</script>

<style lang="stylus" scoped>
.wrapper>>>.swiper-slide
 box-sizing :border-box
 width :100%
 padding-bottom :100%
 height :0
.container
  z-index :99
  position :fixed
  left:0
  top:0
  bottom:0
  right :0
  display: flex
  flex-direction :column
  justify-content : center
  background :#000
  .wrapper
   width :100%
   height :0
   padding-bottom :100%
   overflow :hidden
   .img
    width :100%
    position :absolute
    top:0
    bottom :0
    left:0
    right :0
    margin :auto
</style>
