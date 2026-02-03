<template>
  <div class="container mx-auto max-w-2xl">
    <header class="flex justify-between items-center mt-5">
      <nuxt-link 
        to="/"
        class="text-xl font-semibold p-2 hover:bg-gray-200"
      >Krzysztof Polański</nuxt-link>
      <Menu />
    </header>
    <main class="p-2"><slot /></main>
  </div>
</template>