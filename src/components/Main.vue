<script>
import Hero from "./partials/Hero.vue";
import CtaSeparator from "./partials/CtaSeparator.vue";
import SectionWelcome from "./SectionWelcome.vue";
import SectionOverview from "./SectionOverview.vue";

export default {
  components: {
    Hero,
    CtaSeparator,
    SectionWelcome,
    SectionOverview,
  },
};
</script>

<template>
  <main>
    <Hero />
    <CtaSeparator />
    <SectionWelcome />
    <SectionOverview class="bg_grey" />
  </main>
</template>

<style lang="scss" scoped></style>
