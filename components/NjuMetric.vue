<script setup lang="ts">
defineProps<{
  label: string
  value: string
  hint?: string
}>()
</script>

<template>
  <div class="nju-metric-card">
    <p class="nju-metric-label">{{ label }}</p>
    <div class="nju-metric-value">{{ value }}</div>
    <p v-if="hint" class="nju-metric-hint">{{ hint }}</p>
  </div>
</template>
