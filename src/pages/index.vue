<template>
  <h4>home</h4>
  <ReloadPrompt></ReloadPrompt>
</template>

<script setup lang="ts">
import { registerSW } from 'virtual:pwa-register'
import { RouterLink } from 'vue-router'
const target = ref(null)
onMounted(() => {
  registerSW({
    immediate: true,
    onNeedRefresh() {
      console.log('onNeedRefresh')
    },
    onOfflineReady() {
      console.log('onOfflineReady')
    },
    onRegisteredSW(_swScriptUrl, registration) {
      setInterval(() => {
        registration && registration.update()
      }, 5000)
    }
  })
})
</script>

<style lang="scss" scoped></style>
<route lang="yaml">
meta:
  layout: defaultLayout
  bgColor: yellow
</route>
