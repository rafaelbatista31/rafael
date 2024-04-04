<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Questionário</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 600px;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .question {
            margin-bottom: 20px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f9f9f9;
        }
        input[type="text"] {
            width: calc(100% - 10px);
            padding: 5px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<div class="container">
    <div class="question">
        <p>Cansado de um dia longo?</p>
        <label><input type="radio" name="cansado" value="sim"> Sim</label>
        <label><input type="radio" name="cansado" value="nao"> Não</label>
    </div>
    <div class="question">
        <p>Quantas horas trabalhaste hoje?</p>
        <input type="text" name="horas_trabalhadas" placeholder="Digite o número de horas">
    </div>
    <div class="question">
        <p>Faz a tua escolha: Whiskey ou Cerveja</p>
        <input type="text" name="bebida" placeholder="Whiskey ou Cerveja">
    </div>
    <button type="button" onclick="verificarRespostas()">Enviar</button>
</div>

<script>
    function verificarRespostas() {
        var cansado = document.querySelector('input[name="cansado"]:checked');
        var horas = document.querySelector('input[name="horas_trabalhadas"]').value;
        var bebida = document.querySelector('input[name="bebida"]').value;

        if (cansado && horas && bebida) {
            var mensagem = '';

            if (cansado.value === 'sim') {
                mensagem += 'Sério? Espero que possa relaxar em breve!\n';
            } else {
                mensagem += 'Tudo bem, espero que possa descansar mais tarde.\n';
            }

            var horasInt = parseInt(horas);
            if (!isNaN(horasInt)) {
                if (horasInt < 8) {
                    mensagem += ' Só? Trabalha malandro!\n';
                } else if (horasInt > 8 && horasInt < 24) {
                    mensagem += ' Uff! Tenho a solução para amanhã!\n';
                } else {
                    mensagem += ' Introduz um número a sério...\n';
                }
            } else {
                mensagem += ' Introduz um número a sério...\n';
            }

            bebida = bebida.toLowerCase();
            if (bebida === 'whiskey') {
                mensagem += ' Boa escolha!\n';
            } else if (bebida === 'cerveja') {
                mensagem += ' Tenta outra vez...\n';
            } else {
                mensagem += ' Sê sério...\n';
            }

            alert(mensagem);
        } else {
            alert('Por favor, responda todas as perguntas.');
        }
    }
</script>

</body>
</html>
