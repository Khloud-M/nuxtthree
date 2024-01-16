<template>
  <h2>about page</h2>
  <button @click="enableCustomLayout">Update layout</button>
</template>
<script setup>
// definePageMeta({
//   layout: "custom",
// });
function enableCustomLayout() {
  setPageLayout("custom");
}
useHead({
  title: "about",
});
</script>
