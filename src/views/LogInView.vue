<template>
  <NavBar />
  <div class="login-container">
    <form class="login-box" @submit.prevent="handleLogin">
      <h2>Welcome back</h2>
      <p>sign in to access your market</p>
      <input
        v-model="email"
        type="email"
        placeholder="Enter your email"
        required
      />
      <input
        v-model="password"
        type="password"
        placeholder="Password"
        required
      />
      <button type="submit">Sign In</button>
    </form>
  </div>
  <FooterSec />
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";
import axios from "axios";
import NavBar from "@/components/NavBar.vue";
import FooterSec from "@/components/FooterSec.vue";

const router = useRouter();
const email = ref("");
const password = ref("");

const handleLogin = async () => {
  try {
    const res = await axios.post("https://atw-task.vercel.app/api/login", {
      email: email.value,
      password: password.value,
    });
    localStorage.setItem("token", res.data.data.token);
    router.push("/");
  } catch {
    alert("Login failed");
  }
};
</script>

<style scoped>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background: linear-gradient(to bottom, #1a0033, #000);
}

.login-box {
  background: #1e1e2f;
  padding: 2rem;
  border-radius: 10px;
  color: white;
  width: 300px;
  text-align: center;
}

.login-box input {
  display: block;
  width: 100%;
  margin: 0.5rem 0;
  padding: 0.7rem;
  border: none;
  border-radius: 5px;
}

.login-box button {
  margin-top: 1rem;
  width: 100%;
  padding: 0.7rem;
  background: rgb(2, 22, 121);
  border: none;
  border-radius: 5px;
  color: white;
}
.login-box p {
  color: #212129;
}
</style>
