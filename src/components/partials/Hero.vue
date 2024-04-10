<script>
import Btn from "./Btn.vue";
import RectangularMenu from "./RectangularMenu.vue";

export default {
  components: {
    RectangularMenu,
    Btn,
  },
};
</script>

<template>
  <div class="hero_box">
    <div
      class="container container_custom h-100 d-flex flex-column justify-content-between"
    >
      <!-- Hero text -->
      <div class="text_box">
        <h3 class="mb_20">Learning & Fun</h3>
        <h2 class="fw-bold">Learning Program</h2>
        <h2 class="mb_40">& After-School Care</h2>
        <Btn :textButton="'buy this theme now'" :colorButton="'primary'" />
      </div>
      <!-- /Hero text -->

      <!-- Hero nav -->
      <div class="d-flex justify-content-center">
        <RectangularMenu :itemNum="3" :itemSelected="3" />
      </div>
      <!-- /Hero nav -->
    </div>

    <!-- Hero image elements: in position absolute on hero background -->
    <img
      id="img_02"
      src="../../assets/img/slider1/slider_slide3_img2.png"
      alt="Img 2"
    />
    <img
      id="img_01"
      src="../../assets/img/slider1/slider_slide3_img1.png"
      alt="Img 1"
    />
    <img
      id="img_03"
      src="../../assets/img/slider1/slider_slide3_img3.png"
      alt="Img 3"
    />
    <!-- /Hero image elements -->
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.hero_box {
  height: 600px;
  width: 100%;
  background-image: url(../../assets/img/slider1/slider_slide3_background.png);
  background-position: center;
  position: relative;

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

    &#img_01 {
      left: 62%;
      top: 50%;
      transform: translate(-50%, -50%);
    }

    &#img_02 {
      left: 38%;
      top: 65%;
      z-index: 998;
    }

    &#img_03 {
      left: 70%;
      top: 70%;
      z-index: 998;
    }
  }
}
</style>
