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
}
</style>
<!-- 
<template>
  <section class="collections">
    <h2>Collections</h2>
    <div class="collection-items">
      <div class="collection-card">
        <img src="https://via.placeholder.com/200" alt="NFT 1">
        <p>XO Girls NFT</p>
      </div>
      <div class="collection-card">
        <img src="https://via.placeholder.com/200" alt="NFT 2">
        <p>Game Character</p>
      </div>
      <div class="collection-card">
        <img src="https://via.placeholder.com/200" alt="NFT 3">
        <p>Monkey Collection</p>
      </div>
    </div>
  </section>
</template>

<script>
export default { name: "CollectionsSection" };
</script>

<style scoped>
.collections {
  padding: 40px 20px;
}
.collections h2 {
  margin-bottom: 20px;
  text-align: center;
}
.collection-items {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}
.collection-card {
  background: #1a1a1a;
  padding: 15px;
  border-radius: 10px;
  width: 200px;
  text-align: center;
}
.collection-card img {
  width: 100%;
  border-radius: 10px;
}
</style>
 -->
