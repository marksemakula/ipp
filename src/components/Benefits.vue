<template>
  <section id="benefits" class="benefits">
    <div class="container">
      <div class="section-header">
        <h2>Why Choose IPP?</h2>
        <p class="section-subtitle">Comprehensive support for your educational journey</p>
      </div>
      
      <div class="benefits-layout">
        <div class="benefits-visual">
          <div class="circle-graphic">
            <div class="circle circle-1"></div>
            <div class="circle circle-2"></div>
            <div class="circle circle-3"></div>
            <div class="center-text">
              <span class="stat-number">98%</span>
              <span class="stat-label">Success Rate</span>
            </div>
          </div>
        </div>
        
        <div class="benefits-list">
          <div v-for="benefit in benefits" :key="benefit.id" class="benefit-item">
            <div class="benefit-icon">{{ benefit.icon }}</div>
            <div class="benefit-content">
              <h3>{{ benefit.title }}</h3>
              <p>{{ benefit.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Benefit {
  id: number
  icon: string
  title: string
  description: string
}

const benefits: Benefit[] = [
  {
    id: 1,
    icon: '🏆',
    title: 'Guaranteed Progression',
    description: 'Successful completion guarantees admission to partner universities'
  },
  {
    id: 2,
    icon: '💼',
    title: 'Career Services',
    description: 'Access to career counseling, internships, and job placement support'
  },
  {
    id: 3,
    icon: '🏠',
    title: 'Accommodation Support',
    description: 'Assistance finding safe and comfortable housing near your campus'
  },
  {
    id: 4,
    icon: '📚',
    title: 'Learning Resources',
    description: 'State-of-the-art facilities and comprehensive digital learning materials'
  },
  {
    id: 5,
    icon: '🌐',
    title: 'Cultural Integration',
    description: 'Programs to help you adapt and thrive in your new environment'
  },
  {
    id: 6,
    icon: '💳',
    title: 'Flexible Payment',
    description: 'Scholarships available and flexible payment plans to support your studies'
  }
]
</script>

<style scoped>
.benefits {
  padding: 6rem 0;
  background-color: var(--white);
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-header h2 {
  color: var(--text-dark);
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.25rem;
  color: var(--text-light);
}

.benefits-layout {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 4rem;
  align-items: center;
}

.benefits-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.circle-graphic {
  position: relative;
  width: 300px;
  height: 300px;
}

.circle {
  position: absolute;
  border-radius: 50%;
  border: 3px solid;
}

.circle-1 {
  width: 100%;
  height: 100%;
  border-color: var(--primary-color);
  opacity: 0.3;
  animation: pulse 3s ease-in-out infinite;
}

.circle-2 {
  width: 75%;
  height: 75%;
  top: 12.5%;
  left: 12.5%;
  border-color: var(--primary-color);
  opacity: 0.5;
  animation: pulse 3s ease-in-out infinite 0.5s;
}

.circle-3 {
  width: 50%;
  height: 50%;
  top: 25%;
  left: 25%;
  border-color: var(--primary-color);
  opacity: 0.7;
  animation: pulse 3s ease-in-out infinite 1s;
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
}

.center-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 3rem;
  font-weight: 700;
  color: var(--primary-color);
}

.stat-label {
  display: block;
  font-size: 1rem;
  color: var(--text-light);
  margin-top: 0.5rem;
}

.benefits-list {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.benefit-item {
  display: flex;
  gap: 1.5rem;
  align-items: flex-start;
}

.benefit-icon {
  font-size: 2.5rem;
  flex-shrink: 0;
}

.benefit-content h3 {
  color: var(--text-dark);
  margin-bottom: 0.5rem;
  font-size: 1.25rem;
}

.benefit-content p {
  color: var(--text-light);
  line-height: 1.6;
  margin-bottom: 0;
}

@media (max-width: 968px) {
  .benefits-layout {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .circle-graphic {
    width: 250px;
    height: 250px;
  }
  
  .stat-number {
    font-size: 2.5rem;
  }
}

@media (max-width: 768px) {
  .benefits {
    padding: 4rem 0;
  }
}
</style>
