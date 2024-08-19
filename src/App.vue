<!-- APP -->

<!-------------------------------------->
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
      isDarkMode: false,
    };
  },
  methods: {
  toggleDarkMode() {
    this.isDarkMode = !this.isDarkMode;
    if (this.isDarkMode) {
      document.documentElement.classList.add('dark_mode');
    } else {
      document.documentElement.classList.remove('dark_mode');
    }
  },
  },
  mounted() {
    if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
      this.isDarkMode = true;
      this.toggleDarkMode(true);
    }
  },
};
</script>



<!-------------------------------------->
<template>
  <div id="app">
    <HeaderComponent :isDarkMode="isDarkMode" @update:isDarkMode="toggleDarkMode" />
    <BodyComponent @open-popup="showPopup = true" :isDarkMode="isDarkMode" /> 
    <PopupComponent :visible="showPopup" @close="showPopup = false" />
    <FooterComponent :isDarkMode="isDarkMode" />
  </div>
</template>




<!-------------------------------------->
<style>
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-size: 14px; 
  padding: 0 1rem; 
}

header, footer {
  flex-shrink: 0;
}

body, #app {
  margin: 0;
  padding: 0;
  background-color: var(--bg-color);
  transition: background-color 0.3s ease;
}

main {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  background-color: var(--body-bg-color);
  transition: background-color 0.3s ease;
}

/* Dark Mode Styles */

.dark_mode #app {
  background-color: var(--dark-body-bg-color);
  
}

/* Responsive */
@media (min-width: 1200px) {
  #app {
    font-size: 14px;
    padding: 0 1rem;
  }
}

@media (max-width: 800px) {
  #app {
    font-size: 12px; 
    padding: 0 1rem;
  }
}





</style>