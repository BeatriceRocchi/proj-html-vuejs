<script>
import navItems from "../../assets/data/db_navbar";
export default {
  data() {
    return {
      navItems,
      isHover: false,
    };
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/${img}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <ul class="d-flex align-items-center">
    <!-- TODO: fix icons on hover effects -->
    <li
      class="d-flex flex-column align-items-center justify-content-center"
      v-for="item in navItems"
      :key="item.id"
      @mouseenter="isHover = true"
      @mouseleave="isHover = false"
    >
      <div class="img_box">
        <img v-if="!isHover" :src="getImagePath(item.icon)" :alt="item.title" />
        <img v-else :src="getImagePath(item.icon2)" :alt="item.title" />
      </div>
      <a href="#">{{ item.title }}</a>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

li {
  padding: 0 28px;
  width: 98px;
  height: 100%;
  color: $color-secondary;

  &:hover {
    cursor: pointer;
    background-color: $color-primary;
    color: $color-white;
  }

  .img_box {
    height: 32px;
    margin-bottom: 15px;
  }
}
</style>
