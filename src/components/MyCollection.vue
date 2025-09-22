<template>
  <div class="card">
    <div class="collection-wrapper"></div>
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
});
</script>

<style scoped>
.card {
  background: #1e1e1e;
  color: white;
  padding: 1rem;
  border-radius: 10px;
  text-align: center;
  min-width: 200px;
  transition: transform 0.3s, box-shadow 0.3s;
  cursor: pointer;
}
.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.5);
}
</style>
