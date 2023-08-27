<style lang="scss" scoped>
@use "@/components/Skills/skills" as *;
</style>

<template>
  <section class="main-section portfolio__skills">
    <div class="bottom-shadow">
      <h2>Skills</h2>
    </div>

    <div class="skills-list">
      <template v-for="(skill, index) in skills" :key="index">
        <div class="skill-item">
          <div :class="`${skill.className}--wrapper main-ellipse--wrapper flex-center`">
            <div :class="`white-ellipse--wrapper ${skill.className}`">
              <p class="skill__percentage-wrap">{{ skill.knowledgePercentage }}</p>
              <div class="absolute-lines--wrapper">
                <template v-for="startNum in 24" :key="startNum">
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
import { reactive, ref } from "vue";

const timerSpeed = ref<number>(4450);
const startNum = 0;

const skills = reactive([
  { className: "javascript", nameText: "JavaScript", knowledgePercentage: 80 },
  { className: "html", nameText: "HTML 5", knowledgePercentage: 80 },
  { className: "css", nameText: "CSS", knowledgePercentage: 80 },
  { className: "preprocessors", nameText: "SASS | LESS", knowledgePercentage: 70 },
  { className: "jquery", nameText: "jQuery", knowledgePercentage: 80 },
  { className: "photoshop", nameText: "Figma | Photoshop", knowledgePercentage: 60 }
]);

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
