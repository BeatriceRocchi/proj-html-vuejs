<script>
import { archivesList } from "../assets/data/db_footer.js";
import { featuresList } from "../assets/data/db_footer.js";
import { socialLists } from "../assets/data/db_footer.js";
import newsList from "../assets/data/db_sectionNews.js";
import CardFooter from "./partials/CardFooter.vue";

export default {
  components: {
    CardFooter,
  },
  data() {
    return {
      archivesList,
      featuresList,
      socialLists,
      newsList,
    };
  },
  methods: {
    getImagePath2(img) {
      return new URL(`../assets/img/icons/${img}.png`, import.meta.url).href;
    },

    scrollTop() {
      document.documentElement.scrollTo({ top: 0, behavior: "smooth" }); //For Chrome, FireFox and IE
      document.body.scrollTo({ top: 0, behavior: "smooth" }); //For Safari
    },
  },
};
</script>

<template>
  <footer>
    <div class="upper_footer section_custom">
      <div class="container container_custom">
        <div class="row row-cols-4 g-4">
          <!-- About us -->
          <div class="col">
            <h5>about us</h5>
            <p>
              Ellipsis magna a nulla elite forte maecenas est elementum magna
              etos interdum movum morbi vehicula morbi.
            </p>
            <img
              class="logo"
              src="../assets/img/logo_footer.png"
              alt="Fable logo"
            />
          </div>
          <!-- /About us -->

          <!-- Archives -->
          <div class="col">
            <h5>archives</h5>
            <div
              class="article_box"
              v-for="(item, id) in archivesList"
              :key="id"
            >
              <span class="text-uppercase">{{ item.date }}</span>
              <span> ({{ item.articlesLists.length }})</span>
            </div>
          </div>
          <!-- /Archives -->

          <!-- Features -->
          <div class="col">
            <h5>our features</h5>
            <p>
              Nunc gravida rutrum mauris vehin hasellus ac pretium augue vivamul
              lacus ligul mattis ac vene:
            </p>
            <ul>
              <li
                class="d-flex align-items-center my-2"
                v-for="(item, id) in featuresList"
                :key="id"
              >
                <img
                  class="me-2"
                  src="../assets/img/icons/style_4_alt.png"
                  alt="Tick icon"
                />
                <p class="m-0">{{ item.text }}</p>
              </li>
            </ul>
          </div>
          <!-- /Features -->

          <!-- Posts -->
          <div class="col">
            <h5>recent posts</h5>
            <CardFooter
              class="mb-4"
              v-for="item in newsList"
              :key="item.id"
              :newsElement="item"
            />
          </div>
          <!-- /Posts -->
        </div>
      </div>
    </div>

    <div class="lower_footer">
      <ul class="d-flex justify-content-center">
        <li
          class="square_box d-flex align-items-center justify-content-center"
          v-for="(item, id) in socialLists"
          :key="id"
        >
          <a href="#"><img :src="getImagePath2(item)" :alt="item" /></a>
        </li>
      </ul>
      <p class="text-center">
        © Fable - Children Kindergarten Wordpress Theme by QuanticalLabs
      </p>

      <!-- Button scroll -->
      <div @click="scrollTop()" class="btn_scroll">
        <img src="../assets/img/slider_previous.png" alt="Scroll up icon" />
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@import "../assets/scss/partials/variables";

.upper_footer {
  background-image: url(../assets/img/pattern.png);

  h5 {
    color: $color-white;
    text-transform: uppercase;

    &::after {
      content: "";
      display: block;
      width: 50px;
      background-color: $color-tertiary;
      height: 1px;
      margin-top: 10px;
      margin-bottom: 20px;
    }
  }

  p {
    color: rgba($color-white, 50%);
    margin-bottom: 20px;
    font-size: 0.9rem;
  }

  .logo {
    width: 180px;
  }

  .article_box {
    color: rgba($color-white, 50%);
    font-size: 0.9rem;
    padding: 10px;
    margin-bottom: 5px;
    border: 1px solid rgba($color-white, 50%);
  }
}

.lower_footer {
  padding: 30px 0;
  position: relative;

  .square_box {
    background-color: $color-primary;
    width: 40px;
    aspect-ratio: 1;
    margin: 0px 2px 30px;

    &:hover {
      background-color: $color-secondary;
    }
  }

  p {
    font-size: 0.8rem;
  }

  .btn_scroll {
    position: absolute;
    right: 20px;
    bottom: 20px;
    background-color: darken($color-tertiary, 20%);
    padding: 10px;
    height: 40px;
    width: 40px;
    display: flex;
    align-items: center;
    justify-content: center;

    &:hover {
      cursor: pointer;
      background-color: darken($color-tertiary, 40%);
    }

    img {
      transform: rotate(90deg);
    }
  }
}
</style>
