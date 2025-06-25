<template>
  <div class="hygge-details">
    <div class="lang-switch-ui">
      <button v-for="lang in langs" :key="lang" :class="['px-3 py-1 rounded text-sm font-semibold mx-1', currentLang === lang ? 'bg-blue-600 text-white' : 'bg-white text-blue-600 border border-blue-600']" @click="setLang(lang)">
        {{ langLabels[lang] }}
      </button>
    </div>
    <h1>{{ dict[currentLang].title }}</h1>
    <section>
      <h2>{{ dict[currentLang].roomTitle }}</h2>
      <p>{{ dict[currentLang].roomDesc }}</p>
      <img src="https://images.unsplash.com/photo-1512918728675-ed5a9ecdebfd?auto=format&fit=crop&w=600&q=80" alt="room" />
    </section>
    <section>
      <h2>{{ dict[currentLang].businessTitle }}</h2>
      <p>{{ dict[currentLang].businessDesc }}</p>
    </section>
    <section>
      <h3>{{ dict[currentLang].contactTitle }}</h3>
      <p>{{ dict[currentLang].contactDesc }}</p>
      <div>
        {{ dict[currentLang].emailLabel }}<a href="mailto:liuwq5566@gmail.com">liuwq5566@gmail.com</a><br />
        {{ dict[currentLang].phoneLabel }}<a href="tel:09071235566">09071235566</a>
      </div>
    </section>
    <footer>
      © 2025 Hygge民泊. 保留所有权利.<br />
      <a href="#/">{{ dict[currentLang].home }}</a> · <a href="#/main">{{ dict[currentLang].main }}</a>
    </footer>
    <section>
      <h2>{{ dict[currentLang].introTitle }}</h2>
      <p>{{ dict[currentLang].introDesc }}</p>
      <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=600&q=80" alt="room2" />
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const langs = ['zh', 'en', 'ja'] as const
const langLabels: Record<typeof langs[number], string> = { zh: '中文', en: 'EN', ja: '日本語' }
const dict: Record<typeof langs[number], any> = {
  zh: {
    title: 'Hygge民泊 · 详情介绍',
    roomTitle: '宽敞明亮的客房',
    roomDesc: '每间客房均配备大窗户、独立阳台、厨房和洗衣机，适合家庭和长住客人。',
    businessTitle: '商务与远程办公支持',
    businessDesc: '高速WiFi、办公桌椅、安静环境，满足商务差旅与远程办公需求。',
    contactTitle: '联系方式',
    contactDesc: '如需预订或咨询，欢迎通过以下方式联系我们：',
    emailLabel: '邮箱：',
    phoneLabel: '电话：',
    home: '首页',
    main: '主页面',
    introTitle: 'Hygge民泊 · 详情介绍',
    introDesc: 'Hygge民泊位于大阪市中心，2024年全新开业，致力于为旅客提供温馨、便利、安心的住宿体验。无论是短期旅游、商务出行还是长期居住，我们都能满足您的需求。'
  },
  en: {
    title: 'Hygge Vacation Rental · Details',
    roomTitle: 'Spacious and Bright Rooms',
    roomDesc: 'Each room features large windows, a private balcony, kitchen, and washing machine, perfect for families and long-term guests.',
    businessTitle: 'Business & Remote Work Support',
    businessDesc: 'High-speed WiFi, desk and chair, and a quiet environment for business trips and remote work.',
    contactTitle: 'Contact',
    contactDesc: 'For booking or inquiries, please contact us via:',
    emailLabel: 'Email: ',
    phoneLabel: 'Phone: ',
    home: 'Home',
    main: 'Main',
    introTitle: 'Hygge Vacation Rental · Details',
    introDesc: 'Located in central Osaka, newly opened in 2024, Hygge Vacation Rental is dedicated to providing guests with a warm, convenient, and secure stay. Whether for short-term travel, business, or long-term residence, we can meet your needs.'
  },
  ja: {
    title: 'Hygge民泊 · 詳細案内',
    roomTitle: '広く明るい客室',
    roomDesc: '各客室には大きな窓、専用バルコニー、キッチン、洗濯機が備わっており、家族や長期滞在のお客様に最適です。',
    businessTitle: 'ビジネス・リモートワーク対応',
    businessDesc: '高速WiFi、デスクと椅子、静かな環境でビジネスやリモートワークにも最適。',
    contactTitle: '連絡先',
    contactDesc: 'ご予約やお問い合わせは、以下の方法でご連絡ください。',
    emailLabel: 'メール：',
    phoneLabel: '電話：',
    home: 'ホーム',
    main: 'メイン',
    introTitle: 'Hygge民泊 · 詳細案内',
    introDesc: 'Hygge民泊は大阪市中心部に位置し、2024年新規オープン。温かく便利で安心な滞在を提供します。短期旅行、ビジネス、長期滞在にも対応可能です。'
  }
}
type Lang = typeof langs[number]
const currentLang = ref<Lang>('zh')
function setLang(lang: Lang) { currentLang.value = lang }
</script>

<style scoped>
.hygge-details {
  max-width: 700px;
  margin: 0 auto;
  padding: 2rem;
  position: relative;
}
.lang-switch-ui {
  position: absolute;
  top: 1.5rem;
  left: 1.5rem;
  z-index: 20;
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
