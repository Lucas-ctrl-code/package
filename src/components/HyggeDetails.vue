<template>
  <div class="hygge-details">
    <h1>Hygge民泊 · 详情介绍</h1>
    <section>
      <h2>宽敞明亮的客房</h2>
      <p>每间客房均配备大窗户、独立阳台、厨房和洗衣机，适合家庭和长住客人。</p>
      <img src="https://images.unsplash.com/photo-1512918728675-ed5a9ecdebfd?auto=format&fit=crop&w=600&q=80" alt="公寓示例" />
    </section>
    <section>
      <h2>商务与远程办公支持</h2>
      <p>高速WiFi、办公桌椅、安静环境，满足商务差旅与远程办公需求。</p>
    </section>
    <section>
      <h3>联系方式</h3>
      <p>如需预订或咨询，欢迎通过以下方式联系我们：</p>
      <div>
        邮箱：<a href="mailto:liuwq5566@gmail.com">liuwq5566@gmail.com</a><br />
        电话：<a href="tel:09071235566">09071235566</a>
      </div>
    </section>
    <footer>
      © 2025 Hygge民泊. 保留所有权利.<br />
      <a href="#/">首页</a> · <a href="#/main">主页面</a>
    </footer>
    <section>
      <h2>Hygge民泊 · 详情介绍</h2>
      <p>Hygge民泊位于大阪市中心，2024年全新开业，致力于为旅客提供温馨、便利、安心的住宿体验。无论是短期旅游、商务出行还是长期居住，我们都能满足您的需求。</p>
      <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=600&q=80" alt="客房示例" />
    </section>
  </div>
</template>

<script setup lang="ts">
// 详情页无需特殊逻辑
</script>

<style scoped>
.hygge-details {
  max-width: 700px;
  margin: 0 auto;
  padding: 2rem;
}
.hygge-details img {
  width: 100%;
  max-width: 500px;
  margin: 1em auto;
  display: block;
  border-radius: 12px;
}
footer {
  margin-top: 2em;
  color: var(--color-muted-foreground, #888);
  font-size: 0.95em;
}
section {
  margin-bottom: 2em;
}
</style>
