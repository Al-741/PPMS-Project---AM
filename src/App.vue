

<!-- APP SCRIPT -->


<script>
import HeaderComponent from './components/Header.vue';
import BodyComponent from './components/Body.vue';
import PopupComponent from './components/Popup.vue';
import FooterComponent from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    BodyComponent,
    PopupComponent,
    FooterComponent,
  },
  data() {
    return {
      showPopup: false,
    };
  },
  methods: {
  toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      document.body.classList.toggle('dark-mode', this.isDarkMode);
    },}
};
</script>



<!-------------------------------------->
<template>
  <div id="app" :class="{'dark-mode': isDarkMode}">
    <HeaderComponent :isDarkMode="isDarkMode"  />
    <BodyComponent @open-popup="showPopup = true" :isDarkMode="isDarkMode" /> 
    <PopupComponent :visible="showPopup" @close="showPopup = false" />
    <FooterComponent :isDarkMode="isDarkMode" @toggleDarkMode="toggleDarkMode" />
  </div>
</template>




<!-------------------------------------->
<style>
/* General Styles */
#app {
  text-align: center;
  background-color: #f4f4f4;
  color: #333;
  transition: background-color 0.3s ease, color 0.3s ease;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
}

/* Dark Mode Styles */
.dark-mode {
  background-color: #1e1e1e;
  color: #ffffff;
}


</style>