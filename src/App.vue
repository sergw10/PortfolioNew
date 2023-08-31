<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import InfoLeftPanel from './components/InfoLeftPanel/InfoLeftPanel.vue'
import Skills from './components/Skills/Skills.vue'
import ExperienceView from './components/MyExperience/ExperienceView.vue'
import Works from './components/Works/Works.vue'


// import { useI18n } from "vue-i18n";
// import HelloWorld from "./components/HelloWorld.vue";
// import LocaleSelect from "./components/LocaleSelect.vue";
// import links from "@/data/links.json";

// const { t } = useI18n();
//
// const getImgURL = (src: string) => {
//   return new URL(`./assets/svg/${src}.svg`, import.meta.url).href;
// };
</script>

<!--<template>-->
<!--  <locale-select></locale-select>-->
<!--  <a-->
<!--    v-for="{ alt, src, href } in links"-->
<!--    :key="alt"-->
<!--    class="logo-link"-->
<!--    :href="href"-->
<!--  >-->
<!--    <img class="logo" :alt="alt" :src="getImgURL(src)" />-->
<!--  </a>-->
<!--  <HelloWorld :msg="t('welcome')" />-->
<!--</template>-->

<template>

  <main>
    <InfoLeftPanel></InfoLeftPanel>

    <Skills></Skills>

    <ExperienceView></ExperienceView>

    <Works></Works>
  </main>

</template>

<style lang="scss">
@use "@/styles/boot.scss" as *;
</style>
