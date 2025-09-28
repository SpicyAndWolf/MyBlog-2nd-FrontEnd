<script setup>
import myLogo from "@/assets/logo.jpg";
</script>

<template>
  <nav class="navigation">
    <div class="logo-container">
      <img :src="myLogo" alt="" />
      <span>SpiceNest</span>
    </div>
    <a href="/article">文章</a>
  </nav>
</template>

<style scoped>
.navigation {
  height: 50px;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.logo-container {
  height: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 10px;
  margin-left: 20px;
}

.logo-container img {
  height: 100%;
}
</style>
