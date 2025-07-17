<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }

        .calculator {
            width: 300px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .display {
            width: 100%;
            height: 60px;
            border: none;
            background-color: #333;
            color: white;
            font-size: 2rem;
            text-align: right;
            padding: 10px;
            box-sizing: border-box;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1px;
            padding: 1px;
            background-color: #ddd;
        }

        button {
            height: 60px;
            font-size: 1.5rem;
            border: none;
            background-color: #fff;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #eee;
        }

        button.equals {
            grid-column: span 4;
            background-color: #4CAF50;
            color: white;
        }

        button.equals:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="buttons">
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('/')">/</button>
            
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('*')">*</button>
            
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('-')">-</button>
            
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendToDisplay('+')">+</button>
            
            <button onclick="calculate()" class="equals">=</button>
        </div>
    </div>

    <script>
        let display = document.getElementById('display');

        function appendToDisplay(value) {
            display.value += value;
        }

        function clearDisplay() {
            display.value = '';
        }

        function calculate() {
            try {
                display.value = eval(display.value);
            } catch (error) {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>
