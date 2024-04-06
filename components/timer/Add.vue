<!-- Add.vue -->
<template>
  <div>
    <button class="w-full border-dashed border-2 border-gray-400 rounded-md px-6 py-2 text-sm text-gray-700 hover:bg-gray-100 focus:outline-none focus:border-gray-500 focus:ring focus:ring-gray-300" @click="openModal">
      Add Your Own Timer
    </button>
    <ModalDownload v-if="isModalOpen" @close="closeModal" />
  </div>
</template>

<script>
import ModalDownload from './ModalDownload.vue';

export default {
  name: 'TimerAdd',
  components: {
    ModalDownload,
  },
  layout: 'custom',
  data() {
    return {
      isModalOpen: false,
    };
  },
  methods: {
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
    },
  },
}
</script>
