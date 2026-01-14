<script setup>
</script>

<template>
  <section id="hero" class="hero">
    <div class="container hero__container">
      <div class="hero__content">
        <h3 class="hero__intro">Hi, my name is</h3>
        <h1 class="hero__name">Anas (Placeholder).</h1>
        <h2 class="hero__subtitle">I build things for the web.</h2>
        <p class="hero__description">
          I am a <strong>Frontend Developer</strong> with <strong>5 years of experience</strong> specializing in building (and occasionally designing) exceptional digital experiences. Currently, I'm a student focused on building accessible, human-centered products.
        </p>
        <div class="hero__cta">
          <a href="#projects" class="btn btn--primary">Check out my work!</a>
        </div>
      </div>
      <!-- Optional: Profile Image or Graphic -->
    </div>
            <div class="about__image">
          <div class="image-wrapper">
             <!-- Placeholder for profile image -->
             <!-- Replace with src="../assets/images/profile.jpg" when image is added -->
             <img src="../assets/images/anasPic.webp" alt="Profile" />
          </div>
        </div>
  </section>
</template>

<style lang="scss" scoped>
@use '../styles/variables' as *;
@use '../styles/mixins' as *;

.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 0; // Override section padding for full height feel generally or keep it
  

  @include mobile {
    flex-direction: column-reverse;
    margin: 100px 0 0 0;
  }


  &__container {
    padding-top: 100px; // Account for navbar
  }

  &__intro {
    color: var(--color-primary);
    font-family: var(--font-mono);
    font-size: 1rem;
    margin-bottom: 20px;
    font-weight: 400;
  }

  &__name {
    font-size: clamp(40px, 8vw, 80px);
    color: var(--text-heading);
    margin: 0;
  }

  &__subtitle {
    font-size: clamp(30px, 7vw, 70px);
    color: var(--text-main);
    margin-top: 10px;
    margin-bottom: 20px;
  }

  &__description {
    max-width: 540px;
    font-size: 1.1rem;
    margin-bottom: 50px;
  }
}

.image-wrapper {
        position: relative;
    max-width: 290px;
    border-radius: 50%;
    background-color: var(--color-primary);
    margin-right: 20px;

      
      // &::after {
      //   content: "";
      //   display: block;
      //   position: absolute;
      //   width: 100%;
      //   height: 100%;
      //   border: 2px solid var(--color-primary);
      //   top: 20px;
      //   left: 20px;
      //   z-index: -1;
      //   transition: var(--transition);
      //   border-radius: 4px;
      // }
      
      &:hover::after {
        top: 15px;
        left: 15px;
      }
      
      img {
        width: 290px;
    height: 290px;
    object-fit: cover;
    border-radius: 50%;
    filter: grayscale(100%) contrast(1);
    transition: var(--transition);
    display: block;
    mix-blend-mode: multiply;
    margin-right: 15px;
        
        &:hover {
          filter: none;
          mix-blend-mode: normal;
        }

 

      }
    }

.btn--primary {
  display: inline-block;
  padding: 1rem 1.75rem;
  border: 1px solid var(--color-primary);
  border-radius: 4px;
  color: var(--color-primary);
  font-family: var(--font-mono);
  background: transparent;
  transition: var(--transition);
  
  &:hover {
    background: rgba(100, 255, 218, 0.1);
  }
}
</style>
