<template>
  <div>
    <InputField label="Nama Timer" v-model="name" />
    <InputField label="Deskripsi Timer" v-model="description" />
    <NumberInput label="Waktu (Dalam Menit)" v-model="time" />
  </div>
</template>

<script>
import InputField from '@/components/timer/custom/InputField.vue';
import NumberInput from '@/components/timer/custom/NumberInput.vue';
export default {
  components: {
    InputField,
    NumberInput,
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
  methods: {
    toggleOptions() {
      this.showOptions = !this.showOptions;
    },
  },
};
</script>
