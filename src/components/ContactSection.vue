<script setup>
</script>

<template>
  <section id="contact" class="contact">
    <div class="container contact__container">
      <p class="contact__overline">04. What’s Next?</p>
      <h2 class="contact__title">Get In Touch</h2>
      <p class="contact__description">
        I'm currently looking for new opportunities, and my inbox is always open. Whether you have a question or just want to say hi, I'll try my best to get back to you!
      </p>
      <a href="mailto:anas@example.com" class="btn btn--primary">Say Hello</a>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use '../styles/variables' as *;
@use '../styles/mixins' as *;

.contact {
  text-align: center;
  margin-bottom: 20px;
  
  &__container {
    max-width: 600px;
  }
  
  &__overline {
    color: var(--color-primary);
    font-family: var(--font-mono);
    margin-bottom: 20px;
  }
  
  &__title {
    font-size: clamp(40px, 5vw, 60px);
    margin-bottom: 30px;
    color: var(--text-heading);
  }
  
  &__description {
    font-size: 1.1rem;
    color: var(--text-main);
    margin-bottom: 50px;
  }
}

.btn--primary {
  display: inline-block;
  padding: 1.25rem 1.75rem;
  border: 1px solid var(--color-primary);
  border-radius: 4px;
  color: var(--color-primary);
  font-family: var(--font-mono);
  background: transparent;
  font-size: 14px;
  
  &:hover {
    background: rgba(100, 255, 218, 0.1);
  }
}
</style>
