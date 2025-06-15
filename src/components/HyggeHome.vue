<template>
  <div class="min-h-screen flex items-center justify-center bg-cover bg-center" style="background-image: url('https://github.com/Lucas-ctrl-code/imageimage/blob/main/%E5%9B%BE%E7%89%87_20250615150900.jpg?raw=true');">
    <div class="bg-white/80 dark:bg-black/70 rounded-2xl shadow-2xl flex flex-col md:flex-row w-full max-w-5xl p-6 md:p-10 gap-8 md:gap-12">
      <!-- 左侧内容 -->
      <div class="flex-1 flex flex-col justify-center items-center gap-6">
        <div class="flex gap-2 text-base font-semibold text-gray-700 dark:text-gray-200">
          <span class="cursor-pointer hover:text-blue-600">中文</span>
          <span class="cursor-pointer hover:text-blue-600">EN</span>
          <span class="cursor-pointer hover:text-blue-600">日本語</span>
        </div>
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-2">Hygge民泊</h1>
        <div class="w-full flex flex-col items-center">
          <a href="#/main" class="inline-block px-8 py-3 bg-blue-600 text-white rounded-lg shadow hover:bg-blue-700 transition font-semibold text-lg">进入 Enter</a>
        </div>
        <div class="mt-6 text-gray-600 dark:text-gray-300 text-center text-sm">
          运营商电话：<a href="tel:03-6705-5554" class="underline hover:text-blue-600">03—6705—5554</a><br />
          邮箱：<a href="mailto:vacation.rental.hr@gmail.com" class="underline hover:text-blue-600">vacation.rental.hr@gmail.com</a>
        </div>
      </div>
      <!-- 右侧卡片 -->
      <div class="flex-1 flex items-center justify-center">
        <div class="bg-white/90 dark:bg-gray-900/80 rounded-xl shadow-lg p-8 md:p-10 max-w-md w-full flex flex-col items-center">
          <h2 class="text-2xl font-bold mb-4 text-gray-800 dark:text-white text-center">完美位置</h2>
          <p class="text-gray-700 dark:text-gray-200 text-base leading-relaxed text-center mb-2">
            大阪核心地段，出行不再是一种负担
          </p>
          <p class="text-gray-700 dark:text-gray-200 text-sm leading-relaxed text-center">
            M's玉造坐落于大阪市东区玉造1丁目4−7，是一栋四层楼建筑，从外观到内部都经过精心设计与打理。步行不到3分钟即可抵达JR环状线玉造站与地铁长堀鹤见绿地线3号出口。无论是要去心斋桥血拼、去天王寺看展览、去梅田商务洽谈、或是往返关西机场，几乎都能一班车直达，避免拖着行李转车、换乘的烦恼。
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
// 首页无需特殊逻辑
</script>

<!-- Tailwind CSS 由 Vite 插件或全局引入，无需在此单独引入 -->
<style scoped>
/* 保留空，所有样式由 Tailwind CSS 控制 */
</style>
