<template>
  <main class="main">
    <Header />
    <div class="container">
      <HomeText />
      <Swiper :images="images" @slideHover="slideTarget" />
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      images: [
        {
          id: 1,
          file: require("~/assets/slider/slide-1.png"),
          title: "Title",
          text: "Lorum ipsum",
        },
        {
          id: 2,
          file: require("~/assets/slider/slide-2.png"),
          title: "Title",
          text: "Lorum ipsum",
        },
        {
          id: 3,
          file: require("~/assets/slider/slide-3.png"),
          title: "Title",
          text: "Lorum ipsum",
        },
        {
          id: 4,
          file: require("~/assets/slider/slide-2.png"),
          title: "Title",
          text: "Lorum ipsum",
        },
        {
          id: 5,
          file: require("~/assets/slider/slide-3.png"),
          title: "Title",
          text: "Lorum ipsum",
        },
      ],
    };
  },
  mounted() {
    console.log("");
    // bind bg image and emmit hover event upward from
  },
  methods: {
    slideTarget(value) {
      console.log(value); // someValue
    },
  },
};
</script>

<style scoped>
.main {
  margin: 0 auto;
  height: 100vh;
  background: url("~assets/Background.jpg");
  display: flex;
}

.container {
  margin: 0 auto;
  height: 100vh;
  max-width: 800px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  /* background-color: pink; */
}
</style>
