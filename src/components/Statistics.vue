<script setup lang="ts">
import Container from './Container.vue' 
</script>

<template>
  <Container class="container">
    <h3 class="title">Advanced Statistics</h3>
    <p class="description">Track how your links are performing across the web with our advanced statistics dashboard.</p>
  </Container>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: var(--light-gray);
  padding-top: 60px;
}

.title {
  font-size: 1.75rem;
  font-weight: 700;
  text-align: center;
  color: var(--dark-violet);
  margin-bottom: 2rem;
}

.description {
  text-align: center;
  color: var(--grayish-violet);
  line-height: 2rem;
  margin-bottom: 2.5rem;
  max-width: 400px;
}
</style>
