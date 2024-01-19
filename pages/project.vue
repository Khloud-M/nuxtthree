<template>
  <div>
    project <project-list />
    <section v-if="panding">this data loading ....</section>
    <section v-else-if="error">this data error</section>
    <section v-else>
      <ul v-for="mydata in repos" :key="mydata.id">
        <li class="border border-gray-200 p-4 mt-1 hover:bg-gray-100">
          <a :href="mydata.avatar_url" target="_blank">
            <div class="flex items-center justify-between">
              <div>{{ mydata.login }}</div>
              <div v-if="mydata.type === 'User'">user*</div>
              <div v-else>**organise**</div>
            </div>
          </a>
          <div v-if="mydata.avatar_url.length > 40">this is longer</div>
        </li>
      </ul>
    </section>
  </div>
</template>

<script setup>
const { error, data, panding } = await useFetch("https://api.github.com/users");
const repos = computed(() => {
  return data.value.filter((repo) => repo.type === "Organization");
});
console.log(repos);
definePageMeta({
  colorMode: "light",
});
</script>

<style>
</style>