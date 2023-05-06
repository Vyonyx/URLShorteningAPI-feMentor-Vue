<script setup lang="ts">
import Container from './Container.vue' 
</script>

<template>
  <Container class="container">
    <h3 class="title">Boost your links today</h3>
    <a class="link" href="#">Get Started</a>
  </Container>
</template>

<style scoped lang="scss">
.container {
  background: var(--dark-violet);
  height: 300px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  background-image: url(/bg-boost-mobile.svg);
  background-size: cover;
}

.title {
  text-align: center;
  font-size: 1.5rem;
}

.link {
  background: var(--cyan);
  padding: 1.25rem 3.5rem;
  border-radius: 2rem;
  cursor: pointer;
}

.title,
.link {
  color: white;
  font-weight: 700;
}

@media (min-width: 1440px) {
  .container {
    background-image: url(/bg-boost-desktop.svg);
  }

  .title {
    font-size: 2rem;
  }
}
</style>
