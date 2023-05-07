<script setup lang="ts">
import { ref } from "vue";
import Container from "./Container.vue"

let mobileMenuOpen = ref(false)

function toggleMobileMenu() {
  mobileMenuOpen.value = !mobileMenuOpen.value
}
</script>

<template>
  <Container class=".container">
    <header>
      <h3 class="logo">Shortly</h3>

      <nav @click="toggleMobileMenu" class="hamburger">
        <svg viewBox="0 0 100 80" width="40" height="40">
          <rect width="80" height="10"></rect>
          <rect y="30" width="80" height="10"></rect>
          <rect y="60" width="80" height="10"></rect>
        </svg>

        <nav class="mobile-menu" v-if="mobileMenuOpen">
          <ul>
            <li><a href="#">Features</a></li>
            <li><a href="#">Pricing</a></li>
            <li><a href="#">Resources</a></li>
          </ul>
          <div class="horizontal-divider"></div>
          <ul>
            <li><button>Login</button></li>
            <li><button class="sign-up">Sign Up</button></li>
          </ul>
        </nav>
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
    cursor: pointer;

    svg {
      fill: var(--gray);
    }

    .mobile-menu {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 2rem;
      position: absolute;
      top: 6rem;
      right: 1rem;
      width: calc(100% - 2rem);
      color: white;
      background: var(--dark-violet);
      padding: 2rem 0;
      border-radius: 1rem;

      ul {
        display: flex;
        flex-direction: column;
        font-weight: 700;
        gap: inherit;
        width: 100%;

        li {
          color: white;
          display: flex;
          justify-content: center;
          width: 100%;
          flex-grow: 1;
          padding: 0 2rem;

          a {
            color: inherit;
          }

          button {
            font-weight: 700;
          }

          .sign-up {
            width: 100%;
            max-width: 15rem;
            margin-top: -1rem;
            padding: 0.75rem 1.25rem;
            border-radius: 2rem;
          }
        }
      }

      .horizontal-divider {
        background: var(--gray);
        width: 80%;
        height: 1px;
      }
    }
  }
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
  cursor: pointer;

  &:hover {
    background: var(--light-cyan);
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
