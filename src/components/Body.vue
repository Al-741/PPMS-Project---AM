

<!-- BODY COMPONENTS SCRYPT -->

<script>
export default {
  name: 'BodyComponent',
  methods: {
    openPopup() {
      this.$emit('open-popup');
    },
  },
};
</script>


<!-------------------------------------->
<template>
  <main>
    <section id="home">
      <h1> BODY </h1>
      <p>BODY P</p>
    </section>
    <button @click="openPopup">Open Popup</button>
  </main>
</template>

<!--------------------------------------->
<style scoped>
main {
  padding: 20px;
  color:rgba(0, 0, 0, 0.7);
}

main section {
  margin: 40px 0;
}
</style>
