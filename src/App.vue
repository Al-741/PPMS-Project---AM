

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
};
</script>



<!-------------------------------------->
<template>
  <div id="app">
    <HeaderComponent />
    <BodyComponent @open-popup="showPopup = true" />
    <PopupComponent :visible="showPopup" @close="showPopup = false" />
    <FooterComponent />
  </div>
</template>




<!-------------------------------------->
<style>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  padding-bottom: 60px; /* Make space for footer */
  position: relative;
  min-height: 100vh;
}

#app {
  text-align: center;
}

main {
  padding: 20px;
}

main section {
  margin: 40px 0;
}
</style>
