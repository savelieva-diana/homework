<script setup>
import { ref } from "vue";
import Button from "./components/Button.vue";
import Score from "./components/Score.vue";
import Card from "./components/Card.vue";

const score = 100;
const gameStarted = ref(false);
</script>

<template>
  <div v-if="!gameStarted">
    <p class="word">Запомни слово</p>
    <Score :score="score" />
    <Button @start="gameStarted = true" />
  </div>
  <Card v-if="gameStarted" />
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
