<template>
  <div class="flex items-center space-x-1">
    <div v-if="showText">change to {{ nextMode }}</div>
    <button
      @click="toggle"
      @mouseenter="showText = true"
      @mouseleave="showText = false"
      class="hover:bg-gray-100 dark:hover:bg-gray-600 p-2"
    >
      {{ nextModeIcon }}
    </button>
  </div>
</template>

<script setup>
const colorMode = useColorMode();
const showText = ref(false);
const mode = [
  "system", //0
  "light", //1
  "dark", //2
];
const nextModeIcons = {
  system: "🌗",
  light: "🌕",
  dark: "🌑",
};
const nextMode = computed(() => {
  const currentModeIndex = mode.indexOf(colorMode.preference);
  let nextModeIndex = null;
  if (currentModeIndex + 1 === mode.length) {
    nextModeIndex = 0;
  } else {
    nextModeIndex = currentModeIndex + 1;
  }
  return mode[nextModeIndex];
});
const nextModeIcon = computed(() => {
  return nextModeIcons[nextMode.value];
});
const toggle = () => {
  colorMode.preference = nextMode.value;
};
console.log(nextMode);
</script>

<style>
</style>