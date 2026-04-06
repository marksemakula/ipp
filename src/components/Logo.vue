<template>
  <div class="ipp-logo" :class="size">
    <div class="logo-vertical">
      <span class="letter">I</span>
      <span class="letter">P</span>
      <span class="letter">P</span>
    </div>
    <div class="logo-horizontal">
      <span class="line">International Education</span>
      <span class="line">Pathway Program</span>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  size?: 'small' | 'medium' | 'large'
}>()
</script>

<style scoped>
.ipp-logo {
  display: flex;
  align-items: center;
  gap: 0;
}

.logo-vertical {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  transform: rotate(-90deg);
  transform-origin: center;
}

.logo-vertical .letter {
  font-weight: 700;
  font-family: 'Source Sans 3', 'Ubuntu', sans-serif;
  letter-spacing: 0;
  display: flex;
  align-items: center;
  flex-shrink: 0;
}

.logo-horizontal {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 0.1rem;
}

.logo-horizontal .line {
  font-weight: 500;
  font-family: 'Ubuntu', sans-serif;
  white-space: nowrap;
  display: flex;
  align-items: center;
}

/* Small size (for header/navbar) */
.ipp-logo.small .logo-vertical {
  width: 1.8rem;
  height: 1.2rem;
  min-width: 1.8rem;
}

.ipp-logo.small .logo-vertical .letter {
  font-size: 0.9rem;
  line-height: 1;
}

.ipp-logo.small .logo-horizontal {
  height: 1.8rem;
}

.ipp-logo.small .logo-horizontal .line {
  font-size: 0.7rem;
  line-height: 1.3;
  height: 0.9rem;
}

/* Medium size (default) */
.ipp-logo.medium .logo-vertical,
.ipp-logo:not(.small):not(.large) .logo-vertical {
  width: 2.3rem;
  height: 1.5rem;
  min-width: 2.3rem;
}

.ipp-logo.medium .logo-vertical .letter,
.ipp-logo:not(.small):not(.large) .logo-vertical .letter {
  font-size: 1.1rem;
  line-height: 1;
}

.ipp-logo.medium .logo-horizontal,
.ipp-logo:not(.small):not(.large) .logo-horizontal {
  height: 2.3rem;
}

.ipp-logo.medium .logo-horizontal .line,
.ipp-logo:not(.small):not(.large) .logo-horizontal .line {
  font-size: 0.85rem;
  line-height: 1.3;
  height: 1.15rem;
}

/* Large size (for footer) */
.ipp-logo.large .logo-vertical {
  width: 3rem;
  height: 2rem;
  min-width: 3rem;
}

.ipp-logo.large .logo-vertical .letter {
  font-size: 1.4rem;
  line-height: 1;
}

.ipp-logo.large .logo-horizontal {
  height: 3rem;
}

.ipp-logo.large .logo-horizontal .line {
  font-size: 1.1rem;
  line-height: 1.3;
  height: 1.5rem;
}

/* Color variants */
.ipp-logo .logo-vertical {
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* For footer (white theme) */
.footer .ipp-logo .logo-vertical {
  background: white;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.footer .ipp-logo .logo-horizontal .line {
  color: white;
}

@media (max-width: 768px) {
  .ipp-logo.small .logo-vertical {
    width: 2.5rem;
    height: 1rem;
    min-width: 2.5rem;
  }
  
  .ipp-logo.small .logo-vertical .letter {
    font-size: 1rem;
    line-height: 1;
  }
  
  .ipp-logo.small .logo-horizontal {
    height: 1.5rem;
  }
  
  .ipp-logo.small .logo-horizontal .line {
    font-size: 0.55rem;
    line-height: 1.2;
    height: 0.7rem;
  }
}
</style>
