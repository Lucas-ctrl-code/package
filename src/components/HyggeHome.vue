<template>
  <div class="hygge-home">
    <div class="lang-switch">
      <span>中文</span><span>EN</span><span>日本語</span>
    </div>
    <h1>Hygge民泊</h1>
    <div class="main-links">
      <a href="#/main">进入 Enter</a>
    </div>
    <div class="contact">
      运营商电话：<a href="tel:03-6705-5554">03—6705—5554</a>
      <br />
      邮箱：<a href="mailto:vacation.rental.hr@gmail.com">vacation.rental.hr@gmail.com</a>
    </div>
  </div>
</template>

<script setup lang="ts">
// 首页无需特殊逻辑
</script>

<style scoped>
.hygge-home {
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
.contact {
  margin-top: 2em;
  color: var(--color-muted-foreground, #888);
}
</style>
