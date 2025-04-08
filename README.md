<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Age Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 100px;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
    }
    #result {
      margin-top: 20px;
      font-weight: bold;
      font-size: 18px;
    }
  </style>
</head>
<body>

  <h1>Age Calculator</h1>
  <label for="birthdate">Enter your birthdate:</label><br><br>
  <input type="date" id="birthdate"><br><br>
  <button onclick="calculateAge()">Calculate Age</button>

  <div id="result"></div>

  <script>
    function calculateAge() {
      const birthdate = new Date(document.getElementById('birthdate').value);
      const today = new Date();
      let age = today.getFullYear() - birthdate.getFullYear();
      const m = today.getMonth() - birthdate.getMonth();

      if (m < 0 || (m === 0 && today.getDate() < birthdate.getDate())) {
        age--;
      }

      document.getElementById('result').textContent = 
        isNaN(age) ? "Please select a valid birthdate." : You are ${age} years old.;
    }
  </script>

</body>
</html>
