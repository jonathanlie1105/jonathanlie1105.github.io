<script setup lang="ts">
import BarrierIcon from './icons/IconBarrier.vue'

import Button from '@/core-ui/MyButton.vue'
import contacts from '@/constants/contacts'

function onClickSeeCV() {
  window.open(contacts.cv, '_blank')
}

function onClickContactMe() {
  window.open(`${contacts.email}?subject=Consultation Request`)
}
</script>

<template>
  <div class="greetings">
    <h1 class="green">Hello! I'm Jonathan</h1>
    <h2><BarrierIcon /> UNDER DEVELOPMENT <BarrierIcon /></h2>
    <br />
    <h3>In the meantime, please check out the summary about me.</h3>
    <br />
    <div class="btn-container">
      <Button @click="onClickSeeCV" type="info">See My CV</Button>
      <Button @click="onClickContactMe" type="warning">Get Consultation</Button>
    </div>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h2 {
  font-size: 1.4rem;
  color: var(--vt-c-red);
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h2,
.greetings h3 {
  text-align: center;
}

.btn-container {
  display: flex;
  place-content: center;
  column-gap: calc(var(--section-gap) / 10);
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h2,
  .greetings h3 {
    text-align: left;
  }

  .btn-container {
    place-content: flex-start;
  }
}
</style>
