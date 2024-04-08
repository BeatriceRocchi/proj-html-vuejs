<script>
export default {
  props: {
    itemNum: Number,
    itemSelected: Number,
  },
};
</script>

<template>
  <div
    v-for="n in itemNum"
    :key="n"
    class="rectangle_box"
    :class="n === itemSelected ? 'rectangle_selected' : ''"
  ></div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.rectangle_box {
  height: 12px;
  width: 40px;
  border: 2px solid $color-primary;
  margin: 0 10px 30px 0;
}

.rectangle_selected {
  position: relative;
  bottom: 12px;
}
</style>
