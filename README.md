<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Ethan's Math Class Enrollment</title>
  <!-- Import a cute, playful font -->
  <link href="https://fonts.googleapis.com/css2?family=Indie+Flower&display=swap" rel="stylesheet">
  <style>
    /* Global Styles */
    body {
      font-family: 'Indie Flower', cursive;
      margin: 0;
      padding: 0;
      background: #f0f8ff;
    /* Header */
    header {
      background: linear-gradient(90deg, #ff7eb3, #ff758c);
      color: #fff;
      padding: 20px;
      text-align: center;
      position: sticky;
      top: 0;
      z-index: 1000;
      border-bottom: 3px solid #fff;
    }
    header h1 {
      font-size: 3em;
      margin: 0;
    }
    header p {
      font-size: 1.5em;
      margin: 10px 0;
    }
    .header-buttons {
      margin-top: 15px;
    }
    .header-buttons button {
      background: #fff;
      color: #ff758c;
      border: none;
      padding: 12px 25px;
      font-size: 20px;
      cursor: pointer;
      border-radius: 8px;
      margin: 0 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    }
    .header-buttons button:hover {
      background: #ff758c;
      color: #fff;
    }
    /* Advertisement Banner */
    .ad-banner {
      background: rgba(255,255,255,0.95);
      margin: 20px auto;
      max-width: 900px;
      padding: 30px;
      border-radius: 15px;
      text-align: center;
      font-size: 20px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      position: relative;
    }
    .ad-banner img {
      max-width: 150px;
      margin-bottom: 10px;
      border-radius: 50%;
      border: 4px solid #ff758c;
    }
    .ad-banner h2 {
      margin-top: 0;
      color: #ff758c;
      font-size: 2.5em;
    }
    /* Enrollment Form Container */
    .container {
      width: 90%;
      max-width: 600px;
      margin: 30px auto;
      background: rgba(255,255,255,0.95);
      padding: 30px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.3);
      border-radius: 15px;
      position: relative;
    }
    .course-info {
      margin-bottom: 20px;
      font-size: 20px;
      color: #333;
      text-align: center;
      padding: 15px;
      background: #fff5f8;
      border: 2px dashed #ff758c;
      border-radius: 10px;
    }
    .form-group {
      margin-bottom: 20px;
    }
    label {
      display: block;
      font-weight: bold;
      margin-bottom: 5px;
    }
    input[type="text"],
    input[type="tel"],
    input[type="email"],
    input[type="number"],
    textarea {
      width: 100%;
      padding: 12px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 18px;
    }
    input[type="submit"] {
      background: #ff758c;
      color: #fff;
      padding: 12px 20px;
      border: none;
      border-radius: 8px;
      font-size: 20px;
      cursor: pointer;
      width: 100%;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    }
    input[type="submit"]:hover {
      background: #e05572;
    }
    #confirmation {
      text-align: center;
      margin-top: 20px;
      font-size: 20px;
      color: green;
      font-weight: bold;
    }
    .error {
      color: red;
      font-size: 16px;
    }
    /* Decorative Math Elements */
    .decorations {
      position: absolute;
      top: 10%;
      left: 0;
      width: 100%;
      pointer-events: none;
      z-index: 0;
    }
    .decorations svg {
      width: 80px;
      height: 80px;
      fill: rgba(255, 183, 207, 0.6);
    }
    .circle {
      position: absolute;
      top: 20%;
      left: 5%;
    }
    .triangle {
      position: absolute;
      bottom: 20%;
      right: 10%;
    }
    .euler {
      position: absolute;
      top: 50%;
      right: 5%;
      font-size: 2em;
      color: #ff758c;
      opacity: 0.7;
    }
    .python {
      position: absolute;
      bottom: 10%;
      left: 5%;
      font-size: 1.5em;
      color: #306998;
      background: #fffbf0;
      padding: 5px 10px;
      border-radius: 8px;
      border: 1px solid #306998;
    }
    /* Modal Styles for Information */
    .modal {
      display: none; /* Hidden by default */
      position: fixed; /* Stay in place */
      z-index: 2000; /* Sit on top */
      left: 0;
      top: 0;
      width: 100%; /* Full width */
      height: 100%; /* Full height */
      overflow: auto; /* Enable scroll if needed */
      background-color: rgba(0, 0, 0, 0.7); /* Black w/ opacity */
    }
    .modal-content {
      background-color: #fff;
      margin: 10% auto; /* 10% from the top and centered */
      padding: 20px;
      border: 1px solid #888;
      width: 80%;
      max-width: 600px;
      border-radius: 10px;
      text-align: left;
      font-size: 18px;
    }
    .modal-content h2 {
      color: #ff758c;
    }
    .modal-content ul {
      list-style-type: disc;
      margin-left: 20px;
    }
    .close {
      color: #aaa;
      float: right;
      font-size: 28px;
      font-weight: bold;
    }
    .close:hover,
    .close:focus {
      color: black;
      text-decoration: none;
      cursor: pointer;
    }
    /* Footer for Extra Math Fun */
    footer {
      text-align: center;
      padding: 20px;
      background: #ff7eb3;
      color: #fff;
      position: relative;
    }
    footer pre {
      background: #fff;
      color: #333;
      padding: 10px;
      border-radius: 5px;
      display: inline-block;
      text-align: left;
      font-size: 1.2em;
      margin-top: 10px;
    }
  </style>
  <!-- EmailJS Script -->
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
  <script type="text/javascript">
    (function() {
      // Initialize EmailJS with your User ID
      emailjs.init('OsTI1qjJJAQTrB0wD');
    })();
    
    // Function to smoothly scroll to the enrollment form
    function scrollToEnrollment() {
      let formElement = document.getElementById('enrollmentForm');
      if (formElement) {
        formElement.scrollIntoView({ behavior: 'smooth' });
      } else {
        console.error("Enrollment form element not found");
      }
    }
    
    // Function to toggle the display of the Information modal
    function toggleInfo() {
      const modal = document.getElementById("infoModal");
      if (modal.style.display === "block") {
        modal.style.display = "none";
      } else {
        modal.style.display = "block";
      }
    }
    
    // Close modal when clicking outside the modal content
    window.onclick = function(event) {
      const modal = document.getElementById("infoModal");
      if (event.target == modal) {
        modal.style.display = "none";
      }
    }
    
    // Form Submission and Validation
    document.getElementById('contact-form').addEventListener('submit', function(event) {
      event.preventDefault();

      // Reset previous error messages
      document.getElementById('phoneError').innerText = "";
      document.getElementById('gradeError').innerText = "";
      document.getElementById('addressError').innerText = "";
      
      let phoneInput = document.getElementById('phone');
      let gradeInput = document.getElementById('grade');
      let addressInput = document.getElementById('address');
      
      // Validate U.S. phone number (basic check for proper formatting)
      let phonePattern = /^\(?([2-9][0-8][0-9])\)?[-. ]?([2-9][0-9]{2})[-. ]?([0-9]{4})$/;
      if (!phonePattern.test(phoneInput.value)) {
        document.getElementById('phoneError').innerText = "Please enter a valid U.S. phone number.";
        return;
      }

      // Validate Grade Level (must be between 1 and 12)
      let gradeValue = parseInt(gradeInput.value, 10);
      if (isNaN(gradeValue) || gradeValue < 1 || gradeValue > 12) {
        document.getElementById('gradeError').innerText = "Grade must be between 1 and 12.";
        return;
      }
      
      // Validate Address: Ensure the address includes a Florida location.
      let addressValue = addressInput.value.toLowerCase();
      if (!addressValue.includes("florida") && !addressValue.includes(" fl ")) {
        document.getElementById('addressError').innerText = "Address must be a valid address in Florida.";
        return;
      }

      // If all validations pass, send the form data using EmailJS.
      emailjs.sendForm('service_ethan28', 'template_hlib1bs', this)
        .then(function() {
          document.getElementById('confirmation').innerText = "Thank you for enrolling! We will contact you soon.";
        }, function(error) {
          console.error('Failed to send enrollment information:', error);
          document.getElementById('confirmation').innerText = "There was an error submitting the form. Please try again.";
        });
    });
  </script>
</head>
<body>
  <!-- Decorative Math Elements -->
  <div class="decorations">
    <div class="circle">
      <svg viewBox="0 0 100 100">
        <circle cx="50" cy="50" r="40" />
      </svg>
    </div>
    <div class="triangle">
      <svg viewBox="0 0 100 100">
        <polygon points="50,15 90,85 10,85" />
      </svg>
    </div>
    <div class="euler">e = 2.71828</div>
    <div class="python">def math_fun(): return "Python Rocks!"</div>
  </div>
  
  <!-- Header Section -->
  <header>
    <h1>Ethan's Math Class</h1>
    <p>Engaging, Affordable, and Interactive Math Lessons</p>
    <div class="header-buttons">
      <button onclick="scrollToEnrollment()">Enroll Now</button>
      <button onclick="toggleInfo()">Information</button>
    </div>
  </header>
  
  <!-- Information Modal -->
  <div id="infoModal" class="modal">
    <div class="modal-content">
      <span class="close" onclick="toggleInfo()">&times;</span>
      <h2>Why Choose Us?</h2>
      <ul>
        <li><strong>Cheaper Price:</strong> Enjoy affordable math tutoring sessions.</li>
        <li><strong>Higher Quality:</strong> Learn from an experienced and dedicated tutor.</li>
        <li><strong>Funny Tutor:</strong> Experience math with humor and creativity.</li>
        <li><strong>Easy to Understand:</strong> Clear explanations to master even tough concepts.</li>
        <li><strong>Comprehensive Curriculum:</strong> From Algebra 1 to Precalculus and beyond.</li>
        <li><strong>Flexible Scheduling:</strong> Learn at times that suit you best.</li>
        <li><strong>Interactive Lessons:</strong> Hands-on activities with real-world applications.</li>
        <li><strong>Proven Success:</strong> Boost your math confidence and performance.</li>
        <li><strong>Personalized Attention:</strong> Tailored lessons to fit your learning style.</li>
        <li><strong>And More:</strong> Join us and discover the joy of math!</li>
      </ul>
    </div>
  </div>
  
  <!-- Advertisement Banner -->
  <div class="ad-banner">
    <!-- Your provided picture is used here -->
    <h2>Discover the Joy of Math!</h2>
    <p>Join our classes and experience hands-on learning with interactive problem solving.</p>
    <p><strong>Only $25 per 1.5 hours</strong> – Quality instruction in a fun, supportive environment.</p>
    <p>Conveniently located in Florida – Boost your math skills and build confidence today!</p>
  </div>
  
  <!-- Enrollment Form Section -->
  <div id="enrollmentForm" class="container">
    <h2>Enroll Now</h2>
    <div class="course-info">
      <p>Interactive Lessons | Experienced Tutor | Affordable Price</p>
      <p>Rate: <strong>$25 per 1.5 hours</strong></p>
      <p>Special Offer: Enroll this week and get a free trial class!</p>
    </div>
    <form id="contact-form">
      <div class="form-group">
        <label for="fullname">Full Name</label>
        <input type="text" id="fullname" name="user_name" required>
      </div>
      <div class="form-group">
        <label for="email">Email Address</label>
        <input type="email" id="email" name="user_email" required>
      </div>
      <div class="form-group">
        <label for="phone">Phone Number</label>
        <input type="tel" id="phone" name="user_phone" required>
        <span id="phoneError" class="error"></span>
      </div>
      <div class="form-group">
        <label for="grade">Grade Level (1-12)</label>
        <input type="number" id="grade" name="user_grade" min="1" max="12" required>
        <span id="gradeError" class="error"></span>
      </div>
      <div class="form-group">
        <label for="address">Address (Must be in Florida)</label>
        <textarea id="address" name="user_address" rows="3" required></textarea>
        <span id="addressError" class="error"></span>
      </div>
      <input type="submit" value="Enroll Now">
    </form>
    <div id="confirmation"></div>
  </div>
</body>
</html>
