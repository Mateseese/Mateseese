- 👋 Hi, I’m @Mateseese
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Mateseese/Mateseese is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--<!DOCTYPE html>
<html>

<head>
    <title>Kalkulačka</title>
    <style>
        button {
            width: 40px;
            height: 40px;
            font-size: 25px;
        }

        #display {
            width: 200px;
            height: 40px;
            font-size: 20px;
        }
    </style>
</head>

<body>
    <form name="Kalkulacka">
        <input type="text" name="Cislo1" style="display: none;">
        <input type="text" name="Operator" style="display: none;">
        <input type="text" name="Cislo2" style="display: none;">
        <input type="text" name="Vysledek" id="display" readonly>
        <br>
        <button type="button" onclick="appendToDisplay('7')">7</button>
        <button type="button" onclick="appendToDisplay('8')">8</button>
        <button type="button" onclick="appendToDisplay('9')">9</button>
        <button type="button" onclick="setOperator('+')">+</button>
        <br>
        <button type="button" onclick="appendToDisplay('4')">4</button>
        <button type="button" onclick="appendToDisplay('5')">5</button>
        <button type="button" onclick="appendToDisplay('6')">6</button>
        <button type="button" onclick="setOperator('-')">-</button>
        <br>
        <button type="button" onclick="appendToDisplay('1')">1</button>
        <button type="button" onclick="appendToDisplay('2')">2</button>
        <button type="button" onclick="appendToDisplay('3')">3</button>
        <button type="button" onclick="setOperator('*')">*</button>
        <br>
        <button type="button" onclick="clearDisplay()">C</button>
        <button type="button" onclick="appendToDisplay('0')">0</button>
        <button type="button" onclick="calculate()">=</button>
        <button type="button" onclick="setOperator('/')">/</button>
    </form>

  <script>
    var display = document.getElementById("display");
    var input1 = document.forms["Kalkulacka"]["Cislo1"];
    var operator = document.forms["Kalkulacka"]["Operator"];
    var input2 = document.forms["Kalkulacka"]["Cislo2"];
        

        function appendToDisplay(value) {
            display.value += value;
        }

        function clearDisplay() {
            display.value = "";
            input1.value = "";
            operator.value = "";
            input2.value = "";
        }

        function setOperator(op) {
            if (operator.value === "") {
                input1.value = display.value;
                operator.value = op;
                display.value = "";
            }
        }

        function calculate() {
            if (operator.value !== "") {
                input2.value = display.value;
                var cislo1 = parseFloat(input1.value);
                var op = operator.value;
                var cislo2 = parseFloat(input2.value);
                var vysledek = 0;

                if (op === "+") {
                    vysledek = cislo1 + cislo2;
                } else if (op === "-") {
                    vysledek = cislo1 - cislo2;
                } else if (op === "*") {
                    vysledek = cislo1 * cislo2;
                } else if (op === "/") {
                    if (cislo2 !== 0) {
                        vysledek = cislo1 / cislo2;
                    } else {
                        alert("Nelze dělit nulou.");
                    }
                }

                display.value = vysledek;
                input1.value = "";
                operator.value = "";
                input2.value = "";
            }
        }
    </script>
