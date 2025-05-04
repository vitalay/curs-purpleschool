<script setup>
import Button from "./components/Button.vue";
import Stat from "./components/Stat.vue";
import IconLocation from "./icons/IconLocation.vue";
const data = {
  label: "Влажность",
  stat: "15%",

}

</script>

<template>


  <main class="main">

    <Stat v-bind="data" />
    <Stat label="Осадки" stat="10%" />
    <Button>
      <IconLocation />
      Сохранить
    </Button>
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
