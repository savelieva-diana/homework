<script setup>
const props = defineProps(["score"]);
</script>

<template>
  <div class="score">
    {{ props.score }} <img src="../assets/Heart.png" alt="heart" />
  </div>
</template>

<style scoped>
.score {
  font-family: var(--font);
  font-weight: 700;
  color: #008bfe;
  size: 16px;
  background-color: #cce8ff;
  width: 110px;
  height: 48px;
  border-radius: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 49px;
  right: 66px;
  gap: 10px;
}
</style>
