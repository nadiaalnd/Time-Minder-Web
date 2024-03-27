<template>
  <div>
    <!-- Hero section -->
    <h1>Halo</h1>
  </div>
</template>

<script>
import aosMixin from '@/mixins/aos'
export default {
  name: 'TimerPage',
  mixins: [aosMixin],
}
</script>
<style scoped>
.text-time-gradient {
  background: rgb(255, 191, 28);
  background: linear-gradient(169.4deg, #ffbf1c -6.01%, #ffb700 36.87%, #f8f097 78.04%, #ffbf1c 103.77%);
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.text-minder-gradient {
  background: rgb(3, 10, 48);
  background: linear-gradient(169.4deg, #030A30 -6.01%, #030A30 36.87%, #94caff 78.04%, #030A30 103.77%);
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.bg-features {
  background: url('../assets/img/bg-section.webp');
  background-size: cover;
  background-position: center;
}
.max-h-0 {
  max-height: 0;
}
</style>
