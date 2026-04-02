<script setup lang="ts">
defineProps<{
  index: string | number
  title: string
  body: string
}>()
</script>

<template>
  <div class="nju-step-card">
    <div class="nju-step-index">{{ index }}</div>
    <div class="nju-step-copy">
      <h3>{{ title }}</h3>
      <p>{{ body }}</p>
    </div>
  </div>
</template>
