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
  <div class="col mb-4 d-flex">
    <!-- Left side -->
    <div class="left_side">
      <img :src="getImagePath(staffElement.img)" :alt="staffElement.staff" />
      <div class="staff">{{ staffElement.staff }}</div>
      <div class="role">{{ staffElement.role }}</div>
    </div>

    <!-- Right side -->
    <div class="right_side">
      <div class="quote_box">
        <img
          class="quote_icon"
          src="../../assets/img/quote.png"
          alt="Quote icon"
        />
      </div>
      <p class="text-start">{{ staffElement.description }}</p>
      <div class="d-flex">
        <div
          class="square_box d-flex align-items-center justify-content-center"
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
}

.left_side {
  img {
    width: 100%;
    aspect-ratio: 1;
    object-fit: cover;
  }

  .staff {
    color: $color-secondary;
    margin-top: 10px;
  }

  .role {
    color: darken($color-tertiary, 40%);
    font-size: 0.8rem;
  }
}

.right_side {
  padding-left: 30px;

  .quote_icon {
    border: 2px solid $color-primary;
    padding: 10px 10px 10px 60px;
    position: relative;
    top: 30px;
    left: -120px;
  }

  p {
    padding-top: 50px;
    font-size: 0.9rem;
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
