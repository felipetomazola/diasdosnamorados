<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para o Kaikai</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            font-family: 'Press Start 2P', cursive; /* Fonte estilo bitmap */
            background-color: #000;
            color: #FFF;
            overflow: hidden; /* Evita barras de rolagem */
            text-align: center;
            position: relative;
        }

        /* Importa a fonte para estilo pixelado */
        @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

        /* Efeito de estrelas no fundo */
        .stars {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: transparent;
            z-index: -1;
        }

        .star {
            position: absolute;
            background-color: #FFF;
            border-radius: 50%;
            opacity: 0;
            animation: twinkle linear infinite;
        }

        @keyframes twinkle {
            0% { opacity: 0; transform: scale(0.5); }
            50% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(0.5); }
        }

        .container {
            background-color: rgba(0, 0, 0, 0.7); /* Fundo semi-transparente para o conteúdo */
            padding: 40px;
            border-radius: 10px;
            border: 2px solid #00F; /* Borda azul neon */
            box-shadow: 0 0 20px #00F; /* Brilho azul neon */
        }

        h1 {
            font-size: 2.5em;
            margin-bottom: 30px;
            text-shadow: 0 0 10px #F0F; /* Brilho rosa neon */
        }

        .buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
        }

        .button {
            padding: 15px 30px;
            font-size: 1.2em;
            cursor: pointer;
            border: 2px solid #0F0; /* Borda verde neon */
            background-color: rgba(0, 255, 0, 0.2); /* Fundo verde semi-transparente */
            color: #0F0; /* Texto verde neon */
            border-radius: 5px;
            transition: background-color 0.3s, color 0.3s, border-color 0.3s;
            text-shadow: 0 0 5px #0F0;
        }

        .button:hover {
            background-color: rgba(0, 255, 0, 0.5);
            color: #FFF;
            border-color: #FFF;
        }

        #message {
            font-size: 3em;
            color: #FFD700; /* Dourado */
            text-shadow: 0 0 15px #FFD700;
            display: none; /* Escondido inicialmente */
        }
    </style>
</head>
<body>
    <div class="stars" id="star-container"></div>

    <div class="container" id="question-container">
        <h1>Me ama?</h1>
        <div class="buttons">
            <button class="button" onclick="handleClick('sim')">Sim</button>
            <button class="button" onclick="handleClick('xin')">Xin</button>
        </div>
    </div>

    <div class="container" id="message" style="display: none;">
        <h1>Feliz Dia dos Namorados, Kaikai! ❤️</h1>
    </div>

    <script>
        function handleClick(answer) {
            if (answer === 'xin') {
                document.getElementById('question-container').style.display = 'none';
                document.getElementById('message').style.display = 'block';
            }
            // Se clicar em 'sim', nada acontece, a página permanece como está.
        }

        // Gera estrelas para o fundo
        const starContainer = document.getElementById('star-container');
        const numStars = 100; // Quantidade de estrelas

        for (let i = 0; i < numStars; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            star.style.width = `${Math.random() * 3 + 1}px`; /* Tamanho da estrela */
            star.style.height = star.style.width;
            star.style.top = `${Math.random() * 100}%`;
            star.style.left = `${Math.random() * 100}%`;
            star.style.animationDuration = `${Math.random() * 3 + 2}s`; /* Duração da animação */
            star.style.animationDelay = `${Math.random() * 2}s`; /* Atraso para aparecer */
            starContainer.appendChild(star);
        }
    </script>
</body>
</html>
