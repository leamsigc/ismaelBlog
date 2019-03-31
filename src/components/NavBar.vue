<template>
  <div class="nav-container">
    <nav class="nav">
      <g-link class="nav__link" to="/">Home</g-link>
      <g-link class="nav__link" to="/about">About</g-link>
      <g-link class="nav__link" to="/Blog">Blog</g-link>
    </nav>
  </div>
</template>
<script>
export default {
  name: "NavBar"
};
</script>
<style>
.nav-container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 80px;
  transition: all 0.3s ease-in-out;
  z-index: 2000;
}
.nav__link {
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-weight: 300;
}
.nav__link:hover {
  color: #333;
}
</style>

