<script setup lang="ts">
// Slide d'ouverture d'une séquence du cours.
// Frontmatter : num, color, duration, objective
// Le bloc numéro inverse les couleurs du fond (texte = couleur de la séquence),
// ce qui garde un contraste ≥ 4,5:1 pour toutes les couleurs de la palette.
// Son ombre utilise l'accent lime.
import { computed } from 'vue'

const props = defineProps<{
  num?: string | number
  color?: string
  duration?: string
  objective?: string
}>()

const color = computed(() => props.color ?? 'lime')
</script>

<template>
  <div class="slidev-layout nb-section" :class="`nb-fill-${color}`">
    <div
        v-if="props.num !== undefined"
        class="nb-section-num"
        :style="{
        background: `var(--nb-on-${color})`,
        color: `var(--nb-${color})`,
        boxShadow: '6px 6px 0 var(--nb-accent)',
      }"
    >
      {{ String(props.num).padStart(2, '0') }}
    </div>
    <div class="nb-section-body">
      <slot />
      <div class="nb-section-meta">
        <span v-if="props.duration" class="nb-chip nb-fill-white">⏱ {{ props.duration }}</span>
        <span v-if="props.objective" class="nb-chip nb-fill-white">🎯 {{ props.objective }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.nb-section {
  display: flex;
  align-items: center;
  gap: 3rem;
}

.nb-section-num {
  font-family: 'Archivo Black', sans-serif;
  font-size: 9rem;
  line-height: 1;
  padding: 1rem 1.5rem;
  border: var(--nb-border);
  transform: rotate(-1.5deg);
}

.nb-section-body :deep(h1) {
  color: inherit;
  font-size: 3rem;
}

.nb-section-body :deep(p) {
  font-size: 1.3rem;
  font-weight: 600;
}

.nb-section-meta {
  display: flex;
  gap: 1rem;
  margin-top: 1.5rem;
}

.nb-chip {
  border: var(--nb-border);
  box-shadow: var(--nb-shadow-sm);
  padding: 0.3rem 0.8rem;
  font-weight: 700;
}

/* Sur fond sombre, les ombres navy disparaissent : on passe au lime */
:is(.nb-fill-navy, .nb-fill-violet) .nb-chip {
  box-shadow: 2px 2px 0 var(--nb-accent);
}
</style>