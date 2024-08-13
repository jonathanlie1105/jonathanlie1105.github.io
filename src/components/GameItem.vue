<script setup lang="ts">
import { computed, inject, reactive, type Ref } from 'vue'

type Props = {
  onClick: () => void
  index: number
}

const { onClick, index } = defineProps<Props>()
function callback() {
  onClick()
}

const currentSelectedIndex = inject<Ref<number>>('selectedIdx')
const isSelected = computed(() => currentSelectedIndex?.value === index)
const classObject = reactive({
  selected: isSelected
})
</script>

<template>
  <div class="option" :class="classObject" @click="callback">
    <h2><slot name="name"></slot></h2>
    <slot name="icon"></slot>
  </div>
</template>

<style scoped>
.option {
  display: flex;
  flex-direction: column;
  place-content: center;
  place-items: center;
  border: 1px solid var(--color-border);
  border-radius: 8px;
  padding: 0 10px;
  transition: 0.5s;
}
.selected {
  border-color: var(--color-highlight);
}
</style>
