<template>
  <header class="header" :class="{ 'scrolled': isScrolled }">
    <div class="container">
      <nav class="nav">
        <div class="logo">
          <Logo size="small" />
        </div>
        
        <button class="mobile-toggle" @click="toggleMobileMenu" aria-label="Toggle menu">
          <span></span>
          <span></span>
          <span></span>
        </button>
        
        <ul class="nav-links" :class="{ 'active': mobileMenuOpen }">
          <li><a href="#home" @click="closeMobileMenu">Home</a></li>
          <li><a href="#programs" @click="closeMobileMenu">Programs</a></li>
          <li><a href="#testimonials" @click="closeMobileMenu">Stories</a></li>
          <li><a href="#contact" @click="closeMobileMenu" class="btn btn-primary">Apply</a></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import Logo from './Logo.vue'

const isScrolled = ref(false)
const mobileMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: var(--glass-bg);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--glass-border);
  transition: all 0.3s ease;
}

.header.scrolled {
  box-shadow: var(--shadow-md);
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}

.logo {
  display: flex;
  align-items: center;
}

.mobile-toggle {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 5px;
}

.mobile-toggle span {
  width: 25px;
  height: 3px;
  background-color: var(--text-dark);
  transition: all 0.3s ease;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 2rem;
  align-items: center;
}

.nav-links a {
  text-decoration: none;
  color: var(--text-dark);
  font-weight: 500;
  transition: color 0.3s ease;
  padding: 0.5rem 0;
}

.nav-links a:not(.btn):hover {
  color: var(--primary-color);
}

.nav-links .btn {
  padding: 0.625rem 1.5rem;
}

@media (max-width: 968px) {
  .logo-text {
    font-size: 1rem;
    max-width: 200px;
  }
}

@media (max-width: 768px) {
  .mobile-toggle {
    display: flex;
  }
  
  .nav-links {
    position: fixed;
    top: 80px;
    right: -100%;
    width: 100%;
    max-width: 300px;
    height: calc(100vh - 80px);
    background-color: var(--white);
    flex-direction: column;
    padding: 2rem;
    box-shadow: var(--shadow-xl);
    transition: right 0.3s ease;
    align-items: flex-start;
  }
  
  .nav-links.active {
    right: 0;
  }
  
  .logo-text {
    font-size: 0.875rem;
    max-width: 150px;
  }
  
  .logo-img {
    height: 40px;
  }
}
</style>
