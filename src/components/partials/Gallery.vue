<script>
export default {};
</script>

<template>
  <div class="gallery_wrapper d-flex">
    <div class="img_box">
      <img
        src="../../assets/img/img_gallery/gallery_01.jpg"
        alt="Child drawing"
      />
      <img
        class="hover_img"
        src="../../assets/img/image_overlay.png"
        alt="Plus icon"
      />
    </div>

    <div class="img_box">
      <img
        src="../../assets/img/img_gallery/gallery_02.jpg"
        alt="Child painting"
      />
      <img
        class="hover_img"
        src="../../assets/img/image_overlay.png"
        alt="Plus icon"
      />
    </div>

    <div class="img_box">
      <img
        src="../../assets/img/img_gallery/gallery_03.jpg"
        alt="Child colouring"
      />
      <img
        class="hover_img"
        src="../../assets/img/image_overlay.png"
        alt="Plus icon"
      />
    </div>

    <div class="img_box">
      <img
        src="../../assets/img/img_gallery/gallery_04.jpg"
        alt="Child in a park"
      />
      <img
        class="hover_img"
        src="../../assets/img/image_overlay.png"
        alt="Plus icon"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../../assets/scss/partials/variables";

.gallery_wrapper {
  height: 350px;

  .img_box {
    width: 25%;
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
}
</style>
