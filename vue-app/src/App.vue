<script setup>
let a = 10;
let b = 'Привет';
let c = true;

let e = "<a href='/'>Сылка</a>"
</script>

<template>
  <header>{{ a + ' '  + b + ' ' + c}}</header>
  <main>{{b}}</main>
  <div v-html="e"></div>
  <footer>{{ c }}</footer>
</template>

<style scoped></style>
