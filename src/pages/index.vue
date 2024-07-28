<template>
  <div>
    home page
    <div class="p5 color-blue">p5 ...213</div>
    <p>x: {{ x }}</p>
    <p>y: {{ y }}</p>
    <p>isOutside: {{ isOutside }}</p>
  </div>
  <HelloWorld />
  <ReloadPrompt></ReloadPrompt>
</template>

<script setup lang="ts">
import { registerSW } from 'virtual:pwa-register'
const target = ref(null)
const { x, y, isOutside } = useMouseInElement(target)
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
