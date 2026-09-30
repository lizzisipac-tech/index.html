a# index.html
💖♥️♥️💗teamo
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Una Galaxia Para Ti</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            background-color: #020208;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #ffffff;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        /* Fondo del Espacio */
        #space {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }
        .star {
            position: absolute;
            background-color: #ffffff;
            border-radius: 50%;
            animation: twinkle linear infinite;
        }
        @keyframes twinkle {
            0% { opacity: 0.2; }
            50% { opacity: 1; }
            100% { opacity: 0.2; }
        }
        /* Contenedor de Pantallas */
        .container {
            position: relative;
            z-index: 10;
            text-align: center;
            padding: 20px;
            max-width: 600px;
            width: 90%;
            transition: opacity 0.5s ease-in-out;
        }
        h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-shadow: 0 0 20px rgba(173, 216, 230, 0.8);
            font-weight: 300;
            letter-spacing: 2px;
        }
        p {
            font-size: 1.2rem;
            line-height: 1.6;
            margin-bottom: 30px;
            color: #e0e0ff;
        }
        /* Botón Estilo Galaxia */
        .btn {
            background: linear-gradient(45deg, #4f46e5, #7c3aed);
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.1rem;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 0 15px rgba(124, 58, 237, 0.6);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 25px rgba(124, 58, 237, 0.9);
        }
        /* Elementos Ocultos al Inicio */
        .hidden {
            display: none !important;
            opacity: 0;
        }
        .visible {
            display: block;
            opacity: 1;
        }
        /* Animación del Corazón */
        .heart {
            font-size: 4rem;
            color: #ff2a6d;
            animation: pulse 1.5s infinite;
            margin-top: 20px;
        }
        @keyframes pulse {
            0% { transform: scale(1); filter: drop-shadow(0 0 5px #ff2a6d); }
            50% { transform: scale(1.15); filter: drop-shadow(0 0 20px #ff2a6d); }
            100% { transform: scale(1); filter: drop-shadow(0 0 5px #ff2a6d); }
        }
    </style>
</head>
<body>

    <div id="space"></div>

    <!-- Pantalla 1: Bienvenida -->
    <div id="screen1" class="container visible">
        <h1>Una Galaxia para Ti</h1>
        <p>En todo el universo existen millones de estrellas, pero ninguna brilla tanto como tú. He creado este pequeño espacio para mostrártelo.</p>
        <button class="btn" onclick="nextScreen()">Iniciar Viaje</button>
    </div>

    <!-- Pantalla 2: Tu Mensaje Personalizado -->
    <div id="screen2" class="container hidden">
        <h1>Para: Fernando</h1>
        <p>Quiero que sepas que eres la persona más especial de mi mundo. Gracias por iluminar mis días con tu sonrisa y por ser mi recordatorio constante de lo bonito que es coincidir en esta vida.</p>
        <div class="heart">❤</div>
    </div>

    <script>
        // Generador de estrellas de fondo
        const space = document.getElementById('space');
        const numStars = 150;

        for (let i = 0; i < numStars; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            const size = Math.random() * 3;
            star.style.width = `${size}px`;
            star.style.height = `${size}px`;
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            star.style.animationDuration = `${Math.random() * 3 + 2}s`;
            star.style.animationDelay = `${Math.random() * 2}s`;
            space.appendChild(star);
        }

        // Cambiar de pantalla
        function nextScreen() {
            const s1 = document.getElementById('screen1');
            const s2 = document.getElementById('screen2');
            
            s1.classList.remove('visible');
            s1.classList.add('hidden');
            
            s2.classList.remove('hidden');
            s2.classList.add('visible');
        }
    </script>
</body>
</html>
