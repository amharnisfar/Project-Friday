



    
    Coming Soon
    
        /* Full‑screen background */
        body, html {
            height: 100%;
            margin: 0;
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
            background: linear-gradient(135deg, #2b5876, #4e4376);
            color: #fff;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .container {
            max-width: 600px;
            padding: 20px;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 0.5rem;
            letter-spacing: 2px;
        }

        p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        .countdown {
            display: flex;
            justify-content: space-around;
            gap: 10px;
            flex-wrap: wrap;
        }

        .segment {
            background: rgba(255,255,255,0.1);
            border-radius: 8px;
            padding: 15px 10px;
            min-width: 80px;
        }

        .segment span {
            display: block;
            font-size: 2.5rem;
            font-weight: bold;
        }

        .label {
            font-size: 0.9rem;
            margin-top: 5px;
            opacity: 0.8;
        }
    



    Coming Soon
    We’re launching on October 1 2026

    
        0Days
        0Hours
        0Minutes
        0Seconds
    



    // Target date: 1 Oct 2026 00:00:00 (local time)
    const target = new Date('2026-10-01T00:00:00');

    function updateTimer() {
        const now = new Date();
        const diff = target - now; // ms

        if (diff <= 0) {
            // Countdown finished
            document.getElementById('countdown').innerHTML =
                '<div style="font-size:2rem;">We are live! 🎉</div>';
            clearInterval(interval);
            return;
        }

        const sec = Math.floor(diff / 1000) % 60;
        const min = Math.floor(diff / (1000 * 60)) % 60;
        const hr  = Math.floor(diff / (1000 * 60 * 60)) % 24;
        const day = Math.floor(diff / (1000 * 60 * 60 * 24));

        document.getElementById('days').textContent    = day;
        document.getElementById('hours').textContent   = String(hr).padStart(2, '0');
        document.getElementById('minutes').textContent = String(min).padStart(2, '0');
        document.getElementById('seconds').textContent = String(sec).padStart(2, '0');
    }

    // Update every second
    const interval = setInterval(updateTimer, 1000);
    updateTimer(); // initial call



