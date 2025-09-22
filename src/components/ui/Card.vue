<template>
  <div :class="cardClasses">
    <div v-if="$slots.header" class="card-header">
      <slot name="header" />
    </div>
    <div class="card-body">
      <slot />
    </div>
    <div v-if="$slots.footer" class="card-footer">
      <slot name="footer" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

interface Props {
  variant?: 'default' | 'primary' | 'secondary' | 'success' | 'danger' | 'warning' | 'info' | 'light' | 'dark'
  shadow?: 'none' | 'sm' | 'md' | 'lg'
  hover?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'default',
  shadow: 'sm',
  hover: false
})

const cardClasses = computed(() => {
  const classes = ['card']
  
  // Variant
  if (props.variant !== 'default') {
    classes.push(`border-${props.variant}`)
  }
  
  // Shadow
  if (props.shadow !== 'none') {
    classes.push(`shadow-${props.shadow}`)
  }
  
  // Hover effect
  if (props.hover) {
    classes.push('card-hover')
  }
  
  return classes.join(' ')
})
</script>

<style scoped>
.card-hover {
  transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
}

.card-hover:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15) !important;
}
</style>
