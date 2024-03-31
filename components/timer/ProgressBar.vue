<template>
  <div class="justify-center max-w-xl">
    <div class="relative h-2 bg-neutral-200 rounded-full">
      <div class="absolute top-0 left-0 h-2 rounded-full" :class="{ 'gradient-bg': percentages > 0, 'bg-gray-300': percentages === 0 }" :style="{ width: (100 - percentages) + '%' }"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TimerProgressBar',
  props: {
    percentages: {
      type: Number,
      default: 0,
    },
  }
}
</script>

<style scoped>
.gradient-bg {
  background: linear-gradient(169.4deg, #ffbf1c -6.01%, #ffb700 36.87%, #f8f097 78.04%, #ffbf1c 103.77%);
}
</style>
