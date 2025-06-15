<template>
  <div class="hygge-main">
    <div class="lang-switch">
      <span>中文</span><span>EN</span><span>日本語</span>
    </div>
    <h1>欢迎来到Hygge民泊</h1>
    <p>
      我们为您提供温馨、便利、舒适的住宿体验，位于大阪市中心，适合家庭、商务、留学等多种需求。
    </p>
    <div class="main-links">
      <a href="#/details">查看详情</a>
    </div>
    <footer>
      © 2025 Hygge民泊. 保留所有权利.<br />
      <a href="#/">首页</a> · <a href="#/main">关于我们</a> · <a href="#/main#contact">联系我们</a>
    </footer>
  </div>
</template>

<script setup lang="ts">
// 主页面无需特殊逻辑
</script>

<style scoped>
.hygge-main {
  text-align: center;
  padding: 2rem;
}
.lang-switch span {
  margin: 0 0.5em;
  cursor: pointer;
  font-weight: bold;
}
.main-links {
  margin: 2em 0;
}
footer {
  margin-top: 2em;
  color: var(--color-muted-foreground, #888);
  font-size: 0.95em;
}
</style>
