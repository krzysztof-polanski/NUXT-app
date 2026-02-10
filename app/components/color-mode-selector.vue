<template>
  <div class="flex space-x-2 items-center">
    <div
      v-show="showNextModeLabel"
      class="text-gray-500 text-xs"
    >
      Change to {{ nextMode }}
    </div>
    <button
      class="hover:bg-gray-200 dark:hover:bg-gray-600 px-2 py-1 text-gray-500"
      @click="toggleColorMode"
      @mouseenter="showNextModeLabel = true"
      @mouseleave="showNextModeLabel = false"
    >
      {{ nextModeIcon }}
    </button>
  </div>
</template>

<script setup lang="ts">
const colorMode = useColorMode()

const showNextModeLabel = ref(false)

enum ColorMode {
  SYSTEM = 'system',
  LIGHT = 'light',
  DARK = 'dark',
}

const nextModeIcons = {
  system: '🌓',
  light: '🌕',
  dark: '🌑'
}

const colorModes = Array.from(Object.values(ColorMode))

const nextMode = computed(() => {
  const currentModeIndex = colorModes.indexOf(colorMode.preference as ColorMode)
  let nextModeIndex = null
  if (currentModeIndex + 1 === colorModes.length) {
    nextModeIndex = 0
  } else {
    nextModeIndex = currentModeIndex + 1
  }
  return colorModes[nextModeIndex]
})

const nextModeIcon = computed(() => {
  return nextModeIcons[nextMode.value as ColorMode]
})

const toggleColorMode = (): void => {
  colorMode.preference = nextMode.value as string
}
</script>
