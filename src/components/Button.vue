<script setup>
defineEmits(["start"]);
</script>

<template>
  <button class="button" @click="$emit('start')">Начать игру</button>
</template>

<style scoped>
.button {
  background-color: #008bfe;
  color: var(--color);
  height: 68px;
  width: 335px;
  border-radius: 100px;
  border: none;
  font-family: var(--font);
  font-weight: 400;
  font-size: 24px;
  cursor: pointer;
}
</style>
