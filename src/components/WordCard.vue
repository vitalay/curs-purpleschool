<template>
  <div class="card">
    <div class="content">
      <p v-if="!flipped">{{ word.en }}</p>
      <div v-else>
        <p>{{ word.ru }}</p>
        <div v-if="!answered" class="actions">
          <button @click="mark(true)">✔️</button>
          <button @click="mark(false)">❌</button>
        </div>
        <p v-else>{{ resultText }}</p>
      </div>
    </div>
    <button v-if="!answered" @click="flip">Перевести</button>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const props = defineProps({ word: Object });
const emit = defineEmits(['answered']);

const flipped = ref(false);
const answered = ref(false);
const correct = ref(false);

const resultText = computed(() => correct.value ? 'Завершено' : 'Ошибка');

function flip() {
  flipped.value = true;
}

function mark(success) {
  correct.value = success;
  answered.value = true;
  emit('answered', success);
}
</script>

<style scoped>
.card {
  background: #fff;
  padding: 16px;
  border: 1px solid #ddd;
  border-radius: 6px;
  text-align: center;
}
.actions button {
  margin: 5px;
}
</style>