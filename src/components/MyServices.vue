<script setup lang="ts">
import services from '@/constants/services'
import contacts from '@/constants/contacts'

import ServiceItem from './ServiceItem.vue'

const { softwareEngineering, onDemandSolutions, uiUxDesign } = services

function emailWithSubject(subject: string) {
  window.open(`${contacts.email}?subject=${subject}`)
}
</script>

<template>
  <div class="root">
    <h2>What can I do for you?</h2>
    <div class="service-container">
      <ServiceItem :on-click="() => emailWithSubject('Request Software Development')">
        <template #title>{{ softwareEngineering.title }}</template>
        <template #subtitle>{{ softwareEngineering.subtitle }}</template>
        <template #description>{{ softwareEngineering.description }}</template>
      </ServiceItem>

      <ServiceItem :on-click="() => emailWithSubject('Request On Demand Solutions')">
        <template #title>{{ onDemandSolutions.title }}</template>
        <template #subtitle>{{ onDemandSolutions.subtitle }}</template>
        <template #description>{{ onDemandSolutions.description }}</template>
      </ServiceItem>

      <ServiceItem :on-click="() => emailWithSubject('Request UI/UX Design')">
        <template #title>{{ uiUxDesign.title }}</template>
        <template #subtitle>{{ uiUxDesign.subtitle }}</template>
        <template #description>{{ uiUxDesign.description }}</template>
      </ServiceItem>
    </div>
  </div>
</template>

<style scoped>
.root {
  grid-area: c;
  display: flex;
  flex-direction: column;
  place-content: center;
  row-gap: calc(var(--section-gap) / 8);

  margin: 3rem 0;
}

.service-container {
  display: flex;
  flex-direction: column;
  row-gap: calc(var(--section-gap) / 8);
}

h2 {
  text-align: center;
  color: var(--color-highlight);
}

@media (min-width: 1024px) {
  .service-container {
    flex-direction: row;
    column-gap: calc(var(--section-gap) / 8);
  }
}
</style>
