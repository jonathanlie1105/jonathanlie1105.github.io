<script setup lang="ts">
type Props = {
  type?: 'warning' | 'danger' | 'success' | 'info' | 'default'
  disabled?: boolean
}
withDefaults(defineProps<Props>(), { type: 'default', disabled: false })

const emit = defineEmits(['click'])
function callback(e: MouseEvent) {
  emit('click', e)
}
</script>

<template>
  <button :class="type" :disabled="disabled" @click="callback($event)">
    <slot></slot>
  </button>
</template>

<style scoped>
button {
  padding: 0.6rem 1.25rem;
  border: 1px solid var(--color-border);
  border-radius: 0.5rem;
  background-color: var(--color-background);
  color: var(--color-heading);
  cursor: pointer;
  font-weight: bold;
  transition-duration: 0.2s;
  &:hover {
    background-color: var(--color-background-soft);
  }
  &[disabled] {
    cursor: not-allowed;
  }
  &.danger {
    border-color: var(--vt-c-red);
    &:hover {
      background-color: var(--vt-c-red);
    }
  }
  &.success {
    border-color: var(--vt-c-green);
    &:hover {
      background-color: var(--vt-c-green);
    }
  }
  &.info {
    border-color: var(--vt-c-blue);
    &:hover {
      background-color: var(--vt-c-blue);
    }
  }
  &.warning {
    border-color: var(--vt-c-yellow);
    &:hover {
      background-color: var(--vt-c-yellow);
    }
  }
}
</style>
