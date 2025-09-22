<template>
  <section class="collections">
    <h2>Collections</h2>

    <div class="collection-wrapper">
      <button class="scroll-btn left" @click="scrollLeft">⬅️</button>

      <div class="collection-scroll" ref="scrollContainer">
        <MyCollection
          v-for="c in tasks"
          :key="c.id"
          :title="c.title"
          :description="c.description"
        />
      </div>

      <button class="scroll-btn right" @click="scrollRight">➡️</button>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";
import MyCollection from "./MyCollection.vue";

const tasks = ref([]);
const scrollContainer = ref(null);

onMounted(async () => {
  try {
    const token = localStorage.getItem("token");
    if (!token) return;
    const res = await axios.get("https://atw-task.vercel.app/api/tasks", {
      headers: { Authorization: `Bearer ${token}` },
    });
    tasks.value = res.data.data;
  } catch (err) {
    console.error("Error fetching tasks:", err);
  }
});

function scrollLeft() {
  scrollContainer.value.scrollBy({
    left: -250,
    behavior: "smooth",
  });
}
function scrollRight() {
  scrollContainer.value.scrollBy({
    left: 250,
    behavior: "smooth",
  });
}
</script>

<style scoped>
.collections {
  padding: 2rem;
  background: black;
  color: white;
}

.collection-wrapper {
  position: relative;
  display: flex;
  align-items: center;
}

.collection-scroll {
  display: flex;
  gap: 1rem;
  overflow-x: auto;
  scroll-behavior: smooth;
  padding: 1rem;
  scrollbar-width: none;
}
.collection-scroll::-webkit-scrollbar {
  display: none;
}

.scroll-btn {
  background: rgba(0, 0, 0, 0.6);
  border: none;
  /* color: white; */
  font-size: 20px;
  cursor: pointer;
  padding: 10px;
  border-radius: 50%;
  position: absolute;
  z-index: 10;
  top: 50%;
  transform: translateY(-50%);
}

.scroll-btn.left {
  left: 0;
}

.scroll-btn.right {
  right: 0;
}
</style>
