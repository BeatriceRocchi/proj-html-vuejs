<script>
export default {};
</script>

<template>
  <div class="right_side">
    <div class="carousel_container">
      <img src="../../assets/img/gallery_01.jpg" alt="Image 1" />
      <div class="arrow_container">
        <img src="../../assets/img/slider_previous.png" alt="Prev" />
        <img src="../../assets/img/slider_next.png" alt="Next" />
      </div>
    </div>
    <div class="thumbnails_container d-flex justify-content-between">
      <img src="../../assets/img/gallery_07.jpg" alt="Image 1" />
      <img src="../../assets/img/gallery_01.jpg" alt="Image 1" />
      <img src="../../assets/img/gallery_08.jpg" alt="Image 1" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.right_side {
  width: 50%;
  padding-left: 10px;

  .carousel_container {
    height: 370px;
    position: relative;

    img {
      width: 100%;
      height: 100%;
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

  .thumbnails_container {
    margin-top: 10px;
    height: 125px;
  }
}
</style>
