<template>
  <section id="testimonials" class="testimonials">
    <div class="container">
      <div class="section-header">
        <h2 class="gradient-title">Success Stories</h2>
      </div>
      
      <div class="testimonials-grid">
        <div v-for="testimonial in testimonials" :key="testimonial.id" class="testimonial-card">
          <div class="quote-icon">"</div>
          <p class="testimonial-text">{{ testimonial.text }}</p>
          <div class="testimonial-author">
            <div class="author-name">{{ testimonial.name }}</div>
            <div class="author-details">{{ testimonial.details }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Testimonial {
  id: number
  text: string
  name: string
  details: string
}

const testimonials: Testimonial[] = [
  {
    id: 1,
    text: 'IPP transformed my academic journey. The support was incredible!',
    name: 'Sarah J.',
    details: 'UK University'
  },
  {
    id: 2,
    text: 'Best decision I ever made. The pathway program was exceptional.',
    name: 'Ahmed H.',
    details: 'London Business School'
  },
  {
    id: 3,
    text: 'Made lifelong friends and achieved my dreams. Thank you IPP!',
    name: 'Maria R.',
    details: 'University of Toronto'
  }
]
</script>

<style scoped>
.testimonials {
  padding: 6rem 0;
  background: transparent;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.gradient-title {
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  font-size: 3rem;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
}

.testimonial-card {
  background: var(--glass-bg);
  backdrop-filter: blur(20px);
  border: 1px solid var(--glass-border);
  padding: 2.5rem;
  border-radius: 1.5rem;
  position: relative;
  transition: all 0.4s ease;
}

.testimonial-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(236, 72, 153, 0.3);
}

.quote-icon {
  font-size: 4rem;
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1;
  margin-bottom: 1rem;
  opacity: 0.5;
}

.testimonial-text {
  font-size: 1.1rem;
  color: var(--text-light);
  line-height: 1.7;
  margin-bottom: 1.5rem;
  font-style: italic;
}

.testimonial-author {
  border-top: 1px solid var(--glass-border);
  padding-top: 1rem;
}

.author-name {
  font-weight: 700;
  color: var(--text-dark);
  margin-bottom: 0.25rem;
  font-size: 1.1rem;
}

.author-details {
  font-size: 0.875rem;
  color: var(--text-light);
}

@media (max-width: 768px) {
  .testimonials {
    padding: 4rem 0;
  }
  
  .gradient-title {
    font-size: 2rem;
  }
  
  .testimonials-grid {
    grid-template-columns: 1fr;
  }
}
</style>
