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
        <div id="slideLoad" class="load-bar"></div>
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
    let loader = 0;
    // trigger next slide
    let trigger = setInterval(this.nextSlide, 5000);
    // slide loader on slide change
    this.mySwiper.on("slideChange", function () {
      let load = setInterval(this.slideLoadBar, 10);
    });
  },
  methods: {
    onHoverSlide(file) {
      this.$emit("slideHover", file);
    },
    nextSlide() {
      this.mySwiper.slideNext(1000, false);
    },
    slideLoadBar() {
      document.querySelector(".load-bar").style.width = loader + "%";
      loader++;
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
  transition: all 0.2s linear;
}

.swiper-slide-image:hover {
  transform: scale(1.02);
}

.swiper-slide > .load-bar {
  position: relative;
  bottom: 8px;
  background-color: green;
  height: 4px;
  width: 10%;
}

@media only screen and (max-width: 600px) {
  .swiper-container {
    position: relative;
    /* left: -100px; */
    margin-top: 100px;
  }
}
</style>