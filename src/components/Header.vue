<!-- HEADER COMPONENTS -->

<!-------------------------------------->
<template>
  <header>
    <div class="header_content">
      <a href="#home">
        <img src="../assets/logo_name.png" alt="PPMS Logo" class="logo_name" />
      </a>
      <nav class="center_nav">
        <ul class="nav_list">
          <li><a href="#home">Home</a></li>
          <li><a href="#Training">Training</a></li>
          <li><a href="#Projects">Projects</a></li>
          <li><a href="#Orders">Orders</a></li>
          <li><a href="#Documents">Documents</a></li>
          <li><a href="#Incidents">Incidents</a></li>
        </ul>
      </nav>
      <div class="right_group">
        <ul class="right_nav_list" v-if="!isMenuOpen">
          <li><a href="#Profile">Profile</a></li>
          <li><a href="#Logout">Logout</a></li>
        </ul>
        <button class="menu_toggle" @click="toggleMenu">&#9776;</button>
        <label class="switch">
          <input type="checkbox" :checked="isDarkMode" @change="onToggleDarkMode">
          <span class="slider round">
            <img src="../assets/moon.svg" alt="Moon Icon" class="icon moon-icon" />
            <img src="../assets/sun.svg" alt="Sun Icon" class="icon sun-icon" />
          </span>
        </label>
      </div>

      <!------Hamburger Menu----->
      <nav class="mobile_nav" v-if="isMenuOpen">
        <ul class="nav_list">
          <li><a href="#home"  @click="closeMenu">Home</a></li>
          <li><a href="#Training"  @click="closeMenu">Training</a></li>
          <li><a href="#Projects"  @click="closeMenu">Projects</a></li>
          <li><a href="#Orders"  @click="closeMenu">Orders</a></li>
          <li><a href="#Documents"  @click="closeMenu">Documents</a></li>
          <li><a href="#Incidents"  @click="closeMenu">Incidents</a></li>
          <li><a href="#Profile"  @click="closeMenu">Profile</a></li>
          <li><a href="#Logout"  @click="closeMenu">Logout</a></li>
        </ul>
      </nav>

    </div>
  </header>
</template>


<!-------------------------------------->
<script>
export default {
  name: 'HeaderComponent',
  props: {
    isDarkMode: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      isMenuOpen: false,
    };},
  methods: {
    onToggleDarkMode(event) {
      this.$emit('update:isDarkMode', event.target.checked);
    },
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },

    closeMenu() {
      this.isMenuOpen = false;
    },

  },
};
</script>



<!-------------------------------------->
<style>

header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1rem;
  background: none;
  color: var(--font-color);
  transition: color 0.3s ease;
}

.header_content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.logo_name {
  height: 40px;
  width: auto;
  margin-right: auto;
}


.center_nav {
  flex: 1;
  display: flex;
  justify-content: center;
}

.nav_list {
  display: flex;
  align-items: center;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 1.5rem;
}

.right_group {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-left: auto;
}

.right_nav_list {
  display: flex;
  align-items: center;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 1rem;
}


nav ul li a, .right_nav_list li a {
  text-decoration: none;
  color: inherit;
  font-weight: 500;
  position: relative;
  padding-bottom: 5px;
  transition: color 0.3s ease;
}


nav ul li a:hover, .right_nav_list li a:hover {
  color: var(--link-hover-color);
}

nav ul li a:hover::after, .right_nav_list li a:hover::after {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 2px;
  background-color: var(--link-color);
}


.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  transition: .4s;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 5px;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  transition: .4s;
}

input:checked + .slider {
  background-color: #2196F3;
}

input:checked + .slider:before {
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}


.icon {
  width: 16px;
  height: 16px;
}

.sun_icon {
  position: absolute;
  left: 8px;
}

.moon_icon {
  position: absolute;
  right: 8px;
}


.menu_toggle {
  display: none;
  background: none;
  border: none;
  font-size: 24px;
  cursor: pointer;
}


.mobile_nav {
  display: none;
}

.mobile_nav_list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

/* Dark Mode */
.dark_mode header {
  background-color: var(--dark-body-bg-color);
  color: var(--dark-title-color);
}

.dark_mode nav ul li a:hover, .right_nav_list li a:hover {
  color: var(--dark-link-hover-color);
}

.dark_mode ul li a:hover::after, .right_nav_list li a:hover::after {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 2px;
  background-color: var(--dark-link-color);
}


.dark_mode .switch .slider {
  background-color: #666;
}

.dark_mode .switch input:checked + .slider {
  background-color: var(--dark-link-color);
}

.dark_mode .menu_toggle{
  color: rgba(255, 255, 255, 0.796)
}



/* Responsive */
@media (max-width: 768px) {
  .center_nav,
  .right_nav_list {
    display: none;
  }
  
  .menu_toggle {
    display: block;
  }
  
  
  .mobile_nav {
    display: block;
    position: absolute;
    top: 60px;
    right: 20px;
    background-color: rgb(246, 246, 246);
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    z-index: 1000; 
  }

  
  .mobile_nav_list li a {
    padding: 10px;
    background-color: var(--item-bg-color);
    border-radius: 4px;
  }

  .mobile_nav_list li a:hover {
    background-color: var(--link-hover-bg);
  }

  .dark_mode .mobile_nav {
  background-color: #426975;
  color: var(--dark-title-color); 
}
}
</style>
