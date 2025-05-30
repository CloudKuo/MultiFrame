<template>
  <div class="container">
    <h2><i class="bi bi-apple"></i>API List</h2>
    <table>
      <thead>
        <tr>
          <th>Key</th>
          <th>Value</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="[key, api] in Object.entries(apiList)" :key="key">
          <td>{{ key }}</td>
          <td>{{ api.tt }}</td>
        </tr>
      </tbody>
    </table>
    <button class="btn btn-primary" @click="addApiItem">Add New Item</button>
    <button class="btn btn-primary" @click="openModal">Open Modal</button>
    <button class="btn btn-info" @click="openBootStrapModal">Open BootStrap Modal</button>

    <Modal ref="modalRef" />
    <BootstrapModal ref="bootstrapModalRef" title="自訂標題" message="這是從父元件傳來的訊息！" />

  </div>
</template>

<script>
import Modal from "./Modal.vue";
import BootStrapModal from "./BootStrapModal.vue";
import { ref } from "vue";

export default {
  components: { Modal, BootStrapModal },
  data() {
    return {
      apiList: {
        R: {
          tt: "t",
        },
        T: {
          tt: "t",
        },
      },
    };
  },
  methods: {
    addApiItem() {
      const newKey = "X" + Object.keys(this.apiList).length; // Generate a new key dynamically

      this.apiList[newKey] = { tt: "new value" };
    },
  },
  setup() {
    const modalRef = ref(null);
    const bootstrapModalRef = ref(null);
    const openModal = () => {
      console.log("open");
      if (modalRef.value) {
        modalRef.value.openModal(); // Call the method in Modal.vue
      }
    };

    const openBootStrapModal = () => {
        console.log("open bootStrap");
      if (bootstrapModalRef.value) {
        bootstrapModalRef.value.openModal();
      }
    }

    return { modalRef, bootstrapModalRef, openModal, openBootStrapModal };
  },
};
</script>

<style>
.container {
  max-width: 600px;
  width: 600px;
  height: 600px;
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background: #f9f9f9;
  color: #0056b3;
  text-align: center;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 15px;
}

th,
td {
  border: 1px solid #ddd;
  padding: 8px;
  color: #007bff;
}

th {
  background: #eee;
}

button {
  padding: 10px 15px;
  border: none;
  background: #007bff;
  color: white;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background: #0056b3;
}
</style>
