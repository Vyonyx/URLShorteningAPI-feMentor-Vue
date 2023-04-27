<script setup lang="ts">
import Container from "./Container.vue"
</script>

<template>
  <Container class=".container">
    <header>
      <h3 class="logo">Shortly</h3>

      <nav>
        <ul>
          <li><a href="#">Features</a></li>
          <li><a href="#">Pricing</a></li>
          <li><a href="#">Resources</a></li>
        </ul>

        <ul class="nav-buttons">
          <li><button>Login</button></li>
          <li><button class="sign-up">Sign Up</button></li>
        </ul>
      </nav>
    </header>
  </Container>
</template>

<style scoped lang="scss">
header {
  display: flex;
  align-items: center;
  gap: 3rem;
  color: var(--very-dark-violet);

  .logo {
    font-size: 2rem;
    font-weight: 700;
    cursor: pointer;
  }

  nav {
    flex-grow: 1;
    display: flex;
    align-items: center;

    ul {
      display: flex;
      gap: 1.5rem;

      li {
        cursor: pointer;
        color: var(--gray);

        a {
          color: inherit;
          text-decoration: none;
        }

        button {
          border: transparent;
          background: transparent;
          padding: 0.5rem 1.25rem;
          cursor: pointer;
          color: inherit;
        }
      }
    }

    .nav-buttons {
      margin-left: auto;
    }
  }
}

.sign-up {
  background: var(--cyan);
  color: white;
  border-radius: 1rem;
}
</style>
