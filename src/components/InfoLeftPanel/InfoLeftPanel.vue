<style lang="scss" scoped>
@use '@/components/InfoLeftPanel/infoLeftPanelStyle' as *;
</style>

<template>
  <header class="sidebar">

    <div class="portfolio__profile-img-wrapper">
      <img src="../../assets/images/user.jpg" title="Rubezhin Sergey" alt="portfolio-foto">
    </div>

    <section class="portfolio__profile-name">
      <h1>Rubezhin Sergey</h1>
      <p>Front-end developer</p>
    </section>

    <section class="portfolio__profile-contacts-wrapper">
      <h2>Contacts</h2>
      <div class="grey-line"></div>
      <ul class="portfolio__profile-main-contacts">
        <li>
          <img src="../../assets/images/phone-icon.png" title="phone" alt="phone-icon">
          <span>
            <a href="tel:+380633671084">+38 (063) 367 10 84</a>
          </span>
        </li>
        <li>
          <img src="../../assets/images/mail-icon.png" title="mail" alt="mail-icon">
          <span>
            <a href="mailto:sergw100@gmail.com">sergw100@gmail.com</a>
          </span>
        </li>
        <li>
          <img src="../../assets/images/skype-icon.png" title="skype" alt="skype-icon">
          <span>
            <a href="skype:sergw10?call">sergw10</a>
          </span>
        </li>
      </ul>

      <ul class="portfolio__profile-social-links">
        <li>
          <a target="_blank" href="https://www.linkedin.com/in/sergey-rubezhin-82940a124/">
            <img src="../../assets/images/linked-icon-36.png" title="linkedin" alt="social-icon-linkedin">
          </a>
        </li>
        <li>
          <a target="_blank" href="https://www.facebook.com/profile.php?id=100000175581408">
            <img src="../../assets/images/fb-icon-36.png" title="facebook" alt="social-icon-fb">
          </a>
        </li>
        <li>
          <a target="_blank" href="https://github.com/sergw10">
            <img src="../../assets/images/github-icon-white-36.png" title="github" alt="social-icon-github">
          </a>
        </li>
      </ul>
    </section>

    <section class="portfolio__profile-know-languages">

      <h2>Languages</h2>

      <div class="grey-line"></div>

      <template v-for="(item, index) in languagesList" :key="index">
        <p>{{ item.language }} - {{ item.level }}</p>
      </template>

    </section>
  </header>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import { LanguagesList } from '@/types/types'

const languagesList = reactive<LanguagesList[]> ([
  {language: 'English', level: 'Intermediate'},
  {language: 'Ukrainian', level: 'Native'},
  {language: 'Russian', level: 'Native'},
  {language: 'Polish', level: 'Basic'}
]);
</script>
