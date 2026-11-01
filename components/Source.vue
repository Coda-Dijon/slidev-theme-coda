<script setup lang="ts">
// Crédit de source en bas de slide.
// <Source href="https://..." >Texte</Source>
const props = defineProps<{
  href: string
}>()
</script>

<template>
  <div class="nb-source">
      Source : <a :href="props.href" target="_blank">
      <slot/>
    </a>
  </div>
</template>

<style scoped>
.nb-source {
  position: absolute;
  left: 3.5rem;
  bottom: 0.9rem;
  font-size: 0.72rem;
  font-weight: 600;
  background: var(--nb-white);
  color: var(--nb-navy);
  border: 2px solid var(--nb-ink);
  padding: 0.1rem 0.5rem;
}

.nb-source a {
  color: inherit;
  text-decoration-thickness: 2px;
}
</style>