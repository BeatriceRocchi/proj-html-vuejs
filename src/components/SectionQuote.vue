<script>
import RectangularMenu from "./partials/RectangularMenu.vue";

export default {
  components: {
    RectangularMenu,
  },
};
</script>

<template>
  <section id="section_quote">
    <div
      class="container container_custom h-100 d-flex flex-column justify-content-between align-items-center"
    >
      <div
        class="d-flex flex-column justify-content-between align-items-center"
      >
        <div class="quote_box d-flex align-items-center justify-content-center">
          <img src="../assets/img/quote_alt.png" alt="Quote icon" />
        </div>
        <h3>
          Fable Kindergarten is a great place for my daughter to start her
          schooling experience. It's welcoming and safe and my daughter loves
          being there.
        </h3>
        <div class="author">Joe R. Hamblen</div>
      </div>

      <div class="d-flex justify-content-center">
        <RectangularMenu :itemNum="6" :itemSelected="4" :itemColor="'white'" />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../assets/scss/partials/variables";

#section_quote {
  padding: 80px 0 0;
  height: 525px;
  background-image: url(../assets/img/parallax_02.jpg);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;

  .quote_box {
    border: 1px solid $color-white;
    height: 80px;
    width: 80px;
    border-radius: 50%;
  }

  h3 {
    color: $color-white;
    font-weight: 300;
    padding: 20px 0;
    margin-bottom: 0;

    &::after {
      content: "";
      display: block;
      width: 50px;
      background-color: $color-tertiary;
      height: 1px;
      margin-top: 20px;
      position: relative;
      left: 50%;
      transform: translateX(-50%);
    }
  }

  .author {
    font-size: 0.8rem;
    color: $color-white;
  }
}
</style>
