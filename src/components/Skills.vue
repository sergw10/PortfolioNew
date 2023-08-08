<template>
  <section class="main-section portfolio__skills">

    <div class="bottom-shadow">
      <h2>Skills</h2>
    </div>

    <ul class="profile__skills-wrapper">
      <template v-for="skill in skillsList" :key="skillsList.length">
        <li :class="`ellipse-wrapper ${skill.name}`">
          <div class="skill__ellipse-white">
            <div class="percent-lines"></div>
          </div>
          <div :class="`skill ${skill.name}-skill`"></div>
          <p class="skill__percentage-wrap" :id="`num_${skillsList.length + 1}`"></p>
          <p>{{ skill.text }}</p>
        </li>
      </template>
    </ul>

  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const skillsList = reactive([
  {name: 'html', text: 'HTML'},
  {name: 'css', text: 'CSS'},
  {name: 'js', text: 'JavaScript'},
  {name: 'preprocessors', text: 'SASS/LESS'},
  {name: 'jquery', text: 'JQuery'},
  {name: 'photoshop', text: 'Photoshop/Figma'},
]);

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

<style lang="scss">
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

.html-skill,
.css-skill,
.js-skill,
.preprocessors-skill,
.jquery-skill,
.photoshop-skill,
.skill__ellipse-white {
  background: url('../assets/images/ellipses.png') no-repeat
}

.html-skill {
  background-position: -160px -1px;
}
.css-skill {
  background-position: -1px -1px;
}
.js-skill {
  background-position: -160px -160px;
}
.preprocessors-skill {
  background-position: -319px -160px;
}
.jquery-skill {
  background-position: -1px -160px;
}
.photoshop-skill {
  background-position: -319px -1px;
}

.skill__ellipse-white {
  width: 121px;
  height: 121px;
  position: absolute;
  z-index: 2;
  top: 40px;
  left: 23px;
  background-position: -1px -319px;
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
  }
  100% {
     opacity: 1;
   }
}

.skill__percentage-wrap {
  position: absolute;
  top: 84px;
  left: 63px;
  z-index: 10;
  color: #363b43;
  font-size: 22px;
  font-weight: 700;
}

/* Responsive */
@media screen and ( max-width: 1420px ) {

  .ellipse-wrapper {
    margin: 0 20px;
  }
}

@media screen and ( max-width: 1370px ) {

  .skill {
    margin: 20px 0;

    &__ellipse-white {
      left: 18px;
    }
  }

  .skill__percentage-wrap {
    left: 58px;
  }
}

@media screen and ( max-width: 1000px ) {

  .ellipse-wrapper {
    margin: 0 5px;
  }
}

@media screen and ( max-width: 900px ) {
  .ellipse-wrapper {
    margin: 0 15px;
  }
}

@media screen and ( max-width: 630px ) {

  .ellipse-wrapper {
    margin: 0 5px;
  }
}

</style>
