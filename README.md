<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abrir WhatsApp</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #121212;
            color: white;
        }
        .container {
            background-color: #1e1e1e;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.7);
            text-align: center;
        }
        .display {
            font-size: 24px;
            margin-bottom: 20px;
            border: 1px solid #555;
            padding: 10px;
            border-radius: 4px;
            min-height: 40px;
            color: white; /* Cor do texto no display */
        }
        
        .button-container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
        }
        button {
            width: 100%;
            padding: 15px;
            background-color: #333;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 18px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #555;
        }
        /* Botão Limpar */
        .clear-btn {
            background-color: #004d00; /* Verde escuro */
        }
        .clear-btn:hover {
            background-color: #006400; /* Verde mais claro ao passar o mouse */
        }
        .clear-btn:active {
            background-color: #003300; /* Verde ainda mais escuro ao clicar */
            transition: background-color 0.3s;
        }
        /* Botão Apagar */
        .backspace-btn {
            background-color: #004d00; /* Verde escuro */
        }
        .backspace-btn:hover {
            background-color: #006400; /* Verde mais claro ao passar o mouse */
        }
        .backspace-btn:active {
            background-color: #003300; /* Verde ainda mais escuro ao clicar */
            transition: background-color 0.3s;
        }
        /* Botão Abrir WhatsApp */
        .open-btn {
            background-color: #004d00; /* Verde escuro */
            color: white;
            margin-top: 10px;
        }
        .open-btn:hover {
            background-color: #006400; /* Verde mais claro ao passar o mouse */
        }
        .open-btn:active {
            background-color: #003300; /* Verde ainda mais escuro ao clicar */
            transition: background-color 0.3s;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>Abrir WhatsApp</h2>
    <div class="display" id="display">+55</div>
    <div class="button-container">
        <button onclick="addDigit('1')">1</button>
        <button onclick="addDigit('2')">2</button>
        <button onclick="addDigit('3')">3</button>
        <button onclick="addDigit('4')">4</button>
        <button onclick="addDigit('5')">5</button>
        <button onclick="addDigit('6')">6</button>
        <button onclick="addDigit('7')">7</button>
        <button onclick="addDigit('8')">8</button>
        <button onclick="addDigit('9')">9</button>
        <button class="clear-btn" onclick="clearDisplay()">Limpar</button>
        <button onclick="addDigit('0')">0</button>
        <button class="backspace-btn" onclick="backspace()">Apagar</button>
    </div>
    <button class="open-btn" onclick="abrirWhatsApp()">Abrir WhatsApp</button>
</div>

<script>
    function addDigit(digit) {
        const display = document.getElementById("display");
        display.textContent += digit;
    }

    function clearDisplay() {
        const display = document.getElementById("display");
        display.textContent = "+55";
    }

    function backspace() {
        const display = document.getElementById("display");
        if (display.textContent.length > 3) {
            display.textContent = display.textContent.slice(0, -1);
        }
    }

    function abrirWhatsApp() {
        const display = document.getElementById("display").textContent;
        const numero = display.replace('+55', '');

        if (numero.length >= 10) {
            const link = `https://wa.me/+55${numero}`;
            window.open(link, '_blank');
        } else {
            alert("Por favor, insira um número válido.");
        }
    }
</script>

</body>
</html>
