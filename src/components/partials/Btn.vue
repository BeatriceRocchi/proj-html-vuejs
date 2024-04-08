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
  </button>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

button {
  &:hover {
    background-color: $color-white;
    color: $color-secondary;

    img {
      filter: brightness(0) saturate(100%) invert(31%) sepia(12%)
        saturate(2989%) hue-rotate(206deg) brightness(97%) contrast(87%);
    }
  }
}
img {
  height: 30px;
}
</style>
