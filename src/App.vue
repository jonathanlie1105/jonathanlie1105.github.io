<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import MyContacts from './components/MyContacts.vue'
import MyServices from './components/MyServices.vue'
import RockPaperScissors from './components/RockPaperScissors.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Hi" class="logo" src="./assets/hi.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>

  <MyServices />

  <MyContacts />

  <footer>
    <RockPaperScissors />
  </footer>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  footer {
    grid-area: f;
    border: 0.06rem solid var(--color-border);
    border-radius: 8px;
    padding: 2rem 0;
    margin: 2rem 0;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
