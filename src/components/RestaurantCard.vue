<template>
  <div class="card" @click="$emit('click-card')">
    <h3>{{ restaurant.name }}</h3>
  </div>
</template>

<script setup>
defineProps(['restaurant'])
</script>

<style scoped>
.card {
  padding: 15px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  cursor: pointer;
  transition: 0.2s;
}
.card:hover {
  transform: scale(1.03);
}
</style>
