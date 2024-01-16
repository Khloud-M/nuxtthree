<template>
  <div class="container mx-auto max-w-2xl">
    <header class="flex justify-between items-center">
      <div><NuxtLink to="/" class="text-xl"> Khloud </NuxtLink></div>
      <Menu />
    </header>
    <slot />
  </div>
</template>

<script setup>
useHead({
  titleTemplate: "%s - khloud",
});
</script>

<style>
</style>