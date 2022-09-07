<script setup>
import { ref } from "vue"
import OnboardingFlow from './components/OnboardingFlow.vue';
import OnboardingStep from './components/OnboardingStep.vue';

const items = ref([
  {
    title: 'step one',
    content: 'this is step one'
  },
  {
    title: 'step two',
    content: 'this is step two'
  },
  {
    title: 'step three',
    content: 'this is step three'
  }
])
</script>

<template>
  <OnboardingFlow :number-of-steps="items.length">
    <template #default="{goBack, goNext, showPrevBtn, showNextBtn, currentIndex}">
      <div
        v-for="(item, i) in items"
        :key="i"
      >
        <OnboardingStep
          v-if="i === currentIndex"
          :data="item"
          :go-back="goBack"
          :go-next="goNext"
          :show-prev-btn="showPrevBtn"
          :show-next-btn="showNextBtn"
        />
      </div>
    </template>
  </OnboardingFlow>
</template>

<style scoped>
</style>