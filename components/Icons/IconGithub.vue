<template>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    viewBox="0 0 64 64"
    :width="width"
    :height="height"
  >
    <linearGradient
      id="a"
      x1="31"
      x2="31"
      y1="16"
      y2="55.3"
      gradientUnits="userSpaceOnUse"
      spreadMethod="reflect"
    >
      <stop offset="0" stop-color="#6dc7ff" />
      <stop offset="1" stop-color="#e6abff" />
    </linearGradient>
    <path
      fill="url(#a)"
      d="M25 56v-5c-6.7 1-8.4-3.8-8.4-3.8-1-2.4-2.2-3-2.2-3.1h-.2c-.4-.4-1.7-1.2-1.3-2.3.3-1 1.5-1.1 2-1.1 3.2.2 4.7 3 4.8 3 1.5 2.8 4 2.5 5.5 2 .1-.8.3-1.4.6-2-5-.8-10.5-3.5-10.5-13 0-2.7.8-5 2.4-7-.4-1.2-.8-3.7.5-6.8l.1-.4.5-.1c.4-.2 2.7-.7 7.3 2.4a25 25 0 0 1 12.2 0c4.7-3 7-2.6 7.4-2.4l.4.1.2.4c1.2 3.1.8 5.6.4 6.8 1.7 2 2.5 4.3 2.5 7 0 9.5-5.7 12.2-10.6 13a9 9 0 0 1 .9 4V56h-2v-8.4c0-2.4-1-3.5-1.4-3.9l-1.7-1.5 2.2-.2c5.3-.6 10.6-2.4 10.6-11.4 0-2.3-.8-4.3-2.3-6l-.5-.5.3-.6c.1-.4.9-2.4 0-5.2-.8 0-2.6.4-5.7 2.4l-.3.3-.5-.2a23.1 23.1 0 0 0-12 0l-.4.2-.4-.3a12 12 0 0 0-5.6-2.4c-1 2.8-.2 4.8 0 5.2l.2.6-.4.5a8.7 8.7 0 0 0-2.3 6c0 9 5.3 10.8 10.5 11.4l2.2.3-1.7 1.4c-.4.4-1 1.2-1.2 2.8l-.1.5-.5.2c-1.3.6-5.9 2.2-8.6-2.4 0 0-.5-1-1.5-1.6.7.6 1.5 1.7 2.1 3.3 0 .2 1.4 3.6 7.3 2.3l1.2-.2V56h-2z"
    />
    <linearGradient
      id="b"
      x1="32"
      x2="32"
      y1="5"
      y2="59.2"
      gradientUnits="userSpaceOnUse"
      spreadMethod="reflect"
    >
      <stop offset="0" stop-color="#1a6dff" />
      <stop offset="1" stop-color="#c822ff" />
    </linearGradient>
    <path
      fill="url(#b)"
      d="M32 58a26 26 0 1 1 0-52 26 26 0 0 1 0 52zm0-50a24 24 0 1 0 0 48 24 24 0 0 0 0-48z"
    />
  </svg>
</template>
<script setup>
defineProps({
  width: Number,
  height: Number,
});
</script>
