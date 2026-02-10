<template>
  <div>
    <h1>Welcome to the main page</h1>
  </div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: 'Main page',
  description: 'This is the main page of the website.',
  ogTitle: 'Main page',
  ogDescription: '[og:description]',
  ogImage: '[og:image]',
  ogUrl: '[og:url]',
  twitterTitle: 'Main page',
  twitterDescription: '[twitter:description]',
  twitterImage: '[twitter:image]',
  twitterCard: 'summary'
})

useHead({
  htmlAttrs: {
    lang: 'en'
  },
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: '/favicon.png'
    }
  ]
})
</script>