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
</script>

<template>
  <div class="left">
    <h2 class="green">Tech stack I've used</h2>
    <div class="wrapper">
      <a href="https://expo.dev/"><IconExpo /></a>
      <a target="_blank" href="https://graphql.org/"><IconGraphQL /></a>
      <a target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript">
        <IconJavascript />
      </a>
      <a target="_blank" href="https://nextjs.org/"><IconNext /></a>
      <a target="_blank" href="https://www.postgresql.org/"><IconPostgreSQL /></a>
      <a target="_blank" href="https://www.prisma.io/"><IconPrisma /></a>
      <a target="_blank" href="https://react.dev/"><IconReact /></a>
      <a target="_blank" href="https://tailwindcss.com/"><IconTailwind /></a>
      <a target="_blank" href="https://www.typescriptlang.org/"><IconTypescript /></a>
      <a target="_blank" href="https://vuejs.org/"><IconVue /></a>
    </div>
  </div>
  <div class="right">
    <h2 class="green">See my social media</h2>
    <div class="wrapper">
      <a target="_blank" href="https://www.linkedin.com/in/jonathanlie1105/"><IconLinkedIn /></a>
      <a target="_blank" href="https://github.com/jonathanlie1105"><IconGithub /></a>
      <a target="_blank" href="mailto:joliekidd@gmail.com"><IconGmail /></a>
      <a target="_blank" href="https://wa.me/6282298721226"><IconWhatsapp /></a>
      <a target="_blank" href="https://www.facebook.com/jonathan.lie.54/"><IconFacebook /></a>
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
