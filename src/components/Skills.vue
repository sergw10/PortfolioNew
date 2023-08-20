<template>
  <section class="main-section portfolio__skills">
    <div class="bottom-shadow">
      <h2>Skills</h2>
    </div>

    <div class="skills-list">
      <template v-for="skill in skills" :key="skills.length">
        <div class="skill-item">
          <div :class="`${skill.className}--wrapper main-ellipse--wrapper flex-center`">
            <div :class="`white-ellipse--wrapper ${skill.className}`">
              <p class="skill__percentage-wrap">{{ skill.knowledgePercentage }}</p>
              <div class="absolute-lines--wrapper">
                <template v-for="n in 24">
                  <div class="line-item"></div>
                </template>
              </div>
            </div>
          </div>
          <p class="skill-name">{{ skill.nameText }}</p>
        </div>
      </template>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive, ref, onMounted } from 'vue'

const timerSpeed = ref<number>(4450)

const skills = reactive([
  { className: 'javascript', nameText: 'JavaScript', knowledgePercentage: 80 },
  { className: 'html', nameText: 'HTML 5', knowledgePercentage: 80 },
  { className: 'css', nameText: 'CSS', knowledgePercentage: 80 },
  { className: 'preprocessors', nameText: 'SASS | LESS', knowledgePercentage: 70 },
  { className: 'jquery', nameText: 'jQuery', knowledgePercentage: 80 },
  { className: 'photoshop', nameText: 'Figma | Photoshop', knowledgePercentage: 60 }
])

// function countNumbersFromArray (knowledgePercentage) {
//
//   let numberOfIterations: number = 0;
//
//   setInterval(() => {
//   }, 1000)
// }
//
// onMounted(() => {
//   countNumbersFromArray()
// })
</script>

<style lang="scss">
/* Mixin's */
@mixin linear-gradient($background-from, $background-to) {
  background: $background-from;
  background: linear-gradient(0deg, $background-from 0%, $background-to 100%);
}

@mixin line-item-position($top, $left, $transformDeg, $animationDelay) {
  top: $top;
  left: $left;
  transform: rotate($transformDeg);
  animation-delay: $animationDelay;
}

/* -------------------------------------- */

.portfolio__skills {
  padding-top: 30px;
}

.bottom-shadow {
  position: relative;
  padding: 10px 0;
  box-shadow: 0 2px 0 0 rgba(0, 0, 0, 0.1);
}

.skills-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.skill-item {
  padding: 30px 5px 5px;
}

.skill-name {
  text-align: center;
}

.main-ellipse--wrapper {
  width: 150px;
  min-width: 150px;
  height: 150px;
  min-height: 150px;
  margin-bottom: 10px;
  border-radius: 50%;
  font-size: 18px;
  box-shadow: 0 0 8px 0 rgba(0, 0, 0, 60%);
}

.white-ellipse--wrapper {
  position: relative;
  z-index: 1;
  width: 110px;
  min-width: 110px;
  height: 110px;
  min-height: 110px;
  background-color: white;
  border-radius: 50%;
  box-shadow: 0 0 8px 0 rgba(0, 0, 0, 65%);
}

/* Circles gradient-background */
.html--wrapper {
  @include linear-gradient(rgb(255, 77, 28), rgb(255, 115, 0));
}
.css--wrapper {
  @include linear-gradient(rgb(0, 138, 171), rgb(0, 181, 222));
}
.preprocessors--wrapper {
  @include linear-gradient(rgb(250, 48, 45), rgb(255, 52, 51));
}
.javascript--wrapper {
  @include linear-gradient(rgb(250, 164, 6), rgb(255, 191, 0));
}
.jquery--wrapper {
  @include linear-gradient(rgb(42, 79, 132), rgb(56, 107, 179));
}
.photoshop--wrapper {
  @include linear-gradient(rgb(0, 135, 166), rgb(0, 181, 221));
}

/* Line wrapper */
.absolute-lines--wrapper {
  width: 110px;
  height: 110px;
  position: relative;
  z-index: 1;
}

/* Line colors */
.html .line-item {
  background-color: #ec6c04;
}
.css .line-item {
  background-color: #1c96d4;
}
.javascript .line-item {
  background-color: #f0be26;
}
.preprocessors .line-item {
  background-color: #f33837;
}
.jquery .line-item {
  background-color: #386ab1;
}
.photoshop .line-item {
  background-color: #00b3db;
}

.line-item {
  position: absolute;
  width: 3px;
  height: 14px;
  border-radius: 3px;
  animation-name: showTheLine;
  animation-duration: 0.2s;
  animation-timing-function: ease;
  animation-iteration-count: 1;
  animation-direction: normal;
  animation-fill-mode: forwards;
  opacity: 0;

  &.grey {
    background-color: #e7e7e7;
  }

  /* Animate from 1s - to 4.45s */
  &:first-child {
    @include line-item-position(10px, 53px, 0deg, 1s);
  }
  &:nth-child(2) {
    @include line-item-position(11px, 64px, 15deg, 1.15s);
  }
  &:nth-child(3) {
    @include line-item-position(15px, 74px, 30deg, 1.3s);
  }
  &:nth-child(4) {
    @include line-item-position(21px, 82px, 45deg, 1.45s);
  }
  &:nth-child(5) {
    @include line-item-position(29px, 88px, 60deg, 1.6s);
  }
  &:nth-child(6) {
    @include line-item-position(39px, 92px, 75deg, 1.75s);
  }
  &:nth-child(7) {
    @include line-item-position(50px, 94px, 90deg, 1.9s);
  }
  &:nth-child(8) {
    @include line-item-position(60px, 93px, 105deg, 2.05s);
  }
  &:nth-child(9) {
    @include line-item-position(69px, 89px, 120deg, 2.2s);
  }
  &:nth-child(10) {
    @include line-item-position(77px, 83px, 135deg, 2.35s);
  }
  &:nth-child(11) {
    @include line-item-position(83px, 74px, 150deg, 2.5s);
  }
  &:nth-child(12) {
    @include line-item-position(86px, 64px, 165deg, 2.65s);
  }
  &:nth-child(13) {
    @include line-item-position(87px, 54px, 180deg, 2.8s);
  }
  &:nth-child(14) {
    @include line-item-position(86px, 44px, 195deg, 2.95s);
  }
  &:nth-child(15) {
    @include line-item-position(83px, 34px, 210deg, 3.1s);
  }
  &:nth-child(16) {
    @include line-item-position(77px, 26px, 225deg, 3.25s);
  }
  &:nth-child(17) {
    @include line-item-position(69px, 19px, 240deg, 3.4s);
  }
  &:nth-child(18) {
    @include line-item-position(60px, 15px, 255deg, 3.55s);
  }
  &:nth-child(19) {
    @include line-item-position(50px, 14px, 270deg, 3.7s);
  }
  &:nth-child(20) {
    @include line-item-position(39px, 14px, 285deg, 3.85s);
  }
  &:nth-child(21) {
    @include line-item-position(29px, 18px, 300deg, 4s);
  }
  &:nth-child(22) {
    @include line-item-position(20px, 24px, 315deg, 4.15s);
  }
  &:nth-child(23) {
    @include line-item-position(14px, 33px, 330deg, 4.3s);
  }
  &:nth-child(24) {
    @include line-item-position(11px, 43px, 345deg, 4.45s);
  }

  @keyframes showTheLine {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
}

.skill__percentage-wrap {
  position: absolute;
  top: 36%;
  left: 38%;
  color: black;
  font-size: 22px;
  font-weight: 700;
}
</style>
