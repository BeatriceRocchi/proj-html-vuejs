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
      return new URL(`../../assets/img/icons/${img}`, import.meta.url).href;
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
      :class="item.id === 101 ? 'active' : ''"
    >
      <!-- Class 'active' on list item is used to view the over effect -->

      <div class="img_box mb_20">
        <img :src="getImagePath(item.icon)" :alt="item.title" />
      </div>
      <a href="#">{{ item.title }}</a>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

li {
  width: 100px;
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
}

// Class 'active' on list item is used to view the over effect
.active {
  cursor: pointer;
  background-color: $color-primary;
  color: $color-white;

  img {
    filter: brightness(0) saturate(100%) invert(100%) sepia(95%) saturate(22%)
      hue-rotate(33deg) brightness(105%) contrast(108%);
  }
}
</style>
