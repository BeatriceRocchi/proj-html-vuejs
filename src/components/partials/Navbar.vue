<script>
import navItems from "../../assets/data/db_navbar";
export default {
  data() {
    return {
      navItems,
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
    <li
      class="d-flex flex-column align-items-center justify-content-center"
      v-for="item in navItems"
      :key="item.id"
    >
      <div class="img_box">
        <img :src="getImagePath(item.icon)" :alt="item.title" />
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

    img {
      filter: brightness(0) saturate(100%) invert(100%) sepia(95%) saturate(22%)
        hue-rotate(33deg) brightness(105%) contrast(108%);
    }
  }

  .img_box {
    height: 32px;
    margin-bottom: 15px;
  }
}
</style>
