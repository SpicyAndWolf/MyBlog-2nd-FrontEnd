<script setup>
import { ref } from "vue";
import Navigation from "./components/Navigation.vue";
import UserInfo from "./components/UserInfo.vue";
import RecentArticles from "./components/RecentArticles.vue";

import img1 from "@/assets/images/articleThumb/1.png";
const articlesData = ref([
  {
    link: "/article1",
    imgUrl: img1,
    title: "文章1,这是一个标题很长的文章，很长很长，有多长呢，两三层楼那么长吧",
    tag: "tag1",
    datetime: "2025-09-29",
    summary:
      "文章1的简要概述，但是也不是很简要。这个也很长很长，很长很长，超级无敌长，长啊长啊！超级无敌长！超级超级无敌长！",
  },
  {
    link: "/article2",
    imgUrl: "2",
    title: "文章2",
    tag: "tag2",
    datetime: "2025-09-28",
    summary: "文章2的简要概述",
  },
]);
</script>

<template>
  <div class="app-layout">
    <Navigation></Navigation>
    <main class="main-content">
      <UserInfo></UserInfo>
      <RecentArticles :articles="articlesData"></RecentArticles>
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
  align-items: center;
  justify-content: space-around;
  padding: 0 20px;
}
</style>
