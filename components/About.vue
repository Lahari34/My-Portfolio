<template>
    <section id="about-section" class="about-section">
      <div class="about-content">
        <!-- Left Side: About Text -->
        <div class="about-text">
          <h1>About</h1>
          <h2 class="typewriter">Get to Know Me!</h2>
          <p>{{ aboutUser }}</p>
          <button @click="toggleExtraDetails" class="details-button">
            {{ showDetails ? 'Hide Details' : 'Show More' }}
          </button>
  
          <!-- Extra Details (Toggled) -->
          <div v-if="showDetails" class="extra-details">
            <p><strong>Address</strong>: {{ userDetails.address }}</p>
            <p><strong>School</strong>: {{ userDetails.school }}</p>
            <p><strong>College</strong>: {{ userDetails.college }}</p>
            <p><strong>Languages</strong>: {{ userDetails.languages }}</p>
            <p><strong>Interests</strong>: {{ userDetails.interests }}</p>
            <p><strong>Internship</strong>{{ userDetails.internship }}</p>
          </div>
        </div>
  
        <!-- Right Side: Image and Skills -->
        <div class="about-image-skills">
          <div class="image-container">
            <img src="https://i.ibb.co/FwPStmW/profile-Pic.jpg" alt="User Image" class="profile-image" />
          </div>
          <div class="skills">
            <span v-for="(skill, index) in userSkills" :key="index" class="skill">
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        aboutUser: 'I am a passionate software Developer with self-directed and motivated to apply education and experience in a job role. Excellent listener comfortable completing various tasks to keep operations running smoothly.Energetic individual with outstanding interpersonal, analytical and critical thinking skills.',
        showDetails: false,
        userDetails: {
          address: 'Hyderabad',
          school: 'Dr.HR Techno Schools',
          college: 'Bhoj Reddy Engineering College for Women',
          languages: 'English, Telugu, Hindi',
          interests: 'Listening to Music, Dancing, Watching Movies, Arts, Knowing Amazing Facts',
          internship: 'I have worked as an Intern Bachelor Software Engineer for Honeywell, Bengaluru for 6-months where I had a previlege to work individually on an Immersive project- Immersive Field Simulator(IFS) Virtual Tour. This made me become confident enough to work in any environment and to take challenges',
        },
        userSkills: ['C#', 'ASP.NET', 'Unity 3D', 'React Js', 'SignalR', 'Java', 'C++', 'SQL', 'Python','HTML', 'CSS', 'JavaScript', 'C']
      };
    },
    methods: {
      toggleExtraDetails() {
        this.showDetails = !this.showDetails;
      }
    }
  };
  </script>
  
  <style scoped>
  .about-section {
    background-color: black; /* Changed to black */
    padding: 50px 20px;
  }
  
  .about-content {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    max-width: 1500px;
    margin: 0 auto;
  }
  
  .about-text {
    flex: 1 1 60%;
    padding-right: 20px;
  }
  
  h1 {
    font-size: 48px;
    margin-bottom: 10px;
    color: white; /* Changed to white */
    text-transform: uppercase;
  }
  
  .typewriter {
    font-size: 36px;
    color: red;
    margin-bottom: 20px;
    white-space: nowrap;
    overflow: hidden;
    border-right: 3px solid;
    width: 0;
    animation: typing 3.5s steps(20, end) infinite, blink-caret 0.40s step-end infinite;
  }
  
  @keyframes typing {
    from { width: 0; }
    to { width: 18ch; }
  }
  
  @keyframes blink-caret {
    from, to { border-color: transparent; }
    50% { border-color: red; }
  }
  
  p {
    font-size: 18px;
    color: white; /* Ensure paragraph text is white on black background */
    margin-bottom: 20px;
  }
  
  .details-button {
    background-color: red;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    margin-bottom: 20px;
    border-radius: 5px;
  }
  
  .details-button:hover {
    background-color: darkred;
  }
  
  .extra-details p {
    font-size: 18px;
    color: white; /* Ensure extra details text is white */
    margin-bottom: 10px;
  }
  
  .extra-details p strong {
    min-width: 120px;
    display: inline-block;
    text-align: left;
  }
  
  /* Right Side: Image and Skills */
  .about-image-skills {
    flex: 1 1 35%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .image-container {
    margin-bottom: 20px;
  }
  
  .profile-image {
    width: 300px;
    height: 300px;
  }

  .profile-image:hover {
    opacity: 0.5;
  }

  .about-image-skills {
  flex: 1 1 35%;
  display: flex;
  flex-direction: column;
  align-items: center;
  }

.skills {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
  }

  .skill {
  background-color: rgb(247, 242, 242);
  color: black;
  padding: 10px 20px;
  border-radius: 10px;
  font-size: 14px;
  white-space: nowrap;
}
   
</style>  