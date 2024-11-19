<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora</title>
    <style>
        .calculadora {
            width: 200px;
            margin: 0 auto;
            padding: 20px;
            border: 2px solid #333;
            border-radius: 10px;
        }
        input, button {
            width: 40px;
            height: 40px;
            font-size: 20px;
            margin: 5px;
        }
        input {
            width: 170px;
        }
    </style>
</head>
<body>

    <div class="calculadora">
        <input type="text" id="display" disabled>
        <br>
        <button onclick="appendNumber(1)">1</button>
        <button onclick="appendNumber(2)">2</button>
        <button onclick="appendNumber(3)">3</button>
        <button onclick="appendOperator('+')">+</button>
        <br>
        <button onclick="appendNumber(4)">4</button>
        <button onclick="appendNumber(5)">5</button>
        <button onclick="appendNumber(6)">6</button>
        <button onclick="appendOperator('-')">-</button>
        <br>
        <button onclick="appendNumber(7)">7</button>
        <button onclick="appendNumber(8)">8</button>
        <button onclick="appendNumber(9)">9</button>
        <button onclick="appendOperator('*')">*</button>
        <br>
        <button onclick="appendNumber(0)">0</button>
        <button onclick="clearDisplay()">C</button>
        <button onclick="calculateResult()">=</button>
        <button onclick="appendOperator('/')">/</button>
    </div>

    <script>
        let display = document.getElementById("display");

        // Função para adicionar números ao visor
        function appendNumber(number) {
            display.value += number;
        }

        // Função para adicionar operadores ao visor
        function appendOperator(operator) {
            display.value += ' ' + operator + ' ';
        }

        // Função para limpar o visor
        function clearDisplay() {
            display.value = '';
        }

        // Função para calcular o resultado
        function calculateResult() {
            try {
                // Avalia a expressão matemática no visor
                display.value = eval(display.value);
            } catch (error) {
                display.value = 'Erro';
            }
        }
    </script>

</body>
</html>
