<template>
  <div class="modal"
    :class="{ 'is-active': isModalOpen }">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head has-background-grey-darker">
        <slot name="header" />

        <button class="delete"
          aria-label="close"
          v-on:click="close()">
        </button>
      </header>

      <section class="modal-card-body has-background-grey-darker">
        <slot name="content" />
      </section>

      <footer class="modal-card-foot has-background-grey-darker is-justify-content-flex-end">
        <slot name="footer" />
      </footer>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ModalComponent',
  data() {
    return {
      isModalOpen: false,
    };
  },
  mounted() {
    console.log('Modal component');
  },
  methods: {
    open() {
      this.isModalOpen = true
    },
    close() {
      this.isModalOpen = false
    },
  },
})
</script>

<style lang="scss" scoped>
// .modal.is-active .modal-card {
//   animation: navAnim .2s ease-in-out;
// }

// @keyframes navAnim {
//   0% {
//     display: none;
//     opacity: 0;
//     height: 0;
//   }
//   1% {
//     display: block;
//     opacity: 0;
//   }
//   100% {
//     opacity: 1;
//     height: 396px;
//   }
// }

// .modal .modal-card {
//   animation: navAnimOpen .2s ease-in-out;
// }

// @keyframes navAnimOpen {
//   0% {
//     display: none;
//     opacity: 0;
//     max-height: 0;
//   }
//   1% {
//     display: block;
//     opacity: 0;
//   }
//   100% {
//     opacity: 1;
//     max-height: 396px;
//   }
// }
</style>