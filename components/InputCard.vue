<template>
  <div>
    <div class="flex flex-col justify-center text-center">
      <div class="flex justify-center">
        <IconsIconGithub :width="100" :height="100" />
      </div>

      <h1 class="my-5 text-[3.5rem] font-bold leading-[4rem] text-violet-200">
        Find Your OctoProfile
      </h1>
      <div
        class="relative flex h-10 flex-row-reverse overflow-clip rounded-lg justify-center"
      >
        <input
          class="peer w-60 rounded-r-lg border border-violet-100 px-2 text-violet-900 placeholder-slate-400 transition-colors duration-300 focus:border-violet-800 focus:outline-none"
          type="text"
          v-model="username"
          name="username"
          id="username"
          placeholder="username"
          v-on:keyup.enter="fetchOctoData"
        />
        <label
          class="flex items-center rounded-l-lg border border-violet-100 bg-violet-200 px-2 text-sm text-violet-400 transition-colors duration-300 peer-focus:border-violet-800 peer-focus:bg-violet-600 peer-focus:text-white"
          for="domain"
          >https://github.com/</label
        >
      </div>
    </div>

    <OctoProfileData v-if="octoData" :content="octoData" />
  </div>
</template>
<script setup>
const username = ref("");
const octoData = ref(null);

const fetchOctoData = async () => {
  const response = await $fetch(
    `https://api.github.com/users/${username.value}`
  );
  octoData.value = response;
};
</script>
