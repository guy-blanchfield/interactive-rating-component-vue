<script setup>
// srcipt setup is a compile-time syntactic sugar for using Composition API inside Single-File Components (SFCs)
// see https://vuejs.org/api/sfc-script-setup.html

import TheHeader from './components/TheHeader.vue'
import TheFooter from './components/TheFooter.vue'
import TheMain from './components/TheMain.vue'

// Values in the scope of <script setup> can also be used directly as custom component tag names
// i.e. we don't need to register the components in a component option
</script>

<template>
  <TheHeader title="Interactive Rating Component with Vue" />
  <TheMain />
  <TheFooter />
</template>

<style scoped></style>
