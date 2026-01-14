<script setup>
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="footer">
    <h2>Follow me</h2>
    <div class="footer__socials">
      <!-- Add social icons if available -->
       <a href="https://github.com/anasAboAli" target="_blank">GitHub</a>
       <a href="www.linkedin.com/in/أنس-الحرثاني-a4517b250" target="_blank">LinkedIn</a>
       <a href="https://wa.me/970598143863" target="_blank">WhatsApp</a>
       <a href="https://www.facebook.com/share/1DPgVdnvMn/" target="_blank">Facebook</a>
    </div>
    <div class="footer__copy">
      <p>Designed & Built by Anas</p>
      <p>&copy; {{ currentYear }}</p>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@use '../styles/variables' as *;

.footer {
  padding: 20px 0;
  text-align: center;
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-main);

  .footer__socials {
    gap: 20px;
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
  }
  
  &__copy {
    p {
      margin-bottom: 5px;
      
      &:hover {
        color: var(--color-primary);
      }
    }
  }
}
</style>
