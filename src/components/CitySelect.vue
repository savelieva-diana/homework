<script setup>
import { ref } from "vue";
import locationIcon from "../assets/Location.svg";
import Button from "./Button.vue";
import Input from "./Input.vue";

const emit = defineEmits(["select-city"]);
let isEdited = ref(false);
let city = ref("Moscow");

function edit() {
  isEdited.value = true;
}

function select() {
  isEdited.value = false;
  emit("select-city", "London");
}
</script>

<template>
  <div class="city-select">
    <div v-if="isEdited" class="city-input">
      <Input placeholder="Введите город" v-model="city" />
      <Button @click="select()"> Сохранить </Button>
    </div>
    <Button v-else @click="edit()">
      <img :src="locationIcon" alt="Location" />
      Изменить город
    </Button>
  </div>
</template>

<style scoped>
.city-input {
  display: flex;
  gap: 12px;
}
.city-select {
  width: 420px;
}
</style>
