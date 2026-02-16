<script setup>
import { ref, computed } from 'vue'

const showAll = ref(false)

const projects = ref([
  {
    id: 1,
    title: 'Mobile Store Project',
    description: 'A web application that showcases the latest mobile phones, pricing, and current store offers.',
    tech: ['HTML', 'SCSS', 'JavaScript', 'Vue.js'],
    role: 'Full project designer and developer',
    type: 'Freelance',
    link: 'https://mobile-anas-store.netlify.app/',
    github: '#' // Placeholder
  },{
    id: 2,
    title: 'Movies Library Project',
    description: 'A website that showcases The latest movies, sports broadcasts, and documentaries in a stunning and attractive format.',
    tech: ['HTML', 'SCSS', 'JavaScript', 'firebase'],
    role: 'Full project designer and developer',
    type: 'Freelance',
    link: 'https://movies-library-project.netlify.app/',
    github: '#' // Placeholder
  },
  {
    id: 3,
    title: 'Quran Memorization Center',
    descriptsion: 'A website presenting the achievements of a Quran memorization center and introducing its scholars and preachers.',
    tech: ['HTML', 'SCSS', 'JavaScript', 'Vue.js'],
    role: 'Full project designer and developer',
    type: 'University Project',
    link: 'https://anas-vue-firstpro.netlify.app/',
    github: '#'
  },
  {
    id: 4,
    title: 'Happiness Restaurant',
    description: 'A website showcasing the latest and most delicious Eastern dishes, their prices, and current restaurant offers.',
    tech: ['HTML', 'SCSS', 'JavaScript', 'Vue.js'],
    role: 'Full project designer and developer',
    type: 'Freelance Project',
    link: 'https://happiness-restaurant-2004.netlify.app/',
    github: '#'
  },
  {
    id: 5,
    title: 'WanderLust | Luxury Travel & Extraordinary Destinations',
    description: 'A website showcasing the latest and most luxurious travel packages and destinations from WanderLust',
    tech: ['HTML', 'SCSS', 'JavaScript', 'Vue.js', 'firebase'],
    role: 'Full project designer and developer',
    type: 'Freelance Project',
    link: 'https://wanderlust-company.netlify.app/',
    github: '#'
  }
])

const visibleProjects = computed(() => {
  return showAll.value ? projects.value : projects.value.slice(0, 3)
})
</script>

<template>
  <section id="projects" class="projects">
    <div class="container">
      <h2 class="section-title"><span>03.</span> Some Things I've Built</h2>
      
      <div class="projects__grid">
        <TransitionGroup name="fade">
          <div v-for="project in visibleProjects" :key="project.id" class="project-card">
            <div class="project-card__content">
              <p class="project-card__overline">{{ project.type }}</p>
              <h3 class="project-card__title">
                <a :href="project.link" target="_blank">{{ project.title }}</a>
              </h3>
              
              <div class="project-card__description">
                <p>{{ project.description }}</p>
              </div>
              
              <ul class="project-card__tech-list">
                <li v-for="tech in project.tech" :key="tech">{{ tech }}</li>
              </ul>
              
              <div class="project-card__links">
                  <a :href="project.github" aria-label="GitHub Link" target="_blank">
                      <svg xmlns="http://www.w3.org/2000/svg" role="img" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-github"><title>GitHub</title><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
                  </a>
                  <a :href="project.link" aria-label="External Link" target="_blank">
                      <svg xmlns="http://www.w3.org/2000/svg" role="img" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-external-link"><title>External Link</title><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
                  </a>
              </div>
            </div>
          </div>
        </TransitionGroup>
      </div>

      <div class="projects__show-more">
        <button @click="showAll = !showAll" class="btn-primary">
          {{ showAll ? 'Show less' : 'Show more' }}
        </button>
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

.projects__grid {
    display: flex;
    flex-direction: column;
    gap: 50px;
}

.project-card {
    background-color: var(--bg-card);
    padding: 2rem;
    border-radius: 4px;
    transition: var(--transition);
    border: 1px solid transparent;

    &:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 30px -15px rgba(2,12,27,0.7);
        border: 1px solid var(--color-primary);
    }
    
    &__overline {
        color: var(--color-primary);
        font-family: var(--font-mono);
        font-size: 0.8rem;
        margin-bottom: 5px;
    }

    &__title {
        margin-bottom: 20px;
        a {
            color: var(--text-heading);
            font-size: 1.5rem;
            
            &:hover {
                color: var(--color-primary);
            }
        }
    }

    &__description {
        background-color: #112240; // slightly distinct or just plain
        color: var(--text-main);
        font-size: 1rem;
        border-radius: 4px;
        margin-bottom: 20px;
        padding-right: 20px;
    }

    &__tech-list {
        display: flex;
        flex-wrap: wrap;
        list-style: none;
        margin-bottom: 20px;
        
        li {
            font-family: var(--font-mono);
            font-size: 0.8rem;
            margin-right: 20px;
            color: var(--text-main);
        }
    }

    &__links {
        display: flex;
        align-items: center;
        
        a {
            color: var(--text-main);
            margin-right: 20px;
            
            &:hover {
                color: var(--color-primary);
            }
            
            svg {
                width: 20px;
                height: 20px;
            }
        }
    }
}

.projects__show-more {
    display: flex;
    justify-content: center;
    margin-top: 80px;

    .btn-primary {
        background-color: transparent;
        color: var(--color-primary);
        border: 1px solid var(--color-primary);
        padding: 1.25rem 1.75rem;
        font-size: 0.9rem;
        font-family: var(--font-mono);
        border-radius: 4px;
        cursor: pointer;
        transition: var(--transition);
        
        &:hover {
            background-color: rgba(100, 255, 218, 0.1);
            transform: translateY(-3px);
        }
    }
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(20px);
}
</style>
