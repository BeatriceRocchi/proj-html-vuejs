<script>
export default {
  props: {
    contactElement: Object,
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/icons/${img}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <div class="col">
    <img :src="getImagePath(contactElement.icon)" :alt="contactElement.title" />
    <h4 class="mt_20 mb_20">{{ contactElement.title }}</h4>
    <p>{{ contactElement.row1 }}</p>
    <p>{{ contactElement.row2 }}</p>
    <p :class="contactElement.tag ? 'email' : ''">{{ contactElement.row3 }}</p>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.email {
  color: $color-secondary;
  text-decoration: underline;
  cursor: pointer;
}
</style>
