<template>
  <div class="relative justify-center items-center">
    <!-- Button Pause Timer -->
    <button
      v-if="!timerStarted"
      class="bg-[#EFF5FB] px-4 py-4 sm:py-3 rounded-md text-[#59A7F2] hover:shadow-md transition duration-300"
      @click="startTimer"
    >
      <slot>{{ text }}</slot>
    </button>
    <!-- Button Pause Timer -->
    <button
      v-if="timerStarted"
      class="bg-[#EFF5FB] px-4 mr-4 py-4 sm:py-3 text-[#59A7F2] rounded-md hover:shadow-md transition duration-300"
      @click="pauseTimer"
    >
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24">
        <g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"><rect width="4" height="16" x="14" y="4" rx="1"/><rect width="4" height="16" x="6" y="4" rx="1"/></g>
      </svg>
    </button>
    <!-- Button Finish Timer -->
    <button
      v-if="timerStarted"
      class="bg-[#EFF5FB] px-4 py-4 ml-4 sm:py-3 text-[#59A7F2] rounded-md hover:shadow-md transition duration-300"
      @click="finishTimer"
    >
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24">
        <path fill="currentColor" d="M20.47 5.63c.39.39.39 1.01 0 1.4L9.13 18.37a.984.984 0 0 1-1.4 0l-4.2-4.2a.984.984 0 0 1 0-1.4a.984.984 0 0 1 1.4 0l3.5 3.5L19.07 5.63a.984.984 0 0 1 1.4 0m-2.11-2.12l-9.93 9.93l-2.79-2.79c-.78-.78-2.05-.78-2.83 0l-1.4 1.4c-.78.78-.78 2.05 0 2.83l5.6 5.6c.78.78 2.05.78 2.83 0L22.59 7.74c.78-.78.78-2.05 0-2.83l-1.4-1.4c-.79-.78-2.05-.78-2.83 0"/>
      </svg>
    </button>
  </div>
</template>

<script>
export default {
  name: 'TimerButton',
  props: {
    text: {
      type: String,
      default: 'Start',
    }
  },
  data() {
    return {
      timerStarted: false,
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
