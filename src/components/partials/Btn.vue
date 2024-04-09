<script>
export default {
  props: {
    textButton: String,
    colorButton: String,
  },
};
</script>

<template>
  <button
    class="btn_custom d-flex align-items-center justify-content-center"
    :class="colorButton === 'primary' ? 'primary' : 'secondary'"
  >
    <span>{{ textButton }}</span>
    <img src="../../assets/img/slider_next.png" alt=" arrow" />
  </button>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

img {
  height: 30px;
}
</style>
