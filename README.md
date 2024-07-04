# OIBSIP_Task1Lev2_Calculator
I Developed this Calculator using HTML &amp; CSS , JAVA SCRIPT
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Calculator</title>
    <style>
      body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #282c34;
        font-family: "Arial", sans-serif;
        color: #ffffff;
      }
      .calculator {
        border: 2px solid #000;
        border-radius: 20px;
        padding: 20px;
        background-color: #3a3f47;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        width: 320px;
      }
      .display {
        width: 100%;
        height: 60px;
        margin-bottom: 20px;
        text-align: right;
        padding: 10px;
        border-radius: 10px;
        border: none;
        font-size: 2rem;
        background-color: #1c1e22;
        color: #ffffff;
      }
      .buttons {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 15px;
      }
      .buttons button {
        padding: 20px;
        font-size: 1.5rem;
        border: none;
        border-radius: 10px;
        background-color: #4a4e57;
        color: white;
        cursor: pointer;
        transition: background-color 0.3s, transform 0.2s;
      }
      .buttons button:hover {
        background-color: #5a5e67;
        transform: scale(1.05);
      }
      .buttons .operator {
        background-color: #ff5722;
      }
      .buttons .operator:hover {
        background-color: #e64a19;
      }
      .buttons .equal {
        background-color: #4caf50;
        grid-column: span 2;
      }
      .buttons .equal:hover {
        background-color: #388e3c;
      }
      .buttons .clear {
        background-color: #f44336;
        grid-column: span 2;
      }
      .buttons .clear:hover {
        background-color: #d32f2f;
      }
    </style>
  </head>
  <body>
    <div class="calculator">
      <input type="text" class="display" id="display" disabled />
      <div class="buttons">
        <button onclick="clearDisplay()" class="clear">C</button>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button onclick="appendToDisplay('/')">/</button>
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button onclick="appendToDisplay('*')" class="operator">*</button>
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button onclick="appendToDisplay('-')" class="operator">-</button>
        <button onclick="appendToDisplay('0')">0</button>
        <button onclick="appendToDisplay('.')" class="operator">.</button>
        <button onclick="appendToDisplay('+')" class="operator">+</button>
        <button onclick="calculateResult()" class="equal">=</button>
      </div>
    </div>
    <script>
      function appendToDisplay(value) {
        document.getElementById("display").value += value;
      }

      function clearDisplay() {
        document.getElementById("display").value = "";
      }

      function calculateResult() {
        try {
          const result = eval(document.getElementById("display").value);
          document.getElementById("display").value = result;
        } catch (error) {
          document.getElementById("display").value = "Error";
        }
      }
    </script>
  </body>
</html>
