<script setup lang="ts">
import { ref, shallowRef, defineAsyncComponent } from 'vue'

const HyggeHome = shallowRef(defineAsyncComponent(() => import('./components/HyggeHome.vue')))
const HyggeDetails = shallowRef(defineAsyncComponent(() => import('./components/HyggeDetails.vue')))

const route = ref(window.location.hash.replace('#/', '') || 'home')
window.addEventListener('hashchange', () => {
  route.value = window.location.hash.replace('#/', '') || 'home'
})

const currentComponent = () => {
  if (route.value === 'details') return HyggeDetails.value
  return HyggeHome.value
}
</script>

<template>
  <component :is="currentComponent()" />
</template>

<style scoped>
/* 保持原有样式 */
</style>
