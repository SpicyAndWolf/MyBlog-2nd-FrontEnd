<script setup>
import Navigation from "./components/Navigation.vue";
import rainGif from "@/assets/rain.jfif";
import avatar from "@/assets/avatar.JPG";
</script>

<template>
  <div class="app-layout">
    <Navigation></Navigation>
    <main class="main-content">
      <section class="user-info">
        <div class="rain-gif">
          <img :src="rainGif" />
        </div>
        <div class="avatar">
          <img :src="avatar" />
        </div>
        <nav class="contact-links">
          <a href="/">bilibili</a>
          <a href="/">bangumi</a>
        </nav>
      </section>
      <section class="recent-articles">
        <h2>Recent Articles</h2>
        <ul>
          <li><a href="/article1">文章1</a></li>
          <li><a href="/article2">文章2</a></li>
          <li><a href="/article3">文章3</a></li>
        </ul>
      </section>
    </main>
  </div>
</template>

<style scoped>
.app-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.main-content {
  display: flex;
  flex-direction: row;
  flex: 1;
}

.user-info {
  display: flex;
  width: 300px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.rain-gif {
  width: 80%;
}

.rain-gif img {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.avatar {
  width: 80%;
}

.avatar img {
  width: 100%;
  aspect-ratio: 1;
  object-fit: cover;
  border-radius: 50%;
}
</style>
