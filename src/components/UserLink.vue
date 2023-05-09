<script setup lang="ts">
defineProps<{
  full: string;
  shortened: string;
}>()

function handleClick(e: Event) {
  const buttons = Array.from(document.getElementsByClassName("copy-btn"));
  buttons.forEach(element => {
    element.textContent = "Copy";
    element.classList.remove("was-clicked");
  });

  const target = e.target as HTMLButtonElement;
  target.textContent = "Copied";
  target.classList.toggle("was-clicked");
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

.was-clicked {
  background: var(--dark-violet);

  &:hover {
    background: var(--grayish-violet);
  }
}

@media (min-width: 1440px) {
  .item {
    flex-direction: row;
    justify-content: end;
    align-items: center;
    padding: 1rem;
    gap: 1rem;
    max-width: 800px;
    width: 100%;

    .full-link {
      flex-grow: 1;
      max-width: 40%;
      margin-right: auto;
    }

    .copy-btn {
      margin-bottom: 0;
      width: 120px;
    }
  }

  .horizontal-divider {
    display: none;
  }
}
</style>
