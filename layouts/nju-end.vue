<script setup lang="ts">
import { computed } from 'vue'
import NjuBrand from '../components/NjuBrand.vue'

const props = withDefaults(defineProps<{
  title?: string
  date?: string
  frontmatter?: Record<string, any>
}>(), {
  title: '感谢聆听',
  date: '2026.03'
})

const resolvedTitle = computed(() => props.frontmatter?.title || props.title)
const resolvedDate = computed(() => props.frontmatter?.date || props.date)
</script>

<template>
  <div class="slidev-layout nju-end">
    <NjuBrand />
    <img class="nju-end-watermark" src="/assets/nju-badge-transparent.png" alt="" aria-hidden="true" />
    <div class="nju-end-shell">
      <div class="nju-end-copy">
        <h1>{{ resolvedTitle }}</h1>
      </div>
    </div>
    <div class="nju-date-mark">{{ resolvedDate }}</div>
  </div>
</template>
