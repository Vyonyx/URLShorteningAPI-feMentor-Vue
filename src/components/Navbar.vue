<script setup lang="ts">
import Container from "./Container.vue"
</script>

<template>
  <Container class=".container">
    <header>
      <h3 class="logo">Shortly</h3>

      <nav class="hamburger">
        <svg viewBox="0 0 100 80" width="40" height="40">
          <rect width="80" height="10"></rect>
          <rect y="30" width="80" height="10"></rect>
          <rect y="60" width="80" height="10"></rect>
        </svg>
      </nav>

      <nav class="desktop-links">
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
  justify-content: space-between;
  color: var(--very-dark-violet);

  .logo {
    font-size: 2rem;
    font-weight: 700;
    cursor: pointer;
  }

  .desktop-links {
    display: none;
  }

  .hamburger {
    display: block;

    svg {
      fill: var(--gray);
    }
  }
}

@media (min-width: 1440px) {
  header {
    gap: 3rem;
    justify-content: start;

    .desktop-links {
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

          .sign-up {
            background: var(--cyan);
            color: white;
            border-radius: 1rem;
          }
        }
      }

      .nav-buttons {
        margin-left: auto;
      }
    }

    .hamburger {
      display: none;
    }
  }
}
</style>
