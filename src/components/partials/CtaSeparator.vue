<script>
import Btn from "./Btn.vue";
export default {
  props: {
    CtaTitle: String,
    CtaButtonText: String,
  },
  components: {
    Btn,
  },
};
</script>

<template>
  <div class="separator">
    <div
      class="container container_custom d-flex justify-content-between align-items-center h-100"
    >
      <h3>{{ CtaTitle }}</h3>
      <Btn :textButton="CtaButtonText" :colorButton="'secondary'" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.separator {
  color: $color-white;
  height: 135px;
  background-image: url(../../assets/img/pattern.png);
  background-repeat: no-repeat;
  background-size: cover;

  h3 {
    color: $color-white;
    font-weight: 300;
    font-size: 2.5rem;
    margin: 0;
  }
}
</style>
