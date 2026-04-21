<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Coming Soon</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        font-family: 'Segoe UI', sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(135deg, #1e1e2f, #3a0ca3);
        color: white;
        text-align: center;
    }

    .container {
        backdrop-filter: blur(10px);
        padding: 50px 40px;
        border-radius: 20px;
        background: rgba(255,255,255,0.05);
        box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        max-width: 600px;
    }

    .project-title {
        font-size: 0.9rem;
        letter-spacing: 3px;
        text-transform: uppercase;
        opacity: 0.6;
        margin-bottom: 5px;
    }

    .presented-by {
        font-size: 0.8rem;
        letter-spacing: 2px;
        opacity: 0.5;
        margin-bottom: 15px;
    }

    .quote {
        font-size: 0.95rem;
        font-style: italic;
        opacity: 0.75;
        margin-bottom: 30px;
        line-height: 1.5;
    }

    h1 {
        font-size: 3rem;
        margin-bottom: 10px;
        letter-spacing: 2px;
    }

    p {
        opacity: 0.7;
        margin-bottom: 30px;
    }

    .countdown {
        display: flex;
        gap: 20px;
        justify-content: center;
    }

    .box {
        background: rgba(255,255,255,0.1);
        padding: 20px;
        border-radius: 15px;
        min-width: 80px;
        box-shadow: inset 0 0 10px rgba(255,255,255,0.1);
    }

    .number {
        font-size: 2rem;
        font-weight: bold;
    }

    .label {
        font-size: 0.8rem;
        opacity: 0.7;
        margin-top: 5px;
    }

    @media (max-width: 600px) {
        .countdown {
            flex-wrap: wrap;
        }
    }
</style>
</head>

<body>

<div class="container">

    <div class="project-title">Project-Friday</div>
    <div class="presented-by">Ahar Developers Presents</div>

    <div class="quote">
        "The unstoppable and most powerful AI agent ever. Made with inspiration on Jarvis."
    </div>

    <h1>Coming Soon</h1>
    <p>Something exciting is on the way...</p>

    <div class="countdown">
        <div class="box">
            <div id="days" class="number">00</div>
            <div class="label">Days</div>
        </div>
        <div class="box">
            <div id="hours" class="number">00</div>
            <div class="label">Hours</div>
        </div>
        <div class="box">
            <div id="minutes" class="number">00</div>
            <div class="label">Minutes</div>
        </div>
        <div class="box">
            <div id="seconds" class="number">00</div>
            <div class="label">Seconds</div>
        </div>
    </div>

</div>

<script>
    const targetDate = new Date("October 1, 2026 00:00:00").getTime();

    function updateCountdown() {
        const now = new Date().getTime();
        const diff = targetDate - now;

        if (diff <= 0) {
            document.querySelector(".container").innerHTML = "<h1>We're Live ❤️</h1>";
            return;
        }

        const days = Math.floor(diff / (1000 * 60 * 60 * 24));
        const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
        const minutes = Math.floor((diff / (1000 * 60)) % 60);
        const seconds = Math.floor((diff / 1000) % 60);

        document.getElementById("days").innerText = days;
        document.getElementById("hours").innerText = hours;
        document.getElementById("minutes").innerText = minutes;
        document.getElementById("seconds").innerText = seconds;
    }

    setInterval(updateCountdown, 1000);
    updateCountdown();
</script>

</body>
</html>
