<script setup lang="ts">
import { computed } from 'vue'
import NjuBrand from '../components/NjuBrand.vue'

const props = withDefaults(defineProps<{
  title?: string
  date?: string
  frontmatter?: Record<string, any>
}>(), {
  title: '章节标题',
  date: '2026.03'
})

const resolvedTitle = computed(() => props.frontmatter?.title || props.title)
const resolvedDate = computed(() => props.frontmatter?.date || props.date)
</script>

<template>
  <div class="slidev-layout nju-section">
    <NjuBrand />
    <img class="nju-section-watermark" src="/assets/nju-badge-transparent.png" alt="" aria-hidden="true" />
    <div class="nju-section-shell">
      <div class="nju-section-copy">
        <h1>{{ resolvedTitle }}</h1>
      </div>
      <div v-if="$slots.default" class="nju-section-extra">
        <slot />
      </div>
    </div>
    <div class="nju-date-mark">{{ resolvedDate }}</div>
  </div>
</template>
