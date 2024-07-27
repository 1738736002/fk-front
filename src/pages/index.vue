<template>
  <div>
    home page
    <div class="p5 color-blue">p5</div>
    <p>x: {{ x }}</p>
    <p>y: {{ y }}</p>
    <p>isOutside: {{ isOutside }}</p>
  </div>
</template>

<script setup lang="ts">
const target = ref(null)
const { x, y, isOutside } = useMouseInElement(target)
</script>

<style lang="scss" scoped></style>
