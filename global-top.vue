<script setup>
import { computed, inject, toRef } from 'vue'

const ctx = inject('$$slidev-context')
const nav = toRef(ctx, 'nav')

const sections = [
  { id: 1, label: 'Background' },
  { id: 2, label: 'References' },
  { id: 3, label: 'Our Take' },
  { id: 4, label: 'Reflection' },
]

const perspectives = [
  { id: 1, label: 'Architecture & Taste', color: 'amber' },
  { id: 2, label: 'Agent Legibility', color: 'cyan' },
  { id: 3, label: 'System of Record', color: 'green' },
  { id: 4, label: 'App Legibility', color: 'blue' },
  { id: 5, label: 'Increasing Autonomy', color: 'purple' },
  { id: 6, label: 'Entropy & GC', color: 'rose' },
  { id: 7, label: 'Human Legibility', color: 'teal' },
  { id: 8, label: 'Agility', color: 'orange' },
]

const perspectiveColorMap = {
  amber:  { active: 'border-amber-400 bg-amber-500/20 text-amber-300',   dim: 'border-amber-400/20 bg-amber-500/5 text-amber-300/30' },
  cyan:   { active: 'border-cyan-400 bg-cyan-500/20 text-cyan-300',      dim: 'border-cyan-400/20 bg-cyan-500/5 text-cyan-300/30' },
  green:  { active: 'border-green-400 bg-green-500/20 text-green-300',   dim: 'border-green-400/20 bg-green-500/5 text-green-300/30' },
  blue:   { active: 'border-blue-400 bg-blue-500/20 text-blue-300',      dim: 'border-blue-400/20 bg-blue-500/5 text-blue-300/30' },
  purple: { active: 'border-purple-400 bg-purple-500/20 text-purple-300', dim: 'border-purple-400/20 bg-purple-500/5 text-purple-300/30' },
  rose:   { active: 'border-rose-400 bg-rose-500/20 text-rose-300',      dim: 'border-rose-400/20 bg-rose-500/5 text-rose-300/30' },
  teal:   { active: 'border-teal-400 bg-teal-500/20 text-teal-300',      dim: 'border-teal-400/20 bg-teal-500/5 text-teal-300/30' },
  orange: { active: 'border-orange-400 bg-orange-500/20 text-orange-300', dim: 'border-orange-400/20 bg-orange-500/5 text-orange-300/30' },
}

function getFrontmatter(slide) {
  return slide?.meta?.slide?.frontmatter || {}
}

function getLayout(slide) {
  return getFrontmatter(slide).layout || ''
}

const currentSlideNo = computed(() => nav.value?.currentSlideNo || 1)
const allSlides = computed(() => nav.value?.slides || [])

const sectionStarts = computed(() => {
  const all = allSlides.value
  let sec2 = -1, sec3 = -1, sec4 = -1
  let lastPerspective = -1

  for (const s of all) {
    const layout = getLayout(s)
    if (layout === 'references' && sec2 === -1) sec2 = s.no
    if (layout === 'perspective') {
      if (sec3 === -1) sec3 = s.no
      lastPerspective = s.no
    }
  }

  if (lastPerspective > 0) {
    for (const s of all) {
      if (s.no > lastPerspective && getLayout(s) !== 'perspective') {
        sec4 = s.no
        break
      }
    }
  }

  return { 1: 1, 2: sec2, 3: sec3, 4: sec4 }
})

const currentSection = computed(() => {
  const no = currentSlideNo.value
  const starts = sectionStarts.value
  if (starts[4] > 0 && no >= starts[4]) return 4
  if (starts[3] > 0 && no >= starts[3]) return 3
  if (starts[2] > 0 && no >= starts[2]) return 2
  return 1
})

const isSection3 = computed(() => currentSection.value === 3)

const activeIds = computed(() => {
  const all = allSlides.value
  const current = all.find(s => s.no === currentSlideNo.value)
  const active = getFrontmatter(current).active
  if (!active) return []
  return String(active).split(',').map(Number)
})

function goToSection(id) {
  const target = sectionStarts.value[id]
  if (target > 0 && nav.value) nav.value.go(target)
}

function goToPerspective(perspectiveId) {
  const all = allSlides.value
  for (const s of all) {
    if (getLayout(s) === 'perspective') {
      const fm = getFrontmatter(s)
      const ids = String(fm.active || '').split(',').map(Number)
      if (ids.length === 1 && ids[0] === perspectiveId) {
        if (nav.value) nav.value.go(s.no)
        return
      }
    }
  }
}

function getSectionClasses(id) {
  const isActive = currentSection.value === id
  return isActive
    ? 'border border-white/30 bg-white/10 text-white font-bold'
    : 'border border-white/10 bg-white/5 text-white/30 hover:text-white/50'
}

function getPerspectiveClasses(p) {
  const isActive = activeIds.value.includes(p.id)
  const colors = perspectiveColorMap[p.color]
  return isActive
    ? colors.active + ' font-bold scale-105'
    : colors.dim + ' hover:opacity-70'
}
</script>

<template>
  <div class="global-top-banner">
    <div class="flex items-center gap-1.5 px-4 pt-2">
      <span
        v-for="s in sections"
        :key="s.id"
        :class="getSectionClasses(s.id)"
        class="rounded px-2 py-0.5 text-xs cursor-pointer transition-all duration-200"
        @click="goToSection(s.id)"
      >
        {{ s.label }}
      </span>
    </div>

    <div v-if="isSection3" class="grid grid-cols-4 gap-1 px-4 pt-1.5">
      <span
        v-for="p in perspectives"
        :key="p.id"
        :class="getPerspectiveClasses(p)"
        class="border rounded px-1.5 py-0.5 text-xs cursor-pointer transition-all duration-300"
        @click="goToPerspective(p.id)"
      >
        {{ p.id }}. {{ p.label }}
      </span>
    </div>
  </div>
</template>
