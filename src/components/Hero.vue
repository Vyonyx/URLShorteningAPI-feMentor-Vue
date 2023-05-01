<script setup lang="ts">
import Container from './Container.vue';
</script>

<template>
  <Container class="hero-container">
    <img class="hero-image" src="/illustration-working.svg" alt="person working at desk">
    <div class="hero-text">
      <h1 class="hero-title">More than just shorter links</h1>
      <p class="hero-paragraph">
        Build your brand's recognition and get detailed insights on how your links are performing.
      </p>
      <button class="hero-button">Get Started</button>
    </div>
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

.hero-text {
  margin-top: 2rem;
  place-self: start;
  width: calc(100vw - 4rem);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;

  .hero-title {
    text-align: center;
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--very-dark-violet);
  }

  .hero-paragraph {
    text-align: center;
    color: var(--gray);
    font-size: 1.1rem;
    line-height: 2rem;
  }

  .hero-button {
    border: transparent;
    color: white;
    background: var(--cyan);
    border-radius: 3rem;
    padding: 1rem 2.25rem;
    margin-top: 1rem;
  }
}

@media (min-width: 420px) {
  .hero-image {
    width: 100%;
    max-width: 70vw;
    height: auto;
    place-self: center;
  }

  .hero-text {
    width: 100%;
    margin-top: 4rem;

    .hero-title {
      font-size: 3rem;
    }

    .hero-paragraph {
      max-width: 600px;
    }
  }
}

@media (min-width: 1440px) {
  .hero-container {
    grid-template-rows: 1;
    grid-template-columns: repeat(2, 1fr);
    grid-auto-flow: column;
  }

  .hero-image {
    position: relative;
    place-self: start;
    width: 130%;
    margin-left: 6rem;

    height: auto;
    grid-column-start: 2;
  }

  .hero-text {
    align-self: center;
    grid-column: 0;

    .hero-title,
    .hero-paragraph {
      text-align: start;
    }

    .hero-paragraph,
    .hero-button {
      font-size: 1.3rem;
      align-self: start;
    }

    .hero-title {
      align-self: start;
      font-size: 4.5rem;
    }

    .hero-paragraph {
      width: 90%;
    }
  }
}
</style>
