<script setup lang="ts">
import { computed } from 'vue'
import NjuBrand from '../components/NjuBrand.vue'

const props = withDefaults(defineProps<{
  title?: string
  date?: string
  frontmatter?: Record<string, any>
}>(), {
  title: '',
  date: '2026.03'
})

const resolvedTitle = computed(() => props.frontmatter?.title || props.title)
const resolvedDate = computed(() => props.frontmatter?.date || props.date)
</script>

<template>
  <div class="slidev-layout nju-default">
    <NjuBrand />
    <div class="nju-shell">
      <header class="nju-header">
        <h1>{{ resolvedTitle }}</h1>
      </header>

      <main class="nju-body">
        <slot />
      </main>
    </div>
    <div class="nju-date-mark">{{ resolvedDate }}</div>
  </div>
</template>
