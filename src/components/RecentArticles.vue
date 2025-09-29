<script setup>
import { ref, computed } from "vue";

defineProps({
  articles: {
    type: Array,
    required: true,
  },
});
</script>

<template>
  <section class="recent-articles">
    <h2 class="recent-articles__title">近期文章</h2>
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
  max-width: 600px;
  min-width: 300px;
  width: 100%;
  background-color: #9e9e9e8c;
  padding: 10px;

  box-sizing: border-box;
  border-radius: 15px;
}

.recent-articles__title {
  padding-left: 10px;
  margin: 0;
  margin-bottom: 20px;

  font-size: 1.5rem;
  color: #535353;
  cursor: default;
  transition: color 0.4s ease;
}

.recent-articles__title:hover {
  color: #ffffff;
}

.article-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 10px;

  width: 100%;
}

.article-card {
  display: flex;
  flex-direction: row;
  gap: 20px;
  position: relative; /* 为 stretched-link 提供定位上下文 */
  align-items: center;
  padding: 15px;
  padding-left: 10px;

  border-radius: 15px;
  transition: box-shadow 0.3s, transform 0.3s ease;
}

.article-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.article-card__image {
  width: 110px;
  height: 110px;
  flex-shrink: 0; /* 防止图片在 flex 布局中被压缩 */
  object-fit: cover;

  border-radius: 10px;
}

.article-card__content {
  display: flex;
  flex-direction: column;
  flex-grow: 1; /* 占据所有剩余空间 */
  min-width: 0; /* 修复 flex 布局中 text-overflow 不生效的问题 */
  overflow-wrap: break-word;
  word-break: break-word;
}

.article-card__title {
  margin: 0;
  font-size: 1.2rem;
  font-weight: 600;
}

.article-card__title a {
  text-decoration: none;
  color: rgb(247, 247, 247);

  /* 解决溢出问题 */
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.article-card__title a,
.article-card__title .stretched-link {
  display: block;
}

.article-card__summary {
  margin: 8px 0;
  font-size: 0.9rem;
  color: #dadada;
  line-height: 1.5;

  /* 摘要内容截断，显示2行 */
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
  line-clamp: 2;
  max-height: 3em;
}

.article-card__meta {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  font-size: 0.8rem;
  color: #d4d4d4;
  margin-top: auto;
}

.stretched-link::after {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1;
}

/* 移动端适配 */
@media (max-width: 600px) {
  .recent-articles {
    padding: 15px;
  }

  .article-card {
    flex-direction: column;
  }

  .article-card__image {
    width: 100%;
    height: auto;
    aspect-ratio: 16 / 9;
  }

  /* 添加这个规则 */
  .article-card__content {
    width: 100%;
    max-width: 100%;
  }
}
</style>
