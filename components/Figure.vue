<script setup lang="ts">
// Image neobrutal. `alt` est obligatoire : chaque image doit être décrite.
// <Figure src="/images/inr/odd.webp" alt="Les 17 ODD" caption="..." h="18rem" />
// `bare` retire le cadre (pour les illustrations détourées, ex. bitmojis).
const props = defineProps<{
  src: string
  alt: string
  caption?: string
  h?: string
  bare?: boolean
  tilt?: 'l' | 'r'
}>()

// Préfixe les chemins absolus avec la base (ex. /developper-avec-conscience/ sur GitHub Pages)
const resolvedSrc = props.src.startsWith('/')
    ? import.meta.env.BASE_URL + props.src.slice(1)
    : props.src
</script>

<template>
  <figure class="nb-figure" :class="[{ 'is-bare': props.bare }, props.tilt ? `nb-tilt-${props.tilt}` : '']">
    <img :src="resolvedSrc" :alt="props.alt" :style="{ maxHeight: props.h ?? '20rem' }" loading="lazy">
    <figcaption v-if="props.caption">{{ props.caption }}</figcaption>
  </figure>
</template>

<style scoped>
.nb-figure {
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.nb-figure img {
  max-width: 100%;
  object-fit: contain;
  border: var(--nb-border);
  box-shadow: var(--nb-shadow);
  background: var(--nb-white);
}

.nb-figure.is-bare img {
  border: none;
  box-shadow: none;
  background: transparent;
}

.nb-figure figcaption {
  margin-top: 0.7rem;
  font-size: 0.85rem;
  font-weight: 600;
  text-align: center;
}
</style>