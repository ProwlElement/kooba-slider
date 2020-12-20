<template>
  <div class="swiper-container" v-swiper:mySwiper="swiperOption">
    <div class="swiper-wrapper">
      <div
        class="swiper-slide"
        :key="image.id"
        v-for="image in images"
        @mouseover="onHoverSlide(image.file)"
      >
        <img class="swiper-slide-image" :src="image.file" />
        <div class="flex">
          <h2>{{ image.title }}</h2>
          <p>{{ image.text }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["images"],
  data() {
    return {
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 20,
        loop: true,
      },
    };
  },
  mounted() {
    // console.log("Current Swiper instance object", this.mySwiper);
    //loop over images
    let trigger = setInterval(this.nextSlide, 5000);
  },
  methods: {
    onHoverSlide(file) {
      this.$emit("slideHover", file);
    },
    nextSlide() {
      this.mySwiper.slideNext(1000, false);
    },
  },
};
</script>


<style scoped>
.swiper-container {
  width: 100%;
  height: auto;
}
.swiper-slide {
  color: #fff;
}

.swiper-slide-image {
  width: 100%;
}
</style>