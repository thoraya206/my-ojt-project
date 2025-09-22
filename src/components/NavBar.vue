<template>
  <nav class="navbar">
    <div class="logo">
      <img src="../assets/marketlogo.jpg" alt="Logo" />
    </div>
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Blog</a></li>
      <li><a href="#">Cart</a></li>
      <li><router-link to="/login">Login</router-link></li>
      <li><button class="btn">Sign Up</button></li>
    </ul>
  </nav>
</template>

<style scoped>
.navbar {
  /* display: flex;
  justify-content: space-between;
  padding: 15px 30px;
  color: rgb(28, 103, 54);
  background: transparent; */
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  display: flex;

  justify-content: space-around;
  align-items: center;
  padding: 6px 30px;

  background-color: rgba(0, 0, 0, 0.7);
  color: white;
  z-index: 1000;
}

.navbar ul {
  display: flex;
  gap: 16px;
  list-style: none;
  color: blueviolet;
  /* height: 100px; */
  width: 300px;
  align-items: center;
  /* background-color: ؤ; */
}

.navbar a,
.navbar .btn {
  color: rgb(255, 255, 255);
  text-decoration: none;
}

.btn {
  /* background: rgb(177, 104, 152);
  /* color: black; */
  /* padding: 20px; */
  border-radius: 5px;
  /* padding-left: 20px; */
  /* cursor: pointer;  */
  background: rgb(2, 22, 121);
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 6px;
  cursor: pointer;
  width: 80px;
}
.navbar img {
  height: 30px;
  width: 30px;
}
</style>
