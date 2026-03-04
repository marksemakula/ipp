<template>
  <section id="about" class="about">
    <div class="container">
      <div class="about-content">
        <h2 class="gradient-title">Transform Your Future</h2>
        <p class="lead-text">
          IPP connects ambitious students with world-class universities through personalized pathway programs.
        </p>
        
        <div class="features-grid">
          <div class="feature-card">
            <div class="feature-icon">🎓</div>
            <h4>Excellence</h4>
          </div>
          <div class="feature-card">
            <div class="feature-icon">🌍</div>
            <h4>Global</h4>
          </div>
          <div class="feature-card">
            <div class="feature-icon">👥</div>
            <h4>Support</h4>
          </div>
          <div class="feature-card">
            <div class="feature-icon">✨</div>
            <h4>Success</h4>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped>
.about {
  padding: 6rem 0;
  background: transparent;
}

.about-content {
  max-width: 900px;
  margin: 0 auto;
  text-align: center;
}

.gradient-title {
  background: linear-gradient(135deg, #ffd89b 0%, #19547b 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  font-size: 3rem;
  margin-bottom: 1.5rem;
}

.lead-text {
  font-size: 1.5rem;
  color: rgba(255, 255, 255, 0.9);
  line-height: 1.8;
  margin-bottom: 3rem;
  font-weight: 300;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 2rem;
}

.feature-card {
  padding: 2.5rem 2rem;
  background: var(--glass-bg);
  backdrop-filter: blur(20px);
  border: 1px solid var(--glass-border);
  border-radius: 1.5rem;
  transition: all 0.4s ease;
  position: relative;
}

.feature-card:hover {
  transform: translateY(-10px) rotate(-2deg);
  box-shadow: 0 20px 40px rgba(99, 102, 241, 0.3);
}

.feature-icon {
  font-size: 3.5rem;
  margin-bottom: 1rem;
  display: inline-block;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

.feature-card h4 {
  color: var(--text-dark);
  font-size: 1.25rem;
  font-weight: 700;
  margin: 0;
}

@media (max-width: 768px) {
  .about {
    padding: 4rem 0;
  }
  
  .gradient-title {
    font-size: 2rem;
  }
  
  .lead-text {
    font-size: 1.2rem;
  }
  
  .features-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
}
</style>
