<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav :class="['navbar', { 'navbar--scrolled': isScrolled }]">
    <div class="container navbar__container">
      <router-link to="/" class="navbar__logo">
        &lt;A/&gt;
      </router-link>

      <button class="navbar__toggle" @click="toggleMenu" aria-label="Toggle navigation">
        <span class="hamburger" :class="{ 'open': isMenuOpen }"></span>
      </button>

      <ul class="navbar__menu" :class="{ 'navbar__menu--open': isMenuOpen }">
        <li><a href="#hero" @click="isMenuOpen = false">Home</a></li>
        <li><a href="#about" @click="isMenuOpen = false">About</a></li>
        <li><a href="#skills" @click="isMenuOpen = false">Skills</a></li>
        <li><a href="#projects" @click="isMenuOpen = false">Projects</a></li>
        <li><a href="#contact" @click="isMenuOpen = false">Contact</a></li>
      </ul>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@use '../styles/variables' as *;
@use '../styles/mixins' as *;

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 20px 0;
  z-index: 1000;
  transition: var(--transition);
  background: transparent;

  &--scrolled {
    padding: 15px 0;
    background-color: rgba(10, 25, 47, 0.95); // Using hex var equivalent directly or var
    background-color: var(--bg-nav);
    backdrop-filter: blur(10px);
    box-shadow: 0 10px 30px -10px rgba(2, 12, 27, 0.7);
  }

  &__container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__logo {
    font-family: var(--font-mono);
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--color-primary);
    
    &:hover {
      color: var(--color-secondary);
    }
  }

  &__menu {
    display: flex;
    list-style: none;
    gap: 30px;
    align-items: center;

    a {
      font-size: 0.9rem;
      font-family: var(--font-mono);
      color: var(--text-heading);
      
      &:hover {
        color: var(--color-primary);
      }
    }

    @include mobile {
      position: fixed;
      top: 0;
      right: 0;
      width: 75%;
      height: 100vh;
      background-color: var(--bg-card);
      flex-direction: column;
      justify-content: center;
      transform: translateX(100%);
      transition: transform 0.3s ease-in-out;
      
      &--open {
        transform: translateX(0);
        box-shadow: -10px 0 30px -15px rgba(2, 12, 27, 0.7);
      }
    }
  }
  
  &__toggle {
    display: none;
    background: none;
    border: none;
    cursor: pointer;
    
    @include mobile {
      display: block;
      z-index: 1001;
    }
  }
}

.hamburger {
  display: block;
  width: 30px;
  height: 2px;
  background-color: var(--color-primary);
  position: relative;
  transition: var(--transition);
  
  &::before, &::after {
    content: '';
    position: absolute;
    width: 100%;
    height: 2px;
    background-color: var(--color-primary);
    transition: var(--transition);
    left: 0;
  }
  
  &::before { top: -8px; }
  &::after { top: 8px; }
  
  &.open {
    background-color: transparent;
    
    &::before {
      transform: rotate(45deg);
      top: 0;
    }
    
    &::after {
      transform: rotate(-45deg);
      top: 0;
    }
  }
}

.btn--outline {
  border: 1px solid var(--color-primary);
  padding: 0.5rem 1rem;
  border-radius: 4px;
  color: var(--color-primary) !important;
  
  &:hover {
    background-color: rgba(100, 255, 218, 0.1);
  }
}
</style>
