<template>
  <div class="min-h-screen flex items-center justify-center bg-cover bg-center" style="background-image: url('https://github.com/Lucas-ctrl-code/imageimage/blob/main/%E5%9B%BE%E7%89%87_20250615150900.jpg?raw=true');">
    <div class="bg-white/80 dark:bg-black/70 rounded-2xl shadow-2xl flex flex-col md:flex-row w-full max-w-5xl p-6 md:p-10 gap-8 md:gap-12">
      <!-- 左侧内容 -->
      <div class="flex-1 flex flex-col justify-center items-center gap-6">
        <div class="lang-switch flex gap-2 text-base font-semibold text-gray-700 dark:text-gray-200">
          <span class="cursor-pointer hover:text-blue-600" :class="currentLang==='zh' ? 'text-blue-600' : ''" @click="setLanguage('zh')">中文</span>
          <span class="cursor-pointer hover:text-blue-600" :class="currentLang==='en' ? 'text-blue-600' : ''" @click="setLanguage('en')">EN</span>
          <span class="cursor-pointer hover:text-blue-600" :class="currentLang==='ja' ? 'text-blue-600' : ''" @click="setLanguage('ja')">日本語</span>
        </div>
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-2" data-i18n="title">Hygge民泊</h1>
        <div class="w-full flex flex-col items-center">
          <a href="#/details" class="inline-block px-8 py-3 bg-blue-600 text-white rounded-lg shadow hover:bg-blue-700 transition font-semibold text-lg" data-i18n="enter">进入 Enter</a>
        </div>
        <div class="mt-6 text-gray-600 dark:text-gray-300 text-center text-sm">
          <span data-i18n="phone-label">运营商电话：</span><a href="tel:03-6705-5554" class="underline hover:text-blue-600">03—6705—5554</a><br />
          <span data-i18n="email-label">邮箱：</span><a href="mailto:vacation.rental.hr@gmail.com" class="underline hover:text-blue-600">vacation.rental.hr@gmail.com</a>
        </div>
      </div>
      <!-- 右侧卡片 -->
      <div class="flex-1 flex items-center justify-center">
        <div class="bg-white/90 dark:bg-gray-900/80 rounded-xl shadow-lg p-8 md:p-10 max-w-md w-full flex flex-col items-center">
          <h2 class="text-2xl font-bold mb-4 text-gray-800 dark:text-white text-center" data-i18n="perfect-location-title">完美位置</h2>
          <p class="text-gray-700 dark:text-gray-200 text-base leading-relaxed text-center mb-2" data-i18n="perfect-location-desc1">
            大阪核心地段，出行不再是一种负担
          </p>
          <p class="text-gray-700 dark:text-gray-200 text-sm leading-relaxed text-center" data-i18n="perfect-location-desc2">
            M's玉造坐落于大阪市东区玉造1丁目4−7，是一栋四层楼建筑，从外观到内部都经过精心设计与打理。步行不到3分钟即可抵达JR环状线玉造站与地铁长堀鹤见绿地线3号出口。无论是要去心斋桥血拼、去天王寺看展览、去梅田商务洽谈、或是往返关西机场，几乎都能一班车直达，避免拖着行李转车、换乘的烦恼。
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'

// 多语言字典
const i18nDict = {
  zh: {
    title: "Hygge民泊",
    enter: "进入 Enter",
    "phone-label": "运营商电话：",
    "email-label": "邮箱：",
    "perfect-location-title": "完美位置",
    "perfect-location-desc1": "大阪核心地段，出行不再是一种负担",
    "perfect-location-desc2": "M's玉造坐落于大阪市东区玉造1丁目4−7，是一栋四层楼建筑，从外观到内部都经过精心设计与打理。步行不到3分钟即可抵达JR环状线玉造站与地铁长堀鹤见绿地线3号出口。无论是要去心斋桥血拼、去天王寺看展览、去梅田商务洽谈、或是往返关西机场，几乎都能一班车直达，避免拖着行李转车、换乘的烦恼。"
  },
  en: {
    title: "Hygge Vacation Rental",
    enter: "Enter",
    "phone-label": "Operator Tel:",
    "email-label": "Email:",
    "perfect-location-title": "Perfect Location",
    "perfect-location-desc1": "Prime location in Osaka, travel is no longer a burden",
    "perfect-location-desc2": "M's Tamatsukuri is located at 1-4-7 Tamatsukuri, Higashi-ku, Osaka. This four-story building is meticulously designed inside and out. Less than a 3-minute walk to JR Loop Line Tamatsukuri Station and Metro Nagahori Tsurumi-ryokuchi Line Exit 3. Whether shopping at Shinsaibashi, visiting exhibitions at Tennoji, business meetings in Umeda, or traveling to and from Kansai Airport, almost all can be reached directly without the hassle of transfers."
  },
  ja: {
    title: "Hygge民泊",
    enter: "入る Enter",
    "phone-label": "運営者電話：",
    "email-label": "メール：",
    "perfect-location-title": "完璧な立地",
    "perfect-location-desc1": "大阪中心地、移動が負担にならない",
    "perfect-location-desc2": "M's玉造は大阪市東区玉造1丁目4−7に位置し、外観から内装まで丁寧に設計・管理された4階建ての建物です。JR環状線玉造駅・地下鉄長堀鶴見緑地線3番出口まで徒歩3分以内。心斎橋でのショッピング、天王寺での展示会、梅田でのビジネス、関西空港への往復も、ほぼ乗り換えなしでアクセス可能。重い荷物を持っての乗り換えの煩わしさを解消します。"
  }
} as const

type Lang = keyof typeof i18nDict
const keys = Object.keys(i18nDict.zh) as Array<keyof typeof i18nDict.zh>

const currentLang = ref<Lang>('zh')

function setLanguage(lang: Lang) {
  currentLang.value = lang
  const dict = i18nDict[lang] || i18nDict['zh']
  document.querySelectorAll('[data-i18n]').forEach(el => {
    const key = el.getAttribute('data-i18n') as keyof typeof i18nDict.zh
    if (keys.includes(key)) el.textContent = dict[key]
  })
}

onMounted(() => {
  setLanguage('zh')
})
</script>

<style scoped>
/* 保留空，所有样式由 Tailwind CSS 控制 */
</style>
