<template>
  <div class="w-full mx-auto">
    <section class="sm:mx-4 flex justify-center items-center">
      <div class="max-w-full py-8 sm:px-4">
        <TimerProgressBar :percentages="percentages"
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
import {
  requestPermission,
} from '@/plugins/sendNotification'
export default {
  name: 'TimerPage',
  components: {
    TimerProgressBar,
    TimerView
  },
  mixins: [aosMixin],
  layout: 'custom',
  data() {
    return {
      percentages: 0,
    }
  },
  mounted () {
    requestPermission()
  },
  methods: {
    handleProgress(progress) {
      this.percentages = progress
    },
    handleFinish() {
      this.playAudio()
    },
    playAudio() {
      const audio = new Audio('https://file-examples.com/storage/fef0ba8e7b660ad2093c8cd/2017/11/file_example_MP3_700KB.mp3')
      audio.play()
    }
  }
}
</script>
