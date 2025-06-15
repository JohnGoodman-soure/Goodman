<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <title>Lettera riservata</title>
    <style>
        body {
            font-family: "Times New Roman", Times, serif;
            background-color: #ffffff;
            color: #000000;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            text-align: center;
            padding: 20px;
        }
        #content {
            max-width: 600px;
        }
        h2 {
            margin-bottom: 10px;
            font-size: 24px;
        }
        .countdown {
            font-size: 2em;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div id="content">
        <h2>Ti conosco fin troppo bene...devi aspettare, bimba.</h2>
        <div id="before-date">
            <h1>Il contenuto sarà disponibile tra:</h1>
            <div class="countdown" id="countdown-timer">--:--:--:--</div>
        </div>
    </div>

    <script>
        const unlockDate = new Date("2025-06-30T13:00:00");
        const redirectUrl = "https://drive.google.com/file/d/1iyEBXO7nPSxBXqfzammhR-pQQtz8lM-c/view?pli=1";

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = unlockDate - now;

            if (distance <= 0) {
                clearInterval(timerInterval);
                window.location.href = redirectUrl;
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("countdown-timer").innerHTML =
                days + "g " + hours + "h " + minutes + "m " + seconds + "s";
        }

        const timerInterval = setInterval(updateCountdown, 1000);
        updateCountdown();
    </script>
</body>
</html>
