<script setup>
const id = "red";
const isAdmin = true;
</script>

<template>
  <header>logo</header>
  <header :class="`color- + ${id}`">Лoro</header>
  <main :id>KoHTеHT</main>
  <div>{{ isAdmin ? "Админ" : "Не aдмин" }}</div>
  <footer>{{ 10 + 20 }}</footer>
</template>

<style scoped></style>
