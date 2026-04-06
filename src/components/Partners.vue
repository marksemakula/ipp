<template>
  <section id="partners" class="partners">
    <div class="container">
      <div class="carousel-wrapper">
        <div class="carousel">
          <div class="carousel-track">
            <div v-for="(partner, index) in partners" :key="index" class="partner-logo">
              <img :src="partner.logo" :alt="partner.name" />
            </div>
            <!-- Duplicate for seamless loop -->
            <div v-for="(partner, index) in partners" :key="'dup-' + index" class="partner-logo">
              <img :src="partner.logo" :alt="partner.name" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Partner {
  name: string
  logo: string
}

const partners: Partner[] = [
  { name: 'IPP - International Education Pathway Program', logo: '/logos/ipp-logo.svg' },
  { name: 'Oxford University', logo: '/logos/oxford.png' },
  { name: 'Cambridge University', logo: '/logos/cambridge.png' },
  { name: 'Harvard University', logo: '/logos/havard.png' },
  { name: 'MIT', logo: '/logos/mit.png' },
  { name: 'Stanford University', logo: '/logos/stanford.png' },
  { name: 'Yale University', logo: '/logos/yale.png' },
  { name: 'Princeton University', logo: '/logos/princeton.png' },
  { name: 'Columbia University', logo: '/logos/columbia.png' },
  { name: 'University of Toronto', logo: '/logos/toronto.png' },
  { name: 'Braemar College', logo: '/logos/braemar.webp' },
  { name: 'Imperial College London', logo: '/logos/imperial.png' },
]
</script>

<style scoped>
.partners {
  padding: 4rem 0;
  background: var(--white);
  overflow: hidden;
}

.container h2 {
  text-align: center;
  color: var(--text-dark);
  font-size: 2rem;
  margin-bottom: 3rem;
}

.carousel-wrapper {
  position: relative;
  overflow: hidden;
  padding: 2rem 0;
}

.carousel-wrapper::before,
.carousel-wrapper::after {
  content: '';
  position: absolute;
  top: 0;
  width: 150px;
  height: 100%;
  z-index: 2;
  pointer-events: none;
}

.carousel-wrapper::before {
  left: 0;
  background: linear-gradient(to right, var(--white), transparent);
}

.carousel-wrapper::after {
  right: 0;
  background: linear-gradient(to left, var(--white), transparent);
}

.carousel {
  overflow: hidden;
}

.carousel-track {
  display: flex;
  gap: 4rem;
  animation: scroll 30s linear infinite;
  width: fit-content;
}

.carousel-track:hover {
  animation-play-state: paused;
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

.partner-logo {
  flex-shrink: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 80px;
  padding: 0 1rem;
}

.partner-logo img {
  max-height: 100%;
  max-width: 150px;
  width: auto;
  height: auto;
  object-fit: contain;
  filter: grayscale(100%) brightness(0.8);
  transition: all 0.3s ease;
}

.partner-logo:hover img {
  filter: grayscale(0%) brightness(1);
  transform: scale(1.1);
}

@media (max-width: 768px) {
  .partners {
    padding: 3rem 0;
  }
  
  .container h2 {
    font-size: 1.5rem;
    margin-bottom: 2rem;
  }
  
  .carousel-track {
    gap: 2rem;
    animation: scroll 20s linear infinite;
  }
  
  .partner-logo {
    height: 60px;
  }
}
</style>
