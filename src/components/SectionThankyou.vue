<script setup>
const props = defineProps({
  rating: String,
  required: true,
  default: '0',
})
</script>

<template>
  <section class="thankyou panel">
    <img
      src="../assets/images/illustration-thank-you.svg"
      alt="some random illustration"
      class="thankyou-img"
    />

    <div class="pill-result">
      You selected <span class="text-result">{{ rating }}</span> out of 5
    </div>

    <h2>Thank you!</h2>

    <p>
      We appreciate you taking the time to give a rating. If you ever need more
      support, don&rsquo;t hesitate to get in touch!
    </p>
  </section>
</template>
