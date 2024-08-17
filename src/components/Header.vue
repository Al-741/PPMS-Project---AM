

<!-- HEADER COMPONENTS SCRIPT -->


<script>
export default {
  name: 'HeaderComponent',
  props: {
    isDarkMode: {
      type: Boolean,
      default: false,
    },
  },
};
</script>



<template>
  <header :class="{'dark-mode': isDarkMode}">
    <img src="..\assets\logo_name.png" alt="PPMS Logo" class="logo_name"/>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#Training">Training</a></li>
        <li><a href="#Projects">Projects</a></li>
        <li><a href="#Orders">Orders</a></li>
        <li><a href="#Documents">Documents</a></li>
        <li><a href="#Incidents">Incidents</a></li>
        <li><a href="#Profile">Profile</a></li>
        <li><a href="#Logout">Logout</a></li>
      </ul>
    </nav>    
  </header>
</template>


<!-------------------------------------->
<style>
 header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    background-color: #f8f9fa;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  .logo_name {
    size: 1rem;
  }

  nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    gap: 20px;
  }

  nav ul li {
    margin: 0;
  }

  nav ul li a {
    text-decoration: none;
    color: #333;
    font-weight: 500;
  }

  nav ul li a:hover {
    color: #007bff;
  }

  
  .dark-mode header {
  background-color: #2a2a2a;
  color: #ffffff;
}

.dark-mode nav ul li a {
  color: #ffffff;
}

.dark-mode nav ul li a:hover {
  color: #66b2ff;
}
</style>