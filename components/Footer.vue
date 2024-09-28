<template>
    <footer class="footer">
      <div class="footer-content">
        <p>© {{ currentYear }} My Portfolio. All Rights Reserved.</p>
        <p>Thank you!</p>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentYear: new Date().getFullYear(),
      };
    },
  };
  </script>
  
  <style scoped>
  .footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 20px 10px;
    position: relative;
    bottom: 0;
    width: 100%;
  }
  
  .footer-content p {
    margin: 0;
    font-size: 16px;
  }
  
  .footer-content p:first-of-type {
    margin-bottom: 10px;
  }
  </style>
  