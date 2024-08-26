<script setup lang="ts">
import DefaultLayout from '~/layout/Default.vue'

useHead({
  title: import.meta.env.VITE_APP_TITLE,
})
</script>

<template>
  <DefaultLayout>
    <main font-sans p="x-4 y-10" text="center gray-700 dark:gray-200">
      <RouterView />
      <Footer />
    </main>
  </DefaultLayout>
</template>
