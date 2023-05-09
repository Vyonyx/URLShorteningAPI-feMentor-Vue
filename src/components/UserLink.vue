<script setup lang="ts">
defineProps<{
  full: string;
  shortened: string;
}>()

function handleClick(e: Event) {
  const target = e.target as HTMLButtonElement;
  target.innerText = "Copied";
}
</script>

<template>
  <li class="item">
    <p class="full-link">{{ full }}</p>
    <div class="horizontal-divider"></div>
    <p class="shortened-link">{{ shortened }}</p>
    <button class="copy-btn" @click="e => handleClick(e)">Copy</button>
  </li>
</template>

<style scoped lang="scss">
.item {
  position: relative;
  display: flex;
  flex-direction: column;
  background: white;
  border-radius: 0.5rem;
}

.horizontal-divider {
  position: relative;
  width: 100%;
  height: 1px;
  background: var(--gray);
}

p {
  padding: 1rem;
  white-space: nowrap;
  overflow-x: hidden;
  text-overflow: ellipsis;
  font-size: 1.1rem;
}

.shortened-link {
  color: var(--cyan);
}

.copy-btn {
  width: calc(100% - 2rem);
  margin-bottom: 1rem;
  align-self: center;
  padding: 0.75rem 1.75rem;
  font-weight: 700;
  color: white;
  background: var(--cyan);
  border: transparent;
  border-radius: 0.5rem;
  cursor: pointer;

  &:hover {
    background: var(--light-cyan);
  }
}
</style>
