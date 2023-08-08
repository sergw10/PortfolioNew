<template>
  <section class="main-section">

    <div class="bottom-shadow">
      <h2>Works</h2>
    </div>

    <div class="works-list">
      <template class="works-list" v-for="(item) in realWorks" :key="realWorks.length">
        <div class="work-preview">
          <a target="_blank" :href="item.link">
            <img :src="`src/assets/images/preview_${item.jpgNumber}.jpg`" alt="work preview">
          </a>
        </div>
      </template>

      <template class="works-list" v-for="(item) in emailWorks" :key="realWorks.length">
        <div class="work-preview">
          <a target="_blank" :href="`works/${item.name}/index.html`">
            <img :src="`src/assets/images/preview_${item.jpgNumber}.jpg`" alt="work preview">
          </a>
        </div>
      </template>

      <template class="works-list" v-for="(item) in allWorks" :key="allWorks.length">
        <div class="work-preview">
          <a target="_blank" :href="`works/${item.name}/index.html`">
            <img :src="`src/assets/images/preview_${item.jpgNumber}.jpg`" alt="work preview">
          </a>
        </div>
      </template>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import { AllWorks, RealWorks } from './interface'

const emailWorks: AllWorks = reactive([
  {jpgNumber: 12, name: 'broochy'}
])

const realWorks: RealWorks = reactive([
  {jpgNumber: 11, link: 'http://sabon.com.ua/'},
  {jpgNumber: 111, link: 'http://krovati-soft.sabon.com.ua/'},
  {jpgNumber: 7, link: 'https://www.facebook.com/fartukinua/'},
  {jpgNumber: 13, link: 'http://www.paddocksnewbridge.ie/', oldLink: 'http://paddocksnewbridge.com/'},
  {jpgNumber: 18, link: 'http://castlevernon.ie/'},
  {jpgNumber: 19, link: 'http://www.dneprometiz.com/'},
  {jpgNumber: 20, link: 'https://ambisafe.com/', oldLink: 'http://armorceramics.co/'},
  {jpgNumber: 21, link: 'https://www.youtube.com/watch?v=xKwslbv8uaI', oldLink: 'https://ico.orderbook.io/'}
])

const allWorks: AllWorks = reactive([
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
])
</script>

<style lang="scss">
.works-wrapper {
  margin: 20px 0;
  text-align: center;
}

.work-preview {
  transition: .25s;
  cursor: pointer;
  width: 30%;
  padding: 8px;
  margin: 1% 1% 2%;
  display: inline-block;
  vertical-align: top;
  border-radius: 4px;
  line-height: 0;
  -webkit-box-shadow: 1px 1px 12px 1px rgba(0,0,0,0.2);
  -moz-box-shadow: 1px 1px 12px 1px rgba(0,0,0,0.2);
  box-shadow: 1px 1px 12px 1px rgba(0,0,0,0.2);

  &:hover {
    transform: scale(1.08);
  }

  a {
    width: 100%;
    height: 100%;
    line-height: 0;
    display: inline-block;

    img {
      width: 100%;
      height: 100%;
      -o-object-fit: contain;
      object-fit: contain;
    }
  }
}

/* Responsive */
@media screen and ( max-width: 1370px ) {
  .work-preview {
    width: 47%;
    -webkit-box-shadow: 1px 1px 12px 1px rgba(0,0,0,.3);
    -moz-box-shadow: 1px 1px 12px 1px rgba(0,0,0,.3);
    box-shadow: 1px 1px 12px 1px rgba(0,0,0,.3);
  }
}

@media screen and ( max-width: 900px ) {
  .work-preview {
    width: 47%;
    margin: 2% 1%;
  }
}

@media screen and ( max-width: 725px ) {
  .work-preview {
    width: 400px;
    margin: 3% 1%;
  }
}

@media screen and ( max-width: 530px ) {
  .work-preview {
    height: auto;

    &:first-of-type {
      margin-top: 0;
    }
  }
}

@media screen and ( max-width: 470px ) {
  .work-preview {
    width: 98%;
    margin: 4% 1%;
  }
}
</style>
