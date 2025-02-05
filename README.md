# For-my-wife
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Love 💖</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #ffe6e6;
            color: #ff4d4d;
            overflow: hidden;
        }
        h1 {
            font-size: 2em;
            margin-top: 50px;
        }
        .container {
            margin-top: 20px;
        }
        .buttons {
            margin-top: 20px;
        }
        button {
            font-size: 18px;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }
        #yes, #yes-final {
            background-color: #ff4d4d;
            color: white;
        }
        #no, #no-final {
            background-color: #333;
            color: white;
        }
        #no:hover, #no-final:hover {
            position: absolute;
            left: calc(10% + 80% * Math.random());
            top: calc(10% + 80% * Math.random());
        }
        #balloons, #hearts {
            display: none;
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
        }
        .emoji {
            position: absolute;
            font-size: 30px;
            animation: float 5s linear infinite;
        }
        @keyframes float {
            from { transform: translateY(100vh); opacity: 1; }
            to { transform: translateY(-10vh); opacity: 0; }
        }
    </style>
</head>
<body>
    <h1 id="question">Do you love me? 💖</h1>
    <div class="container">
        <div class="buttons">
            <button id="yes" onclick="nextStep()">Yes</button>
            <button id="no" onmouseover="moveNo()">No</button>
        </div>
    </div>

    <div id="balloons"></div>
    <div id="hearts"></div>

    <audio id="drumroll" src="https://www.fesliyanstudios.com/play-mp3/4385" preload="auto"></audio>
    <audio id="song" src="https://www.youtube.com/embed/AdBzzpq3xV4?autoplay=1" preload="auto"></audio>

    <script>
        let step = 1;

        function nextStep() {
            if (step === 1) {
                document.getElementById("question").innerHTML = "You sure, baby??? 😘";
            } else if (step === 2) {
                document.getElementById("question").innerHTML = "Great, now the big question...";
                document.getElementById("drumroll").play();
                setTimeout(() => {
                    document.getElementById("question").innerHTML = 
                        "Alexia Alessandra Mejias, would you be my Valentine? I love you so much with all my heart, and I'd love to take you out on this day. If anyone asked already, tell them no because you're mine. So what's your answer?";
                    document.querySelector(".buttons").innerHTML = 
                        `<button id="yes-final" onclick="finalYes()">Yes</button>
                         <button id="yes-final" onclick="finalYes()">Yesssssss</button>`;
                }, 3000);
            }
            step++;
        }

        function moveNo() {
            let noButton = document.getElementById("no");
            noButton.style.left = Math.random() * (window.innerWidth - 100) + "px";
            noButton.style.top = Math.random() * (window.innerHeight - 50) + "px";
        }

        function finalYes() {
            document.body.innerHTML = "<h1>Yay! 🎉 I love you so much! 💖</h1>";
            document.getElementById("song").play();
            startBalloonsAndHearts();
        }

        function startBalloonsAndHearts() {
            let balloons = document.getElementById("balloons");
            let hearts = document.getElementById("hearts");
            balloons.style.display = "block";
            hearts.style.display = "block";

            for (let i = 0; i < 30; i++) {
                let balloon = document.createElement("div");
                balloon.classList.add("emoji");
                balloon.innerHTML = "🎈";
                balloon.style.left = Math.random() * 100 + "vw";
                balloon.style.animationDuration = Math.random() * 3 + 3 + "s";
                balloons.appendChild(balloon);

                let heart = document.createElement("div");
                heart.classList.add("emoji");
                heart.innerHTML = "❤️";
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.animationDuration = Math.random() * 3 + 3 + "s";
                hearts.appendChild(heart);
            }
        }
    </script>
</body>
</html>
<audio id="song" src="/mnt/data/Lady Gaga, Bruno Mars - Die With A Smile (Lyrics).mp3" preload="auto"></audio>
