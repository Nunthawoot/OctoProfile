<template>
  <div class="mx-auto">
    <div class="grid justify-center">
      <IconsIconGithub :width="100" :height="100" />
    </div>

    <h1 class="my-5 text-[3.5rem] font-bold leading-[4rem] text-black">
      Find Your OctoProfile
    </h1>
    <div
      class="relative flex h-10 w-full flex-row-reverse overflow-clip rounded-lg"
    >
      <input
        class="peer w-full rounded-r-lg border border-slate-400 px-2 text-slate-900 placeholder-slate-400 transition-colors duration-300 focus:border-sky-400 focus:outline-none"
        type="text"
        v-model="username"
        name="username"
        id="username"
        placeholder="username"
        v-on:keyup.enter="fetchOctoData"
      />
      <label
        class="flex items-center rounded-l-lg border border-slate-400 bg-slate-50 px-2 text-sm text-slate-400 transition-colors duration-300 peer-focus:border-sky-400 peer-focus:bg-sky-400 peer-focus:text-white"
        for="domain"
        >https://github.com/</label
      >
    </div>
  </div>
</template>
<script setup>
const username = ref("");
const octoData = ref();

const fetchOctoData = async () => {
  const response = await $fetch(
    `https://api.github.com/users/${username.value}`
  );
  console.log(response)
  octoData.value = response;
};
// const getData = await useFetch("https://api.github.com/users/nunthawoot");

// async consoleHitOn() {
//     const getData = await useState("https://api.github.com/users/nunthawoot");
// }
</script>
