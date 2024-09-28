<template>
    <section id="intro-section" class="intro">
      <div class="intro-content">
        <!-- Left: Image -->
        <div class="image-container">
          <img src="https://i.ibb.co/FwPStmW/profile-Pic.jpg" alt="User Image" class="profile-image" />
        </div>
        <!-- Right: Text -->
        <div class="text-container">
          <h1>Software Developer</h1>
          <h2> Hi I'm <span class="user-name">{{ userName }}</span></h2>
          <p>{{ userIntro }}</p>
          <button @click="navigateToProjects" class="projects-button">Projects</button>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        userName: 'Lahari Tipirishetty', // Replace this with dynamic user name or props
        userIntro: 'I am a Software Developer based in India, with a passion for creating elegant and efficient solutions that seamlessly integrate user-friendly experience. I have built an application leveraging cutting-edge technologies to drive innovation.', 
      };
    },
    methods: {
      navigateToProjects() {
        const projectsSection = document.getElementById('projects-section');
        if (projectsSection) {
          projectsSection.scrollIntoView({ behavior: 'smooth' });
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .intro {
    background-color: black;
    color: white;
    padding: 50px 20px;
    margin-top: 5%;
  }
  
  .intro-content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    max-width: 1200px;
    margin: 0 auto;
  }
  
  .image-container {
    flex: 1 1 200px;
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
  }
  .image-container:hover {
    opacity: 0.5;
  }
  
  .profile-image {
    width: 250px;
    height: 250px;
    border-radius: 50%;
    object-fit: cover;
    size: 50px;
  }
  
  .text-container {
    flex: 2 1 500px;
    color: white;
    text-align: left;
  }
  
  h1 {
    font-size: 48px;
    margin-bottom: 20px;
    text-transform: uppercase;
  }
  
  h2 {
    font-size: 36px;
    margin-bottom: 20px;
  }
  
  .user-name {
    color: red;
  }
  
  p {
    font-size: 18px;
    margin-bottom: 30px;
  }
  
  .projects-button {
    background-color: red;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 18px;
    cursor: pointer;
    border-radius: 5px;
  }
  
  .projects-button:hover {
    background-color: darkred;
  }
  
  /* Responsive design */
  @media (max-width: 768px) {
    .intro-content {
      flex-direction: column;
      text-align: center;
    }
  
    .text-container {
      text-align: center;
    }
  
    h1, h2 {
      font-size: 30px;
    }
  
    p {
      font-size: 16px;
    }
  }
  </style>
  