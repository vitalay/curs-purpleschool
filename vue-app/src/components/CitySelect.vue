<script setup>
import IconLocation from "../icons/IconLocation.vue";
import Button from "./Button.vue";
import Input from "./Input.vue";

const emit = defineEmits({

  selectCity(payload){
      // console.log(`ошибка: ${payload}`)
    return payload;
  }
});

function select() {
  emit("selectCity", "London");

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