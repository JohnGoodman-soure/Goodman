# Ciao-bimba
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <title>Lettera riservata</title>
    <style>
        body {
            font-family: Arial, sans-serif;
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
        .countdown {
            font-size: 2em;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div id="content">
        <div id="before-date">
            <h1>Conto alla rovescia</h1>
            <div class="countdown" id="countdown-timer">--:--:--:--</div>
        </div>
    </div>

    <script>
        const unlockDate = new Date('2025-06-30T08:00:00');
        const redirectUrl = "https://drive.google.com/file/d/1iyEBXO7nPSxBXqfzammhR-pQQtz8lM-c/view?pli=1)"

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = unlockDate - now;

            if (distance <= 0) {
                window.location.href = redirectUrl;
                clearInterval(timerInterval);
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
