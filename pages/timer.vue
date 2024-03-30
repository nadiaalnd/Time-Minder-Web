<!-- TimerPage.vue -->
<template>
  <section class="w-full h-full flex justify-center items-center min-w-screen">
      <div class="py-8">
        <TimerProgressBar :percentages="percentages"/>
        <div class="pt-8">
          <TimerView @progress="handleProgress" @finishTimer="handleFinish"/>
        </div>
      </div>
  </section>
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
      const audio = new Audio('https://file-examples.com/storage/fe17d655216606dd89d5226/2017/11/file_example_MP3_700KB.mp3')
      audio.play()
    }
  }
}
</script>
