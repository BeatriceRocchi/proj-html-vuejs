<script>
import CardContacts from "./partials/CardContacts.vue";
import contactsList from "../assets/data/db_sectionContact";
import Btn from "./partials/Btn.vue";

export default {
  data() {
    return {
      contactsList,
    };
  },
  components: {
    CardContacts,
    Btn,
  },
};
</script>

<template>
  <section class="section_custom text-center">
    <div class="container container_custom">
      <h2>Contact Us</h2>
      <h5 class="mt_20 mb_30">Our postal address and contact details</h5>
      <img
        class="header_divider"
        src="../assets/img/header_divider.png"
        alt="---"
      />

      <div class="row row-cols-4 justify-content-between">
        <CardContacts
          v-for="item in contactsList"
          :key="item.id"
          :contactElement="item"
        />
      </div>

      <form action="#" class="form_custom d-flex mt_20">
        <div class="flex-grow-1 h-100 me-4">
          <div class="d-flex mt_20 mb_20 name_box">
            <input
              type="text"
              class="form-control"
              id="inputName"
              placeholder="Your Name *"
              required
            />
            <span><img src="../assets/img/image.png" alt="Image icon" /></span>
          </div>

          <input
            type="email"
            class="form-control mt_20 mb_20"
            id="inputEmail"
            placeholder="Your E-mail *"
            required
          />
          <input
            type="text"
            class="form-control"
            id="inputSubject"
            placeholder="Subject"
          />
        </div>
        <div class="flex-grow-1 mt_20">
          <textarea
            class="form-control h-100"
            placeholder="Your Message *"
            required
          ></textarea>
        </div>
      </form>
      <Btn
        class="mx-auto mt_40"
        type="submit"
        :textButton="'send message'"
        :colorButton="'primary'"
      />
    </div>
  </section>
</template>

<style lang="scss" scoped>
.form_custom {
  input,
  textarea {
    border-radius: 0;
  }

  .name_box {
    position: relative;

    img {
      position: absolute;
      top: 50%;
      right: 10px;
      transform: translateY(-50%);
    }
  }
}
</style>
