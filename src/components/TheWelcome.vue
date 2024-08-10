<script setup lang="ts">
import WelcomeItem from './WelcomeItem.vue'
import EngineerIcon from './icons/IconEngineer.vue'
import CybersecurityIcon from './icons/IconCybersecurity.vue'
import PianistIcon from './icons/IconPianist.vue'
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <EngineerIcon />
    </template>
    <template #heading>Software Engineer</template>

    With over four years of experience, I have completed various projects using the PERN stack
    (PostgreSQL, Express.js, React, Node.js) with TypeScript. I am currently working as a full-time
    Software Engineer at
    <a href="https://www.kodefox.com/" target="_blank">KodeFox, Inc</a>.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <CybersecurityIcon />
    </template>
    <template #heading>Cybersecurity Enthusiast</template>

    I have a bachelor's degree in Computer Science with a focus on Cybersecurity. I also obtained a
    certification in 2020. Although I am currently a Software Engineer, I remain passionate about
    cybersecurity and related fields.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <PianistIcon />
    </template>
    <template #heading>Musician</template>

    I started my music journey as a hobby and have always enjoyed playing the piano. I am now at
    Grade Four at my local music school. Additionally, I play piano at my local church services.
  </WelcomeItem>
</template>
