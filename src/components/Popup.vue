
<!-- POPUP COMPONENTS SCRYPT -->


<script>
export default {
  name: 'PopupComponent',
  props: {
    visible: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    closePopup() {
      this.$emit('close');
    },
  },
};
</script>

<!-------------------------------------->
<template>
  <div v-if="visible" class="popup-overlay">
    <div class="popup-content">
      <h2>Popup Title</h2>
      <p>POPUP P</p>
      <button @click="closePopup">Close</button>
    </div>
  </div>
</template>



<!-------------------------------------->
<style scoped>
.popup-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup-content {
  background: white;
  padding: 20px;
  border-radius: 8px;
  text-align: center;
  color:rgba(0, 0, 0, 0.7)
}

.popup-content button {
  margin-top: 20px;
  padding: 10px 20px;
}
</style>
