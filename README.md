<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, initial-scale=1.0, maximum-scale=5.0">
    <title>Kartu Ucapan</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4), url('https://www.transparenttextures.com/patterns/wood-pattern.png');
            background-size: cover;
            flex-direction: column;
            overflow: auto;
        }
        .envelope {
            width: 250px;
            height: 150px;
            background: #f0e2d9;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            border-radius: 10px;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.1);
            transform: scale(1.1);
            transition: transform 0.3s;
            margin: 20px;
        }
        .envelope:hover {
            transform: scale(1.2);
        }
        .envelope::before {
            content: '💌';
            font-size: 4em;
            z-index: 1;
        }
        .card {
            display: none;
            width: 90%;
            max-width: 800px;
            height: auto;
            background: #fff;
            border-radius: 20px;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
            text-align: center;
            padding: 30px;
            box-sizing: border-box;
            position: relative;
            overflow: hidden;
        }
        .title {
            font-size: 2em;
            color: #333;
            margin-bottom: 20px;
            z-index: 1;
            position: relative;
        }
        .message {
            font-size: 1.2em;
            color: #555;
            white-space: pre-wrap;
            z-index: 1;
            position: relative;
        }
        .button {
            margin-top: 30px;
            display: inline-block;
            padding: 10px 20px;
            font-size: 1em;
            color: #fff;
            background: #ff6f61;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            text-decoration: none;
            transition: background 0.3s;
            z-index: 1;
            position: relative;
        }
        .button:hover {
            background: #e55a4e;
        }
        .scrolling-message {
            display: none;
            width: 90%;
            max-width: 600px;
            background: #fff;
            border: 1px solid #f0e2d9;
            border-radius: 20px;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.1);
            padding: 30px;
            font-size: 1.2em;
            text-align: left;
            color: #333;
            line-height: 1.6;
            animation: slideIn 1s ease-out forwards;
            background-image: linear-gradient(transparent 1px, #d3c6b2 1px, transparent 2px);
            background-size: 100% 20px;
            background-position: top;
            padding-left: 20px;
            margin: 20px;
        }
        @keyframes slideIn {
            0% {
                transform: translateY(50%);
                opacity: 0;
            }
            100% {
                transform: translateY(0);
                opacity: 1;
            }
        }
        .confetti {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }
        .confetti div {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #ff6f61;
            opacity: 0;
            animation: confetti 3s linear infinite;
        }
        @keyframes confetti {
            0% {
                transform: translateY(0) rotate(0);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(720deg);
                opacity: 0;
            }
        }
    </style>
    <script>
        function bukaAmplop() {
            document.getElementById('envelope').style.display = 'none';
            document.getElementById('card').style.display = 'block';
        }

        function bukaHadiah() {
            document.getElementById('card').style.display = 'none';
            document.getElementById('scrollingMessage').style.display = 'block';
            document.getElementById('confetti').style.display = 'block';
            const music = document.getElementById('music');
            if (music.paused) {
                music.play();
            }
            generateConfetti();
        }

        function generateConfetti() {
            const confettiContainer = document.getElementById('confetti');
            for (let i = 0; i < 100; i++) {
                const confettiPiece = document.createElement('div');
                confettiPiece.style.left = Math.random() * 100 + '%';
                confettiPiece.style.animationDelay = Math.random() * 2 + 's';
                confettiPiece.style.backgroundColor = `rgb(${Math.random() * 255}, ${Math.random() * 255}, ${Math.random() * 255})`;
                confettiContainer.appendChild(confettiPiece);
            }
        }
    </script>
</head>
<body>
    <div id="envelope" class="envelope" onclick="bukaAmplop()"></div>

    <div id="card" class="card">
        <div class="title">Kartu Ucapan</div>
        <div class="message">Selamat Ulang Tahun!<br>Semoga sehat dan bahagia selalu.</div>
        <button class="button" onclick="bukaHadiah()">Buka Hadiah</button>
    </div>

    <div id="scrollingMessage" class="scrolling-message">
        Terima kasih telah menjadi orang yang luar biasa dalam hidupku. Semoga hari-harimu selalu penuh kebahagiaan dan keberkahan!
    </div>

    <div id="confetti" class="confetti"></div>

    <audio id="music" src="c:\Users\HAMIDAH NURAINI\Downloads\James Arthur - A Thousand Years (Christina Perri Cover).mp3" preload="auto"></audio>
</body>
</html>
