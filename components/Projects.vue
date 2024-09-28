<template>
    <section id="projects-section" class="projects-section">
      <h1>Projects</h1>
      <div class="projects-container">
        <!-- Project 1: Ultimate Frolic Hub -->
        <div class="project-item">
          <img src="https://i.ibb.co/fFf6BrX/project1.png" alt="Ultimate Frolic Hub" class="project-image" />
          <h2>Ultimate Frolic Hub</h2>
          <button @click="toggleDetails('project1')" class="show-more-btn">
            {{ showProject1Details ? 'Show Less' : 'Show More' }}
          </button>
          <p v-if="showProject1Details" class="project-details">
            The “Ultimate Frolic Hub” is a gaming platform that offers a pool of four classic and engaging games designed to provide endless entertainment. 
            With diverse games like Memory Matching, Word Chaining, Word Scramble, and Ultimate Tic-Tac-Toe, this hub promises hours of fun, intellectual stimulation, and strategic gameplay for all ages.
          </p>
        </div>
  
        <!-- Project 2: Detection of Phishing Websites -->
        <div class="project-item">
          <img src="https://i.ibb.co/1QzjhNL/project2.png" alt="Detection of Phishing Websites" class="project-image" />
          <h2>Detection of Phishing Websites</h2>
          <button @click="toggleDetails('project2')" class="show-more-btn">
            {{ showProject2Details ? 'Show Less' : 'Show More' }}
          </button>
          <p v-if="showProject2Details" class="project-details">
            This project involves the development of a machine learning-based system to detect phishing websites by analyzing URL features. It uses feature engineering on lexical, network-based, and reputation properties to identify phishing URLs accurately.
          </p>
        </div>
  
        <!-- Project 3: IFS Virtual Tour -->
        <div class="project-item">
          <img src="https://i.ibb.co/hFNwPF0/project3.jpg" alt="IFS Virtual Tour" class="project-image" />
          <h2>IFS Virtual Tour</h2>
          <button @click="toggleDetails('project3')" class="show-more-btn">
            {{ showProject3Details ? 'Show Less' : 'Show More' }}
          </button>
          <p v-if="showProject3Details" class="project-details">
            The IFS Virtual Tour is a digital replica of a physical plant, typically accessed through VR or a digital device. It allows for immersive training and exploration of a plant, ensuring the safety and guidance of users in hazardous environments.
          </p>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        showProject1Details: false,
        showProject2Details: false,
        showProject3Details: false,
        activeProject: null,
      };
    },
    methods: {
      toggleDetails(project) {
        if (project === 'project1') {
          this.showProject1Details = !this.showProject1Details;
          this.showProject3Details = null;
          this.showProject2Details = null;
        } else if (project === 'project2') {
          this.showProject2Details = !this.showProject2Details;
          this.showProject1Details = null;
          this.showProject3Details = null;
        } else if (project === 'project3') {
          this.showProject3Details = !this.showProject3Details;
          this.showProject1Details = null;
          this.showProject2Details = null;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .projects-section {
    background-color: black; /* Background color is black */
    padding: 50px 20px;
    color: white;
    text-align: center;
  }
  
  h1 {
    font-size: 48px;
    margin-bottom: 40px;
    color: white; /* White text for the heading */
    text-transform: uppercase;
  }
  
  .projects-container {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    max-width: 1200px;
    margin: 0 auto;
  }
  
  .project-item {
    flex: 1 1 30%;
    margin-bottom: 40px;
    text-align: center;
  }
  
  .project-image {
    width: 100%;
    height: auto;
    border-radius: 8px;
    object-fit: cover;
  }
  
  h2 {
    font-size: 24px;
    margin-top: 15px;
  }
  
  .show-more-btn {
    background-color: blue; /* Button color is blue */
    color: white; /* Text color is white */
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 15px;
  }
  
  .show-more-btn:hover {
    background-color: darkblue;
  }
  
  .project-details {
    margin-top: 15px;
    font-size: 16px;
  }
  
  /* Responsive Design */
  @media (max-width: 768px) {
    .projects-container {
      flex-direction: column;
      align-items: center;
    }
  
    .project-item {
      flex: 1 1 100%;
      margin-bottom: 20px;
    }
  }
  </style>
  