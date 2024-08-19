<!-- FOOTER COMPONENTS -->

<!-------------------------------------->
<template>
  <footer>
    <img src="../assets/logo.png" alt="PPMS_Logo" class="logo" />
    <nav>
      <ul>
        <li><a href="#terms">Terms of Service</a></li>
        <li><a href="#contact">Contact Us</a></li>
      </ul>
    </nav>
    <p>&copy; PPMS Exercise Alice Miermon</p>
 </footer>
</template>



<!-------------------------------------->
<script>
export default {
  name: 'FooterComponent',
  props: {
    isDarkMode: {
      type: Boolean,
      default: false,
    },
  },
};
</script>



<!-------------------------------------->
<style scoped>
footer {
  padding: 20px;
  padding-top: 1rem;
  text-align: center;
  background-color: var(--bg-color);
  color: var(--title-color);
  transition: background-color 0.3s ease, color 0.3s ease;
}

footer p {
  margin-top: 1rem;
  font-size: 14px;
}

footer nav ul {
  display: flex;
  justify-content: center;
  gap: 15px;
  list-style: none;
  padding: 0;
  margin: 10px 0 0 0;
}

footer nav ul li a {
  text-decoration: none;
  color: inherit;
  font-size: 14px;
  transition: color 0.3s ease;
}

footer nav ul li a:hover {
  color: var(--link-hover-color);
}

.logo{
  height: 40px;
  width: auto;
  margin-right: auto;
}
.dark_mode footer {
  background-color: var(--dark-body-bg-color);
  color: var(--footer-dark-title-color);
}
</style>
