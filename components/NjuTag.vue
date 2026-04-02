<script setup lang="ts">
defineProps<{
  text: string
}>()
</script>

<template>
  <span class="nju-chip">{{ text }}</span>
</template>
