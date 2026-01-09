<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Cuenta regresiva – Cumpleaños de Ethan</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body, html {
    width: 100%;
    height: 100%;
    font-family: 'Segoe UI', system-ui, sans-serif;
    background: radial-gradient(circle at top, #0f172a, #020617);
    overflow: hidden;
}

/* Contenedor */
.container {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Tarjeta glass */
.card {
    backdrop-filter: blur(20px);
    background: rgba(255, 255, 255, 0.08);
    border-radius: 25px;
    padding: 50px 70px;
    text-align: center;
    color: white;
    box-shadow:
        0 0 60px rgba(0, 200, 255, 0.35),
        inset 0 0 20px rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    animation: glow 4s ease-in-out infinite alternate;
}

@keyframes glow {
    from {
        box-shadow: 0 0 40px rgba(0,200,255,0.25);
    }
    to {
        box-shadow: 0 0 80px rgba(0,200,255,0.6);
    }
}

h1 {
    font-size: 3em;
    margin-bottom: 20px;
    letter-spacing: 1px;
}

#countdown {
    font-size: 2.4em;
    font-weight: 600;
    margin-top: 10px;
}

.date {
    margin-top: 15px;
    font-size: 1.2em;
    color: #cbd5f5;
    opacity: 0.85;
}
</style>
</head>

<body>

<div class="container">
    <div class="card">
        <h1>🎂 Cumpleaños de Ethan</h1>
        <div id="countdown">Cargando…</div>
        <div class="date">11 de febrero de 2026</div>
    </div>
</div>

<script>
const targetDate = new Date("2026-02-11T00:00:00").getTime();

function updateCountdown() {
    const now = new Date().getTime();
    const diff = targetDate - now;

    if (diff <= 0) {
        document.getElementById("countdown").innerHTML = "🎉 ¡Feliz cumpleaños!";
        return;
    }

    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
    const minutes = Math.floor((diff / (1000 * 60)) % 60);
    const seconds = Math.floor((diff / 1000) % 60);

    document.getElementById("countdown").innerHTML =
        `${days} días · ${hours} h · ${minutes} m · ${seconds} s`;
}

setInterval(updateCountdown, 1000);
updateCountdown();
</script>

</body>
</html>
