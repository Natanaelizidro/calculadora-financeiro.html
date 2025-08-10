
[finaceiro calculadora de organização pessoal.html.txt](https://github.com/user-attachments/files/21703403/finaceiro.calculadora.de.organizacao.pessoal.html.txt)
<!DOCTYPE html>
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Orçamento Pessoal</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        .fundo {
            background-image: linear-gradient(45deg, rgb(10, 173, 10), rgb(20, 170, 220));
            height: 100vh;
            color: white;
            font-family: Arial, Helvetica, sans-serif;
            text-align: center;
        }
        .calculadora {
            position: absolute;
            background-color: rgba(0, 0, 0, 0.8);
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border-radius: 15px;
            padding: 15px;
        }
        .botao {
            width: 130px;
            height: 50px;
            font-size: 25px;
            cursor: pointer;
            margin: 3px;
            background-color: rgb(31,31,31);
            border: none;
            color: #fff;
        }
        .botao:hover {
            background-color: black;
        }
        #resultado {
            background-color: white;
            width: 530px;
            height: 30px;
            margin: 5px;
            font-size: 25px;
            color: black;
            text-align: right;
            padding: 5px;
        }
    </style>
</head>
<body>
    <div class="fundo">
        <h1>Natanael Dos Santos Izidro</h1>
        <div class="calculadora"> 
            <h1>Calculadora de Orçamento Pessoal</h1>
            <p id="resultado">0</p>
            <table>
                <tr>
                    <td><button class="botao" onclick="clean()">C</button></td>
                    <td><button class="botao" onclick="back()">&lt;</button></td>
                    <td><button class="botao" onclick="insert('/')">/</button></td>
                    <td><button class="botao" onclick="insert('*')">X</button></td>
                </tr>
                <tr>
                    <td><button class="botao" onclick="insert('7')">7</button></td>
                    <td><button class="botao" onclick="insert('8')">8</button></td>
                    <td><button class="botao" onclick="insert('9')">9</button></td>
                    <td><button class="botao" onclick="insert('-')">-</button></td>
                </tr>
                <tr> 
                    <td><button class="botao" onclick="insert('4')">4</button></td>
                    <td><button class="botao" onclick="insert('5')">5</button></td>
                    <td><button class="botao" onclick="insert('6')">6</button></td>
                    <td><button class="botao" onclick="insert('+')">+</button></td>
                </tr>
                <tr> 
                    <td><button class="botao" onclick="insert('1')">1</button></td>
                    <td><button class="botao" onclick="insert('2')">2</button></td>
                    <td><button class="botao" onclick="insert('3')">3</button></td>
                    <td rowspan="2"><button class="botao" style="height: 106px;" onclick="calcular()">=</button></td>
                </tr>
                <tr>
                    <td colspan="2"><button class="botao" style="width: 270px;" onclick="insert('0')">0</button></td>
                    <td><button class="botao" onclick="insert('.')">.</button></td>
                </tr>                    
            </table>
        </div>
    </div>

    <script>
        function insert(num) {
            var campo = document.getElementById('resultado');
            if (campo.innerHTML === "0") {
                campo.innerHTML = num;
            } else {
                campo.innerHTML += num;
            }
        }

        function clean() {
            document.getElementById("resultado").innerHTML = "0";
        }

        function back() {
            var resultado = document.getElementById("resultado").innerHTML;
            resultado = resultado.slice(0, -1);
            document.getElementById("resultado").innerHTML = resultado || "0";
        }

        function calcular() {
            var resultado = document.getElementById('resultado').innerHTML;
            try {
                document.getElementById("resultado").innerHTML = eval(resultado);
            } catch (e) {
                document.getElementById("resultado").innerHTML = "Erro";
            }
        }
    </script>
</body>
</html>
