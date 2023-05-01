<script setup lang="ts">

</script>

<template>
  <section>
    <slot />
  </section>
</template>

<style scoped lang="scss">
section {
  --padding-amount: 2rem;
  padding: var(--padding-amount);
}

@media (min-width: 420px) {
  section {
    padding: var(--padding-amount) 3rem;
  }
}

@media (min-width: 1440px) {
  section {
    padding: var(--padding-amount) 10rem;
  }
}
</style>
