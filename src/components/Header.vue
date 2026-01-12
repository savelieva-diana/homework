<script setup>
import Score from "./Score.vue";

defineProps({
  score: Number,
});
</script>

<template>
  <div class="header">
    <p class="title">Запомни слово</p>
    <Score :score="score" />
  </div>
</template>

<style scoped>
.header {
  padding-bottom: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.title {
  font-family: var(--font);
  font-weight: 700;
  text-transform: uppercase;
}
</style>
