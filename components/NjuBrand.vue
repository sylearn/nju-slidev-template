<script setup lang="ts">
withDefaults(defineProps<{
  school?: string
}>(), {
  school: '南京大学'
})
</script>

<template>
  <div class="nju-brand" aria-label="南京大学">
    <img class="nju-brand-badge" src="/assets/nju-badge-transparent.png" alt="南京大学校标" />
    <div class="nju-brand-text">
      <span>{{ school }}</span>
    </div>
  </div>
</template>
