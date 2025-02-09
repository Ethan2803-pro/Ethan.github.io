<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Ethan Math Class Enrollment</title>
  <style>
    /* Basic styles */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #f4f4f4;
    }
    header {
      background: #007BFF;
      color: #fff;
      padding: 20px;
      text-align: center;
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    header button {
      background: #fff;
      color: #007BFF;
      border: none;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
      margin-top: 10px;
    }
    .container {
      width: 90%;
      max-width: 600px;
      margin: 50px auto;
      background: #fff;
      padding: 30px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h1, h2 {
      text-align: center;
    }
    #feeInfo {
      text-align: center;
      font-size: 18px;
      color: #333;
      margin-bottom: 20px;
    }
    .form-group {
      margin-bottom: 15px;
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
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    input[type="submit"] {
      background: #007BFF;
      color: #fff;
      padding: 10px 15px;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      cursor: pointer;
      width: 100%;
    }
    input[type="submit"]:hover {
      background: #0056b3;
    }
    #confirmation {
      text-align: center;
      margin-top: 20px;
      font-size: 18px;
      color: green;
      font-weight: bold;
    }
    .error {
      color: red;
      font-size: 14px;
    }
  </style>
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
  <script type="text/javascript">
    (function() {
      emailjs.init('OsTI1qjJJAQTrB0wD');
    })();
  </script>
</head>
<body>
  <header>
    <h1>Ethan Math Class Enrollment</h1>
    <button onclick="scrollToEnrollment()">Enrollment</button>
  </header>
  
  <div id="enrollmentForm" class="container">
    <h2>Enroll Now</h2>
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
        <label for="address">Address</label>
        <textarea id="address" name="user_address" rows="3" required></textarea>
      </div>
      <input type="submit" value="Enroll Now">
    </form>
    <div id="confirmation"></div>
  </div>
  
  <script>
    function scrollToEnrollment() {
      let formElement = document.getElementById('enrollmentForm');
      if (formElement) {
        formElement.scrollIntoView({ behavior: 'smooth' });
      } else {
        console.error("Enrollment form element not found");
      }
    }
    
    document.getElementById('contact-form').addEventListener('submit', function(event) {
      event.preventDefault();

      let phoneInput = document.getElementById('phone');
      let phoneError = document.getElementById('phoneError');
      let gradeInput = document.getElementById('grade');
      let gradeError = document.getElementById('gradeError');

      phoneError.innerText = "";
      gradeError.innerText = "";

      // U.S. phone number validation
      let phonePattern = /^\(?([2-9][0-8][0-9])\)?[-. ]?([2-9][0-9]{2})[-. ]?([0-9]{4})$/;
      if (!phonePattern.test(phoneInput.value)) {
        phoneError.innerText = "Please enter a valid U.S. phone number.";
        return;
      }

      // Grade validation (ensure it's between 1 and 12)
      let gradeValue = parseInt(gradeInput.value, 10);
      if (gradeValue < 1 || gradeValue > 12 || isNaN(gradeValue)) {
        gradeError.innerText = "Grade must be between 1 and 12.";
        return;
      }

      // Send form data using EmailJS if all validations pass
      emailjs.sendForm('service_ethan28', 'template_hlib1bs', this)
        .then(function() {
          document.getElementById('confirmation').innerText = "Thank you for enrolling! We will contact you soon.";
        }, function(error) {
          console.error('Failed to send enrollment information:', error);
          document.getElementById('confirmation').innerText = "There was an error submitting the form. Please try again.";
        });
    });
  </script>
</body>
</html>

