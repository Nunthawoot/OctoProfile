<template>
  <div v-if="!pending">
    <div
      v-for="(value, key, index) in languages"
      :key="index"
      class="text-sm text-violet-700"
    >
      {{ key }}: {{ percentage(value) }}%
    </div>
  </div>
</template>
<script setup>
const props = defineProps({
  languagesApi: String,
});
const total = ref(0);
const { pending, data: languages } = useLazyAsyncData("languages", () =>
  $fetch(props.languagesApi)
);
watch(languages, (newLanguages) => {
  total.value = Object.values(newLanguages).reduce((a, b) => a + b, 0);
  languages.value = newLanguages;
});

function percentage(percent) {
  return ((percent / total.value) * 100).toFixed(2);
}
</script>
