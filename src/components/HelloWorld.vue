<script setup lang="ts">
import { useI18n } from "vue-i18n";

defineProps<{ msg: string }>();

const { t } = useI18n();
</script>

<template>
  <h1>{{ msg }}</h1>
  <p>
    {{ t("setup") }}
    <a href="https://code.visualstudio.com/">VSCode</a>
    +
    <a href="https://github.com/johnsoncodehk/volar">Volar</a>
    +
    <a href="https://github.com/lokalise/i18n-ally">i18n-ally</a>
  </p>

  <p>
    {{ t("see-readme.see") }} <code>README.md</code>
    {{ t("see-readme.more-info") }}
  </p>

  <h2>{{ t("docs") }}</h2>
  <p>
    <a href="https://vitejs.dev/guide/features.html"> Vite </a>
    |
    <a href="https://v3.vuejs.org/">Vue 3</a>
    |
    <a href="https://storybook.js.org/docs/vue/get-started/introduction">
      Storybook
    </a>
    |
    <a href="https://www.typescriptlang.org/docs/"> Typescript </a>
    |
    <a href="https://eslint.org/docs/user-guide/"> ESLint </a>
    |
    <a href="https://prettier.io/docs/en/index.html"> Prettier </a>
  </p>

  <h3>{{ t("check-reactivity") }}</h3>

  <p>
    {{ t("hmr.edit") }}
    <code>components/HelloWorld.vue</code>
    {{ t("hmr.test") }}
  </p>
</template>

<style lang="scss" scoped>
/*@use "@/styles/functions/color" as *;*/

</style>
