<script setup lang="ts">
import Container from './Container.vue' 
</script>

<template>
  <Container class="container">
    <p class="footer-title">Shortly</p>

    <div class="links-section">
      <h6 class="links-heading">Features</h6>
      <ul class="footer-links">
        <li><a href="#">Link Shortening</a></li>
        <li><a href="#">Branding Links</a></li>
        <li><a href="#">Analytics</a></li>
      </ul>
    </div>

    <div class="links-section">
      <h6 class="links-heading">Resources</h6>
      <ul class="footer-links">
        <li><a href="#">Blog</a></li>
        <li><a href="#">Developers</a></li>
        <li><a href="#">Support</a></li>
      </ul>
    </div>

    <div class="links-section">
      <h6 class="links-heading">Company</h6>
      <ul class="footer-links">
        <li><a href="#">About</a></li>
        <li><a href="#">Our Team</a></li>
        <li><a href="#">Careers</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>

    <ul class="social-media-links">
      <li><a href="#"><img src="/icon-facebook.svg" alt="Shortly Facebook"></a></li>
      <li><a href="#"><img src="/icon-twitter.svg" alt="Shortly Twitter"></a></li>
      <li><a href="#"><img src="/icon-pinterest.svg" alt="Shortly Pinterest"></a></li>
      <li><a href="#"><img src="/icon-instagram.svg" alt="Shortly Instagram"></a></li>
    </ul>
  </Container>
</template>

<style scoped lang="scss">
.container {
  background: var(--very-dark-violet);
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3rem;
  padding-top: 4rem;
  padding-bottom: 4rem;

  .footer-title {
    font-size: 2rem;
  }

  .links-heading {
    text-align: center;
    margin-bottom: 2rem;
    font-weight: 700;
  }

  .footer-links {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  li a {
    color: var(--grayish-violet);
    cursor: pointer;
  }

  .social-media-links {
    display: flex;
    gap: 1.5rem;
  }
}

@media (min-width: 1440px) {
  .container {
    flex-direction: row;
    justify-content: end;
    align-items: start;
    gap: 5rem;
  }

  .footer-title {
    flex-grow: 1;
  }

  .links-section {
    display: flex;
    flex-direction: column;
    align-items: start;
  }

  .footer-links li {
    align-self: start;
  }
}
</style>
