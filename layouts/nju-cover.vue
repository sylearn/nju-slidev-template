<script setup lang="ts">
import { computed } from 'vue'
import NjuBrand from '../components/NjuBrand.vue'

const props = withDefaults(defineProps<{
  title?: string
  speaker?: string
  affiliation?: string
  mentor?: string
  date?: string
  school?: string
  frontmatter?: Record<string, any>
}>(), {
  title: '研究汇报',
  speaker: '你的姓名',
  affiliation: '南京大学 / 学院',
  mentor: '导师：万建国',
  date: '2026.03',
  school: '南京大学'
})

const resolvedTitle = computed(() => props.frontmatter?.title || props.title)
const resolvedSpeaker = computed(() => props.frontmatter?.speaker || props.speaker)
const resolvedAffiliation = computed(() => props.frontmatter?.affiliation || props.affiliation)
const resolvedMentor = computed(() => props.frontmatter?.mentor || props.mentor)
const resolvedDate = computed(() => props.frontmatter?.date || props.date)
const resolvedSchool = computed(() => props.frontmatter?.school || props.school)
</script>

<template>
  <div class="slidev-layout nju-cover">
    <NjuBrand :school="resolvedSchool" />

    <div class="nju-cover-main">
      <h1>{{ resolvedTitle }}</h1>

      <div class="nju-cover-meta nju-cover-meta-single">
        <div>
          <span>汇报人</span>
          <strong>{{ resolvedSpeaker }}</strong>
        </div>
        <div>
          <span>单位</span>
          <strong>{{ resolvedAffiliation }}</strong>
        </div>
        <div>
          <span>指导教师</span>
          <strong>{{ resolvedMentor }}</strong>
        </div>
      </div>
    </div>

    <img class="nju-cover-watermark" src="/assets/nju-badge-transparent.png" alt="" aria-hidden="true" />
    <div class="nju-date-mark">{{ resolvedDate }}</div>
  </div>
</template>
