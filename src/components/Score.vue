<script setup>
defineProps({
  score: Number,
});
</script>

<template>
  <div class="score">
    {{ score }} <img src="../assets/Heart.png" alt="heart" />
  </div>
</template>

<style scoped>
.score {
  font-family: var(--font);
  font-weight: 700;
  color: #008bfe;
  font-size: 16px;
  background-color: #cce8ff;
  width: 110px;
  height: 48px;
  border-radius: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  cursor: pointer;
}
</style>
