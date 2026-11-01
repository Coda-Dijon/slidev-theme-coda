<script setup lang="ts">
// Quiz à choix multiple : la bonne réponse s'affiche au clic suivant.
// Usage (ajouter `clicks: 1` dans le frontmatter de la slide) :
// <Quiz question="..." :options="['a', 'b', 'c']" :answer="2" source="WWF 2019" />
//
// Accessibilité : la bonne réponse n'est pas signalée par la couleur seule
// (icône ✓ + libellé pour les lecteurs d'écran), et les mauvaises réponses restent lisibles (barrées, contraste conservé).
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'

const props = defineProps<{
  question: string
  options: string[]
  answer: number
  source?: string
}>()

const { $clicks } = useSlideContext()
const revealed = computed(() => $clicks.value >= 1)
</script>

<template>
  <div class="nb-quiz">
    <div class="nb-quiz-question">{{ props.question }}</div>
    <ol class="nb-quiz-options">
      <li
          v-for="(option, i) in props.options"
          :key="i"
          class="nb-quiz-option"
          :class="{
          'nb-fill-lime is-answer': revealed && i === props.answer,
          'nb-fill-white': !(revealed && i === props.answer),
          'is-wrong': revealed && i !== props.answer,
        }"
      >
        <span class="nb-quiz-letter nb-fill-navy" aria-hidden="true">{{ String.fromCharCode(65 + i) }}</span>
        <span class="nb-quiz-text">{{ option }}</span>
        <span v-if="revealed && i === props.answer" class="nb-quiz-check" aria-hidden="true">✓</span>
        <span v-if="revealed && i === props.answer" class="sr-only">Bonne réponse</span>
      </li>
    </ol>
    <div v-if="revealed && props.source" class="nb-quiz-source">Source : {{ props.source }}</div>
  </div>
</template>

<style scoped>
.nb-quiz-question {
  font-family: 'Archivo Black', sans-serif;
  font-size: 1.6rem;
  line-height: 1.2;
  margin-bottom: 1.5rem;
}

.nb-quiz-options {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.2rem;
  list-style: none;
  padding: 0;
}

.nb-quiz-options > li {
  padding-left: 1rem;
  margin: 0;
}

.nb-quiz-options > li::before {
  display: none;
}

.nb-quiz-option {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  border: var(--nb-border);
  box-shadow: var(--nb-shadow);
  padding: 0.8rem 1rem;
  font-size: 1.3rem;
  font-weight: 700;
  transition: transform 0.2s, box-shadow 0.2s;
}

.nb-quiz-letter {
  font-family: 'Archivo Black', sans-serif;
  width: 2rem;
  height: 2rem;
  flex-shrink: 0;
  display: grid;
  place-items: center;
}

.nb-quiz-check {
  margin-left: auto;
  font-family: 'Archivo Black', sans-serif;
  font-size: 1.4rem;
}

.nb-quiz-option.is-answer {
  background: var(--nb-accent);
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0 var(--nb-ink);
}

/* Mauvaises réponses : ombre retirée et texte barré, mais contraste intact */
.nb-quiz-option.is-wrong {
  box-shadow: none;
  border-style: dashed;
}

.nb-quiz-option.is-wrong .nb-quiz-text {
  text-decoration: line-through;
  text-decoration-thickness: 2px;
}

.nb-quiz-source {
  margin-top: 1.2rem;
  font-size: 0.95rem;
  font-style: italic;
}
</style>