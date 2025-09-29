<script setup>
import rainGif from "@/assets/rain.jfif";
import avatar from "@/assets/avatar.JPG";
</script>

<template>
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
</template>

<style scoped>
.user-info {
  display: flex;
  width: 300px;
  min-width: 200px;
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
