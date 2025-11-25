<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Traductor con Fondo Personalizable</title>
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

    .bg-container {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      z-index: -1;
      filter: brightness(0.7);
    }

    .panel {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100%;
      text-align: center;
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

    button, input {
      margin-top: 15px;
      padding: 10px 20px;
      font-size: 18px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
    }

    #bgInput {
      width: 70%;
      max-width: 400px;
    }

    button {
      background: rgba(255,255,255,0.2);
      color: white;
      backdrop-filter: blur(3px);
    }
  </style>
</head>
<body>

  <div id="bg" class="bg-container"></div>

  <div class="panel">
    <h1>Traductor Personalizable</h1>

    <input id="bgInput" type="text" placeholder="Pega aquí la URL de tu fondo" />
    <button onclick="cambiarFondo()">Cambiar fondo</button>

    <textarea id="input"></textarea>
    <button onclick="traducir()">Traducir</button>
    <textarea id="output" readonly></textarea>
  </div>

<script>
  function cambiarFondo() {
    const url = document.getElementById('bgInput').value;
    if (url.trim() !== "") {
      document.getElementById('bg').style.backgroundImage = `url('${url}')`;
    }
  }

  function traducir() {
    const texto = document.getElementById('input').value;
    // Traducción de ejemplo (reverse)
    document.getElementById('output').value = texto.split('').reverse().join('');
  }
</script>

</body>
</html>
