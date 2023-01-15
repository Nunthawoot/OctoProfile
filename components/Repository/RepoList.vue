<template>
  <div>
    <div class="text-2xl font-semibold text-violet-400 mb-8">Repositories</div>
    <div v-if="pending">"Loading"</div>
    <div v-else class="grid grid-cols-4 gap-8">
      <div v-for="item in contentList" :key="item.id">
        <RepositoryRepoCard :content="item" />
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  repoApi: String,
});
const { pending, data: contentList } = useLazyAsyncData("contentList", () =>
  $fetch(props.repoApi)
);
watch(contentList, (newContentList) => {
  contentList.value = newContentList;
});
</script>
