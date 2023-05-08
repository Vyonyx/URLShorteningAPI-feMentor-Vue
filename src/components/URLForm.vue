<script setup lang="ts">
import { ref } from 'vue';
import Container from './Container.vue'

const urlText = ref("");

async function urlApiRequest(e: Event) {
  e.preventDefault();
  if (!urlText.value) return;

  const response = await fetch("https://api.shrtco.de/v2/shorten?" + new URLSearchParams({ url: urlText.value }), {
    method: "get",
  })

  const data = await response.json();
  if (!data.ok) return;

  const shortenedURL = data.result.full_short_link;
}
</script>

<template>
  <Container class="container">
    <form @submit="e => urlApiRequest(e)" class="url-form">
      <input v-model="urlText" type="text" placeholder="Shorten a link here...">
      <button>Shorten it!</button>
    </form>
  </Container>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  justify-content: center;
  position: relative;

  &::before {
    position: absolute;
    content: '';
    width: 100%;
    height: 50%;
    bottom: 0;
    left: 0;
    background: var(--light-gray);
  }
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
