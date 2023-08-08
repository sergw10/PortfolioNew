<script setup lang="ts" xmlns="">
import { RouterLink, RouterView } from 'vue-router'
import InfoLeftPanel from './components/InfoLeftPanel.vue'
import Skills from './components/Skills.vue'
import Experience from './components/Experience.vue'
import Works from './components/Works/Works.vue'
</script>

<template>
  <main>
    <InfoLeftPanel></InfoLeftPanel>

    <Skills></Skills>

    <Experience></Experience>

    <Works></Works>
  </main>
</template>

<style lang="scss">
.main-section {
  padding: 0 15px 0 350px;

  h2 {
    font-size: 21px;
    font-weight: 600;
    text-transform: uppercase;
  }
}

/* Responsive for main Classes */
@media screen and ( max-width: 900px ) {
  .main-section {
    padding: 0 15px;
  }
}
</style>
