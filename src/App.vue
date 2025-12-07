<script setup>
import Stat from "./components/Stat.vue";
import CitySelect from "./components/CitySelect.vue";
import { ref } from "vue";

const data = {
  label: "Влажность",
  stat: "90 %",
};

let savedCity = ref("Moscow");

function getCity(city) {
  savedCity.value = city;
  console.log(city);
}
</script>

<template>
  <main class="main">
    {{ savedCity }}
    <Stat v-bind="data" />
    <Stat label="Осадки" stat="0 %" />
    <CitySelect @select-city="getCity" />
  </main>
</template>

<style scoped>
.main {
  background: var(--color-bg-main);
  padding: 60px 50px;
  border-radius: 25px;
}
</style>
