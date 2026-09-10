# Surpresa-<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Uma perguntinha 🐱💗</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: Arial, sans-serif;

            background: linear-gradient(
                135deg,
                #ffd6e7,
                #fff0f6
            );

            overflow: hidden;
        }

        .container {
            width: 92%;
            max-width: 450px;
            text-align: center;
        }

        /* GATINHO */

        .cat {
            font-size: 90px;
            animation: flutuar 2s ease-in-out infinite;
            user-select: none;
        }

        @keyframes flutuar {
            0%, 100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-10px);
            }
        }

        h1 {
            color: #d94f83;
            font-size: 28px;
            margin: 10px 0;
        }

        .intro {
            color: #704456;
            font-size: 17px;
            margin-bottom: 20px;
        }

        /* BOTÃO ABRIR */

        .open-btn {
            border: none;
            background: #ff6fa3;
            color: white;

            padding: 15px 25px;

            border-radius: 15px;

            font-size: 18px;
            font-weight: bold;

            cursor: pointer;

            box-shadow: 0 5px 15px rgba(200, 60, 110, 0.25);

            transition: 0.2s;
        }

        .open-btn:hover {
            transform: scale(1.06);
        }

        /* CARTINHA */

        .letter-window {
            margin-top: 20px;

            background: white;

            padding: 25px;

            border-radius: 25px;

            box-shadow:
                0 15px 35px rgba(150, 50, 90, 0.2);

            opacity: 0;

            transform: scale(0.5);

            pointer-events: none;

            transition:
                opacity 0.5s ease,
                transform 0.5s ease;
        }

        .letter-window.open {
            opacity: 1;
            transform: scale(1);
            pointer-events: auto;
        }

        .letter {
            color: #684052;
            line-height: 1.6;
            font-size: 16px;
        }

        .question {
            margin-top: 18px;

            color: #d94f83;

            font-size: 23px;

            font-weight: bold;
        }

        /* ÁREA DOS BOTÕES */

        .buttons {
            position: relative;

            display: flex;

            justify-content: center;

            align-items: center;

            gap: 25px;

            width: 100%;

            height: 80px;

            margin-top: 20px;
        }

        .btn {
            width: 120px;
            height: 50px;

            border: none;

            border-radius: 15px;

            font-size: 18px;
            font-weight: bold;

            cursor: pointer;

            transition: 0.2s;
        }

        /* SIM */

        .yes-btn {
            background: #ff6fa3;
            color: white;

            z-index: 2;
        }

        .yes-btn:hover {
            transform: scale(1.08);
        }

        /* NÃO */

        .no-btn {
            background: #eeeeee;
            color: #555;

            position: absolute;

            left: calc(50% + 25px);

            top: 15px;

            z-index: 10;

            transition:
                left 0.18s ease,
                top 0.18s ease;
        }

        /* RESPOSTA */

        .answer {
            display: none;

            margin-top: 15px;

            color: #d94f83;

            font-size: 20px;

            font-weight: bold;

            animation: aparecer 0.5s ease;
        }

        @keyframes aparecer {
            from {
                opacity: 0;
                transform: scale(0.7);
            }

            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        /* CORAÇÕES */

        .hearts {
            position: fixed;

            bottom: -20px;

            font-size: 22px;

            animation: subir 4s linear forwards;

            pointer-events: none;
        }

        @keyframes subir {
            from {
                transform: translateY(0);
                opacity: 1;
            }

            to {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }

        /* CELULAR */

        @media (max-width: 500px) {

            h1 {
                font-size: 24px;
            }

            .cat {
                font-size: 75px;
            }

            .letter-window {
                padding: 20px;
            }

            .question {
                font-size: 21px;
            }
        }
    </style>
</head>

<body>

    <div class="container">

        <!-- GATINHO -->

        <div class="cat">
            🐱
        </div>

        <h1>
            Oi... tenho uma perguntinha 💗
        </h1>

        <p class="intro">
            Esse gatinho trouxe uma cartinha especialmente para você... 🐱💌
        </p>

        <!-- BOTÃO PARA ABRIR -->

        <button class="open-btn" onclick="openLetter()">
            Abrir cartinha 💌
        </button>


        <!-- CARTA -->

        <div class="letter-window" id="letter">

            <div class="letter">

                <p>
                    Oii! 🐱💗
                </p>

                <p>
                    Eu queria te falar uma coisa
                    que talvez seja um pouquinho difícil
                    de dizer pessoalmente...
                </p>

                <p>
                    Você se tornou uma pessoa muito
                    especial para mim. Eu gosto muito
                    de conversar com você e dos momentos
                    que passamos juntos. ✨
                </p>

                <p>
                    Então esse gatinho veio fazer
                    uma pergunta muito importante...
                </p>

                <div class="question">
                    Quer namorar comigo? 💗
                </div>


                <!-- BOTÕES -->

                <div class="buttons" id="buttonArea">

                    <button
                        class="btn yes-btn"
                        onclick="yesAnswer()">
                        SIM 💗
                    </button>

                    <button
                        class="btn no-btn"
                        id="noButton">
                        NÃO 😭
                    </button>

                </div>


                <!-- RESPOSTA -->

                <div
                    class="answer"
                    id="answer">
                </div>

            </div>

        </div>

    </div>


    <script>

        /* ABRIR CARTINHA */

        function openLetter() {

            const letter =
                document.getElementById("letter");

            letter.classList.add("open");
        }


        /* BOTÃO NÃO */

        const noButton =
            document.getElementById("noButton");

        const buttonArea =
            document.getElementById("buttonArea");


        function fugir() {

            const areaWidth =
                buttonArea.clientWidth;

            const areaHeight =
                buttonArea.clientHeight;

            const buttonWidth =
                noButton.offsetWidth;

            const buttonHeight =
                noButton.offsetHeight;


            /*
                Calcula uma posição aleatória
                dentro da área dos botões.
            */

            const maxX =
                areaWidth - buttonWidth;

            const maxY =
                areaHeight - buttonHeight;


            const randomX =
                Math.random() * maxX;

            const randomY =
                Math.random() * maxY;


            noButton.style.left =
                randomX + "px";

            noButton.style.top =
                randomY + "px";
        }


        /*
            PC:
            quando o mouse chega perto,
            o botão foge.
        */

        noButton.addEventListener(
            "mouseenter",
            fugir
        );


        /*
            Celular:
            quando a pessoa toca no botão,
            ele foge antes do clique.
        */

        noButton.addEventListener(
            "touchstart",
            function(event) {

                event.preventDefault();

                fugir();

            },
            { passive: false }
        );


        /*
            Também funciona se alguém
            conseguir clicar.
        */

        noButton.addEventListener(
            "click",
            function(event) {

                event.preventDefault();

                fugir();

            }
        );


        /* RESPOSTA SIM */

        function yesAnswer() {

            const answer =
                document.getElementById("answer");

            answer.innerHTML =
                "AAAAAA! 🥹💗🐱<br>" +
                "Agora esse gatinho está muito feliz! 💕";

            answer.style.display =
                "block";


            criarCoracoes();
        }


        /* CORAÇÕES */

        function criarCoracoes() {

            for (
                let i = 0;
                i < 20;
                i++
            ) {

                setTimeout(function() {

                    const heart =
                        document.createElement("div");

                    heart.className =
                        "hearts";

                    heart.innerHTML =
                        ["💗", "💕", "💖", "💘", "❤️"]
                        [Math.floor(Math.random() * 5)];


                    heart.style.left =
                        Math.random() * 100 + "vw";


                    heart.style.animationDuration =
                        (3 + Math.random() * 3) + "s";


                    document.body.appendChild(
                        heart
                    );


                    setTimeout(function() {

                        heart.remove();

                    }, 6000);

                }, i * 100)
            }
        }

    </script>

</body>


</html>
