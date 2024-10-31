# raahilaalam.github.io
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
            background-color: #f0f0f0;
        }
        .calculator {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .calculator input {
            width: 100%;
            padding: 10px;
            font-size: 18px;
            text-align: right;
            margin-bottom: 10px;
            border: none;
            border-radius: 5px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1) inset;
        }
        .calculator button {
            width: 20%;
            padding: 15px;
            font-size: 18px;
            border: none;
            margin: 5px;
            border-radius: 5px;
            cursor: pointer;
            background-color: #ececec;
        }
        .calculator button.operation {
            background-color: #f0ad4e;
            color: white;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" readonly>
        <div>
            <button onclick="clearDisplay()">C</button>
            <button onclick="deleteLast()">DEL</button>
            <button onclick="appendNumber('/')">/</button>
            <button onclick="appendNumber('*')">*</button>
        </div>
        <div>
            <button onclick="appendNumber('7')">7</button>
            <button onclick="appendNumber('8')">8</button>
            <button onclick="appendNumber('9')">9</button>
            <button onclick="appendNumber('-')">-</button>
        </div>
        <div>
            <button onclick="appendNumber('4')">4</button>
            <button onclick="appendNumber('5')">5</button>
            <button onclick="appendNumber('6')">6</button>
            <button onclick="appendNumber('+')">+</button>
        </div>
        <div>
            <button onclick="appendNumber('1')">1</button>
            <button onclick="appendNumber('2')">2</button>
            <button onclick="appendNumber('3')">3</button>
            <button onclick="calculate()">=</button>
        </div>
        <div>
            <button onclick="appendNumber('0')">0</button>
            <button onclick="appendNumber('.')">.</button>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
let display = document.getElementById('display');

function clearDisplay() {
    display.value = '';
}

function deleteLast() {
    display.value = display.value.slice(0, -1);
}

function appendNumber(number) {
    display.value += number;
}

function calculate() {
    try {
        display.value = eval(display.value);
    } catch (error) {
        display.value = 'Error';
    }
}
