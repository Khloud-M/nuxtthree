<template>
  <div>
    <nav>
      <ul>
        <li>
          <NuxtLink to="/"> main </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/about"> about </NuxtLink>
        </li>
      </ul>
    </nav>
    <slot />
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>