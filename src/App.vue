<script setup lang="ts">
// import { RouterLink, RouterView } from 'vue-router'

$(document).ready(() => {
  setTimeout( function () {
    const arrNum = [0, 80, 82, 65, 87, 80, 63],
      speed = 4900;

    for (let i = 1; i <= 6 ; i++ ) {

      $('#num_' + i).animate({ num: arrNum[i] - 1/* - begin */ }, {
        duration: speed,
        step: function (num){
          this.innerHTML = (num + 1).toFixed(0) + '%';
        }
      });
    }
  }, 1000);

//-------------------------------------

  for (let j = 0; j < 24; j++) {
    $('.percent-lines').append('<div></div>');
  }

  const arrOfGreyLines = [4,4,7,3,4,8],
    linesWrap = document.querySelectorAll('.percent-lines');

  for (let i = 0; i < 6; i++) {

    let arrAllLines = linesWrap[i].childNodes,
      numGreyLines = arrOfGreyLines[i],
      arrAllLinesCopy = Array.prototype.slice.call(arrAllLines),
      arrOfGreyLinesChange = arrAllLinesCopy.slice(-numGreyLines);

    for (let l = 0; l < numGreyLines; l++) {
      arrOfGreyLinesChange[l].style.backgroundColor = '#e7e7e7';
    }
  }
})
</script>

<template>
  <main>

    <aside class="portfolio__profile-info">
      <figure>
        <div class="portfolio__profile-img-wrapper">
          <img src="images/user.png" title="Rubezhin Sergey" alt="portfolio-foto">
        </div>
      </figure>

      <section class="portfolio__profile-name">
        <h1>Rubezhin Sergey</h1>
        <p>Front-end developer</p>
      </section>

      <section class="portfolio__profile-contacts-wrapper">
        <h2>Contacts</h2>
        <div class="grey-line"></div>
        <ul class="portfolio__profile-main-contacts">
          <li>
            <img src="images/phone-icon.png" title="phone" alt="phone-icon">
            <span>
              <a href="tel:+380633671084">+38 (063) 367 10 84</a>
            </span>
          </li>
          <li>
            <img src="images/mail-icon.png" title="mail" alt="mail-icon">
            <span>
              <a href="mailto:sergw100@gmail.com">sergw100@gmail.com</a>
            </span>
          </li>
          <li>
            <img src="images/skype-icon.png" title="skype" alt="skype-icon">
            <span>
              <a href="skype:sergw10?call">sergw10</a>
            </span>
          </li>
        </ul>
        <ul class="portfolio__profile-social-links">
          <li>
            <a target="_blank" href="https://www.linkedin.com/in/sergey-rubezhin-82940a124/">
              <img src="images/linked-icon-36.png" title="linkedin" alt="social-icon-linkedin">
            </a>
          </li>
          <li>
            <a target="_blank" href="https://www.facebook.com/profile.php?id=100000175581408">
              <img src="images/fb-icon-36.png" title="facebook" alt="social-icon-fb">
            </a>
          </li>
          <li>
            <a target="_blank" href="https://github.com/sergw10">
              <img src="images/github-icon-white-36.png" title="github" alt="social-icon-github">
            </a>
          </li>
        </ul>
      </section>

      <section class="portfolio__profile-know-languges">
        <h2>Languages</h2>
        <div class="grey-line"></div>
        <p>English - intermediate</p>
        <p>Ukrainian - native</p>
        <p>Russian - native</p>
        <p>Polski - basic</p>
      </section>
    </aside>

    <section class="main-section portfolio__skills">
      <div class="bottom-shadow">
        <!-- <p class="alert-message">Page is currently under development!</p> -->
        <h2>Skills</h2>
      </div>
      <ul class="profile__skills-wrapper">
        <li class="ellipse-wrapper html">
          <div class="skill__ellipse-white">
            <div class="percent-lines">

            </div>
          </div>
          <div class="skill html-skill"></div>
          <p class="skill__percentage-wrap" id="num_1"></p>
          <p>HTML</p>
        </li>
        <li class="ellipse-wrapper css">
          <div class="skill__ellipse-white">
            <div class="percent-lines">

            </div>
          </div>
          <div class="skill css-skill"></div>
          <p class="skill__percentage-wrap" id="num_2"></p>
          <p>CSS</p>
        </li>
        <li class="ellipse-wrapper js">
          <div class="skill__ellipse-white">
            <div class="percent-lines">

            </div>
          </div>
          <div class="skill js-skill"></div>
          <p class="skill__percentage-wrap" id="num_3"></p>
          <p>JS</p>
        </li>
        <li class="ellipse-wrapper sass">
          <div class="skill__ellipse-white">
            <div class="percent-lines">

            </div>
          </div>
          <div class="skill sass-less-skill"></div>
          <p class="skill__percentage-wrap" id="num_4"></p>
          <p>SASS/LESS</p>
        </li>
        <li class="ellipse-wrapper jquery">
          <div class="skill__ellipse-white">
            <div class="percent-lines">

            </div>
          </div>
          <div class="skill jquery-skill"></div>
          <p class="skill__percentage-wrap" id="num_5"></p>
          <p>JQUERY</p>
        </li>
        <li class="ellipse-wrapper photoshop">
          <div class="skill__ellipse-white">
            <div class="percent-lines">

            </div>
          </div>
          <div class="skill photoshop-skill"></div>
          <p class="skill__percentage-wrap" id="num_6"></p>
          <p>PHOTOSHOP</p>
        </li>
      </ul>
    </section>

    <section class="main-section">
      <div class="bottom-shadow">
        <h2>Experience</h2>
      </div>
      <div class="experince__wrapper">
        <div>
          <b class="experince__company-name">Web-monsters</b>
          <p class="expirience_time">September 2016 - December 2016. <b>(3 months)</b></p>
          <p>Development: mobile version, landing-pages, company portfolio site, work with WordPress.
            <br>Use: HTML, CSS, JS, jQuery, Less.
            <br>Cooperation with back-end PHP developer.
          </p>
        </div>
        <br>
        <div>
          <b class="experince__company-name"><a target="_blank" href="http://stanton-lab.com/">Stanton-lab</a></b>
          <p class="expirience_time">October 2016 - December 2017 <b>(1 year 2 month)</b></p>
          <p><b>Development:</b> adaptive layouts, landing-pages, portfolio, post-launch project maintenance.
            <br><b>Use:</b> HTML, CSS, JS, jQuery, Sass/Scss, Gulp, Pug (Jade), Git, Docker (some experience).
            <br>Cooperation with back-end Ruby developers.
          </p>
        </div>
        <br>
        <div>
          <b class="experince__company-name"><a target="_blank" href="http://dbosoft.com.ua/">DBO Soft</a></b>
          <p class="expirience_time">December 2017 - February 2018 <b>(3 months)</b></p>
          <p class="expirience_time">December 2018 - December 2019 <b>(1 year)</b></p>
          <p><b>Development:</b> Maintenance of a large complex project to create services for Ukrainian and
            foreign banks.
            <br><b>Use:</b> HTML, CSS, JS, jQuery, Less, Grunt, BackboneJs, UnderscoreJs, MarionetteJs.
            <br>Interaction with the testers team.
          </p>
        </div>
        <br>
        <div>
          <b class="experince__company-name"><a target="_blank" href="https://www.softserveinc.com/uk-ua">SoftServe</a></b>
          <p class="expirience_time">January 2020 - December 2022 <b>(2 years)</b></p>
          <p><b>Development:</b> Maintenance of a large web project for the provision of orthodontic services in
            the
            USA, Canada, New Zealand and the UK. Reformatting the project to the latest technologies.
            <br><b>Use:</b> HTML, CSS, JS, jQuery, Scss, Gulp, BackboneJs, Vue.js 2.
            <br>Interaction with the dev and testers teams.
          </p>
        </div>
        <br>
        <div>
          <b class="experince__company-name"><a target="_blank" href="https://fnx.com.ua/ua">Fenix
            Industry</a></b>
          <p class="expirience_time">August 2022 - January 2023 <b>(6 months)</b></p>
          <p><b>Development:</b> Internet corporate websites, websites for the delivery of cars from the USA,
            landing page, sites on Wordpress.
            <br><b>Use:</b> HTML, CSS, JS, jQuery, Less, Gulp, Bitbucket, a little PHP.
            <br>Cooperation with back-end PHP developers.
          </p>
        </div>
        <br>
        <div>
          <b class="experince__company-name"><a target="_blank" href="https://www.ampelfy.com/">Ampelfy LLC</a></b>
          <p class="expirience_time">March 2023 - May 2023 <b>(2 months)</b></p>
          <p><b>Development:</b> Participated in the development of the <a target="_blank" href="https://projectsimple.ai/">ProjectSimple</a>
            (unique Agile project management platform)
            <br><b>Use:</b> Vue.js 3, Vuex, Typescript, Scss, Git.
          </p>
        </div>
        <br>
      </div>
    </section>

    <section class="main-section">
      <div class="bottom-shadow">
        <h2>Works</h2>
      </div>
      <div class="works-wrapper">
        <div class="work-preview">
          <a target="_blank" href="works/take/index.html">
            <img src="images/preview_1.jpg" alt="work preview 1">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/daylite/index.html">
            <img src="images/preview_2.jpg" alt="work preview 2">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/cruise/index.html">
            <img src="images/preview_3.jpg" alt="work preview 3">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/design-lab/index.html">
            <img src="images/preview_4.jpg" alt="work preview 4">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/webMonster-landing/index.html">
            <img src="images/preview_5.jpg" alt="work preview 5">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/webMonster-mainSite/index.html">
            <img src="images/preview_6.jpg" alt="work preview 6">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="https://www.facebook.com/fartukinua/">
            <img src="images/preview_7.jpg" alt="work preview 7">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/garant-service/index.html">
            <img src="images/preview_8.jpg" alt="work preview 8">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/mogo/index.html">
            <img src="images/preview_9.jpg" alt="work preview 9">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/smart-agency/index.html">
            <img src="images/preview_10.jpg" alt="work preview 10">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="http://sabon.com.ua/">
            <img src="images/preview_11.jpg" alt="work preview 11">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="http://krovati-soft.sabon.com.ua/">
            <img src="images/preview_11_1.jpg" alt="work preview 11_1">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/broochy/index.html">
            <img src="images/preview_12.jpg" alt="work preview 12">
          </a>
        </div>
        <div class="work-preview">
          <!-- <a target="_blank" href="http://paddocksnewbridge.com/">-->
          <a target="_blank" href="http://www.paddocksnewbridge.ie/">
            <img src="images/preview_13.jpg" alt="work preview 13">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/ucgt/index.html">
            <img src="images/preview_16.jpg" alt="work preview 14">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="works/internet-shop/app/index.html">
            <img src="images/preview_17.jpg" alt="work preview 17">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="http://castlevernon.ie/">
            <img src="images/preview_18.jpg" alt="work preview 18">
          </a>
        </div>
        <div class="work-preview">
          <a target="_blank" href="http://www.dneprometiz.com/">
            <img src="images/preview_19.jpg" alt="work preview 19">
          </a>
        </div>
        <div class="work-preview">
          <!-- <a target="_blank" href="http://armorceramics.co/"> -->
          <a target="_blank" href="https://ambisafe.com/">
            <img src="images/preview_20.jpg" alt="work preview 20">
          </a>
        </div>
        <div class="work-preview">
          <!-- <a target="_blank" href="https://ico.orderbook.io/"> -->
          <a target="_blank" href="https://www.youtube.com/watch?v=xKwslbv8uaI">
            <img src="images/preview_21.jpg" alt="work preview 21">
          </a>
        </div>
      </div>
    </section>
  </main>
</template>

<style lang="scss">

/* Portfolio contact */

.portfolio__profile {

  &-info {
    overflow: auto;
    position: fixed;
    top: 0;
    left: 0;
    width: 320px;
    height: 100%;
    background-color: #363b43;
    padding: 40px 15px 15px 15px;

    figure {
      margin-bottom: 30px;
    }

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

    .mCSB_scrollTools .mCSB_dragger .mCSB_dragger_bar {
      background-color: hsl(0, 1%, 41%);
    }
  }

  &-img-wrapper {
    width: 150px;
    height: 150px;
    margin: 0 auto;
    border-radius: 50%;
    overflow: hidden;

    img {
      width: 100%;
      height: 100%;
    }
  }

  &-name {
    padding-top: 0;
    padding-bottom: 30px;
    text-align: center;

    p {
      margin-top: 10px;
      color: #ffffff;
      font-size: 18px;
    }
  }

  &-contacts-wrapper {
    padding: 27px 0 25px;
  }

  &-main-contacts {

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

  &-social-links {
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

  &-social-links__hidden {
    display: none;
  }

  &-know-languges {

    p {
      font-size: 16px;
      font-weight: 300;
      color: #ffffff;
      padding: 10px 0;
    }
  }

  &-know-languges,
  &-contacts-wrapper {

    h2 {
      font-weight: 500;
    }
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
/* --------------------------- */


/* Portfolio skills */
.main-section {
  padding: 0 15px 0 350px;

  h2 {
    font-size: 21px;
    font-weight: 600;
    text-transform: uppercase;
  }
}

.portfolio__skills {
  padding-top: 30px;
}

.bottom-shadow {
  position: relative;
  padding: 10px 0;
  -webkit-box-shadow: 0 2px 0 0 rgba(0,0,0,.1);
  -moz-box-shadow: 0 2px 0 0 rgba(0,0,0,.1);
  box-shadow: 0 2px 0 0 rgba(0,0,0,.1);
}

.profile__skills-wrapper {
  margin: 15px 0 25px;
  position: relative;
  text-align: center;
}

.ellipse-wrapper {
  position: relative;
  display: inline-block;
  vertical-align: top;
  text-align: center;

  p {
    text-transform: uppercase;
    font-size: 18px;
  }
}

.skill {
  position: relative;
  z-index: 1;
  margin: 20px 5px 10px;
  width: 157px;
  height: 157px;
  background-repeat: no-repeat;
}

.html-skill {
  background: url('../images/ellipses.png') no-repeat -160px -1px;
}
.css-skill {
  background: url('../images/ellipses.png') no-repeat -1px -1px;
}
.js-skill {
  background: url('../images/ellipses.png') no-repeat -160px -160px;
}
.sass-less-skill {
  background: url('../images/ellipses.png') no-repeat -319px -160px;
}
.jquery-skill {
  background: url('../images/ellipses.png') no-repeat -1px -160px;
}
.photoshop-skill {
  background: url('../images/ellipses.png') no-repeat -319px -1px;
}

.skill__ellipse-white {
  width: 121px;
  height: 121px;
  position: absolute;
  z-index: 2;
  top: 40px;
  left: 23px;
  background-repeat: no-repeat;
  background: url('../images/ellipses.png') no-repeat -1px -319px;
}


.html-color {
  color: #ff6200;
}
.css-color {
  color: #0089ce;
}
.js-color {
  color: #fdb100;
}
.less-color {
  color: #6d8dbc;
}
.sass-color {
  color: #ff3231;
}
.jquery-color {
  color: #0769ad;
}
.gulp-color {
  color: #cf4647;
}
.pug-color {
  color: #a86454;
}
.github-color {
  color: #24292e;
}
.docker-color {
  color: #306a8a;
}


.html .percent-lines div {
  background-color: #ec6c04;
}

.css .percent-lines div {
  background-color: #1c96d4;
}

.js .percent-lines div {
  background-color: #f0be26;
}

.sass .percent-lines div {
  background-color: #f33837;
}

.jquery .percent-lines div {
  background-color: #386ab1;
}

.photoshop .percent-lines div {
  background-color: #00b3db;
}


.percent-lines {

  div {
    position: absolute;
    width: 3px;
    height: 14px;
    background-color: #e7e7e7;
    border-radius: 3px;
    animation-name: opacity_line;
    animation-duration: .2s;
    animation-timing-function: ease;
    animation-iteration-count: 1;
    animation-direction: normal;
    animation-fill-mode: forwards;
    opacity: 0;
  }

  div.grey {
    background-color: #e7e7e7;
  }

  div:first-child {
    top: 12px;
    left: 59px;
    animation-delay: 1s;
  }

  div:nth-child(2) {
    top: 14px;
    left: 70px;
    transform: rotate(18deg);
    animation-delay: 1.1s;
  }

  div:nth-child(3) {
    top: 18px;
    left: 79px;
    transform: rotate(35deg);
    animation-delay: 1.2s;
  }

  div:nth-child(4) {
    top: 24px;
    left: 87px;
    transform: rotate(50deg);
    animation-delay: 1.4s;
  }

  div:nth-child(5) {
    top: 32px;
    left: 92px;
    transform: rotate(67deg);
    animation-delay: 1.6s;
  }

  div:nth-child(6) {
    top: 41px;
    left: 95px;
    transform: rotate(79deg);
    animation-delay: 1.8s;
  }

  div:nth-child(7) {
    top: 51px;
    left: 96px;
    transform: rotate(90deg);
    animation-delay: 2s;
  }

  div:nth-child(8) {
    top: 60px;
    left: 95px;
    transform: rotate(100deg);
    animation-delay: 2.2s;
  }

  div:nth-child(9) {
    top: 69px;
    left: 92px;
    transform: rotate(114deg);
    animation-delay: 2.4s;
  }

  div:nth-child(10) {
    top: 77px;
    left: 87px;
    transform: rotate(128deg);
    animation-delay: 2.6s;
  }

  div:nth-child(11) {
    top: 84px;
    left: 79px;
    transform: rotate(146deg);
    animation-delay: 2.8s;
  }

  div:nth-child(12) {
    top: 89px;
    left: 70px;
    transform: rotate(162deg);
    animation-delay: 3s;
  }

  div:nth-child(13) {
    top: 91px;
    left: 60px;
    transform: rotate(180deg);
    animation-delay: 3.2s;
  }

  div:nth-child(14) {
    top: 90px;
    left: 50px;
    transform: rotate(195deg);
    animation-delay: 3.4s;
  }

  div:nth-child(15) {
    top: 86px;
    left: 40px;
    transform: rotate(210deg);
    animation-delay: 3.6s;
  }

  div:nth-child(16) {
    top: 80px;
    left: 31px;
    transform: rotate(225deg);
    animation-delay: 3.8s;
  }

  div:nth-child(17) {
    top: 71px;
    left: 24px;
    transform: rotate(240deg);
    animation-delay: 4s;
  }

  div:nth-child(18) {
    top: 61px;
    left: 20px;
    transform: rotate(255deg);
    animation-delay: 4.2s;
  }

  div:nth-child(19) {
    top: 51px;
    left: 19px;
    transform: rotate(270deg);
    animation-delay: 4.4s;
  }

  div:nth-child(20) {
    top: 41px;
    left: 20px;
    transform: rotate(285deg);
    animation-delay: 4.6s;
  }

  div:nth-child(21) {
    top: 31px;
    left: 24px;
    transform: rotate(300deg);
    animation-delay: 4.8s;
  }

  div:nth-child(22) {
    top: 22px;
    left: 30px;
    transform: rotate(315deg);
    animation-delay: 5s;
  }

  div:nth-child(23) {
    top: 16px;
    left: 39px;
    transform: rotate(330deg);
    animation-delay: 5.2s;
  }

  div:nth-child(24) {
    top: 13px;
    left: 49px;
    transform: rotate(350deg);
    animation-delay: 5.4s;
  }
}

@keyframes opacity_line {
  0% {
    opacity: 0;
  };
  100% {
     opacity: 1;
     };
}

p.skill__percentage-wrap {
  position: absolute;
  top: 84px;
  left: 63px;
  z-index: 10;
  color: #363b43;
  font-size: 22px;
  font-weight: 700;
}
/* --------------------------- */

/* Portfolio experience */
.experince__wrapper {
  margin: 10px 0;

  p {
    font-size: 16px;
  }

  div {
    padding: 5px 0;
    line-height: 1.48;

    b {
      font-weight: 600;

      a {
        color: inherit;
        text-decoration: none;

        &:hover {
          text-decoration: underline;
        }
      }
    }
  }
}

.experince__company-name {
  font-size: 22px;
}

.expirience_time {
  font-size: 13px;
  font-style: italic;
  margin-bottom: 5px;
}

/* --------------------------- */

/* Portfolio works */
.works {

  &-wrapper {
    margin: 20px 0;
    text-align: center;
  }
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
/* --------------------------- */

/* Responsive */
@media screen and ( max-width: 1500px ) {

  .portfolio__profile {

    &-info {
      padding: 20px 5px 15px 25px;
    }

    &-name {
      padding-bottom: 0;
    }

    &-contacts-wrapper {
      padding: 30px 0 15px;
    }

    &-social-links {
      margin: 10px 0 20px;
    }

    &-info h2 {
      margin-bottom: 5px;
    }
  }

  .grey-line {
    margin-bottom: 0;
  }
}

@media screen and ( max-width: 1420px ) {

  .ellipse-wrapper {
    margin: 0 20px;
  }
}

@media screen and ( max-width: 1370px ) {

  .work-preview {
    width: 47%;
    -webkit-box-shadow: 1px 1px 12px 1px rgba(0,0,0,.3);
    -moz-box-shadow: 1px 1px 12px 1px rgba(0,0,0,.3);
    box-shadow: 1px 1px 12px 1px rgba(0,0,0,.3);
  }

  .skill {
    margin: 20px 0;

    &__ellipse-white {
      left: 18px;
    }
  }

  p.skill__percentage-wrap {
    left: 58px;
  }
}

@media screen and ( max-width: 1000px ) {

  .ellipse-wrapper {
    margin: 0 5px;
  }
}

@media screen and ( max-width: 900px ) {

  .portfolio__profile {

    &-info {
      width: 100%;
      position: relative;
      padding: 20px 25px 15px;

      .grey-line {
        display: none;
      }
    }

    &-name {
      text-align: center;
    }

    &-contacts-wrapper,
    &-know-languges {
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

    &-social-links__hidden {
      display: block;
      text-align: center;

      .portfolio__profile-social-links {
        display: inherit;
      }
    }
  }

  .main-section {
    padding: 0 15px;
  }

  ul.portfolio__profile-social-links {
    display: none;
  }

  .work-preview {
    width: 47%;
    margin: 2% 1%;
  }

  .ellipse-wrapper {
    margin: 0 15px;
  }
}

@media screen and ( max-width: 725px ) {

  .work-preview {
    width: 400px;
    margin: 3% 1%;
  }
}

@media screen and ( max-width: 630px ) {

  .ellipse-wrapper {
    margin: 0 5px;
  }
}

@media screen and ( max-width: 530px ) {

  .portfolio__profile {

    &-img-wrapper {
      width: 100px;
      height: 100px;
    }

    &-contacts-wrapper,
    &-know-languges {
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

    &-know-languges {
      margin-top: 10px;
      margin-bottom: 20px;
    }
  }

  ul.portfolio__profile-social-links {
    display: none;
  }

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
