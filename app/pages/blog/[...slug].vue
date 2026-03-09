<template>
  <article
    v-if="page"
    class="
      prose dark:prose-invert
      prose-pre:bg-white dark:prose-pre:bg-gray-800
      prose-pre:text-gray-700 dark:prose-pre:text-gray-300
    "
  >
    <ContentRenderer :value="page"/>
  </article>
  <article v-else>
    <div class="empty-page">
      <h1>Page Not Found</h1>
      <p>Oops! The content you're looking for doesn't exist.</p>
      <NuxtLink to="/">Go back home</NuxtLink>
    </div>
  </article>
</template>

<script setup>
const route = useRoute()

const { data: page } = await useAsyncData(route.path, () => {
    return queryCollection('content').path(route.path).first()
})
useSeoMeta({
  title: page.value.title,
  description: page.value.description,
  ogTitle: page.value.title,
  ogDescription: page.value.description,
  ogImage: page.value.image,
  twitterCard: 'summary_large_image',
  twitterDescription: page.value.description
})
</script>