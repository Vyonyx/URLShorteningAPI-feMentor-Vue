<script setup lang="ts">
import Container from './Container.vue';
</script>

<template>
  <Container class="hero-container">
    <img class="hero-image" src="/illustration-working.svg" alt="person working at desk">
  </Container>
</template>

<style scoped lang="scss">
.hero-container {
  overflow-x: hidden;
  display: grid;
  grid-template-rows: auto;
  grid-template-columns: 1;
}

.hero-image {
  height: 320px;
}

@media (min-width: 420px) {
  .hero-image {
    width: 100%;
    max-width: 70vw;
    height: auto;
    place-self: center;
  }
}

@media (min-width: 1440px) {
  .hero-container {
    grid-template-rows: 1;
    grid-template-columns: repeat(2, 1fr);
  }

  .hero-image {
    position: relative;
    place-self: start;
    width: 130%;
    margin-left: 6rem;

    height: auto;
    grid-column-start: 2;
  }
}
</style>
