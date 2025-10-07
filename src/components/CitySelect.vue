<script setup>
import locationIcon from "../assets/Location.svg";
import Button from "./Button.vue";

const emit = defineEmits(["select-city"]);

function select() {
  emit("select-city", "London");
}
</script>
<template>
  <Button @click="select()">
    <img :src="locationIcon" alt="Location" />
    Изменить город
  </Button>
  <input />
  <Button> Сохранить </Button>
</template>
