<template>
  <div style="height:100vh;width:100vw;background-image: url(https://github.com/Lucas-ctrl-code/package/blob/main/image-cache.jpg?raw=true); background-size: cover; background-repeat: no-repeat; background-position: center;" class="flex items-center justify-center">
    <div class="absolute top-8 right-8 flex gap-4 z-10">
      <button v-for="lang in langs" :key="lang" :class="['px-4 py-2 rounded font-semibold', currentLang === lang ? 'bg-blue-600 text-white' : 'bg-white text-blue-600 border border-blue-600']" @click="setLang(lang)">
        {{ langLabels[lang] }}
      </button>
    </div>
    <div class="flex flex-col justify-center items-center w-full">
      <h1 class="text-5xl font-bold mb-8 text-center" style="color: #2563eb;">{{ dict[currentLang].welcome }}</h1>
      <a href="#/details" class="inline-block px-8 py-3 bg-blue-600 text-white rounded-lg shadow hover:bg-blue-700 transition font-semibold text-lg mt-4" data-i18n="enter">{{ dict[currentLang].enter }}</a>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const langs = ['zh', 'en', 'ja'] as const
const langLabels: Record<typeof langs[number], string> = { zh: '中文', en: 'EN', ja: '日本語' }
const dict: Record<typeof langs[number], { welcome: string; enter: string }> = {
  zh: { welcome: '欢迎', enter: '进入 Enter' },
  en: { welcome: 'Welcome', enter: 'Enter' },
  ja: { welcome: 'ようこそ', enter: '入る Enter' }
}
type Lang = typeof langs[number]
const currentLang = ref<Lang>('en')
function setLang(lang: Lang) { currentLang.value = lang }
</script>

<style scoped>
/* 保留空，所有样式由 Tailwind CSS 控制 */
</style>
