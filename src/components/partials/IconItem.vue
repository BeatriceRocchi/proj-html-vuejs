<script>
export default {
  props: {
    itemElement: Object,
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/${img}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <div class="d-flex flex-column align-items-center">
    <div
      class="img_box d-flex align-items-center justify-content-center"
      :class="itemElement.id % 2 === 0 ? 'bg_secondary' : 'bg_primary'"
    >
      <img :src="getImagePath(itemElement.img)" :alt="itemElement.title" />
    </div>
    <h4>{{ itemElement.title }}</h4>
    <p>{{ itemElement.description }}</p>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.img_box {
  height: 180px;
  width: 180px;
  border-radius: 50%;

  img {
    width: 63px;
  }
}

p {
  padding: 0 10px;
}

.bg_primary {
  background-color: $color-primary;
}

.bg_secondary {
  background-color: $color-secondary;
}
</style>
