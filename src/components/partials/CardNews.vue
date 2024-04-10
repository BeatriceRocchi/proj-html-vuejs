<script>
export default {
  props: {
    newsElement: Object,
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/${img}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <div class="col card_news text-start">
    <p>{{ newsElement.date }}</p>
    <div class="img_box">
      <img :src="getImagePath(newsElement.img)" :alt="newsElement.title" />
      <div class="id text-center">{{ newsElement.id }}</div>
    </div>
    <h4 class="p-0">{{ newsElement.title }}</h4>
    <p class="text_box">
      {{ newsElement.description }} <span class="light_text">[...]</span>
    </p>
    <div class="d-flex lower_card">
      <div class="d-flex align-items-center">
        <img src="../../assets/img/author.png" alt="Author icon" />
        <p>{{ newsElement.author }}</p>
      </div>
      <div class="d-flex align-items-center">
        <img src="../../assets/img/category.png" alt="Category icon" />
        <p>{{ newsElement.types.join(", ") }}</p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.img_box {
  height: 200px;
  position: relative;
  margin: 20px 0;

  img {
    height: 100%;
    width: 100%;
    object-fit: cover;
  }

  .id {
    position: absolute;
    width: 40px;
    line-height: 40px;
    aspect-ratio: 1;
    right: 0;
    bottom: 0;
    color: $color-white;
    background-color: $color-primary;
  }
}

.text_box {
  border-bottom: 1px solid $color-tertiary;
  padding: 20px 0;
}

.lower_card {
  padding: 10px 0;

  img {
    height: 15px;
    margin-right: 5px;
  }

  p {
    margin-right: 20px;
  }
}

.light_text {
  color: lighten($color-tertiary, 0.2%);
}
</style>
