

<!-- BODY COMPONENTS SCRYPT -->

<script>
export default {
  name: 'BodyComponent',
  methods: {
    openPopup() {
      this.$emit('open-popup');
    },
  },

  props: {
    isDarkMode: {
      type: Boolean,
      default: false,
    },
  },
};
</script>


<!-------------------------------------->
<template>
  <div class="{'dark-mode': isDarkMode}">
    <section class="intro">
      <h2>Welcome to Our Website</h2>
      <p>This is a brief introduction to what we do.</p>
    </section>

    <section class="features">
      <h2>Our Features</h2>
      <div class="feature-block">
        <h3>Feature 1</h3>
        <p>Description of Feature 1.</p>
      </div>
      <div class="feature-block">
        <h3>Feature 2</h3>
        <p>Description of Feature 2.</p>
      </div>
      <div class="feature-block">
        <h3>Feature 3</h3>
        <p>Description of Feature 3.</p>
      </div>
    </section>

    <section class="services">
      <h2>Our Services</h2>
      <div class="service-block">
        <h3>Service 1</h3>
        <p>Details about Service 1.</p>
      </div>
      <div class="service-block">
        <h3>Service 2</h3>
        <p>Details about Service 2.</p>
      </div>
    </section>

    <section class="testimonials">
      <h2>What Our Clients Say</h2>
      <blockquote>
        "This service is amazing! Highly recommend."
        <cite>- Happy Client</cite>
      </blockquote>
    </section>
    <button @click="openPopup">Open Popup</button>
  </div>
</template>




<!--------------------------------------->
<style scoped>
  /* General Body Styling */
  body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
  }

  /* Section Styling */
  section {
    padding: 20px;
    margin: 20px 0;
    background-color: #ffffff;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }

  /* Specific Section Styling */
  .intro {
    background-color: #e3f2fd;
  }

  .features {
    background-color: #f9fbe7;
  }

  .services {
    background-color: #ffebee;
  }

  .testimonials {
    background-color: #e8f5e9;
  }

  /* Feature and Service Block Styling */
  .feature-block,
  .service-block {
    margin-bottom: 20px;
  }

  h2 {
    margin-top: 0;
    color: #333;
  }

  h3 {
    margin-bottom: 10px;
    color: #555;
  }

  p {
    margin: 0;
    color: #666;
  }

  blockquote {
    font-style: italic;
    color: #555;
    padding-left: 10px;
    margin: 10px 0;
  }

  cite {
    display: block;
    margin-top: 5px;
    text-align: right;
    color: #333;
  }

  /* Dark Mode Styles */
.dark-mode {
  background-color: #2a2a2a;
  color: #ffffff;
}

.dark-mode section {
  background-color: #333;
  color: #ffffff;
}
</style>


