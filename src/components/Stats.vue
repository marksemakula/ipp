<template>
  <section class="stats">
    <div class="container">
      <div class="stats-grid">
        <div v-for="stat in stats" :key="stat.id" class="stat-card">
          <div class="stat-value">{{ stat.value }}</div>
          <div class="stat-label">{{ stat.label }}</div>
          <div class="stat-description">{{ stat.description }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Stat {
  id: number
  value: string
  label: string
  description: string
}

const stats: Stat[] = [
  {
    id: 1,
    value: '10,000+',
    label: 'Students Enrolled',
    description: 'Successful graduates worldwide'
  },
  {
    id: 2,
    value: '150+',
    label: 'Partner Universities',
    description: 'Across 25 countries'
  },
  {
    id: 3,
    value: '98%',
    label: 'Success Rate',
    description: 'Students achieving their goals'
  },
  {
    id: 4,
    value: '50+',
    label: 'Countries Represented',
    description: 'Diverse student community'
  }
]
</script>

<style scoped>
.stats {
  padding: 6rem 0;
  background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
  color: var(--white);
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 3rem;
}

.stat-card {
  text-align: center;
  padding: 2rem;
}

.stat-value {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: var(--secondary-color);
}

.stat-label {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.stat-description {
  font-size: 1rem;
  opacity: 0.9;
}

@media (max-width: 768px) {
  .stats {
    padding: 4rem 0;
  }
  
  .stats-grid {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 2rem;
  }
  
  .stat-value {
    font-size: 2.5rem;
  }
}
</style>
