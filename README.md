<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Feliz Dia dos Namorados 💖</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
      color: white;
      background-size: cover;
      background-position: center;
    }

    .container {
      padding: 40px 20px;
      background-color: rgba(0, 0, 0, 0.5);
      min-height: 100vh;
    }

    .profile-pic {
      width: 200px;
      height: 200px;
      border-radius: 50%;
      object-fit: cover;
      border: 5px solid white;
      margin-bottom: 20px;
    }

    .message {
      font-size: 1.5em;
      margin: 30px 0;
    }

    audio {
      margin-top: 30px;
    }

    .upload-section {
      background: rgba(255,255,255,0.1);
      padding: 10px;
      border-radius: 10px;
      margin-top: 30px;
    }

    input {
      margin: 10px;
    }

    .hidden {
      display: none;
    }

    h1 {
      font-size: 2.5em;
    }

    label {
      display: block;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <div class="container" id="main-container">
    <h1>Feliz Dia dos Namorados, Meu Amor 💕</h1>
    
    <img id="photoPreview" class="profile-pic hidden" alt="Sua foto">

    <div class="message" id="mensagemTexto">
      Você é a razão dos meus sorrisos, o amor da minha vida. <br>
      Que esse Dia dos Namorados seja apenas mais um dos muitos que viveremos juntos. Te amo! 💘
    </div>

    <audio controls id="audioPlayer" class="hidden">
      Seu navegador não suporta áudio.
    </audio>

    <div class="upload-section">
      <label for="photoInput">Adicione uma foto dela:</label>
      <input type="file" id="photoInput" accept="image/*">

      <label for="musicInput">Adicione uma música romântica (MP3):</label>
      <input type="file" id="musicInput" accept="audio/*">

      <label for="bgInput">Imagem de fundo personalizada:</label>
      <input type="file" id="bgInput" accept="image/*">
    </div>
  </div>

  <script>
    const photoInput = document.getElementById('photoInput');
    const photoPreview = document.getElementById('photoPreview');
    const musicInput = document.getElementById('musicInput');
    const audioPlayer = document.getElementById('audioPlayer');
    const bgInput = document.getElementById('bgInput');
    const mainContainer = document.getElementById('main-container');

    photoInput.addEventListener('change', function () {
      const file = this.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function (e) {
          photoPreview.src = e.target.result;
          photoPreview.classList.remove('hidden');
        };
        reader.readAsDataURL(file);
      }
    });

    musicInput.addEventListener('change', function () {
      const file = this.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function (e) {
          audioPlayer.src = e.target.result;
          audioPlayer.classList.remove('hidden');
        };
        reader.readAsDataURL(file);
      }
    });

    bgInput.addEventListener('change', function () {
      const file = this.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function (e) {
          document.body.style.backgroundImage = `url(${e.target.result})`;
        };
        reader.readAsDataURL(file);
      }
    });
  </script>
</body>
</html>
