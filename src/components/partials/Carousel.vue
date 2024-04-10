<script>
export default {
  data() {
    return {
      counter: 1,
      imgList: [
        {
          title: "Children drawing",
          url: "gallery_07.jpg",
        },
        {
          title: "Children colouring",
          url: "gallery_01.jpg",
        },
        {
          title: "Teacher and children",
          url: "gallery_08.jpg",
        },
      ],
    };
  },
  methods: {
    getImagePath(img) {
      return new URL(`../../assets/img/slider2/${img}`, import.meta.url).href;
    },

    goNext(direction) {
      direction ? this.counter++ : this.counter--;

      if (this.counter < 0) {
        this.counter = this.imgList.length - 1;
      } else if (this.counter === this.imgList.length) {
        this.counter = 0;
      }
    },
  },
};
</script>

<template>
  <div class="right_side">
    <!-- Carousel container -->
    <div class="carousel_wrapper w-100">
      <div class="carousel_item">
        <img
          :src="getImagePath(imgList[counter].url)"
          :alt="imgList[counter].title"
        />
      </div>

      <div class="arrow_container">
        <img
          @click="goNext(false)"
          src="../../assets/img/slider2/slider_previous.png"
          alt="Prev"
        />
        <img
          @click="goNext(true)"
          src="../../assets/img/slider2/slider_next.png"
          alt="Next"
        />
      </div>
    </div>
    <!-- /Carousel container -->

    <!-- Thumbnails container -->
    <div class="thumbnails_wrapper w-100 d-flex justify-content-between">
      <img
        v-for="(img, id) in imgList"
        :key="id"
        :src="getImagePath(img.url)"
        :alt="img.title"
        :class="counter === id ? 'active' : ''"
        @click="counter = id"
      />
    </div>
    <!-- /Thumbnails container -->
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.right_side {
  width: 50%;
  padding-left: 10px;

  .carousel_wrapper {
    position: relative;

    img {
      width: 100%;
      object-fit: cover;
    }

    .arrow_container {
      position: absolute;
      width: 100%;
      display: flex;
      justify-content: space-between;
      top: 50%;
      transform: translateY(-50%);

      img {
        height: 40px;
        width: 40px;
        background-color: $color-primary;
      }
    }
  }

  .thumbnails_wrapper {
    margin-top: 10px;
    height: 125px;

    img {
      width: calc(100% / 3.2);
      object-fit: cover;
      padding-bottom: 10px;
    }
  }

  .active {
    border-bottom: 2px solid $color-primary;
  }
}
</style>
