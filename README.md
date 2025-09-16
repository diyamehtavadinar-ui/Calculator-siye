# Calculator-siye
It is a calculator that can perform addition, subtraction, multiplication and division 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #f0f4f8;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .calculator {
      background-color: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 8px 16px rgba(0,0,0,0.1);
      width: 320px;
    }

    .calculator h2 {
      text-align: center;
      margin-bottom: 20px;
      color: #333;
    }

    input[type="number"], select {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }

    button {
      width: 100%;
      padding: 10px;
      background-color: #0078D7;
      color: white;
      border: none;
      border-radius: 6px;
      font-size: 16px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #005fa3;
    }

    #result {
      margin-top: 20px;
      font-size: 18px;
      text-align: center;
      color: #0078D7;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <h2>Simple Calculator</h2>
    <input type="number" id="num1" placeholder="Enter first number">
    <input type="number" id="num2" placeholder="Enter second number">
    <select id="operation">
      <option value="add">Addition (+)</option>
      <option value="subtract">Subtraction (−)</option>
      <option value="multiply">Multiplication (×)</option>
      <option value="divide">Division (÷)</option>
    </select>
    <button onclick="calculate()">Calculate</button>
    <p id="result"></p>
  </div>

  <script>
    function calculate() {
      const num1 = parseFloat(document.getElementById('num1').value);
      const num2 = parseFloat(document.getElementById('num2').value);
      const operation = document.getElementById('operation').value;
      let result;

      if (isNaN(num1) || isNaN(num2)) {
        result = "Please enter valid numbers.";
      } else {
        switch (operation) {
          case "add":
            result = num1 + num2;
            break;
          case "subtract":
            result = num1 - num2;
            break;
          case "multiply":
            result = num1 * num2;
            break;
          case "divide":
            result = num2 !== 0 ? num1 / num2 : "Cannot divide by zero.";
            break;
          default:
            result = "Invalid operation.";
        }
      }

      document.getElementById('result').textContent = "Result: " + result;
    }
  </script>
</body>
</html>
