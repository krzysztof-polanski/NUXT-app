<template>
  <div>We are inside a blog!</div>
  <div>Blog ID: {{ route.params.id }}</div>
</template>

<script setup>
const route = useRoute()
</script>