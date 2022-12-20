<script setup>
import SectionRating from '../components/SectionRating.vue'
import SectionThankyou from '../components/SectionThankyou.vue'

import { ref } from 'vue'

const ratingSubmitted = ref(false)
const rating = ref(0)

const handleSubmitRating = (data) => {
  // receives data from the emit event (submit-rating)
  // and sets rating.value to data
  rating.value = data
  console.log(`rating is ${rating.value}`)
  ratingSubmitted.value = true
}

const handleChangeRating = (data) => {
  // keeps rating updated with the currently checked radio
  // don't really need it, it was just for display / testing
  // the change event might come in handy though

  // receives data from the emit event (change-rating)
  // and sets rating.value to data
  rating.value = data
  console.log(`rating is ${rating.value}`)
}
</script>

<template>
  <main class="main-container">
    <SectionRating
      v-if="ratingSubmitted === false"
      @submit-rating="handleSubmitRating"
      @change-rating="handleChangeRating"
    />
    <SectionThankyou v-else :rating="rating" />
  </main>
</template>
