<script>
import Btn from "./Btn.vue";
import RectangularMenu from "./RectangularMenu.vue";

export default {
  components: {
    RectangularMenu,
    Btn,
  },
  data() {
    return {
      counter: 0,
      imgList: [
        {
          id: 0,
          bgImg: "slider_slide1_background.png",
          img1: "slider_slide1_img1.png",
          img2: "slider_slide1_img2.png",
          title: "Welcome to Fable",
          subtitle1: "Perfect Education",
          subtitle2: "For Your Child",
        },
        {
          id: 1,
          bgImg: "slider_slide2_background.png",
          img1: "slider_slide2_img1.png",
          img2: "slider_slide2_img2.png",
          title: "Friendly Atmosphere",
          subtitle1: "Welcoming Place",
          subtitle2: "For Every Child",
        },
        {
          id: 2,
          bgImg: "slider_slide3_background.png",
          img1: "slider_slide3_img1.png",
          img2: "slider_slide3_img2.png",
          img3: "slider_slide3_img3.png",
          title: "Learning & Fun",
          subtitle1: "Learning Program",
          subtitle2: "& After-School Care",
        },
      ],
    };
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/slider1/${img}`, import.meta.url).href;
    },

    goNext(direction) {
      direction ? this.counter++ : this.counter--;

      if (this.counter < 0) {
        this.counter = this.imgList.length - 1;
      } else if (this.counter === this.imgList.length) {
        this.counter = 0;
      }
    },
  },
};
</script>

<template>
  <div
    class="hero_box w-100"
    :style="{
      'background-image': 'url(' + getImagePath(imgList[counter].bgImg) + ')',
    }"
  >
    <!-- Arrow-container -->
    <div class="arrow_container">
      <img
        id="prev_arrow"
        @click="goNext(false)"
        src="../../assets/img/slider_previous.png"
        alt="Prev"
      />
      <img
        id="next_arrow"
        @click="goNext(true)"
        src="../../assets/img/slider_next.png"
        alt="Next"
      />
    </div>
    <!-- /Arrow-container -->

    <div
      class="container container_custom h-100 d-flex flex-column justify-content-between"
    >
      <!-- Hero text -->
      <div class="text_box" :class="counter === 0 ? 'text-center' : ''">
        <h3 class="mb_20">{{ imgList[counter].title }}</h3>
        <h2 class="fw-bold">{{ imgList[counter].subtitle1 }}</h2>
        <h2 class="mb_40">{{ imgList[counter].subtitle2 }}</h2>
        <Btn
          :class="counter === 0 ? 'mx-auto' : ''"
          :textButton="'buy this theme now'"
          :colorButton="'primary'"
        />
      </div>
      <!-- /Hero text -->

      <!-- Slider nav -->
      <div class="d-flex justify-content-center">
        <RectangularMenu :itemNum="3" :itemSelected="counter + 1" />
      </div>
      <!-- /Slider nav -->
    </div>

    <!-- Hero images elements: in position absolute on hero background -->

    <!-- Images for the element with id=1 of imgList -->
    <div v-if="counter === 0">
      <img
        id="id0_img1"
        src="../../assets/img/slider1/slider_slide1_img1.png"
        alt="Img 1"
      />
      <img
        id="id0_img2"
        src="../../assets/img/slider1/slider_slide1_img2.png"
        alt="Img 2"
      />
    </div>
    <!-- /Images -->

    <!-- Images for the element with id=1 of imgList -->
    <div v-if="counter === 1">
      <img
        id="id1_img1"
        src="../../assets/img/slider1/slider_slide2_img1.png"
        alt="Img 1"
      />
      <img
        id="id1_img2"
        src="../../assets/img/slider1/slider_slide2_img2.png"
        alt="Img 2"
      />
    </div>
    <!-- /Images -->

    <!-- Images for the element with id=2 of imgList -->
    <div v-if="counter === 2">
      <img
        id="id2_img2"
        src="../../assets/img/slider1/slider_slide3_img2.png"
        alt="Img 2"
      />
      <img
        id="id2_img1"
        src="../../assets/img/slider1/slider_slide3_img1.png"
        alt="Img 1"
      />
      <img
        id="id2_img3"
        src="../../assets/img/slider1/slider_slide3_img3.png"
        alt="Img 3"
      />
    </div>
    <!-- /Images -->

    <!-- /Hero image elements -->
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.hero_box {
  height: 600px;
  width: 100%;
  background-position: center;
  position: relative;

  .arrow_container {
    position: absolute;
    width: 100%;
    display: flex;
    top: 50%;
    transform: translateY(-50%);

    #prev_arrow,
    #next_arrow {
      margin: 0 20px;
      height: 40px;
      width: 40px;
      border-radius: 50%;
      background-color: $color-tertiary;

      &:hover {
        background-color: darken($color-tertiary, 20%);
        cursor: pointer;
      }
    }

    #next_arrow {
      right: 0;
    }
  }

  .text_box {
    padding-top: 160px;
    z-index: 999;
  }

  h3 {
    font-family: "Handlee", cursive;
    color: $color-primary;
    font-size: 2.5rem;
  }

  img {
    position: absolute;

    &#id0_img1 {
      left: 25%;
      top: 50%;
      transform: translate(-50%, -50%);
    }

    &#id0_img2 {
      left: 70%;
      top: 50%;
      transform: translate(-50%, -50%);
    }

    &#id2_img1 {
      left: 62%;
      top: 50%;
      transform: translate(-50%, -50%);
    }

    &#id2_img2 {
      left: 38%;
      top: 65%;
      z-index: 998;
    }

    &#id2_img3 {
      left: 70%;
      top: 70%;
      z-index: 998;
    }

    &#id1_img1 {
      left: 55%;
      top: 50%;
      z-index: 999;
      transform: translate(-50%, -50%);
    }

    &#id1_img2 {
      left: 60%;
      top: 5%;
      z-index: 998;
    }
  }
}
</style>
