<template>
  <div>
    <NumberInput label="Waktu (Dalam Menit)" v-model="time" @update:modelValue="updateTime" />
  </div>
</template>

<script>
import NumberInput from '@/components/timer/custom/NumberInput.vue';
export default {
  components: {
    NumberInput,
  },
  props: {
    initValTime: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      name: '',
      description: '',
      time: 0,
      showOptions: false,
      enableBreak: false,
      breakDuration: 0,
      breakCount: 0,
    };
  },
  watch: {
    initValTime(newValue) {
      this.time = newValue;
    },
  },
  created() {
    this.time = parseInt(localStorage.getItem('customTime'));
  },
  methods: {
    toggleOptions() {
      this.showOptions = !this.showOptions;
    },
    updateName(value) {
      this.$emit('update:name', value);
    },
    updateDescription(value) {
      this.$emit('update:description', value);
    },
    updateTime(value) {
      console.log(value);
      this.$emit('update:time', value);
    },
  },
};
</script>
