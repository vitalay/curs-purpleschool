<script setup>
// const props = defineProps(['value']);
// const emit = defineEmits(['update:value']);
const data = defineModel({ 
  type: String, 
  required: true, 
});


</script>


<template>
  <input 
  class="input" 
  v-model="data"

  />
</template>
<style scoped>
.input {
  color: white;
  border-radius: 10px;
  background: var(--color-bg-card);
  box-shadow: 1px 2px 4px 0px var(--color-bg-main);
  border: none;
  font-size: 18px;
  height: 53px;
  width: 260px;


  padding: 15px 20px;
}

.input::placeholder {
  color: var(--color-text-placeholder);
}
</style>