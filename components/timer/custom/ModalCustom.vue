<template>
  <div class="fixed z-10 inset-0 overflow-y-auto" role="dialog" aria-modal="true">
    <div class="flex items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
      <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
      <div class="inline-block align-bottom bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full">
        <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
          <h3 class="text-lg leading-6 font-medium text-gray-900">Tambah Waktumu Sendiri!</h3>
          <FormInput />
        </div>
        <div class="px-4 py-3 sm:px-6 sm:flex sm:flex-row-reverse">
          <button @click="apply" class="bg-yellow-500 hover:bg-yellow-600 text-white py-2 px-4 rounded-md">
            Terapkan
          </button>
          <button @click="reset" class="border-2 hover:bg-gray-100 border-neutral-950 py-2 px-4 mr-2 rounded-md">
            Reset
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FormInput from '@/components/timer/custom/FormInput.vue';

export default {
  components: {
    FormInput,
  },
  methods: {
    apply() {
      // Logika untuk menerapkan perubahan
    },
    reset() {
      // Logika untuk mereset form
    },
  },
};
</script>
