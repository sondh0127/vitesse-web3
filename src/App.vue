<script setup lang="ts">
// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
import { useCryptoStore } from './stores/crypto'

// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'Vitesse',
  meta: [
    { name: 'description', content: 'Opinionated Vite Starter Template' },
  ],
})

const crypto = useCryptoStore()

</script>

<template>
  <Loader v-if="crypto.loading" />
  <router-view />
</template>
