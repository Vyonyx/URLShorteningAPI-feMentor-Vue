<script setup lang="ts">
defineProps<{
  title: string;
  description: string;
  icon: string;
}>()
</script>

<template>
  <article class="card">
    <div class="symbol">
      <img :src="icon" :alt="title + ' symbol'">
    </div>

    <h6 class=" title">{{ title }}</h6>
    <p class="description">{{ description }}</p>
  </article>
</template>

<style scoped lang="scss">
.card {
  --symbol-size: 80px;
  --card-top-offset: 2rem;

  position: relative;
  background: white;
  border-radius: 5px;
  padding: 2rem;
  padding-top: var(--symbol-size);
  height: fit-content;
}

.symbol {
  width: var(--symbol-size);
  aspect-ratio: 1/1;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%, -50%);
  background: var(--dark-violet);
  border-radius: 100%;
  padding: 1.5rem;
  display: flex;
  justify-content: center;
  align-items: center;

  img {
    width: 100%;
  }
}

.title {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--dark-violet);
  margin-bottom: 2rem;
}

.description {
  color: var(--grayish-violet);
  line-height: 1.5rem;
}

.title,
.description {
  text-align: center;
}

@media (min-width: 1440px) {
  .stat-card {
    max-width: 400px;
  }

  .symbol {
    left: 4rem;
  }

  .title,
  .description {
    text-align: start;
  }
}
</style>
