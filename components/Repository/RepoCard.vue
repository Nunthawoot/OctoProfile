<template>
  <div class="bg-violet-100 rounded-xl card">
    <Nuxt-link :to="content.html_url" target="_blank" class="">
      <header class="p-2 border-b flex items-center">
        <div class="flex flex-col">
          <h4 class="text-xs font-semibold">Name</h4>
          <h1 class="text-lg font-mono font-bold text-violet-600">
            {{ content.name }}
          </h1>
        </div>
        <div
          class="ml-auto p-1 rounded-full bg-violet-300 text-violet-700 text-xs"
        >
          {{ content.visibility }}
        </div>
      </header>
      <div class="flex flex-wrap p-2 w-full gap-4">
        <div class="flex flex-col w-full">
          <RepositoryRepoLanguages :languagesApi="content.languages_url" />
        </div>

        <div class="grid grid-cols-2">
          <div class="flex flex-row gap-x-1">
            <h4 class="text-xs">Create:</h4>
            <h1 class="text-xs font-thin">
              {{ formateTime(content.created_at) }}
            </h1>
          </div>

          <div class="flex flex-row gap-x-1">
            <h4 class="text-xs">Last Update:</h4>
            <h1 class="text-xs font-thin">
              {{ formateTime(content.updated_at) }}
            </h1>
          </div>
        </div>
      </div>
    </Nuxt-link>
  </div>
</template>
<script setup>
const props = defineProps({
  content: Object,
});

function formateTime(value) {
  return new Date(value).toLocaleString(undefined, {
    year: "numeric",
    month: "2-digit",
    day: "2-digit",
  });
}
</script>
<style lang="postcss" scoped>
.card:hover {
  scale: 1;
  border-radius: 12px;
  background: linear-gradient(145deg, #838ce3, #bc67f5);
  outline: none;
}
</style>
