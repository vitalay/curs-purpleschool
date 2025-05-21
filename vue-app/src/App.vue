<script setup>
// import My from "./components/My.vue";
import CitySelect from "./components/CitySelect.vue";
import Stat from "./components/Stat.vue";

import { computed, ref } from "vue";



// const myy = {
//   mi: 'Moskov',
//   ci: '80%',
 
// }

let savedCity = ref("Moskov");

let data = ref({
  humidity: 90,
  rain: 0,
  wind: 3
});


// let dataModified = ref({
//   label: "Влажнасть",
//   stat: "90%"
// });



const dataModified = computed(() => {

  return [
    {
    label: "Влажнасть",
    stat: data.value.humidity + "%",
    },
  {
    label: "Осадки",
    stat: data.value.rain + "%",
    },
  {
    label: "Ветер",
    stat: data.value.wind + "км/ч",
    },
  ];

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
    <div id="city"> {{ savedCity }} </div>
    <!-- <My @citi-select="getCit" />
    <My :mi="myy.mi" :ci="myy.ci" />
    <My mi="жопа" ci="100%" /> -->
    <Stat v-for="item in dataModified" v-bind="item" :key="item.label" />

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
