<script>
import RectangularMenu from "./RectangularMenu.vue";
export default {
  components: {
    RectangularMenu,
  },
};
</script>

<template>
  <div class="hero_box">
    <div
      class="container container_custom h-100 d-flex flex-column justify-content-between"
    >
      <h3>Learning & Fun</h3>
      <div class="d-flex justify-content-center">
        <RectangularMenu :itemNum="3" :itemSelected="3" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.hero_box {
  height: 600px;
  background-image: url(../../assets/img/hero.jpg);
  // TODO: cercare e cambiare hero img in assets forniti
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;

  h3 {
    font-family: "Handlee", cursive;
    font-weight: normal;
    color: $color-tertiary;
    padding-top: 160px;
  }
}
</style>
