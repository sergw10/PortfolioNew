<style lang="scss" scoped>
@use "@/components/Works/worksStyle" as *;
</style>

<template>
  <section class="main-section">

    <div class="bottom-shadow">
      <h2>Works</h2>
    </div>

    <div class="works-list">
      <template v-for="(item, index) in realWorks" :key="index">
        <div class="work-preview">
          <a target="_blank" :href="item.link">
            <img :src="buildSrcForWorkPreviewImages(item.jpgNumber)" alt="work preview">
          </a>
        </div>
      </template>

      <template v-for="(item, index) in emailWorks" :key="index">
        <div class="work-preview">
          <a target="_blank" :href="buildHrefForWorkPreviewImages(item.name)">
            <img :src="buildSrcForWorkPreviewImages(item.jpgNumber)" alt="work preview">
          </a>
        </div>
      </template>

      <template v-for="(item, index) in allWorks" :key="index">
        <div class="work-preview">
          <a target="_blank" :href="buildHrefForWorkPreviewImages(item.name)">
            <img :src="buildSrcForWorkPreviewImages(item.jpgNumber)" alt="work preview">
          </a>
        </div>
      </template>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import { AllWorks, RealWorks } from '@/types/types'

const emailWorks = reactive<AllWorks[]>([
  {jpgNumber: 12, name: 'broochy'}
]);

const realWorks = reactive<RealWorks[]>([
  {jpgNumber: 11, link: 'http://sabon.com.ua/'},
  {jpgNumber: 111, link: 'http://krovati-soft.sabon.com.ua/'},
  {jpgNumber: 7, link: 'https://www.facebook.com/fartukinua/'},
  {jpgNumber: 13, link: 'http://www.paddocksnewbridge.ie/', oldLink: 'http://paddocksnewbridge.com/'},
  {jpgNumber: 18, link: 'http://castlevernon.ie/'},
  {jpgNumber: 19, link: 'http://www.dneprometiz.com/'},
  {jpgNumber: 20, link: 'https://ambisafe.com/', oldLink: 'http://armorceramics.co/'},
  {jpgNumber: 21, link: 'https://www.youtube.com/watch?v=xKwslbv8uaI', oldLink: 'https://ico.orderbook.io/'}
]);

const allWorks = reactive<AllWorks[]>([
  {jpgNumber: 1, name: 'take'},
  {jpgNumber: 2, name: 'daylite'},
  {jpgNumber: 3, name: 'cruise'},
  {jpgNumber: 4, name: 'design-lab'},
  {jpgNumber: 5, name: 'webMonster-landing'},
  {jpgNumber: 6, name: 'webMonster-mainSite'},
  {jpgNumber: 8, name: 'garant-service'},
  {jpgNumber: 9, name: 'mogo'},
  {jpgNumber: 10, name: 'smart-agency'},
  {jpgNumber: 16, name: 'ucgt'},
  {jpgNumber: 17, name: 'internet-shop'}
]);

function buildSrcForWorkPreviewImages (jpgNumber: number) {
  return `src/assets/images/preview_${jpgNumber}.jpg`
}

function buildHrefForWorkPreviewImages (itemName: string) {
  return `works/${itemName}/index.html`
}
</script>
