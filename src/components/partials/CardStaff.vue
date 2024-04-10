<script>
export default {
  props: {
    staffElement: Object,
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/${img}`, import.meta.url).href;
    },
    getImagePath2(img) {
      return new URL(`../../assets/img/${img}.png`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <div class="col p-0 mb-4 d-flex">
    <!-- Left side -->
    <div class="left_side h-100">
      <div class="img_box">
        <img :src="getImagePath(staffElement.img)" :alt="staffElement.staff" />
        <img
          class="hover_img"
          src="../../assets/img/image_overlay.png"
          alt="Plus icon"
        />
      </div>

      <div class="staff mt_20">{{ staffElement.staff }}</div>
      <div class="role">{{ staffElement.role }}</div>
    </div>
    <!-- /Left side -->

    <!-- Right side -->
    <div class="right_side d-flex flex-column">
      <div>
        <img
          class="quote_icon"
          src="../../assets/img/quote.png"
          alt="Quote icon"
        />
      </div>

      <p class="text-start">{{ staffElement.description }}</p>
      <div class="d-flex align-items-end">
        <div
          class="square_box align-self-end d-flex align-items-center justify-content-center"
          v-for="(contact, id) in staffElement.contacts"
          :key="id"
        >
          <img :src="getImagePath2(contact)" :alt="contact" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.left_side,
.right_side {
  width: 50%;
  padding: 0 10px;
}

.left_side {
  .img_box {
    width: 245px;
    height: 245px;
    position: relative;

    &:hover .hover_img {
      display: block;
    }

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .hover_img {
      display: none;
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      background-color: rgba($color-secondary, 50%);
      padding: 25px;
      height: 80px;
      width: 80px;
      border-radius: 50%;
    }
  }

  .staff {
    color: $color-secondary;
  }

  .role {
    color: darken($color-tertiary, 20%);
    font-size: 0.9rem;
  }
}

.right_side {
  padding-left: 20px;

  .quote_icon {
    border: 2px solid $color-primary;
    padding: 10px 10px 10px 60px;
    position: relative;
    top: 20px;
    left: -120px;
  }

  p {
    padding-top: 50px;
  }

  .square_box {
    background-color: $color-primary;
    width: 40px;
    aspect-ratio: 1;
    margin: 2px;
    margin-top: 10px;
  }
}
</style>
