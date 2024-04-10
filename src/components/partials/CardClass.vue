<script>
import Btn from "./Btn.vue";

export default {
  components: {
    Btn,
  },
  props: {
    itemElement: Object,
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/img_class/${img}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <div class="col">
    <div class="card_class d-flex justify-content-between mb_15 mt_15">
      <div class="left_side text-start">
        <h4>{{ itemElement.title }}</h4>
        <h6>Class name</h6>
        <div class="info_box w-100 d-flex justify-content-center text-center">
          <div class="info_box_item">
            <h6>{{ itemElement.years }}</h6>
            <h6>{{ itemElement.unit }} olds</h6>
          </div>
          <div class="info_box_item">
            <h6>{{ itemElement.size }}</h6>
            <h6>Class size</h6>
          </div>
        </div>
      </div>

      <div class="right_side position-relative">
        <img :src="getImagePath(itemElement.img)" :alt="itemElement.title" />
        <Btn
          class="position-absolute bottom-0 end-0"
          :textButton="'read more'"
          :colorButton="'primary'"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.card_class {
  background-color: $color-secondary;
  height: 190px;

  .left_side {
    padding: 20px;
    flex-grow: 1;

    h4 {
      color: $color-white;
      padding-bottom: 5px;
    }

    .info_box {
      margin-top: 60px;

      &_item {
        padding: 0 15px;

        &:first-child {
          border-right: 1px solid $color-tertiary;
        }

        h6:first-child {
          color: $color-white;
          padding-bottom: 5px;
        }
      }
    }
  }

  .right_side {
    width: 50%;

    img {
      height: 100%;
      width: 100%;
      object-fit: cover;
    }
  }
}
</style>
