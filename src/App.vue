<script setup>
import { ref } from "vue";
import Button from "./components/Button.vue";
import Header from "./components/Header.vue";
import Card from "./components/Card.vue";

const score = ref(100);
const gameStarted = ref(false);
const cards = ref([
  {
    id: 1,
    number: "01",
    word: "unadmitted",
    translation: "недопущенный",
    state: "closed",
    status: "pending",
  },
  {
    id: 2,
    number: "02",
    word: "armour-piercer",
    translation: "бронебойный",
    state: "closed",
    status: "pending",
  },
  {
    id: 3,
    number: "03",
    word: "stamen",
    translation: "тычинка",
    state: "closed",
    status: "pending",
  },
  {
    id: 4,
    number: "04",
    word: "vino",
    translation: "вино",
    state: "closed",
    status: "pending",
  },
  {
    id: 5,
    number: "05",
    word: "pollination",
    translation: "опыление",
    state: "closed",
    status: "pending",
  },
  {
    id: 6,
    number: "06",
    word: "dust-coat",
    translation: "пыльник",
    state: "closed",
    status: "pending",
  },
  {
    id: 7,
    number: "07",
    word: "camel caravan",
    translation: "караван верблюдов",
    state: "closed",
    status: "pending",
  },
  {
    id: 8,
    number: "08",
    word: "automobile",
    translation: "автомобиль",
    state: "closed",
    status: "pending",
  },
  {
    id: 9,
    number: "09",
    word: "oscillotron",
    translation: "осциллотрон",
    state: "closed",
    status: "pending",
  },
  {
    id: 10,
    number: "10",
    word: "carom",
    translation: "карамболь",
    state: "closed",
    status: "pending",
  },
  {
    id: 11,
    number: "11",
    word: "lead",
    translation: "свинец",
    state: "closed",
    status: "pending",
  },
  {
    id: 12,
    number: "12",
    word: "harem",
    translation: "гарем",
    state: "closed",
    status: "pending",
  },
]);
</script>

<template>
  <div class="layout">
    <Header :score="score" />

    <div class="card-grid" v-if="gameStarted">
      <Card v-for="card in cards" :key="card.id" :card="card" />
    </div>

    <div v-else class="start-screen">
      <Button @start="gameStarted = true" />
    </div>
  </div>
</template>

<style scoped>
.layout {
  padding: 50px 65px;
}

.start-screen {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.card-grid {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 25px;
}
</style>
