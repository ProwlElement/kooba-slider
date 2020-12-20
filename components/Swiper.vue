<template>
  <div v-swiper:mySwiper="swiperOption">
    <div class="swiper-wrapper">
      <div class="swiper-slide" :key="image" v-for="image in images">
        <img :src="image" />
      </div>
    </div>
    <!-- If we need navigation buttons -->
    <div class="swiper-nav relative mb-20 mt-8">
      <div
        @click="mySwiper.slidePrev()"
        class="swiper-button-prev bg-purple rounded-full p-6"
      ></div>
      <div
        @click="mySwiper.slideNext()"
        class="swiper-button-next bg-purple rounded-full p-6"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [ require('~/assets/slider/slide-1.png'), require('~/assets/slider/slide-2.png'), require('~/assets/slider/slide-3.png') ],
      swiperOption: {
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },
        // ...
      },
    };
  },
  mounted() {
    console.log("Current Swiper instance object", this.mySwiper);
    this.mySwiper.slideTo(0, 1000, false);
  },
};
</script>


<style scoped>
.swiper-nav {
  width: 150px;
}
.swiper-nav > div::after {
  transform: scale(0.5);
}
</style>