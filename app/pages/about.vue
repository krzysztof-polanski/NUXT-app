<template>
  <article class="prose dark:prose-invert prose-h1:text-2xl">
    <ContentRenderer :value="doc"/>
  </article>
</template>

<script setup>
const route = useRoute()
const { data: doc } = await useAsyncData(route.path, () =>
  queryCollection('content').path(route.path).first()
)
</script>