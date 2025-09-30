<script setup></script>

<template>
  <article class="article-container">
    <header class="article-header">
      <h1 class="article__title">松鼠的世界</h1>
      <div class="article__meta">
        <div class="article__tags">
          <router-link class="tag">科技</router-link>
          <span> / </span>
          <router-link class="tag">Vue</router-link>
        </div>
        <time>2025-9-29</time>
      </div>
    </header>
    <div class="article__content">
      <p>在秋日的午后，当金黄的落叶如雨般飘零，我常常驻足于公园的林荫道下，凝视着那些敏捷的身影。</p>
      <p>
        松鼠，属于啮齿目松鼠科，全球约有285种，已知物种遍布各大洲。 回溯历史，松鼠的祖先可追溯到约5000万年前的始新世。
      </p>
      <p>松鼠的生活习性，充满了智慧与策略。最著名的莫过于它们的储藏行为。</p>
      <p>在饮食上，松鼠是杂食性动物，以坚果、种子为主，但也摄取昆虫、鸟蛋和树皮。</p>
      <p>不同种类的松鼠，各有其独特的生活方式。譬如飞鼠，并非真正飞行，而是通过皮膜滑翔。</p>
      <p>繁殖是松鼠生命中的重要篇章。通常每年两次，一次在春季，一次在夏季。</p>
      <blockquote>这是一个引用的段落，可能引用了某本书或某句话。</blockquote>
      <ul>
        <li>列表项一</li>
        <li>列表项二</li>
      </ul>
      <p>最后一个段落...</p>
    </div>
  </article>
</template>

<style scoped>
.article-container {
  background-color: #ffffffee;

  width: 100%;
  overflow: hidden;
}

.article-header {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  aspect-ratio: 3/1;

  background-image: url("@/assets/images/background-04.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.article-header::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;

  background: linear-gradient(to top, rgb(255, 255, 255) 0%, rgba(255, 255, 255, 0.233) 30%, transparent 50%);
}

.article__title {
  background-color: transparent;
  color: aliceblue;
  font-size: 4rem;
  z-index: 1;
}

.article__meta {
  position: absolute;
  bottom: 5px;
  right: 10px;
  z-index: 1;

  display: flex;
  align-items: center;
  gap: 15px;
}

.article__meta time {
  display: block;
  padding: 8px;

  background-color: #6e6e6e36;
  border-radius: 15px;
  color: #6e6e6e;
  font-size: 12px;
  cursor: default;

  transition: color 0.2s ease-in-out;
}

.article__meta time:hover {
  color: #070707;
}

.article__tags {
  display: flex;
  align-items: center;
  padding: 8px;

  background-color: #6e6e6e36;
  border-radius: 15px;
}

.article__tags span {
  display: block;
  font-size: 12px;
  font-weight: 800;
  color: #6e6e6e;
  cursor: default;
}

.article__tags .tag {
  text-decoration: none;
  color: #6e6e6e;
  font-size: 12px;
  font-weight: 600;

  transition: color 0.2s ease-in-out;
}

.article__tags .tag:hover {
  text-decoration: underline;
  color: #070707;
}

.article__content {
  max-width: 800px;
  margin: 40px auto 60px;
  padding: 0 20px;
  box-sizing: border-box;

  color: #333333;
  font-size: 17px;
  line-height: 1.8;
  letter-spacing: 0.05em;

  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif,
    "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji", "PingFang SC", "Hiragino Sans GB",
    "Microsoft YaHei", "WenQuanYi Micro Hei";

  word-wrap: break-word;
  overflow-wrap: break-word;
}

.article__content p {
  margin-top: 0;
  margin-bottom: 1.5em;
  text-align: justify;
}

.article__content p:last-child {
  margin-bottom: 0;
}

.article__content h2,
.article__content h3,
.article__content h4 {
  color: #222;
  margin-top: 2em;
  margin-bottom: 1em;
  line-height: 1.4;
}

.article__content h2 {
  font-size: 1.8rem;
}
.article__content h3 {
  font-size: 1.5rem;
}
.article__content h4 {
  font-size: 1.2rem;
}

.article__content a {
  color: #c44569;
  text-decoration: none;
  border-bottom: 1px solid #c4456955;
  transition: border-bottom 0.3s ease;
}

.article__content a:hover {
  border-bottom: 1px solid #c44569;
}

.article__content blockquote {
  margin: 2em 0;
  padding: 0.5em 1.5em;
  border-left: 4px solid #c44569;
  background-color: #f8f8f8;
  color: #666;
}

.article__content ul,
.article__content ol {
  margin-bottom: 1.5em;
  padding-left: 1.8em;
}
</style>
