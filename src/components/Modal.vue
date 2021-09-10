<template>
  <div class="backdrop">
    <div class="modal" :class="{ dark: theme === 'dark' }">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  data() {
    return {
      title: "Modal Content",
    };
  },
};
</script>

<style>
.backdrop {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  display: grid;
  place-content: center;
}
.modal {
  min-width: 360px;
  background: #fff;
  padding: 25px;
  border-radius: 12px;
}
.modal.dark {
  background: black;
  color: #fff;
}
.modal h1 {
  margin-bottom: 30px;
}
</style>