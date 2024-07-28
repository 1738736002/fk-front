<template>
  <div class="layout">
    <header :style="`background: ${bgColor};`">
      <!-- Header content goes here -->
      头部
    </header>
    <main>
      <!-- Content area goes here -->
      <RouterView></RouterView>
    </main>
  </div>
</template>

<script setup lang="ts">
const bgColor = useRouter().currentRoute.value.meta.bgColor
</script>

<style scoped lang="scss"></style>
