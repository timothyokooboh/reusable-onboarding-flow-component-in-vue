<template>
    <div>
       <slot
            :goBack="goBack"
            :goNext="goNext"
            :showPrevBtn="showPrevBtn"
            :showNextBtn="showNextBtn"
            :current-index="currentIndex"
        >
    </slot>
    </div>
  </template>
  
  <script setup>
    import { ref, computed,  } from "vue";
    
    const props = defineProps({
        numberOfSteps: {
            type: Number,
            default: 0
        }
    })

    const currentIndex = ref(0)
    
   const goBack = () => {
    currentIndex.value -= 1;
  }
   
   const goNext = () => {
     currentIndex.value += 1
  }
   
   const showPrevBtn = computed(() => {
     return currentIndex.value != 0
  })
   
  const showNextBtn = computed(() => {
    return currentIndex.value != props.numberOfSteps - 1
  })
  </script>