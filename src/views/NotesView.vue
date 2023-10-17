<script setup>
import { computed } from 'vue'
import { ref } from 'vue'

const notes = {
  Symfony: 9,
  Integration: 16,
  Reseau: 13,
  Graphisme: 11,
  Anglais: 5,
  Allemand: 1,
  Mathematiques: 8,
  Physique: 10,
  Chimie: 10,
  Histoire: 12,
}

const mots = ["mot1", "mot2", "mot3", "mot4",]
const awesome = ref(true)

const moyenne = computed(() => {
  return (symfony + integration + reseau) / 3 
})
</script>

<template>
  <div class="about">
    <h1>This is the Notes page</h1>
    <ul>
      <template v-for="(note, key) in notes">
        <li>
          <span :class="{
            'text-red': note < 8,
            'text-orange': note < 10 && note >= 8,
            'text-green': note >= 10
          }">
            {{ key }}: {{ note }}
          </span>
        </li>
      </template>
    </ul>
    <!-- <p>
      La moyenne est de {{ moyenne }}
    </p> -->
    <button @click="awesome = !awesome">Basculer</button>

    <h1 v-if="awesome">Vue est magnifique!</h1>
    <h1 v-else>Oh non 😢</h1>
  </div>
</template>

<style>

.text-red {
  color: red;
}

.text-green {
  color: green;
}

.text-orange {
  color: orange;
}

@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
}

@media (max-width: 1024px) {
  .about {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding-top: 2rem;
  }
  
  ul {
    padding-top: 1rem;
    width: 100%;
    text-align: start;
  }
}
</style>