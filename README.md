<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            text-align: center;
            background-color: #ffccd5;
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            position: relative;
            overflow: hidden;
        }

        h1 {
            color: #d63384;
            font-size: 3em;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
            z-index: 10;
            margin-bottom: 30px;
        }

        .buttons {
            margin-top: 20px;
            z-index: 10;
        }

        .btn {
            font-size: 1.5em;
            padding: 10px 20px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.3);
        }

        .yes {
            background-color: #28a745;
            color: white;
            box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.3);
        }

        .no {
            background-color: #dc3545;
            color: white;
            margin-left: 20px;
            box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.3);
        }

        /* Animated Hearts */
        .heart {
            position: absolute;
            font-size: 3em;
            color: red;
            opacity: 0.8;
            animation: heart-animation 2s infinite ease-in-out;
        }

        .heart-top-left { top: 10%; left: 10%; }
        .heart-top-right { top: 10%; right: 10%; }
        .heart-bottom-left { bottom: 10%; left: 10%; }
        .heart-bottom-right { bottom: 10%; right: 10%; }

        @keyframes heart-animation {
            0% { transform: scale(1); }
            50% { transform: scale(1.5); }
            100% { transform: scale(1); }
        }

        /* Confetti Animation */
        @keyframes confetti {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }

        .confetti {
            position: absolute;
            top: 0;
            left: 50%;
            width: 5px;
            height: 10px;
            background-color: #ff6347;
            animation: confetti 2s infinite;
            opacity: 0;
            z-index: 5;
        }

        .confetti:nth-child(odd) { animation-duration: 3s; }
        .confetti:nth-child(even) { animation-duration: 4s; }

        /* Background Sparkle Effect */
        .sparkle {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: white;
            border-radius: 50%;
            animation: sparkle 1.5s infinite ease-in-out;
            opacity: 0.8;
        }

        @keyframes sparkle {
            0% { transform: scale(0.5); opacity: 1; }
            100% { transform: scale(1.5); opacity: 0; }
        }

        /* Media Queries for Responsiveness */
        @media (max-width: 768px) {
            h1 {
                font-size: 2em;
            }

            .btn {
                font-size: 1.2em;
                padding: 12px 22px;
            }

            .heart {
                font-size: 2.5em;
            }

            .heart-top-left, .heart-top-right, .heart-bottom-left, .heart-bottom-right {
                font-size: 2.2em;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 1.8em;
            }

            .btn {
                font-size: 1em;
                padding: 10px 18px;
            }

            .heart {
                font-size: 2em;
            }

            .heart-top-left, .heart-top-right, .heart-bottom-left, .heart-bottom-right {
                font-size: 1.8em;
            }
        }
    </style>
    <script>
        function handleNoClick() {
            let yesButton = document.querySelector('.yes');
            let noButton = document.querySelector('.no');
            yesButton.style.fontSize = '2.5em';
            yesButton.style.padding = '15px 30px';
            noButton.style.display = 'none';
        }

        // Generate Confetti
        function createConfetti() {
            const confettiContainer = document.querySelector('body');
            for (let i = 0; i < 50; i++) {
                const confettiPiece = document.createElement('div');
                confettiPiece.classList.add('confetti');
                confettiPiece.style.left = `${Math.random() * 100}%`;
                confettiPiece.style.animationDuration = `${Math.random() * 2 + 2}s`;
                confettiContainer.appendChild(confettiPiece);
            }
        }

        // Generate Sparkles
        function createSparkles() {
            const sparkleContainer = document.querySelector('body');
            for (let i = 0; i < 20; i++) {
                const sparkle = document.createElement('div');
                sparkle.classList.add('sparkle');
                sparkle.style.top = `${Math.random() * 100}%`;
                sparkle.style.left = `${Math.random() * 100}%`;
                sparkle.style.animationDuration = `${Math.random() * 1 + 1.5}s`;
                sparkleContainer.appendChild(sparkle);
            }
        }

        // Call functions when the page loads
        window.onload = () => {
            createConfetti();
            createSparkles();
        };
    </script>
</head>
<body>
    <h1>Will You Be My Valentine? 💖</h1>
    <div class="buttons">
        <button class="btn yes" onclick="window.location.href='deonpractice.html';">Yes</button>
        <button class="btn no" onclick="handleNoClick()">No</button>
    </div>

    <!-- Hearts in Each Corner -->
    <div class="heart heart-top-left">❤️</div>
    <div class="heart heart-top-right">❤️</div>
    <div class="heart heart-bottom-left">❤️</div>
    <div class="heart heart-bottom-right">❤️</div>

</body>
</html>
