<script setup>


</script>


<template>
  <button class="button">

    
    <slot />
  </button>
</template>

<style scoped>
.button {
  border: none;
  background: var(--gradient);
  font-size: 20px;
  font-weight: 600;
  border-radius: 10px;
  padding: 14px;
  font-family: var(--font);
  color: var(--primary);
  cursor: pointer;

}

.button:hover {
  background: var(--gradient-inverted);
}
</style>