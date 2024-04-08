<script>
import Hero from "./partials/Hero.vue";
import CtaSeparator from "./partials/CtaSeparator.vue";
import SectionWelcome from "./SectionWelcome.vue";

export default {
  components: {
    Hero,
    CtaSeparator,
    SectionWelcome,
  },
};
</script>

<template>
  <main>
    <Hero />
    <CtaSeparator />
    <SectionWelcome />
  </main>
</template>

<style lang="scss" scoped></style>
