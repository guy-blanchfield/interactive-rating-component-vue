<script setup>
import { ref } from 'vue'
// this will be the ref for the radio button v-model bound state
const ratingRadio = ref(null)

// ref for the submit button, to programmatically blur it
const ratingSubmitButton = ref(null)

// defineEmits is similar to defineProps (a macro)
const emit = defineEmits(['submit-rating', 'change-rating'])

const handleRatingSubmit = () => {
  if (ratingRadio.value) {
    emit('submit-rating', ratingRadio.value)
  } else {
    // blur the submit button, using a template ref
    ratingSubmitButton.value.blur()
    // console.log(`blurring ${ratingSubmitButton.value.name}`)
  }
}

const handleRatingChange = () => {
  emit('change-rating', ratingRadio.value)
}
</script>

<template>
  <section class="rating panel">
    <!-- icon here as icon - should probably be a background on the h2 or the ratings panel itself 
        but given how it's layed out, it's probably supposed to be an actual element -->
    <div class="rating-icon">
      <span class="rating-icon-inner" aria-hidden="true"></span>
    </div>

    <h2>How did we do?</h2>

    <!-- form should probably include the question! -->
    <form
      @submit.prevent="handleRatingSubmit"
      class="rating-form"
      id="rating-form"
    >
      <fieldset class="rating-fieldset">
        <legend class="rating-legend">
          Please let us know how we did with your support request. All feedback
          is appreciated to help us improve our offering!
        </legend>

        <div class="rating-radios">
          <!-- wrapping label method so we don't need an extra div -->
          <label class="rating-radio-label">
            <input
              type="radio"
              id="rating-radio-1"
              name="rating-radio"
              value="1"
              v-model="ratingRadio"
              @change="handleRatingChange"
            />
            <span class="rating-radio-label-inner">1</span>
          </label>

          <label class="rating-radio-label">
            <input
              type="radio"
              id="rating-radio-2"
              name="rating-radio"
              value="2"
              v-model="ratingRadio"
              @change="handleRatingChange"
            />
            <span class="rating-radio-label-inner">2</span>
          </label>

          <label class="rating-radio-label">
            <input
              type="radio"
              id="rating-radio-3"
              name="rating-radio"
              value="3"
              v-model="ratingRadio"
              @change="handleRatingChange"
            />
            <span class="rating-radio-label-inner">3</span>
          </label>

          <label class="rating-radio-label">
            <input
              type="radio"
              id="rating-radio-4"
              name="rating-radio"
              value="4"
              v-model="ratingRadio"
              @change="handleRatingChange"
            />
            <span class="rating-radio-label-inner">4</span>
          </label>

          <label class="rating-radio-label">
            <input
              type="radio"
              id="rating-radio-5"
              name="rating-radio"
              value="5"
              v-model="ratingRadio"
              @change="handleRatingChange"
            />
            <span class="rating-radio-label-inner">5</span>
          </label>
        </div>
      </fieldset>

      <button
        class="rating-btn btn-submit"
        type="submit"
        name="rating-submit"
        value="submit"
        ref="ratingSubmitButton"
      >
        Submit
      </button>
    </form>
  </section>
  <!-- <h2>Rating</h2>
  <button @click="handleIncrement">Increment rating</button>
  <button @click="handleClick">Submit Rating</button> -->
</template>
