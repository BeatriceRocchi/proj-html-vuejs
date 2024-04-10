<script>
export default {
  props: {
    newsElement: Object,
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/img_news/${img}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <div class="d-flex align-items-center">
    <div class="img_box">
      <img :src="getImagePath(newsElement.img)" :alt="newsElement.title" />
    </div>
    <div class="ms-3">
      <h6>{{ newsElement.title }}</h6>
      <div class="d-flex text_box">
        <img src="../../assets/img/date_footer.png" alt="Calendar icon" />
        <div class="date_box">{{ newsElement.date }}</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.img_box {
  height: 80px;
  aspect-ratio: 1;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

h6 {
  color: $color-white;
}

.text_box {
  margin-top: 5px;

  img {
    height: 16px;
    width: auto;
  }

  .date_box {
    font-size: 0.8rem;
    padding-left: 8px;
    color: rgba($color-white, 50%);
  }
}
</style>
