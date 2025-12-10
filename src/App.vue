<script setup>
import { ref } from "vue";
import Button from "./components/Button.vue";
import Score from "./components/Score.vue";
import Card from "./components/Card.vue";

const score = ref(100);
const gameStarted = ref(false);
const card = ref({
  word: "unadmitted",
  translation: "недопущенный",
  state: "closed",
  status: "pending",
});
</script>

<template>
  <div>
    <p class="word">Запомни слово</p>
    <Score :score="score" />
    <div v-if="!gameStarted">
      <Button @start="gameStarted = true" />
    </div>
    <Card v-if="gameStarted" :card="card" />
  </div>
</template>

<style scoped>
.word {
  font-family: var(--font);
  font-weight: 700;
  text-transform: uppercase;
  position: fixed;
  top: 49px;
  left: 66px;
}
</style>
