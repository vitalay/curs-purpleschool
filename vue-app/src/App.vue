<script setup>
import CitySelect from "./components/CitySelect.vue";
import Stat from "./components/Stat.vue";


const data = {
  label: "Влажность",
  stat: "15%",

}
function getCity(City) {
  console.log(City);
}
</script>

<template>


  <main class="main">
    
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
