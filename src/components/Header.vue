

<!-- HEADER COMPONENTS SCRIPT -->


<script>
export default {
  name: 'HeaderComponent',
};
</script>



<!-------------------------------------->
<template>
  <header>
    <img src="..\assets\logo_name.png" alt="PPMS Logo" />
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
<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  background-color: var(--header-bg);
}
</style>