# Health-check-bmi
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>BMI Health Check</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>BMI Health Check</h1>
    <p>Supporting SDG 3: Good Health and Well-being</p>
    <input type="number" id="weight" placeholder="Enter weight (kg)" />
    <input type="number" id="height" placeholder="Enter height (m)" />
    <button onclick="calculateBMI()">Calculate BMI</button>
    <p id="result"></p>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background-color: #f0f8ff;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.container {
  text-align: center;
  background: white;
  padding: 30px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}
input {
  margin: 10px;
  padding: 8px;
  width: 200px;
}
button {
  padding: 10px 20px;
  background-color: #28a745;
  color: white;
  border: none;
  border-radius: 5px;
}
function calculateBMI() {
  const weight = parseFloat(document.getElementById("weight").value);
  const height = parseFloat(document.getElementById("height").value);

  if (weight > 0 && height > 0) {
    const bmi = weight / (height * height);
    let status = "";

    if (bmi < 18.5) status = "Underweight";
    else if (bmi < 25) status = "Normal weight";
    else if (bmi < 30) status = "Overweight";
    else status = "Obese";

    document.getElementById("result").innerText =
      `Your BMI is ${bmi.toFixed(2)}. Status: ${status}`;
  } else {
    document.getElementById("result").innerText = "Please enter valid values.";
  }
}
