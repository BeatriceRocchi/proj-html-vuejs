<script>
import Btn from "./Btn.vue";
export default {
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
      <h3>How to Enroll Your Child to a Class?</h3>
      <Btn :textButton="'Learn More'" :colorButton="'secondary'" />
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
}
</style>
