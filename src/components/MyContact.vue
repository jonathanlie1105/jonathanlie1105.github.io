<script setup lang="ts">
import IconFacebook from './icons/IconFacebook.vue'
import IconGithub from './icons/IconGithub.vue'
import IconGmail from './icons/IconGmail.vue'
import IconLinkedIn from './icons/IconLinkedIn.vue'
import IconWhatsapp from './icons/IconWhatsapp.vue'
import IconExpo from './icons/IconExpo.vue'
import IconGraphQL from './icons/IconGraphQL.vue'
import IconJavascript from './icons/IconJavascript.vue'
import IconNext from './icons/IconNext.vue'
import IconPostgreSQL from './icons/IconPostgreSQL.vue'
import IconPrisma from './icons/IconPrisma.vue'
import IconReact from './icons/IconReact.vue'
import IconTailwind from './icons/IconTailwind.vue'
import IconTypescript from './icons/IconTypescript.vue'
import IconVue from './icons/IconVue.vue'

import contacts from '@/constants/contacts'
import techStacks from '@/constants/techStacks'

const { linkedIn, github, email, whatsApp, faceBook } = contacts
const { javascript, typescript, react, expo, postgreSql, graphQl, prisma, nextJs, tailwind, vue } =
  techStacks
</script>

<template>
  <div class="left">
    <h2 class="green">Tech stack I've used</h2>
    <div class="wrapper">
      <a target="_blank" :href="javascript"><IconJavascript /></a>
      <a target="_blank" :href="typescript"><IconTypescript /></a>
      <a target="_blank" :href="react"><IconReact /></a>
      <a target="_blank" :href="expo"><IconExpo /></a>
      <a target="_blank" :href="postgreSql"><IconPostgreSQL /></a>
      <a target="_blank" :href="graphQl"><IconGraphQL /></a>
      <a target="_blank" :href="prisma"><IconPrisma /></a>
      <a target="_blank" :href="nextJs"><IconNext /></a>
      <a target="_blank" :href="tailwind"><IconTailwind /></a>
      <a target="_blank" :href="vue"><IconVue /></a>
    </div>
  </div>
  <div class="right">
    <h2 class="green">See my social media</h2>
    <div class="wrapper">
      <a target="_blank" :href="linkedIn"><IconLinkedIn /></a>
      <a target="_blank" :href="github"><IconGithub /></a>
      <a target="_blank" :href="email"><IconGmail /></a>
      <a target="_blank" :href="whatsApp"><IconWhatsapp /></a>
      <a target="_blank" :href="faceBook"><IconFacebook /></a>
    </div>
  </div>
</template>

<style scoped>
.left {
  display: flex;
  flex-direction: column;
  grid-area: d;
  row-gap: calc(var(--section-gap) / 10);
}
.right {
  display: flex;
  flex-direction: column;
  grid-area: e;
  row-gap: calc(var(--section-gap) / 10);
}
.wrapper {
  display: flex;
  flex-wrap: wrap;
  column-gap: calc(var(--section-gap) / 10);
}

@media (min-width: 1024px) {
  .wrapper {
    width: 75%;
  }
}
</style>
