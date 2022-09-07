<template>
    <div>
        <h3>
            title: {{ data.title }}
        </h3>
    <div>
      content: {{ data.content }}
    </div>
    
    <button v-if="showPrevBtn" @click="goBack">
      back
    </button>
    <button v-if="showNextBtn" @click="goNext">
      next
    </button>
    </div>
  </template>
  
  <script setup>
    defineProps({
      data: {
            title: String,
            content: String
        },
        test: String,
        goBack: Function,
        goNext: Function,
        showPrevBtn: Boolean,
        showNextBtn: Boolean
    })
  </script>