<template>
  <header class="sidebar">

    <div class="portfolio__profile-img-wrapper">
      <img src="../assets/images/user.jpg" title="Rubezhin Sergey" alt="portfolio-foto">
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
          <img src="../assets/images/phone-icon.png" title="phone" alt="phone-icon">
          <span>
            <a href="tel:+380633671084">+38 (063) 367 10 84</a>
          </span>
        </li>
        <li>
          <img src="../assets/images/mail-icon.png" title="mail" alt="mail-icon">
          <span>
            <a href="mailto:sergw100@gmail.com">sergw100@gmail.com</a>
          </span>
        </li>
        <li>
          <img src="../assets/images/skype-icon.png" title="skype" alt="skype-icon">
          <span>
            <a href="skype:sergw10?call">sergw10</a>
          </span>
        </li>
      </ul>

      <ul class="portfolio__profile-social-links">
        <li>
          <a target="_blank" href="https://www.linkedin.com/in/sergey-rubezhin-82940a124/">
            <img src="../assets/images/linked-icon-36.png" title="linkedin" alt="social-icon-linkedin">
          </a>
        </li>
        <li>
          <a target="_blank" href="https://www.facebook.com/profile.php?id=100000175581408">
            <img src="../assets/images/fb-icon-36.png" title="facebook" alt="social-icon-fb">
          </a>
        </li>
        <li>
          <a target="_blank" href="https://github.com/sergw10">
            <img src="../assets/images/github-icon-white-36.png" title="github" alt="social-icon-github">
          </a>
        </li>
      </ul>
    </section>

    <section class="portfolio__profile-know-languages">

      <h2>Languages</h2>

      <div class="grey-line"></div>

      <template v-for="(item) in languagesList" :key="languagesList.length">
        <p>{{ item.language }} - {{ item.level }}</p>
      </template>

    </section>
  </header>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import type { LanguagesList } from '@/types/types'

const languagesList = reactive<LanguagesList[]> ([
  {language: 'English', level: 'Intermediate'},
  {language: 'Ukrainian', level: 'Native'},
  {language: 'Russian', level: 'Native'},
  {language: 'Polish', level: 'Basic'}
]);

</script>

<style lang="scss" scoped>

.sidebar {
  overflow: auto;
  position: fixed;
  top: 0;
  left: 0;
  width: 320px;
  height: 100%;
  background-color: #363b43;
  padding: 40px 15px 15px 15px;

  h1 {
    color: #62c3f5;
    font-size: 24px;
  }

  h2 {
    font-size: 18px;
    font-weight: 300;
    text-transform: uppercase;
    color: #ffffff;
    margin-bottom: 10px;
  }
}

.portfolio__profile-img-wrapper {
  width: 89px;
  height: 89px;
  margin: 0 auto 30px;
  border-radius: 50%;
  overflow: hidden;
  border: 4px white solid;

  img {
    width: 100%;
    height: 100%;
  }
}

.portfolio__profile-name {
  padding-top: 0;
  padding-bottom: 30px;
  text-align: center;

  p {
    margin-top: 10px;
    color: #ffffff;
    font-size: 18px;
  }
}

.portfolio__profile-contacts-wrapper {
  padding: 27px 0 25px;

  h2 {
    font-weight: 500;
  }
}

.portfolio__profile-main-contacts {

  img, span {
    display: inline-block;
    vertical-align: middle;
  }

  span {
    margin-left: 7px;
    padding: 10px 5px;
    color: #ffffff;
    font-weight: 300;
    font-size: 16px;

    a {
      color: inherit;
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }
  }
}

.portfolio__profile-social-links {
  margin: 23px 0;

  li:first-child {
    margin-left: 0;
  }

  li {
    margin: 0 4px;
    display: inline-block;
    vertical-align: top;

    a {

      img:hover {
        transform: scale(1.06);
      }
    }
  }
}

.portfolio__profile-know-languages {

  h2 {
    font-weight: 500;
  }

  p {
    font-size: 16px;
    font-weight: 300;
    color: #ffffff;
    padding: 10px 0 0;
  }
}

.portfolio__close {
  position: absolute;
  top: 10px;
  right: 10px;
  width: 35px;
  height: 35px;

  div {
    width: 29px;
    height: 3px;
    background-color: #ffffff;
    margin: 6px auto;

    &:first-child.active,
    &:nth-child(2).active {
      position: absolute;
      margin: 0;
    }

    &:first-child.active {
      transform: rotate(-225deg);
      top: 16px;
      left: 5px;
    }

    &:nth-child(2).active {
      transform: rotate(225deg);
      top: 16px;
      left: 5px;
    }
  }
}

.grey-line {
  width: 100%;
  margin-bottom: 15px;
  height: 2px;
  background-color: #43474f;
}

/* Responsive */
@media screen and ( max-width: 1500px ) {
  .sidebar {
    padding: 20px 5px 15px 25px;
  }

  .portfolio__profile-name {
    padding-bottom: 0;
  }

  .portfolio__profile-contacts-wrapper {
    padding: 30px 0 15px;
  }

  .portfolio__profile-social-links {
    margin: 10px 0 20px;
  }

  .grey-line {
    margin-bottom: 0;
  }
}

@media screen and ( max-width: 900px ) {

  .sidebar {
    width: 100%;
    position: relative;
    padding: 20px 25px 15px;

    .grey-line {
      display: none;
    }
  }

  .portfolio__profile-name {
    text-align: center;
  }

  .portfolio__profile-contacts-wrapper,
  .portfolio__profile-know-languages {
    width: 49%;
    display: inline-block;
    vertical-align: top;
    padding: 25px 0 5px;
    text-align: center;
    margin-top: 20px;

    h2 {
      margin: 0 auto 20px;
    }

    ul, p, h2 {
      width: 215px;
      display: inline-block;
      vertical-align: top;
      text-align: left;
    }
  }
}

@media screen and ( max-width: 530px ) {

.portfolio__profile-img-wrapper {
    width: 100px;
    height: 100px;
  }

.portfolio__profile-contacts-wrapper,
.portfolio__profile-know-languages {
    width: 100%;

    ul, p, h2 {
      display: block;
      margin: 0 auto;
      text-align: left;
    }

    h2 {
      margin-bottom: 15px;
      text-align: center;
    }
  }

.portfolio__profile-know-languages {
    margin-top: 10px;
    margin-bottom: 20px;
  }
}
</style>
