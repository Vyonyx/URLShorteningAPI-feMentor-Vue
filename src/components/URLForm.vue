<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Container from './Container.vue'
import UserLink from './UserLink.vue'

interface UserUrls {
  full: string;
  shortened: string;
}

const urlText = ref("");
const existingShortenedUrls = ref<UserUrls[]>();

onMounted(() => {
  const savedURLS = JSON.parse(window.localStorage.getItem("savedURLS") || '[]');
  existingShortenedUrls.value = savedURLS._rawValue || [];
})

async function urlApiRequest(e: Event) {
  e.preventDefault();
  if (!urlText.value) return;

  const response = await fetch("https://api.shrtco.de/v2/shorten?" + new URLSearchParams({ url: urlText.value }), {
    method: "get",
  })

  const data = await response.json();
  if (!data.ok) return;

  const shortenedURL = data.result.full_short_link;
  const urlData: UserUrls = { full: urlText.value, shortened: shortenedURL };
  existingShortenedUrls.value?.push(urlData);

  window.localStorage
    .setItem("savedURLS", JSON.stringify(existingShortenedUrls))

  urlText.value = "";
}
</script>

<template>
  <Container class="container">
    <form @submit="e => urlApiRequest(e)" class="url-form">
      <input v-model="urlText" type="text" placeholder="Shorten a link here...">
      <button>Shorten it!</button>
    </form>
  </Container>

  <Container class="url-container">
    <ul>
      <UserLink v-for="{ full, shortened } in existingShortenedUrls" :full="full" :shortened="shortened" />
    </ul>
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

.url-container {
  padding-top: 0;
  background: var(--light-gray);

  ul {
    display: flex;
    flex-direction: column;
    gap: 2rem;
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
