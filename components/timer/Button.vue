<template>
  <div class="relative justify-center items-center">
    <button
      v-if="!timerStarted"
      class="bg-gradient-to-r from-yellow-500 to-yellow-300 px-4 py-4 sm:py-3 rounded-md text-white hover:shadow-md transition duration-300"
      @click="startTimer"
    >
      <slot>Start</slot>
    </button>
    <button
      v-if="timerStarted"
      class="bg-gradient-to-r from-yellow-500 to-yellow-300 px-4 py-4 sm:py-3 rounded-md text-white hover:shadow-md transition duration-300"
      @click="pauseTimer"
    >
      <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 4h4v16H6zM14 4h4v16h-4z"></path>
      </svg>
    </button>
    <button
      v-if="timerStarted"
      class="bg-gradient-to-r from-yellow-500 to-yellow-300 px-4 py-4 sm:py-3 rounded-md text-white hover:shadow-md transition duration-300"
      @click="finishTimer"
    >
      <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
      </svg>
    </button>
  </div>
</template>

<script>
export default {
  name: 'TimerButton',
  data() {
    return {
      timerStarted: false
    };
  },
  methods: {
    startTimer() {
      this.timerStarted = true;
      this.$emit('startTimer');
    },
    pauseTimer() {
      this.timerStarted = false;
      this.$emit('pauseTimer');
    },
    finishTimer() {
      this.timerStarted = false;
      this.$emit('finishTimer');
    }
  }
}
</script>
