<template>
  <div id="app">
    <NavBar />
    <main>
      <router-view />
    </main>
    <FooterSec />
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import FooterSec from "./components/FooterSec.vue";

export default {
  name: "App",
  components: {
    NavBar,
    FooterSec,
  },
};
</script>
<style>
#app {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  margin: 0;
  padding: 0;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

main {
  flex: 1;
  margin: 0;
  background-color: linear-gradient(to bottom, #1a0033, #000);
}
</style>
