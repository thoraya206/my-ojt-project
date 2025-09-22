<template>
  <div>
    <section class="hero">
      <h1>Your own Market</h1>
      <p>ةarketplace</p>
      <button class="btn">Get Started</button>
    </section>
    <DescHero />
    <MyList />
  </div>
</template>

<script>
import MyList from "@/components/MyList.vue";
import DescHero from "@/components/DescHero.vue";
import axios from "axios";

export default {
  data() {
    return {
      dataFromApi: null,
    };
  },
  components: {
    MyList,
    DescHero,
  },
  async created() {
    try {
      const res = await axios.post("https://atw-task.vercel.app/api/login", {
        email: "demo@demo.com",
        password: "123456789",
      });

      this.dataFromApi = res.data;
    } catch (error) {
      console.error("Error fetching API:", error);
    }
  },
};
</script>

<style scoped>
.hero {
  background: url("../assets/images.jpg") no-repeat center center/cover;
  color: rgb(2, 22, 121);
  text-align: center;
  padding: 5rem 2rem;
  margin: 0;
}

.hero .btn {
  margin-top: 1rem;
  padding: 0.7rem 1.5rem;
  background: rgb(2, 22, 121);
  border: none;
  border-radius: 5px;
  color: white;
}
</style>
