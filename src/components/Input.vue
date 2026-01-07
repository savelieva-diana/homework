<script setup>
const model = defineModel({ type: String, required: true });
</script>

<template>
  <input class="input" v-model="model" />
</template>

<style scoped>
.input {
  color: var(--primary);
  border-radius: 10px;
  background: var(--color-bg-card);
  box-shadow: 1px 2px 4px 0px var(--color-bg-main);
  border: none;
  height: 53px;
  width: 260px;
  font-size: 18px;
  font-family: var(--font);
  padding: 8px 16px;
}
.input::placeholder {
  color: var(--color-text-placeholder);
}
</style>
