<template>

    <!-- Modal Component -->
    <teleport to="body">
      <div v-if="showModal" class="modal-overlay" @click="closeModal">
        <div class="modal-content" @click.stop>
          <h3>Modal Title</h3>
          <p>This is a simple modal in Vue 3.</p>
          <button @click="closeModal">Close</button>
        </div>
      </div>
    </teleport>
</template>

<script>
export default {
  data() {
    return {
      showModal: false,
    };
  },
  methods: {
    openModal() {
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
  },
};
</script>

<style>
button {
  padding: 10px 15px;
  background: #007bff;
  color: rgb(10, 9, 9);
  border: none;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background: #0056b3;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  background: rgb(7, 6, 6);
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  text-align: center;
  width: 600px;
  height: 600px;
}
</style>
