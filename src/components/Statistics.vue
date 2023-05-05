<script setup lang="ts">
import { ref } from 'vue';
import Container from './Container.vue'
import StatCard from './StatCard.vue'

const cardContent = ref([
  {
    title: "Brand Recognition",
    description: "Boost your brand recognition with each click. Generic links don't mean a thing. Brand links help instil confidence in your content.",
    icon: "/icon-brand-recognition.svg",
  },
  {
    title: "Detailed Records",
    description: "Gain insights into who is clicking your links. Knowing when and where people engage with your content helps inform better decisions.",
    icon: "/icon-detailed-records.svg",
  },
  {
    title: "Fully Customizable",
    description: "Improve brand awareness and content discoverability through customizable links, superchargin audience engagement.",
    icon: "/icon-fully-customizable.svg",
  }
])
</script>

<template>
  <Container class="container">
    <h3 class="title">Advanced Statistics</h3>
    <p class="description">Track how your links are performing across the web with our advanced statistics dashboard.</p>

    <div class="card-container">
      <div class="connecting-bar"></div>
      <StatCard class="stat-card" v-for="{ title, description, icon } in cardContent" :title="title"
        :description="description" :icon="icon" />
    </div>
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

.card-container {
  --card-gap: 7rem;
  display: flex;
  flex-direction: column;
  gap: var(--card-gap);
  margin: 3rem 0;
  position: relative;
}

.connecting-bar {
  width: 10px;
  height: 100%;
  background: var(--cyan);
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}
</style>
