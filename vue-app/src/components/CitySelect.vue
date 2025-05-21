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

let city = ref("")

let isEdited = ref(false);

function select() {
  isEdited.value = false;
  emit("selectCity", "London");


}
function edit() {
isEdited.value = true;
}

// function updateCity(newCity) {
  
//   city.value = newCity;
  
// }
// {/* <Input
//   placeholder="Ведите город" 
//     : value="city" 
//     @update: value = "updateCity"
//   /> */}

</script>

<template>
  {{ city }}
  <div class="city-select">
    <div v-show="isEdited" class="city-input">
      <Input placeholder="Ведите город" v-model="city" />
      <Button @click="select()">Сохранить</Button>
    </div>

    <Button v-show="!isEdited" @click="edit()">
      <IconLocation />
      Изминить город
    </Button>
  </div>
</template>

<style scoped>
.city-input {
  display: flex;
  gap: 10px;
  align-items: center;
 
}
.city-select {
  width: 420px;
}

</style>