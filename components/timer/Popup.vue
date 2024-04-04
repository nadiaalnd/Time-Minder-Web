<template>
  <div
    v-if="show" id="default-modal" tabindex="-1" aria-hidden="true"
    class="fixed inset-0 overflow-y-auto z-50 flex items-center justify-center bg-black bg-opacity-50">
    <div class="relative p-4 max-w-2xl w-full">
      <!-- Konten Modal -->
      <div class="relative bg-white rounded-lg shadow dark:bg-gray-700">
        <!-- Header Modal -->
        <div class="flex items-center justify-between p-4 md:p-5 border-b rounded-t dark:border-gray-600">
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white">
            Waktu Habis
          </h3>
          <button
            type="button"
            class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm w-8 h-8 ms-auto inline-flex justify-center items-center dark:hover:bg-gray-600 dark:hover:text-white"
            @click="$emit('close')">
            <svg class="w-3 h-3" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 14">
              <path
                stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6"/>
            </svg>
            <span class="sr-only">Close modal</span>
          </button>
        </div>
        <!-- Isi Modal -->
        <div class="p-4 md:p-5 space-y-4 h-12">
          <p class="text-gray-600 dark:text-gray-400">
            Waktu telah habis, silahkan istirahat sejenak.
          </p>
        </div>
        <!-- Footer Modal -->
        <div class="flex items-center p-4 md:p-5 border-t border-gray-200 rounded-b dark:border-gray-600">
          <button
            type="button"
            class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
            @click="$emit('close')">
            OKE SUWON BOLO
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TimerPopup',
  props: {
    show: {
      type: Boolean,
      default: false
    }
  }
}
</script>
