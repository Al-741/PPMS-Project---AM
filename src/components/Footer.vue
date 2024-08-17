

<!-- FOOTER COMPONENT SCRYPT -->

<script>
export default {
  props: {
    isDarkMode: Boolean,
  },
  methods: {
    toggleDarkMode() {
      this.$emit('toggleDarkMode');
    },
  },
};
</script>



<!-------------------------------------->
<template>
  <footer>
    <div class="footer-content">
      <p>&copy; 2024 Your Company. All rights reserved.</p>
      <button @click="toggleDarkMode" class="dark-mode-toggle">
        <img :src="isDarkMode ? '..\assets\sun.svg' : '..\assets\moon.svg'" :alt="isDarkMode ? 'Light Mode' : 'Dark Mode'" />
      </button>
    </div>
  </footer>
</template>



<style scoped>
footer {
  padding: 20px;
  background-color: #f8f9fa;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
  color:#333;
}

/* Ensure the content within the footer is aligned and visible */
.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

/* Dark Mode Toggle Button Styles */
.dark-mode-toggle {
  background: none;
  border: none;
  cursor: pointer;
}

.dark-mode-toggle img {
  width: 30px;
  height: 30px;
}

/* Dark Mode Styles in Footer */
.dark-mode footer {
  background-color: #333;
  color: #fff;
}
</style>