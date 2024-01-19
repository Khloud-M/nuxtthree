<template>
  <div class="container mx-auto max-w-2xl">
    <header class="flex justify-between items-center">
      <div><NuxtLink to="/" class="text-xl"> Khloud </NuxtLink></div>
      <Menu />
      <ClientOnly>
        <color-mode-selector />
      </ClientOnly>
    </header>
    <slot />
  </div>
</template>
<script setup>
// const colorMode = useColorMode();

// console.log(colorMode.preference);
// colorMode.preference = "dark";
useHead({
  titleTemplate: "%s - khloud",
});
</script>

<style>
body {
  @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-300;
}
</style>