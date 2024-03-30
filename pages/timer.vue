<template>
  <div class="w-full mx-auto">
    <section class="relative justify-center items-center px-8 mx-auto ">
      <div class="py-8">
        <TimerProgressBar/>
        <div class="pt-8">
          <TimerView/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import aosMixin from '@/mixins/aos'
import TimerProgressBar from '@/components/timer/ProgressBar.vue'
import TimerView from '@/components/timer/View.vue'
export default {
  name: 'TimerPage',
  components: {
    TimerProgressBar,
    TimerView
  },
  mixins: [aosMixin],
  layout: 'custom',
}
</script>
