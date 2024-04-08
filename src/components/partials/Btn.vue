<script>
export default {
  props: {
    textButton: String,
  },
};
</script>

<template>
  <button class="btn_custom d-flex align-items-center justify-content-center">
    <span>{{ textButton }}</span>
    <img src="../../assets/img/slider_next.png" alt=" arrow" />
    <!-- TODO: change color to arrow img -->
  </button>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

button {
  &:hover {
    background-color: $color-white;
    color: $color-secondary;
  }
}
img {
  height: 30px;
}
</style>
