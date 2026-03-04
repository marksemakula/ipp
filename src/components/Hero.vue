<template>
  <section id="home" class="hero">
    <header class="header">
      <div class="container header-container">
        <div class="logo">IPP</div>
        
        <button class="mobile-toggle" @click="toggleMobileMenu" aria-label="Toggle menu">
          <span></span>
          <span></span>
          <span></span>
        </button>
        
        <nav class="nav-links" :class="{ 'active': mobileMenuOpen }">
          <a href="#home" @click="closeMobileMenu">Home</a>
          <a href="#partners" @click="closeMobileMenu">Partners</a>
          <a href="#programs" @click="closeMobileMenu">Programs</a>
          <a href="#contact" @click="closeMobileMenu">Contact</a>
        </nav>
      </div>
    </header>

    <div class="container hero-container">
      <div class="hero-content">
        <h1 class="hero-title">International Education Pathway Program</h1>
        <p class="hero-subtitle">
          Transform your future with world-class pathway programs designed for global success.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const mobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}
</script>

<style scoped>
.hero {
  position: relative;
  min-height: 55vh;
  background: var(--white);
}

.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: var(--white);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  padding: 1rem 0;
}

.header-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--primary-color);
}

.mobile-toggle {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
}

.mobile-toggle span {
  width: 25px;
  height: 3px;
  background-color: var(--text-dark);
  transition: all 0.3s ease;
}

.nav-links {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.nav-links a {
  text-decoration: none;
  color: var(--text-dark);
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-links a:not(.btn):hover {
  color: var(--primary-color);
}

.hero-container {
  display: flex;
  align-items: center;
  min-height: 55vh;
  padding-top: 80px;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.hero-title {
  font-size: 3.5rem;
  color: var(--text-dark);
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.hero-subtitle {
  font-size: 1.25rem;
  color: var(--text-light);
  margin-bottom: 2.5rem;
  line-height: 1.8;
}

.hero-actions {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  flex-wrap: wrap;
}

@media (max-width: 768px) {
  .mobile-toggle {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: 70px;
    left: 0;
    right: 0;
    background: var(--white);
    flex-direction: column;
    padding: 2rem;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    transform: translateY(-100%);
    opacity: 0;
    transition: all 0.3s ease;
    pointer-events: none;
  }

  .nav-links.active {
    transform: translateY(0);
    opacity: 1;
    pointer-events: all;
  }

  .hero-title {
    font-size: 2.5rem;
  }

  .hero-subtitle {
    font-size: 1.1rem;
  }

  .hero-actions {
    flex-direction: column;
    align-items: stretch;
  }

  .hero-actions a {
    text-align: center;
  }
}
</style>
