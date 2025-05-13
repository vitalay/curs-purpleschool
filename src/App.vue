<template>
  <StartScreen v-if="!gameStarted" @start="startGame" />
  <GameScreen v-else @restart="restartGame" />
</template>

<script setup>
import { ref } from 'vue';
import StartScreen from './components/StartScreen.vue';
import GameScreen from './components/GameScreen.vue';

const gameStarted = ref(false);

function startGame() {
  gameStarted.value = true;
}

function restartGame() {
  gameStarted.value = false;
}
</script>