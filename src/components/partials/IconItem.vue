<script>
export default {
  props: {
    itemElement: Object,
    itemType: String,
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/icons/${img}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <div class="d-flex flex-column align-items-center text-center">
    <!-- Upper part: icons -->
    <div
      class="img_box d-flex align-items-center justify-content-center"
      :class="[
        itemElement.id % 2 === 0 ? 'bg_secondary' : 'bg_primary',
        itemType === 'border' ? 'white_box' : '',
      ]"
    >
      <img
        v-if="itemElement.img"
        :src="getImagePath(itemElement.img)"
        :alt="itemElement.title"
      />
      <div class="number_box" v-else>{{ itemElement.num }}</div>
    </div>
    <!-- /Upper part: icons -->

    <!-- Lower part: title and description -->
    <h4 class="mt_20 mb_20" :class="itemType === 'border' ? 'white_text' : ''">
      {{ itemElement.title }}
    </h4>
    <p :class="itemType === 'border' ? 'white_text' : ''">
      {{ itemElement.description }}
    </p>
    <!-- /Lower part: title and description -->
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.img_box {
  height: 180px;
  width: 180px;
  border-radius: 50%;
  color: $color-white;

  img {
    width: 63px;
  }
}

.number_box {
  font-size: 3rem;
  font-weight: 300;
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

.white_text {
  color: $color-white;
}

.white_box {
  background-color: transparent;
  border: 2px solid $color-white;
}
</style>
