<template>
  <footer class="footer">
    <div class="links">
      <a href="#">Features</a>
      <a href="#">Services</a>
      <a href="#">Products</a>
      <a href="#">Resources</a>
    </div>
    <p>© 2025 NFT Marketplace. All rights reserved.</p>
  </footer>
</template>

<script>
export default {
  name: "FooterSection",
};
</script>

<style scoped>
.footer {
  background: linear-gradient(to top, rgb(2, 22, 121), #111);
  color: #fff;
  text-align: center;
  padding: 30px 20px;
  margin-top: 40px;
}

.links {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 15px;
  margin-bottom: 20px;
}

.links a {
  color: #fff;
  text-decoration: none;
}
</style>
