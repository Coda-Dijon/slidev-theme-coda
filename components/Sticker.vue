<script setup lang="ts">
// Étiquette inclinée : <Sticker color="magenta">À retenir</Sticker>
const props = defineProps<{
  color?: string
  rotate?: number
}>()
</script>

<template>
  <span
      class="nb-sticker"
      :class="`nb-fill-${props.color ?? 'magenta'}`"
      :style="{ transform: `rotate(${props.rotate ?? -2}deg)` }"
  ><slot /></span>
</template>

<style scoped>
.nb-sticker {
  display: inline-block;
  font-family: 'Archivo Black', sans-serif;
  font-size: 0.95rem;
  text-transform: uppercase;
  border: var(--nb-border);
  box-shadow: var(--nb-shadow-sm);
  padding: 0.2rem 0.7rem;
}
</style>