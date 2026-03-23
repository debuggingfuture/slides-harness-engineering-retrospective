<script setup>
defineProps({
  active: {
    type: [Number, String],
    default: 0,
  },
})
</script>

<template>
  <div class="slidev-layout perspective-layout">
    <slot />
  </div>
</template>

<style scoped>
.perspective-layout {
  padding: 5rem 2rem 1.5rem;
}
</style>
