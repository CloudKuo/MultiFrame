<template>
  <!-- Bootstrap Modal -->
  <div ref="modalRef" class="modal fade" tabindex="-1">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">{{ title }}</h5>
          <button type="button" class="btn-close" @click="closeModal"></button>
        </div>
        <div class="modal-body">
          <p>{{ message }}</p>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" @click="closeModal">
            Close
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, onMounted, defineExpose } from "vue";
import { Modal } from "bootstrap";

export default {
  props: {
    title: {
      type: String,
      default: "Bootstrap Modal",
    },
    message: {
      type: String,
      default: "這是一個 Bootstrap Modal。",
    },
  },
  setup() {
    const modalRef = ref(null);
    let modalInstance = null;

    onMounted(() => {
      if (modalRef.value) {
        modalInstance = new Modal(modalRef.value);
      }
    });

    const openModal = () => {
      console.log("Bootstrap Modal 開啟");
      if (modalInstance) {
        modalInstance.show();
      }
    };

    const closeModal = () => {
      console.log("Bootstrap Modal 關閉");
      if (modalInstance) {
        modalInstance.hide();
      }
    };

    defineExpose({ openModal, closeModal }); // 🔥 這步驟是關鍵！

    return { modalRef };
  },
};
</script>

<style scoped>
.modal-content {
  text-align: center;
}
</style>
