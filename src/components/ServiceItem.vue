<script setup lang="ts">
type Props = {
  onClick: () => void
}

const { onClick } = defineProps<Props>()
</script>

<template>
  <div class="container" @click="onClick">
    <h3><slot name="title"></slot></h3>
    <!-- <h4><slot name="subtitle"></slot></h4> -->
    <p><slot name="description"></slot></p>
    <span>Click to Request!</span>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  row-gap: 0.6rem;
  border: 0.06rem solid var(--color-border);
  border-radius: 1rem;
  padding: 1rem;

  &:hover {
    cursor: pointer;
    background-color: var(--color-background-soft);
    transition: 0.5ms;
  }
}

h3 {
  text-align: center;
  color: var(--vt-c-green);
}

p {
  text-align: justify;
}

span {
  text-align: end;
  font-size: small;
  color: var(--color-heading);
}
</style>
