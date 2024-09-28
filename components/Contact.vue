<template>
    <section id="contact-section" class="contact-section">
      <h1>Contact</h1>
      <div class="contact-container">
        <!-- User Name -->
        <div class="contact-block">
          <label for="username">Username: </label>
          <div class="contact-info">{{ contactInfo.name }}</div>
        </div>
  
        <!-- Email -->
        <div class="contact-block">
          <label for="email">Email: </label>
          <div class="contact-info">{{ contactInfo.email }}</div>
        </div>
  
        <!-- Contact Number -->
        <div class="contact-block">
          <label for="phone">Contact Number: </label>
          <div class="contact-info">{{ contactInfo.phone }}</div>
        </div>
  
        <!-- Hire Me Button -->
        <button @click="showThankYou" class="hire-btn">
          {{ contactInfo.hireme }}
        </button>
  
        <!-- Thank You Message and Handshake Image -->
        <div v-if="thankYouVisible" class="thank-you-container">
          <h2 class="thank-you-text">Thank You!</h2>
          <img src="https://i.ibb.co/HDCCd69/download.jpg" alt="Handshake" class="handshake-image" />
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        contactInfo: {
          name: 'Lahari Tipirishetty',
          email: 'laharitsh34@gmail.com',
          phone: '7893833076',
          hireme: 'Hire Me!'
        },
        thankYouVisible: false
      };
    },
    methods: {
      showThankYou() {
        this.thankYouVisible = true;
        setTimeout(() => {
          // Reset thank you message visibility after 5 seconds
          this.thankYouVisible = false;
        }, 5000);
      }
    }
  };
  </script>
  
  <style scoped>
  .contact-section {
    background-color: black; /* Black background for the contact section */
    padding: 50px 20px;
    color: white;
    text-align: center;
  }
  
  h1 {
    font-size: 48px;
    margin-bottom: 40px;
    color: white;
    text-transform: uppercase;
  }
  
  .contact-container {
    max-width: 600px;
    margin: 0 auto;
  }
  
  .contact-block {
    background-color: #d3d3d3; /* Pale gray rounded blocks */
    color: black;
    border-radius: 30px;
    padding: 15px 20px;
    margin-bottom: 20px;
    display: flex;
    justify-content: center; /* Center the content horizontally */
    align-items: center;     /* Center the content vertically */
    flex-direction: row;  /* Stack label and contact info vertically */
  }
  
  .contact-block label {
    font-weight: bold;
  }
  
  .contact-info {
    font-size: 18px;
    text-align: center;
  }
  
  .hire-btn {
    background-color: green; /* Green button with white text */
    color: white;
    border: none;
    padding: 15px 30px;
    font-size: 18px;
    border-radius: 30px;
    cursor: pointer;
    margin-top: 20px;
  }
  
  .hire-btn:hover {
    background-color: darkgreen;
  }
  
  .thank-you-container {
    margin-top: 30px;
    animation: fadeIn 1.5s ease-out; /* Fade in animation for Thank You text */
  }
  
  .thank-you-text {
    font-size: 36px;
    color: white;
    margin-bottom: 20px;
    animation: shake 0.5s; /* Shake animation for Thank You text */
  }
  
  .handshake-image {
    width: 150px;
    height: auto;
    animation: fadeIn 2s ease-out; /* Fade in animation for Handshake image */
  }
  
  /* Keyframes for animations */
  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  
  @keyframes shake {
    0% { transform: translate(1px, 1px) rotate(0deg); }
    10% { transform: translate(-1px, -2px) rotate(-1deg); }
    20% { transform: translate(-3px, 0px) rotate(1deg); }
    30% { transform: translate(3px, 2px) rotate(0deg); }
    40% { transform: translate(1px, -1px) rotate(1deg); }
    50% { transform: translate(-1px, 2px) rotate(-1deg); }
    60% { transform: translate(-3px, 1px) rotate(0deg); }
    70% { transform: translate(3px, 1px) rotate(-1deg); }
    80% { transform: translate(-1px, -1px) rotate(1deg); }
    90% { transform: translate(1px, 2px) rotate(0deg); }
    100% { transform: translate(1px, -2px) rotate(-1deg); }
  }
  
  /* Responsive Design */
  @media (max-width: 768px) {
    .contact-block {
      flex-direction: column;
      text-align: left;
    }
  }
  </style>
  