<template>
  <div class="w-full mx-auto">
    <section class="sm:mx-4 flex justify-center items-center">
      <Popup :show="showAlert" @close="closeAlert"/>
      <div class="max-w-full py-8 sm:px-4">
        <TimerProgressBar
          :percentages="percentages"
          class="sm:mx-auto px-4 sm:px-6 pb-2 sm:py-8"/>
        <div class="sm:mx-auto sm:px-6">
          <TimerView @progress="handleProgress" @finishTimer="handleFinish"/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import aosMixin from '@/mixins/aos'
import TimerProgressBar from '@/components/timer/ProgressBar.vue'
import TimerView from '@/components/timer/View.vue'
import Popup from "@/components/timer/Popup.vue";
import {
  requestPermission,
} from '@/plugins/sendNotification'

export default {
  name: 'TimerPage',
  components: {
    TimerProgressBar,
    TimerView,
    Popup,
  },
  mixins: [aosMixin],
  layout: 'custom',
  data() {
    return {
      percentages: 0,
      showAlert: false,
      audio: null,
    }
  },
  mounted() {
    requestPermission();
    this.audio = new Audio('https://file-examples.com/storage/fe0e2ce82f660c1579f31b4/2017/11/file_example_MP3_700KB.mp3');
  },
  methods: {
    handleProgress(progress) {
      this.percentages = progress;
    },
    handleFinish() {
      this.playAudio();
      this.showAlert = true;
    },
    closeAlert() {
      if (this.audio) {
        this.audio.pause();
        this.audio.currentTime = 0;
      }
      this.showAlert = false;
    },
    playAudio() {
      if (this.audio) {
        this.audio.play();
      }
    }
  }
}
</script>
