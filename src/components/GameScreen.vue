<template>
  <div class="game-screen">
    <h2>Запомни слово</h2>
    <div class="grid">
      <WordCard
        v-for="(word, index) in words"
        :key="index"
        :word="word"
        @answered="onAnswer"
      />
    </div>
    <button @click="$emit('restart')">Начать заново</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import WordCard from './WordCard.vue';

const words = ref([
  { en: 'unlimited', ru: 'неограниченный' },
  { en: 'armour-piercer', ru: 'бронебойный' },
  { en: 'stamen', ru: 'тычинка' },
  { en: 'vino', ru: 'вино' },
  { en: 'pollination', ru: 'опыление' },
  { en: 'dust-coat', ru: 'пыльник' },
  { en: 'caravan vertebrates', ru: 'караван млекопитающих' },
  { en: 'автомобиль', ru: 'автомобиль' },
  { en: 'oscillotron', ru: 'осциллотрон' },
  { en: 'carom', ru: 'рикошет' },
  { en: 'свинец', ru: 'свинец' },
  { en: 'harem', ru: 'гарем' },
]);

function onAnswer(result) {
  // Тут можно добавить счёт, статистику и т.д.
}
</script>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
  margin: 20px;
}
.game-screen {
  padding: 20px;
}
</style>