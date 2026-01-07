<script setup></script>
<template>
  <button class="button">
    <div><slot name="icon"></slot></div>
    <slot />
  </button>
</template>
<style scoped>
.button {
  background: var(--gradient);
  font-family: var(--font);
  color: var(--color-primary);
  border: none;
  border-radius: 10px;
  padding: 14px;
  font-size: 20px;
  font-weight: 600;
  cursor: pointer;
  display: flex;
  gap: 9px;
  align-items: center;
  width: 100%;
  justify-content: center;
  height: 53px;
}
.button:hover {
  background: var(--gradient-inverted);
}
</style>
