<script setup>
</script>

<template>
  <section id="skills" class="skills">
    <div class="container">
      <h2 class="section-title"><span>02.</span> Technical Skills</h2>
      
      <div class="skills__grid">
        <div class="skills__category">
          <h3>Web Technologies</h3>
          <ul>
            <li><span class="icon">html 5</span> HTML</li>
            <li><span class="icon">css 3</span> CSS</li>
            <li><span class="icon">sass</span> SCSS</li>
            <li><span class="icon">javascript</span> JavaScript</li>
          </ul>
        </div>
        
        <div class="skills__category">
          <h3>Libraries & Frameworks</h3>
          <ul>
            <li><span class="icon">vue.js</span> Vue.js</li>
            <li><span class="icon">router</span> Vue Router</li>
          </ul>
        </div>
        
        <div class="skills__category">
          <h3>Tools</h3>
          <ul>
            <li><span class="icon">git</span> Git</li>
            <li><span class="icon">github</span> GitHub</li>
            <li><span class="icon">npm</span> NPM</li>
            <li><span class="icon">figma</span> Figma</li>
          </ul>
        </div>

        <div class="skills__category">
          <h3>Methodologies</h3>
          <ul>
            <li>Responsive Web Design</li>
            <li>Figma to Code</li>
          </ul>
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
  
  span {
    color: var(--color-primary);
    font-family: var(--font-mono);
    margin-right: 10px;
  }
}

.skills {
  &__grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
  }
  
  &__category {
    background-color: var(--bg-card);
    padding: 20px;
    border-radius: 4px;
    transition: var(--transition);
    
    &:hover {
      transform: translateY(-5px);
    }
    
    h3 {
      font-size: 1.2rem;
      margin-bottom: 20px;
      color: var(--color-primary);
    }
    
    ul {
      list-style: none;
      padding: 0;
      
      li {
        display: flex;
        align-items: center;
        margin-bottom: 10px;
        font-family: var(--font-mono);
        color: var(--text-main);
        
        .icon {
          // Placeholder for icon integration logic if svg is needed, 
          // or just simple text for now if icons aren't available as assets
          display: none; // Hide placeholder text
        }

        &::before {
            content: '▹';
            color: var(--color-primary);
            margin-right: 10px;
        }
      }
    }
  }
}
</style>
