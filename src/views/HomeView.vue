<template>
  <div>
    <NavBar />

    <section class="hero">
      <h1>Your own Market</h1>
      <p>ةarketplace</p>
      <button class="btn">Get Started</button>
    </section>
    <DescHero />
    <MyList />
    <FooterSec />
    <!-- <h2>بيانات من الـ API:</h2>
    <pre>{{ dataFromApi }}</pre> -->
  </div>
</template>

<script>
import MyList from "@/components/MyList.vue";
import NavBar from "..//components/NavBar.vue";
// import MyList from "@/components/MyList.vue";
import FooterSec from "@/components/FooterSec.vue";
import DescHero from "@/components/DescHero.vue";
import axios from "axios";

export default {
  data() {
    return {
      dataFromApi: null,
    };
  },
  components: {
    NavBar,
    MyList,
    FooterSec,
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
