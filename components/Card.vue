<script setup lang="ts">
// Boîte neobrutal : <Card title="..." color="magenta" tilt="l">contenu</Card>
// Couleurs : navy, lime, magenta, violet, blue, lavender, white
const props = defineProps<{
  title?: string
  color?: string
  tilt?: 'l' | 'r'
}>()
</script>

<template>
  <div
      class="nb-card"
      :class="[`nb-fill-${props.color ?? 'white'}`, props.tilt ? `nb-tilt-${props.tilt}` : '']"
  >
    <div v-if="props.title" class="nb-card-title">{{ props.title }}</div>
    <div class="nb-card-body"><slot /></div>
  </div>
</template>

<style scoped>
.nb-card {
  border: var(--nb-border);
  box-shadow: var(--nb-shadow);
  padding: 1rem 1.2rem;
}

.nb-card-title {
  font-family: 'Archivo Black', sans-serif;
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  padding-bottom: 0.4rem;
  border-bottom: 3px solid currentColor;
}

.nb-card-title:last-child {
  margin-bottom: 0;
  padding-bottom: 0;
  border-bottom: none;
}

.nb-card-body :deep(p),
.nb-card-body :deep(li) {
  font-size: 1rem;
}
</style>