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
          <div v-if="!timerStarted">
            <TimerButton
              :text="textButton"
              @startTimer="startTimer"/>
          </div>
          <div v-else>
            <TimerButton
              @pauseTimer="pauseTimer"
              @finishTimer="finishTimer"/>
          </div>
<!--          <TimerButton-->
<!--            v-if="!timerStarted"-->
<!--            :text="textButton"-->
<!--            @startTimer="startTimer"-->
<!--          />-->
<!--          <TimerButton-->
<!--            v-else-->
<!--            @pauseTimer="pauseTimer"-->
<!--            @finishTimer="finishTimer"-->
<!--          />-->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TimerButton from '~/components/timer/Button.vue';
import Timer from "@/plugins/timer";
import {sendNotification} from "@/plugins/sendNotification";

export default {
  name: 'TimerView',
  components: {TimerButton},
  data() {
    return {
      timerStarted: false,
      timer: "00:00",
      countdown: null,
      progress: 0,
      timerType: 'short',
      timerTypes: ['short', 'long'],
      isPaused: false,
      textButton: 'Start',
      time: {short: 5 * 60, long: 15 * 60}
    };
  },
  created() {
    this.timer = this.formatTime(this.time[this.timerType]);
  },
  methods: {
    startTimer() {
      if (this.isPaused) {
        this.continueTimer();
        this.isPaused = false;
        return;
      }
      const duration = this.time[this.timerType];
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
      this.textButton = 'Continue';
      this.timerStarted = false;
      this.isPaused = true;
    },
    finishTimer(isReset = false) {
      this.timerStarted = false;
      this.countdown = null;
      this.timer = this.formatTime(this.time[this.timerType]);
      this.$emit('finishTimer');
      if (!isReset) {
        this.runSendNotification();
      }
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
          this.progress = parseFloat((this.countdown.duration / this.time[this.timerType] * 100).toFixed(2));
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
      if (this.isPaused || this.timerStarted) {
        this.finishTimer(true);
      }
      this.timerStarted = false;
      this.timerType = type;
      console.log(this.timerStarted)
      this.textButton = 'Start';
      this.timer = this.formatTime(this.time[type]);
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
