<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Carta con Polvo de Hadas</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      background-color: black;
      position: relative;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    
    /* Fondo con partículas de luz (destellos de estrellas) */
    .sparkles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      /* Crea pequeños puntos blancos que se repiten */
      background: radial-gradient(circle, rgba(255,255,255,0.8) 1px, transparent 1px) repeat;
      background-size: 30px 30px;
      animation: twinkle 2s infinite ease-in-out;
      z-index: -1;
    }
    @keyframes twinkle {
      0% { opacity: 0.8; }
      50% { opacity: 0.5; }
      100% { opacity: 0.8; }
    }
    
    /* Estilo para el sobre (tradicional con brillos) */
    .envelope {
      position: relative;
      width: 300px;
      height: 200px;
      background: linear-gradient(145deg, #f1f1f1, #d1d1d1);
      border: 2px solid #e6e6e6;
      border-radius: 8px;
      cursor: pointer;
      box-shadow: 0 4px 15px rgba(255,255,255,0.3);
      transition: transform 0.6s, box-shadow 0.6s;
      overflow: hidden;
      z-index: 1;
    }
    .envelope:hover {
      transform: scale(1.1);
      box-shadow: 0 8px 20px rgba(255,255,255,0.6);
    }
    
    .flap {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 50%;
      background: linear-gradient(145deg, #f1f1f1, #ffffff);
      transform-origin: top;
      transition: transform 0.6s;
      border-bottom: 2px solid rgba(0,0,0,0.1);
      box-shadow: 0 0 20px rgba(255,223,0,0.6);
    }
    .envelope.open .flap {
      transform: rotateX(-180deg);
    }
    
    /* Estilo del mensaje (sin marco) */
    .message {
      display: none;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-family: 'Comic Sans MS', cursive, sans-serif;
      font-size: 32px;
      font-weight: bold;
      font-style: italic;
      text-align: center;
      color: black;
      letter-spacing: 2px;
      background: transparent;
      padding: 20px;
      /* Efecto de borde dorado en el texto */
      text-shadow: 2px 2px 5px rgba(255,223,0,0.9), 2px -2px 5px rgba(255,223,0,0.9);
    }
    .envelope.open .message {
      display: block;
    }
  </style>
</head>
<body>
  <!-- Fondo con partículas de luz -->
  <div class="sparkles"></div>
  
  <!-- Sobre con animación -->
  <div class="envelope" onclick="openEnvelope()">
    <div class="flap"></div>
    <div class="message">
      <div>Te quiero.</div>
      <div>Buenas noches, Rayan</div>
    </div>
  </div>
  
  <!-- Sonido de polvo de hadas (destello mágico) -->
  <audio id="sound" src="https://www.soundjay.com/magic/magic-sparkle-1.wav" preload="auto"></audio>
  
  <script>
    function openEnvelope() {
      document.querySelector('.envelope').classList.toggle('open');
      document.getElementById('sound').play();
    }
  </script>
</body>
</html>
