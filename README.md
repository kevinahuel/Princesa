<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Para Agustina 💖</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(to right, #fcb1b1, #ffd6d6);
      font-family: 'Segoe UI', sans-serif;
      color: #fff;
      text-align: center;
      overflow-x: hidden;
    }

    .container {
      padding: 50px 20px;
      position: relative;
      z-index: 2;
    }

    h1 {
      font-size: 3em;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.4em;
      max-width: 700px;
      margin: 0 auto 40px;
    }

    .heart {
      font-size: 4em;
      animation: beat 1s infinite;
    }

    @keyframes beat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.2); }
    }

    .button {
      background-color: white;
      color: #ff5e7e;
      border: none;
      padding: 15px 35px;
      font-size: 1.2em;
      margin-top: 30px;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .button:hover {
      background-color: #ffe6eb;
      transform: scale(1.05);
    }

    .gallery {
      display: none;
      margin-top: 40px;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
    }

    .gallery img {
      width: 200px;
      height: auto;
      border-radius: 20px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.3);
    }

    @media (max-width: 600px) {
      .gallery img {
        width: 90%;
      }
    }

    /* Corazones flotantes */
    .heart-float {
      position: fixed;
      top: -50px;
      font-size: 20px;
      color: #ff4d6d;
      animation: float 6s infinite;
      z-index: 1;
    }

    @keyframes float {
      0% {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(120vh) scale(1.5);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <!-- Reproductor de música (oculto) -->
  <audio autoplay loop>
    <source src="musica/rauw-alejandro.mp3" type="audio/mp3">
    Tu navegador no soporta el audio.
  </audio>

  <div class="container">
    <div class="heart">❤️</div>
    <h1>Para vos, Agustina</h1>
    <p>
      Este pequeño rincón del universo es solo para recordarte lo mucho que te amo.  
      Gracias por ser la luz de mis días, la calma en mi tormenta, y la sonrisa en mis mañanas.  
      Sos mi todo.
    </p>
    <button class="button" onclick="toggleGallery()">Haz clic para ver nuestros recuerdos 💕</button>

    <div id="gallery" class="gallery">
      <!-- Tus imágenes personalizadas -->
      <img src="fotos/.jpg" alt="Recuerdo 1">
      <img src="fotos/foto2.jpg" alt="Recuerdo 2">
      <img src="fotos/foto3.jpg" alt="Recuerdo 3">
      <img src="fotos/foto4.jpg" alt="Recuerdo 4">
    </div>
  </div>

  <!-- Script para mostrar galería -->
  <script>
    function toggleGallery() {
      const galeria = document.getElementById("gallery");
      galeria.style.display = galeria.style.display === "flex" ? "none" : "flex";
    }

    // Corazones flotantes
    setInterval(() => {
      const heart = document.createElement("div");
      heart.className = "heart-float";
      heart.innerHTML = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = (Math.random() * 20 + 10) + "px";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }, 500);
  </script>
</body>
</html>
