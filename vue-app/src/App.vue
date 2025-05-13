<script setup>
import CitySelect from "./components/CitySelect.vue";
import Stat from "./components/Stat.vue";
import { computed, ref } from "vue";


let savedCity = ref("Moskov");

let data = ref({
  humidity: 90
})

// let dataModified = ref({
//   label: "Влажнасть",
//   stat: "90%"
// });

const dataModified = computed(() => {

  return {
    label: "Влажнасть",
    stat: data.value.humidity + "%",
  };
});


function getCity(City) {
  savedCity.value = City;
  data.value.humidity = 20;
}

// const user = {
//   name: "Anton",
// }
// const handler = {
//   get(target, prop, receiver)  {
//     console.log("Get value");
//     return target[prop];
// },
//   set(obj, prop, value) {
//     if (prop == "name") {
//       console.log("Set value");
//       obj[prop] = value;
//       return true;
//     }

//     },
// }
</script>

<template>


  <main class="main">
    {{ savedCity }}
   
    <Stat v-bind="dataModified" />
    <Stat v-bind="data" />
    <Stat label="Осадки" stat="10%" />
    <CitySelect @select-city="getCity" />
  </main>



</template>

<style scoped>
main {
  padding: 60px 50px;
  border-radius: 25px;
  background-color: var(--color-bg-main);
  display: grid;
}
</style>
