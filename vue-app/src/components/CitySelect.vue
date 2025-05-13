<script setup>
import IconLocation from "../icons/IconLocation.vue";
import Button from "./Button.vue";
import Input from "./Input.vue";
import { ref } from "vue";

const emit = defineEmits({

  selectCity(payload){
      // console.log(`ошибка: ${payload}`)
    return payload;
  }
});
let isEdited = ref(false);

function select() {
  isEdited.value = false;
  emit("selectCity", "London");

}
function edit() {
isEdited.value = true;
}
</script>

<template>
  <Button @click="edit()">
    <IconLocation />
    Изминить город
  </Button>
  <div v-if="isEdited">
  <Input />
  <Button @click="select()">Сохранить</Button>
  </div>
</template>