<template>
  <div class="ipp-logo" :class="resolvedSize">
    <img
      src="/IPP.png"
      alt="International Education Pathway Program logo"
      class="logo-image"
    />
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = withDefaults(
  defineProps<{
    size?: 'small' | 'medium' | 'large'
  }>(),
  {
    size: 'medium',
  },
)

const resolvedSize = computed(() => props.size)
</script>

<style scoped>
.ipp-logo {
  display: inline-flex;
  align-items: center;
  justify-content: flex-start;
}

.logo-image {
  display: block;
  width: auto;
  max-width: 100%;
  object-fit: contain;
  object-position: left center;
}

.ipp-logo.small .logo-image {
  height: 48px;
}

.ipp-logo.medium .logo-image {
  height: 72px;
}

.ipp-logo.large .logo-image {
  height: 108px;
}

@media (max-width: 768px) {
  .ipp-logo.small .logo-image {
    height: 42px;
  }

  .ipp-logo.medium .logo-image {
    height: 64px;
  }

  .ipp-logo.large .logo-image {
    height: 88px;
  }
}
</style>
