<script>
import Carousel from "./partials/Carousel.vue";
export default {
  components: {
    Carousel,
  },
};
</script>

<template>
  <section class="section_custom">
    <div class="container container_custom d-flex justify-content-between">
      <!-- Left side -->
      <div class="left_side">
        <!-- Nav items headers -->
        <ul
          class="nav nav-pills nav-pills_custom"
          id="pills-tab"
          role="tablist"
        >
          <li class="nav-item" role="presentation">
            <button
              class="nav-link active mb_40"
              id="pills-overview-tab"
              data-bs-toggle="pill"
              data-bs-target="#pills-overview"
              type="button"
              role="tab"
              aria-controls="pills-overview"
              aria-selected="true"
            >
              Overview
            </button>
          </li>
          <li class="nav-item" role="presentation">
            <button
              class="nav-link"
              id="pills-mission-tab"
              data-bs-toggle="pill"
              data-bs-target="#pills-mission"
              type="button"
              role="tab"
              aria-controls="pills-mission"
              aria-selected="false"
            >
              Our Mission
            </button>
          </li>
        </ul>
        <!-- /Nav items headers -->

        <!-- Nav items contents: title on top and list items with icon and description on bottom -->
        <div class="tab-content" id="pills-tabContent">
          <!-- First content: overview -->
          <div
            class="tab-pane fade show active"
            id="pills-overview"
            role="tabpanel"
            aria-labelledby="pills-overview-tab"
            tabindex="0"
          >
            <h3 class="mb_40">
              Our philosophy is learning through play as we offer a stimulating
              environment for children.
            </h3>

            <ul>
              <li class="d-flex align-items-center mb_30">
                <div class="img_box">
                  <img
                    src="../assets/img/icons/clock_alt.png"
                    alt="Clock icon"
                  />
                </div>

                <div>
                  <h4 class="mb_20">Full Day Sessions</h4>
                  <p>
                    Pulvinar est metro ligula blandit maeceas retrum gravida
                    cuprum. Maecenas node estibulum.
                  </p>
                </div>
              </li>

              <li class="d-flex align-items-center">
                <div
                  class="img_box d-flex justify-content-center align-items-center"
                >
                  <img
                    src="../assets/img/icons/diagram_alt.png"
                    alt="Diagram icon"
                  />
                </div>
                <div>
                  <h4 class="mb_20">Varied Classes</h4>
                  <p>
                    Pulvinar est metro ligula blandit maeceas retrum gravida
                    cuprum. Maecenas node estibulum.
                  </p>
                </div>
              </li>
            </ul>
          </div>
          <!-- /First content -->

          <!-- Second content: mission -->
          <div
            class="tab-pane fade"
            id="pills-mission"
            role="tabpanel"
            aria-labelledby="pills-mission-tab"
            tabindex="0"
          >
            <h3 class="mb_40">Our mission is...</h3>
            <ul>
              <li class="d-flex align-items-center mb_30">
                <div class="img_box">
                  <img
                    src="../assets/img/icons/clock_alt.png"
                    alt="Clock icon"
                  />
                </div>
                <div>
                  <h4 class="mb_20">Full Day Sessions</h4>
                  <p>
                    Pulvinar est metro ligula blandit maeceas retrum gravida
                    cuprum. Maecenas node estibulum.
                  </p>
                </div>
              </li>

              <li class="d-flex align-items-center">
                <div
                  class="img_box d-flex justify-content-center align-items-center"
                >
                  <img
                    src="../assets/img/icons/diagram_alt.png"
                    alt="Diagram icon"
                  />
                </div>
                <div>
                  <h4 class="mb_20">Varied Classes</h4>
                  <p>
                    Pulvinar est metro ligula blandit maeceas retrum gravida
                    cuprum. Maecenas node estibulum.
                  </p>
                </div>
              </li>
            </ul>
          </div>
          <!-- Second content: mission -->
        </div>
        <!-- /Nav items contents -->
      </div>
      <!-- /Left side -->

      <!-- Right side -->
      <Carousel />
      <!-- /Right side -->
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../assets/scss/partials/variables";

.left_side {
  width: 50%;
  padding-right: 50px;
}

.nav-pills_custom .nav-link {
  width: fit-content;
  padding: 15px 30px;
  border-radius: 0;
  margin-right: 20px;
  font-size: 1.2rem;
}

.nav-pills_custom .nav-link:not(.active) {
  color: darken($color-tertiary, 30%);
  border-bottom: 1px solid darken($color-tertiary, 10%);
}

.nav-pills_custom .nav-link.active {
  background-color: $color-primary;
  position: relative;

  &::after {
    content: "";
    width: 0;
    height: 0;
    position: absolute;
    bottom: -8px;
    left: 50%;
    transform: translateX(-50%);
    border-left: 10px solid transparent;
    border-right: 10px solid transparent;
    border-top: 10px solid $color-primary;
  }
}

.img_box {
  height: 80px;
  aspect-ratio: 1/1;
  margin-right: 30px;
  border-radius: 50%;
  background-color: $color-primary;
  display: flex;
  align-items: center;
  justify-content: center;

  img {
    width: 32px;
    height: 32px;
  }
}
</style>
