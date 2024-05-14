<template>
  <div class="mt-2">
    <label class="block text-sm font-medium text-gray-700">{{ label }}</label>
    <input v-model="inputValue" @input="$emit('update:modelValue', inputValue)" type="text" class="mt-1 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md">
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    modelValue: String,
  },
  data() {
    return {
      inputValue: this.modelValue,
    };
  },
  watch: {
    modelValue(newValue) {
      this.inputValue = newValue;
    },
  },
};
</script>
