<script setup>
import { ref } from "vue";
import locationIcon from "../assets/Location.svg";
import Button from "./Button.vue";

const emit = defineEmits(["select-city"]);

let isEdited = ref(false);

function edit() {
  isEdited.value = true;
}

function select() {
  isEdited.value = false;
  emit("select-city", "London");
}
</script>
<template>
  {{ isEdited }}
  <Button @click="edit()">
    <img :src="locationIcon" alt="Location" />
    Изменить город
  </Button>
  <input />
  <Button @click="select()"> Сохранить </Button>
</template>
