<template>
  <div class="message-container">
    <p>{{ msg }}</p>
  </div>
</template>
<script>
export default {
  name: "Message",
  props: {
    msg: String,
  },
  methods: {
    showMessage() {
      if (this.msg) {
        document.querySelector(".message-container").style.display = "flex";
      } else {
        document.querySelector(".message-container").style.display = "none";
      }
    },
  },
  mounted() {
    this.showMessage();
  },
  watch: {
    msg() {
      this.showMessage();
    },
  },
};
</script>
<style scoped>
.message-container {
  color: #004085;
  background-color: #cce5ff;
  border: 2px solid #b8daff;
  border-radius: 5px;
  padding: 10px;
  max-width: 400px;
  margin: 30px auto;
  display: none;
}
</style>
