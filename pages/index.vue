<template>
  <main class="main">
    <div class="container">
      <Header />
      <div class="inner-container">
        <HomeText />
        <Swiper :images="images" @slideHover="slideTarget" />
      </div>
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
          title: "First Title",
          text: "Lorum ipsum",
        },
        {
          id: 2,
          file: require("~/assets/slider/slide-2.png"),
          title: "Second Title",
          text: "Lorum ipsum",
        },
        {
          id: 3,
          file: require("~/assets/slider/slide-3.png"),
          title: "Third Title",
          text: "Lorum ipsum",
        },
        {
          id: 4,
          file: require("~/assets/slider/slide-2.png"),
          title: "Fourth Title",
          text: "Lorum ipsum",
        },
        {
          id: 5,
          file: require("~/assets/slider/slide-3.png"),
          title: "Fifth Title",
          text: "Lorum ipsum",
        },
        {
          id: 6,
          file: require("~/assets/slider/slide-3.png"),
          title: "Sixth Title",
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
    slideTarget(file) {
      console.log(file);
      document.querySelector(".main").style.backgroundImage =
        "url(" + file + ")";
    },
  },
};
</script>

<style scoped>
.main {
  margin: 0 auto;
  height: 100vh;
  background: url("~assets/Background.jpg") no-repeat center center;
  background-size: cover;
  transition: all 1s linear;
}

.container {
  margin: 0 auto;
  max-width: 80%;
  display: flex;
}

.inner-container {
  position: relative;
  margin: 0 auto;
  height: 100vh;
  width: 600px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  /* background-color: pink; */
}

@media only screen and (max-width: 600px) {
  .container {
    flex-flow: column nowrap;
  }

  .inner-container {
    max-width: 100%;
  }
}
</style>
