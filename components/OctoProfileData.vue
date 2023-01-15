<template>
  <div class="">
    <div class="grid items-center justify-center text-center text-violet-200">
      <div class="py-4">
        <img :src="content.avatar_url" class="mx-auto" />
      </div>

      <p class="font-semibold text-3xl py-4">{{ content.login }}</p>
      <div class="flex gap-x-4 text-sm">
        <div>
          Followers <span>{{ content.followers }}</span>
        </div>
        <div>
          Following <span>{{ content.following }}</span>
        </div>
        <div>
          Public repos <span>{{ content.public_repos }}</span>
        </div>
        <div>
          Public gists <span>{{ content.public_gists }}</span>
        </div>
      </div>
    </div>
    <RepositoryRepoList v-if="content.public_repos !== 0" :repoApi="content.repos_url" />
  </div>
</template>
<script setup>
defineProps({
  content: Object,
});
</script>
<style lang="postcss" scoped>
img {
  border-radius: 50%;
  width: 200px;
  height: 200px;
}
</style>
