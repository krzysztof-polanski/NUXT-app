<template>
  <div class="container mx-auto max-w-2xl">
    <header class="flex justify-between items-center mt-5">
      <nuxt-link 
        to="/"
        class="text-xl font-semibold p-2 hover:bg-gray-200"
      >Krzysztof Polański</nuxt-link>
      <Menu />
    </header>
    <main class="p-2 mt-10"><slot /></main>
  </div>
</template>

<script setup lang="ts">
const colorMode = useColorMode()

const changeColorMode = (mode: 'light' | 'dark' | 'system'): void => {
  colorMode.preference = mode
}

useHead({
  titleTemplate: '%s - Krzysztof Polański',
  link: [
    {
      rel: 'preconnect',
      href: 'https://fonts.googleapis.com',
    },
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap',
      crossorigin: '',
    },
  ],
})
onBeforeMount(() => {
  changeColorMode('system')
})
</script>

<style>
body {
  font-family: 'Roboto', sans-serif;
}
body {
  @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-300;
}
</style>
