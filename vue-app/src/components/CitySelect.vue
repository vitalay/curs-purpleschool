<script setup>
import IconLocation from "../icons/IconLocation.vue";
import Button from "./Button.vue";
import Input from "./Input.vue";

const emit = defineEmits(["select-city"]);

function select() {
  emit("select-city", "Moscow");

}
</script>

<template>
  <Button @click="select()">
    <IconLocation />
    Изминить город
  </Button>
  <Input />
  <Button>Сохранить</Button>
</template>