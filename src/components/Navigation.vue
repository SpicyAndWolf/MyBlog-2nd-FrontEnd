<script setup>
import myLogo from "@/assets/logo.jpg";

// 博客名称
const blogName = "SPICE-NEST";
const blogNameChars = blogName.split("");
</script>

<template>
  <nav class="navigation">
    <a href="/" class="logo-container">
      <img :src="myLogo" alt="SpiceNest Logo" />
      <div class="blog-name-container">
        <span v-for="(char, index) in blogNameChars" :key="index" class="char">
          {{ char }}
        </span>
      </div>
    </a>
    <ul class="navigation-links">
      <li><a href="/article">文章</a></li>
    </ul>
  </nav>
</template>

<style scoped>
@font-face {
  font-family: "Aurora";
  src: url("@/assets/fonts/Aurora.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}

.navigation {
  height: 50px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  padding: 0 20px;
}

.logo-container {
  height: 85%;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 10px;
  text-decoration: none;
}

.logo-container img {
  height: 100%;
  aspect-ratio: 1;
  object-fit: cover;
  border-radius: 50%;
  transition: box-shadow 0.3s;
}

.logo-container:hover img {
  box-shadow: 0 0 10px 1.5px #e294aad3;
}

.blog-name-container {
  display: flex;
  margin-top: 5px;
}

.logo-container .char {
  display: inline-block;
  color: #333;
  font-size: 1.2rem;
  font-weight: bold;
  font-family: "Aurora", serif;
  transition: color 0.4;
}

.logo-container:hover .char {
  color: #c44569;
}

.navigation-links {
  display: flex;
  flex-direction: row;
  flex: 1;
  justify-content: center;
  gap: 30px;
  list-style: none;
  padding: 0;
  margin: 0;
}

.navigation-links a {
  text-decoration: none;
  color: #555;
  font-weight: 500;
  font-size: 18px;
  transition: color 0.3s;
}

.navigation-links a:hover {
  color: #c44569;
}
</style>
