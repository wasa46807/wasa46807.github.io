<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Traductor Épico</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body, html {
      height: 100%;
      font-family: Arial, sans-serif;
      color: white;
    }
    .video-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      z-index: -1;
    }
    .video-bg video {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    .container {
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      backdrop-filter: blur(4px);
      padding: 20px;
    }
    textarea {
      width: 80%;
      max-width: 600px;
      height: 120px;
      padding: 10px;
      border-radius: 10px;
      border: none;
      font-size: 16px;
    }
    button {
      margin-top: 15px;
      padding: 10px 20px;
      font-size: 18px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      background: rgba(255,255,255,0.2);
      backdrop-filter: blur(3px);
      color: white;
    }
  </style>
</head>
<body>

  <div class="video-bg">
    <!-- Reemplaza "video.mp4" con tu video real de 2 segundos -->
    <video src="video.mp4" autoplay loop muted></video>
  </div>

  <div class="container">
    <h1>Traductor</h1>
    <textarea id="input"></textarea>
    <button onclick="traducir()">Traducir</button>
    <textarea id="output" readonly></textarea>
  </div>

<script>
  function traducir() {
    const texto = document.getElementById('input').value;
    // Traducción falsa de ejemplo
    document.getElementById('output').value = texto.split('').reverse().join('');
  }
</script>

</body>
</html>
