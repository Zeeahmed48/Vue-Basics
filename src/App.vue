<template>
  <button @click="openModal" class="open_modalBtn">Open Modal</button>
  <div v-if="showModal">
    <Modal :header="header" :text="text" :theme="theme" />
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first Vue App",
      header: "Signup",
      text: "Doesn't have an Account",
      theme: "default",
      showModal: false,
    };
  },
  methods: {
    openModal() {
      this.showModal = true;
    },
  },
};
</script>

<style>
.open_modalBtn {
  background: rosybrown;
  color: #fff;
  font-size: 16px;
  padding: 12px 18px;
  border-radius: 8px;
  border: none;
}
</style>
