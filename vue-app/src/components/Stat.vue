<script setup>
const { label , stat } = defineProps({
  label: {
    type: String,
    required: true,
  },
  stat: {
    type: String,
    required: true,
}
});

</script>
<template>
  <div class="stat">
    <div class="stat-name">{{ label}}</div>
    <div class="stat-value">{{ stat }}</div>
  </div>
</template>

<style scoped>
.stat {
 display: flex;
 font-size: 28px;
 justify-content: space-between;
 gap: 10px;
}
.stat-name {
  font-weight: 700;
  text-transform: uppercase;
}
.stat-value {
  font-weight: 500;}
</style>