<template>
  <nav class="font-mono">
    <ul class="flex space-x-4">
      <li>
        <nuxt-link
          to="/"
          class="link"
        >Home</nuxt-link>
      </li>
      <li>
        <nuxt-link
          to="/about"
          class="link"
        >About</nuxt-link>
      </li>
      <li>
        <nuxt-link
          to="/projects"
          class="link"
        >Projects</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.link {
  @apply p-1 hover:bg-gray-200;
}
</style>
