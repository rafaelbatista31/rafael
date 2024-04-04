<html>
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
        <input type="text" placeholder="Resposta">
    </div>
    <div class="question">
        <p>Quantas horas trabalhaste hoje?</p>
        <input type="text" placeholder="Resposta">
    </div>
    <div class="question">
        <p>Faz a tua escolha: Whiskey ou Cerveja</p>
        <input type="text" placeholder="Resposta">
    </div>
    <button>Enviar</button>
</div>

<script>
    document.querySelector('button').addEventListener('click', function() {
        var respostas = document.querySelectorAll('input[type="text"]');
        var mensagem = '';

        if (respostas[0].value === 'Sim') {
            mensagem += 'Sério? Espero que possa relaxar em breve!';
        } else {
            mensagem += 'Tudo bem, espero que possa descansar mais tarde.';
        }

        var horas = parseInt(respostas[1].value);
        if (!isNaN(horas)) {
            if (horas < 8) {
                mensagem += ' Só? Trabalha malandro!';
            } else if (horas > 8 && horas < 24) {
                mensagem += ' Uff! Tenho a solução para amanhã!';
            } else {
                mensagem += ' Introduz um número a sério...';
            }
        }

        var bebida = respostas[2].value.toLowerCase();
        if (bebida === 'whiskey') {
            mensagem += ' Boa escolha!';
        } else if (bebida === 'cerveja') {
            mensagem += ' Tenta outra vez...';
        } else {
            mensagem += ' Sê sério...';
        }

        alert(mensagem);
    });
</script>

</body>
</html>
