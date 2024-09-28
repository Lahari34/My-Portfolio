<template>
    <header class="header">
      <nav class="navbar">
        <!-- Branding / Logo -->
        <div class="navbar-brand">
          <span class="username">{{ userName }}</span>
        </div>
  
        <!-- Desktop Menu -->
        <ul class="navbar-links" v-if="!isMobile">
          <li><a href="javascript:void(0)" @click="scrollToSection('intro-section')">Intro</a></li>
          <li><a href="javascript:void(0)" @click="scrollToSection('about-section')">About</a></li>
          <li><a href="javascript:void(0)" @click="scrollToSection('projects-section')">Projects</a></li>
          <li><a href="javascript:void(0)" @click="scrollToSection('contact-section')">Contact</a></li>
        </ul>
  
        <!-- Mobile Menu -->
        <div class="mobile-menu" v-if="isMobile">
          <button @click="toggleMenu" class="menu-button">
            &#9776; <!-- Menu Icon -->
          </button>
          <ul v-if="showMenu" class="dropdown-menu">
            <li><a href="javascript:void(0)" @click="scrollToSection('intro-section'); toggleMenu()">Intro</a></li>
            <li><a href="javascript:void(0)" @click="scrollToSection('about-section'); toggleMenu()">About</a></li>
            <li><a href="javascript:void(0)" @click="scrollToSection('projects-section'); toggleMenu()">Projects</a></li>
            <li><a href="javascript:void(0)" @click="scrollToSection('skills-section'); toggleMenu()">Skills</a></li>
          </ul>
        </div>
      </nav>
    </header>
  </template>
  
  <script>
  export default {
    data() {
      return {
        userName: "My Portfolio", // Replace with dynamic user name if needed
        isMobile: false,
        showMenu: false
      };
    },
    mounted() {
      this.checkMobile();
      window.addEventListener("resize", this.checkMobile);
    },
    beforeDestroy() {
      window.removeEventListener("resize", this.checkMobile);
    },
    methods: {
      checkMobile() {
        this.isMobile = window.innerWidth <= 768;
      },
      toggleMenu() {
        this.showMenu = !this.showMenu;
      },
      scrollToSection(sectionId) {
        const section = document.getElementById(sectionId);
        if (section) {
          window.scrollTo({
            top: section.offsetTop,
            behavior: "smooth"
          });
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .header {
    background-color: #333;
    padding: 10px;
    color: white;
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 1000;
  }
  
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .navbar-brand {
    font-size: 20px;
    font-weight: bold;
    padding-left: 3%;
  }
  
  .navbar-links {
    list-style: none;
    display: flex;
    gap: 20px;
    padding-right: 5%;
  }
  
  .navbar-links a {
    color: white;
    text-decoration: none;
    cursor: pointer;
  }
  
  .mobile-menu {
    display: none;
  }
  
  .menu-button {
    background-color: transparent;
    color: white;
    border: none;
    font-size: 24px;
    cursor: pointer;
    padding-right: 30px;
  }
  
  .dropdown-menu {
    list-style: none;
    background-color: #333;
    padding: 10px;
    padding-right: 25px;
    position: absolute;
    top: 50px;
    right: 10px;
    z-index: 1000;
  }
  
  .dropdown-menu li {
    margin-bottom: 10px;
  }
  
  .dropdown-menu a {
    color: white;
    text-decoration: none;
    cursor: pointer;
  }
  
  @media (max-width: 768px) {
    .navbar-links {
      display: none;
    }
    .mobile-menu {
      display: block;
    }
  }
  </style>
  