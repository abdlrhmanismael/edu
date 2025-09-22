<template>
  <button 
    :type="type" 
    :class="buttonClasses" 
    :disabled="disabled"
    @click="handleClick"
  >
    <slot />
  </button>
</template>

<script setup lang="ts">
import { computed } from 'vue'

interface Props {
  variant?: 'primary' | 'secondary' | 'success' | 'danger' | 'warning' | 'info' | 'light' | 'dark' | 'outline-primary' | 'outline-secondary'
  size?: 'sm' | 'md' | 'lg'
  type?: 'button' | 'submit' | 'reset'
  disabled?: boolean
  block?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'primary',
  size: 'md',
  type: 'button',
  disabled: false,
  block: false
})

const emit = defineEmits<{
  click: [event: MouseEvent]
}>()

const buttonClasses = computed(() => {
  const classes = ['btn']
  
  // Variant
  if (props.variant.startsWith('outline-')) {
    classes.push(`btn-outline-${props.variant.replace('outline-', '')}`)
  } else {
    classes.push(`btn-${props.variant}`)
  }
  
  // Size
  if (props.size !== 'md') {
    classes.push(`btn-${props.size}`)
  }
  
  // Block
  if (props.block) {
    classes.push('w-100')
  }
  
  return classes.join(' ')
})

const handleClick = (event: MouseEvent) => {
  if (!props.disabled) {
    emit('click', event)
  }
}
</script>

<style scoped>
.btn-primary {
  background-color: #1e40af;
  border-color: #1e40af;
  color: white;
  font-weight: 600;
  font-size: 1rem;
  padding: 0.75rem 2rem;
  border-radius: 50px;
  transition: all 0.2s ease;
}

.btn-primary:hover {
  background-color: #1d4ed8;
  border-color: #1d4ed8;
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(30, 64, 175, 0.3);
}

.btn-lg {
  font-size: 1.1rem;
  padding: 0.875rem 2.5rem;
}
</style>