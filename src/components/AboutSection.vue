<script setup>
</script>

<template>
  <section id="about" class="about">
    <div class="container">
      <h2 class="section-title"><span>01.</span> About Me</h2>
      
      <div class="about__content">
        <div class="about__text">
          <p>
            Hello! My name is Anas and I enjoy creating things that live on the internet. I am a <strong>Frontend Developer</strong> with <strong>five years of experience</strong> building modern, responsive, and scalable user interfaces using Vue.js.
          </p>
          <p>
            I believe that clean code and thoughtful design are the foundation of successful digital products. My focus is always on delivering high-performance web applications with an excellent user experience.
          </p>
          <p>
            Currently, I am a <strong>Student</strong>, constantly learning and refining my craft.
          </p>

          <div class="about__details">
            <h3>Key Attributes</h3>
            <ul class="styled-list">
              <li>Clean and well-structured code</li>
              <li>Fast and efficient execution</li>
              <li>Strong problem-solving skills</li>
              <li>Ability to work independently</li>
              <li>Strong collaboration within a team</li>
            </ul>
          </div>
        </div>
 
        
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use '../styles/variables' as *;
@use '../styles/mixins' as *;

.section-title {
  display: flex;
  align-items: center;
  font-size: clamp(26px, 5vw, 32px);
  margin-bottom: 40px;
  width: 100%;
  white-space: nowrap; // Keep number and title together
  
  span {
    color: var(--color-primary);
    font-family: var(--font-mono);
    font-size: clamp(20px, 3vw, 24px);
    margin-right: 10px;
    font-weight: 400;
  }
  
  &::after {
    content: "";
    display: block;
    width: 300px;
    height: 1px;
    background-color: #233554;
    margin-left: 20px;
    
    @include mobile {
      width: 100%;
    }
  }
}

.about {
  &__content {
    display: grid;
    grid-template-columns: 3fr 2fr;
    gap: 50px;
    
    @include tablet {
      display: block;
    }
  }
  
  &__text {
    p {
      margin-bottom: 15px;
    }
  }
  
  &__details {
    margin-top: 20px;
    
    h3 {
      font-size: 1.1rem;
      margin-bottom: 15px;
      color: var(--text-heading);
    }
  }
  
  &__image {
    @include tablet {
      margin-top: 50px;
      display: flex;
      justify-content: center;
    }
    
    
  }
}

.styled-list {
  display: grid;
  grid-template-columns: repeat(2, minmax(140px, 200px));
  padding: 0;
  margin: 20px 0 0 0;
  list-style: none;
  
  li {
    position: relative;
    padding-left: 20px;
    margin-bottom: 10px;
    font-family: var(--font-mono);
    font-size: 13px;
    
    &::before {
      content: "▹";
      position: absolute;
      left: 0;
      color: var(--color-primary);
    }
  }
}
</style>
