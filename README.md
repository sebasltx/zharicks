</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Te amo</title>
    
    <link rel="stylesheet" href="xd.css">
    
    <style>
        #No {
            grid-row: 5;
            grid-column: 6;
        }
        .hidden {
            display: none;
        }
        .hearts, .confetti {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: 10;
        }
        .heart, .confetti-piece {
            position: absolute;
            animation: float 5s infinite;
        }
        .heart {
            font-size: 24px;
            color: red;
        }
        .confetti-piece {
            width: 10px;
            height: 10px;
            background-color: #fff;
        }
        @keyframes float {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-100vh); opacity: 0; }
        }
    </style>
</head>
<body>  
    <div>
        <p id="p" hidden>Yo tambien te amo</p>
        <h1 id="1">Me Perdonas</h1>
        <img src="xd.gif" alt="Gatito">
        <section>
            <button id="Si">Si</button>
            <button id="No">No</button>
        </section>
        <div id="animations" class="hidden">
            <div class="hearts"></div>
            <div class="confetti"></div>
            <img id="extraGif" src="y2.gif" alt="Extra Gif" class="hidden">
        </div>
    </div>
   
    <script>
        document.getElementById('Si').addEventListener('click', function() {
            document.getElementById('p').removeAttribute('hidden');
            document.getElementById('animations').classList.remove('hidden');
            document.getElementById('extraGif').classList.remove('hidden');

            // Generate hearts and confetti
            for (let i = 0; i < 30; i++) {
                let heart = document.createElement('div');
                heart.className = 'heart';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
                heart.innerHTML = '❤️';
                document.querySelector('.hearts').appendChild(heart);

                let confettiPiece = document.createElement('div');
                confettiPiece.className = 'confetti-piece';
                confettiPiece.style.left = Math.random() * 100 + 'vw';
                confettiPiece.style.animationDuration = (Math.random() * 2 + 3) + 's';
                confettiPiece.style.backgroundColor = '#' + Math.floor(Math.random() * 16777215).toString(16);
                document.querySelector('.confetti').appendChild(confettiPiece);
            }
        });
    </script>
          <script src="xd.js"></script>
</body>
</html>
