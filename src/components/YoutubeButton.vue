<template>
  <a
    :href="href"
    target="_blank"
    class="px-2 py-1 rounded border-2 bg-red-400 border-red-500 hover:bg-red-600 transition-colors text-white"
  >
    <slot></slot>
  </a>
</template>

<script setup>
const props = defineProps({
  href: String,
});
</script>
