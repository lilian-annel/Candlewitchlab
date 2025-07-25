<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Candle Witch Lab</title>
  <link href="https://fonts.googleapis.com/css2?family=UnifrakturCook:wght@700&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #0a0a0a;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
      overflow: hidden;
    }

    .brand {
      font-family: 'UnifrakturCook', cursive;
      font-size: 3.5rem;
      color: #f0e6dc;
      text-shadow: 2px 2px 6px #6b0f1a;
      letter-spacing: 2px;
      margin-bottom: 1rem;
      z-index: 2;
    }

    h1 {
      font-family: 'UnifrakturCook', cursive;
      font-size: 2.2rem;
      line-height: 1.5;
      color: #f0e6dc;
      text-shadow: 2px 2px 4px #3b0a0a;
      max-width: 90%;
      letter-spacing: 1px;
      margin: 0;
      z-index: 2;
    }

    .emojis {
      font-family: sans-serif;
    }

    /* Mist Effect */
    .mist {
      position: absolute;
      top: 0;
      left: 0;
      width: 200%;
      height: 200%;
      background: url('https://raw.githubusercontent.com/hampusborgos/cdn/main/fog-overlay/fog1.png') repeat;
      background-size: cover;
      opacity: 0.07;
      animation: drift 120s linear infinite;
      z-index: 1;
      pointer-events: none;
    }

    @keyframes drift {
      0% {
        transform: translate(0, 0);
      }
      100% {
        transform: translate(-20%, -20%);
      }
    }

    /* Audio Controls */
    .audio-container {
      position: absolute;
      bottom: 20px;
      z-index: 3;
    }

    audio {
      filter: brightness(0.8);
    }
  </style>
</head>
<body>
  <!-- Mist Overlay -->
  <div class="mist"></div>

  <!-- Title -->
  <div class="brand">Candle Witch Lab</div>

  <!-- Tagline -->
  <h1>
    Witchy candles born of science & shadow.<br>
    Shop coming soon <span class="emojis">🧪🖤</span>
  </h1>

  <!-- Sound -->
  <div class="audio-container">
    <audio controls autoplay loop muted>
      <source src="https://files.catbox.moe/03c47u.mp3" type="audio/mpeg">
      Your browser does not support the audio element.
    </audio>
  </div>
</body>
</html>
