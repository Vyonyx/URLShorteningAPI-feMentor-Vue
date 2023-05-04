<script setup lang="ts">
import Container from './Container.vue'
</script>

<template>
  <Container class="container">
    <form class="url-form">
      <input type="text" placeholder="Shorten a link here...">
      <button>Shorten it!</button>
    </form>
  </Container>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  justify-content: center;
}

.url-form {
  position: relative;
  display: flex;
  flex-direction: column;
  padding: 1.25rem;
  gap: 1rem;
  background: var(--dark-violet);
  border-radius: 1rem;
  max-width: 800px;
  flex-grow: 1;

  &::before {
    position: absolute;
    content: '';
    width: 100%;
    height: 100%;
    border-radius: inherit;
    top: 0;
    left: 0;
    background-image: url('/bg-shorten-mobile.svg');
    background-size: 75%;
    background-repeat: no-repeat;
    background-position: top right;
  }

  input,
  button {
    z-index: 10;
    border-radius: 0.5rem;
    border: transparent;
    padding: 1rem;
  }

  input {
    color: red;
  }

  button {
    background: var(--cyan);
    color: white;
    font-weight: 700;
  }
}

@media (min-width: 1440px) {
  .url-form {
    flex-direction: row;
    padding: 3rem;
    border-radius: 10px;

    &::before {
      background-image: url('/bg-shorten-desktop.svg');
      background-position: top right;
      background-size: cover;
    }

    input {
      flex-grow: 1;
    }

    button {
      padding: 1rem 2rem;
    }
  }
}
</style>
