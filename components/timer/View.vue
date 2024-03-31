<template>
  <div class="w-full mx-auto">
    <div class="w-screen max-w-lg mx-auto">
      <div class="bg-features relative p-8 shadow-lg rounded-lg">
        <div class="mb-4 flex justify-center">
          <button
            v-for="type in timerTypes"
            :key="type"
            :class="{ 'bg-gradient-to-r from-yellow-500 to-yellow-300': timerType === type, 'bg-gray-300': timerType !== type }"
            class="mr-4 px-4 py-2 rounded-md text-white hover:shadow-md transition duration-300"
            @click="setTimer(type)"
          >
            {{ type === 'short' ? 'Short Break' : 'Long Break' }}
          </button>
        </div>
        <!-- Timer -->
        <div class="text-8xl font-bold text-center mb-4">{{ timer }}</div>
        <!-- Button -->
        <div class="mb-4 flex justify-center">
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
import Timer from "@/plugins/timer";
import {
  sendNotification
} from "@/plugins/sendNotification";

export default {
  name: 'TimerView',
  components: {
    TimerButton
  },
  data() {
    return {
      timerStarted: false,
      timer: "00:00",
      countdown: null,
      progress: 0,
      timerType: 'short',
      timerTypes: ['short', 'long'],
      isPaused: false
    };
  },
  created() {
    this.timer = this.formatTime(this.timerType === 'short' ? 5 * 60 : 15 * 60);
  },
  methods: {
    startTimer() {
      if(this.isPaused) {
        this.continueTimer();
        this.isPaused = false;
        return;
      }
      const duration = this.timerType === 'short' ? 5 * 60 : 15 * 60;
      this.timer = this.formatTime(duration);
      this.countdown = Timer(duration, this.finishTimer.bind(this));
      this.countdown.start();
      this.timerStarted = true;
      this.updateTimer();
      this.$emit('startTimer');
    },
    continueTimer() {
      this.countdown.start();
      this.timerStarted = true;
      this.updateTimer();
    },
    pauseTimer() {
      if (this.countdown) {
        this.countdown.stop();
      }
      this.timerStarted = false;
      this.isPaused = true;
    },

    finishTimer() {
      this.timerStarted = false;
      this.countdown = null;
      this.timer = this.formatTime(this.timerType === 'short' ? 5 * 60 : 15 * 60);
      this.$emit('finishTimer');
      this.runSendNotification();
    },
    runSendNotification() {
      sendNotification("Time's up!", {
        body: `Your ${this.timerType === 'short' ? 'short break' : 'long break'} is over!`
      });
    },
    updateTimer() {
      setInterval(() => {
        if (this.countdown) {
          const seconds = this.countdown.duration % 60;
          const minutes = Math.floor((this.countdown.duration / 60) % 60);
          this.timer = `${this.pad(minutes)}:${this.pad(seconds)}`;
          this.progress = parseFloat((this.countdown.duration / (this.timerType === 'short' ? 5 * 60 : 15 * 60) * 100).toFixed(2));
          // eslint-disable-next-line no-console
          console.log("progress", this.progress);
          this.$emit('progress', this.progress);
        }
      }, 1000);
    },
    formatTime(seconds) {
      const minutes = Math.floor((seconds % 3600) / 60);
      const remainingSeconds = seconds % 60;
      return `${this.pad(minutes)}:${this.pad(remainingSeconds)}`;
    },
    pad(num) {
      return num.toString().padStart(2, '0');
    },
    setTimer(type) {
      if(this.timerStarted) {
        this.finishTimer();
      }
      this.timerType = type;
      const duration = this.timerType === 'short' ? 5 * 60 : 15 * 60;
      this.timer = this.formatTime(duration);
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
