<script setup>
import { ref, computed } from "vue";

// 样式
const recentArticlesWidth = ref(520);
const articleCardPadding = ref(10);
const articleCardWidth = computed(() => recentArticlesWidth.value - 2 * articleCardPadding.value);
const articleCardHeight = computed(() => (articleCardWidth.value * 2) / 9);

defineProps({
  articles: {
    type: Array,
    required: true,
  },
});
</script>

<template>
  <section class="recent-articles">
    <h2>Recent Articles</h2>
    <ul class="article-list">
      <li class="article-list__item" v-for="article in articles" :key="article.link">
        <article class="article-card">
          <img class="article-card__image" :src="article.imgUrl" alt="文章头图" />
          <div class="article-card__content">
            <h3 class="article-card__title">
              <a href="/article1">
                {{ article.title }}
                <span class="stretched-link"></span>
              </a>
            </h3>
            <p class="article-card__summary">{{ article.summary }}</p>
            <div class="article-card__meta">
              <span class="tag">{{ article.tag }}</span>
              <time :datetime="article.datetime">{{ article.datetime }}</time>
            </div>
          </div>
        </article>
      </li>
    </ul>
  </section>
</template>

<style scoped>
.recent-articles {
  width: v-bind(recentArticlesWidth + "px");
}

.article-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 15px;

  width: 100%;
}

.article-card {
  display: flex;
  flex-direction: row;
  gap: 20px;
  position: relative; /* 为 stretched-link 提供定位上下文 */
  height: v-bind(articleCardHeight + "px");
  width: v-bind(articleCardWidth + "px");
  align-items: center;
  padding: v-bind(articleCardPadding + "px");

  background: #c5bdbd9a;
  border-radius: 5px;
}

.article-card__image {
  height: 100%;
  aspect-ratio: 1;
  object-fit: cover;
}

.article-card__content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  flex: 1;
  height: 100%;
  min-width: 0;
}

.article-card__title {
  margin: 0;
  font-size: 1.1rem;
}

.article-card__title a {
  display: block;
  text-decoration: none;
  color: black;

  /* 解决溢出问题 */
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.article-card__summary {
  margin: 5px 0;
  font-size: 0.9rem;
  color: #555;

  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
  line-clamp: 2;
  line-height: 1.5;
  max-height: 3em;
}

.article-card__meta {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  font-size: 0.8rem;
  color: #777;
  margin-top: auto;
}

.stretched-link::after {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: -1; /* 为了调试，暂时设置为-1 */
}
</style>
