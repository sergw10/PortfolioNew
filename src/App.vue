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
</style>
