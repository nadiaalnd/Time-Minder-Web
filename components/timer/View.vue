<template>
  <div class="container mx-auto mt-4">
    <div class="max-w-sm mx-auto">
      <div class="bg-features relative p-4 shadow rounded-2xl overflow-hidden">
        <div class="text-center mb-4">
          <h2 class="text-lg font-bold">Ini Nanti Pilihan</h2>
        </div>
        <div v-if="timerStarted" class="text-4xl text-center mb-4">{{ timer }}</div>
        <div class="mb-4">
          <TimerButton
            v-if="!timerStarted"
            @startTimer="startTimer"
          />
          <TimerButton
            v-if="timerStarted"
            @pauseTimer="pauseTimer"
            @finishTimer="finishTimer"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import TimerButton from '~/components/timer/Button.vue';

export default {
  name: 'TimerView',
  components: {
    TimerButton
  },
  data() {
    return {
      timerStarted: false,
      timer: '00:00:00',
      intervalId: null,
      startTime: null,
      elapsedTime: 0
    };
  },
  methods: {
    startTimer() {
      if (!this.timerStarted) {
        this.timerStarted = true;
        this.startTime = Date.now() - this.elapsedTime;
        this.intervalId = setInterval(this.updateTimer, 1000);
      }
    },
    pauseTimer() {
      if (this.timerStarted) {
        clearInterval(this.intervalId);
        this.timerStarted = false;
      }
    },
    finishTimer() {
      clearInterval(this.intervalId);
      this.timerStarted = false;
      this.elapsedTime = 0;
      this.timer = '00:00:00';
    },
    updateTimer() {
      if (this.timerStarted) {
        const now = Date.now();
        this.elapsedTime = now - this.startTime;
        const formattedTime = this.formatTime(this.elapsedTime);
        this.timer = formattedTime;
      }
    },
    formatTime(ms) {
      const totalSeconds = Math.floor(ms / 1000);
      const hours = Math.floor(totalSeconds / 3600);
      const minutes = Math.floor((totalSeconds % 3600) / 60);
      const seconds = totalSeconds % 60;
      return `${this.pad(hours)}:${this.pad(minutes)}:${this.pad(seconds)}`;
    },
    pad(number) {
      if (number < 10) {
        return '0' + number;
      }
      return number;
    }
  }
}
</script>
<style scoped>
.bg-features {
  background: url('assets/img/bg-section.webp');
  background-size: cover;
  background-position: center;
}
</style>
