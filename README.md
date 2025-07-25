<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Candle Witch Lab</title>
  <link href="https://fonts.googleapis.com/css2?family=UnifrakturCook:wght@700&display=swap" rel="stylesheet" />
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
      color: #f0e6dc;
      font-family: 'UnifrakturCook', cursive;
      position: relative;
    }

    .brand {
      font-size: 3.5rem;
      text-shadow: 2px 2px 6px #6b0f1a;
      letter-spacing: 2px;
      margin-bottom: 1rem;
      z-index: 3;
      user-select: none;
    }

    h1 {
      font-size: 2.2rem;
      line-height: 1.5;
      text-shadow: 2px 2px 4px #3b0a0a;
      max-width: 90%;
      letter-spacing: 1px;
      margin: 0;
      z-index: 3;
      user-select: none;
    }

    .emojis {
      font-family: sans-serif;
    }

    /* Mist using multiple animated circles */
    .mist {
      position: absolute;
      top: 0;
      left: 0;
      width: 120%;
      height: 120%;
      pointer-events: none;
      z-index: 1;
      overflow: visible;
    }

    .mist div {
      position: absolute;
      border-radius: 50%;
      background: radial-gradient(circle at center, rgba(240, 230, 220, 0.12), transparent 70%);
      filter: blur(40px);
      animation-timing-function: linear;
      animation-iteration-count: infinite;
      opacity: 0.1;
    }

    .mist div:nth-child(1) {
      width: 300px;
      height: 300px;
      top: 10%;
      left: 20%;
      animation-name: drift1;
      animation-duration: 90s;
      animation-direction: alternate;
    }
    .mist div:nth-child(2) {
      width: 400px;
      height: 400px;
      top: 50%;
      left: 60%;
      animation-name: drift2;
      animation-duration: 120s;
      animation-direction: alternate-reverse;
    }
    .mist div:nth-child(3) {
      width: 250px;
      height: 250px;
      top: 70%;
      left: 30%;
      animation-name: drift3;
      animation-duration: 100s;
      animation-direction: alternate;
    }
    .mist div:nth-child(4) {
      width: 350px;
      height: 350px;
      top: 30%;
      left: 80%;
      animation-name: drift4;
      animation-duration: 110s;
      animation-direction: alternate-reverse;
    }
    .mist div:nth-child(5) {
      width: 280px;
      height: 280px;
      top: 60%;
      left: 10%;
      animation-name: drift5;
      animation-duration: 95s;
      animation-direction: alternate;
    }

    @keyframes drift1 {
      0% { transform: translate(0, 0); }
      100% { transform: translate(-20px, 15px); }
    }
    @keyframes drift2 {
      0% { transform: translate(0, 0); }
      100% { transform: translate(25px, -20px); }
    }
    @keyframes drift3 {
      0% { transform: translate(0, 0); }
      100% { transform: translate(-15px, 20px); }
    }
    @keyframes drift4 {
      0% { transform: translate(0, 0); }
      100% { transform: translate(20px, 25px); }
    }
    @keyframes drift5 {
      0% { transform: translate(0, 0); }
      100% { transform: translate(-25px, -15px); }
    }

    /* Custom audio controls container */
    .audio-container {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: rgba(15, 15, 15, 0.6);
      border-radius: 8px;
      padding: 10px 15px;
      z-index: 5;
      display: flex;
      align-items: center;
      gap: 10px;
      user-select: none;
      font-family: Arial, sans-serif;
      color: #ddd;
    }

    .audio-container button {
      background: none;
      border: none;
      color: #f0e6dc;
      font-size: 1.2rem;
      cursor: pointer;
      user-select: none;
    }

    input[type="range"] {
      -webkit-appearance: none;
      width: 120px;
      height: 6px;
      border-radius: 3px;
      background: #3b0a0a;
      cursor: pointer;
    }

    input[type="range"]::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: #f0e6dc;
      cursor: pointer;
      border: 1.5px solid #6b0f1a;
      transition: background 0.2s ease;
    }

    input[type="range"]:focus::-webkit-slider-thumb {
      background: #d94b4b;
    }
  </style>
</head>
<body>
  <div class="mist">
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
  </div>

  <div class="brand">Candle Witch Lab</div>
  <h1>
    Witchy candles born of science & shadow.<br />
    Shop coming soon <span class="emojis">🧪🖤</span>
  </h1>

  <div class="audio-container" aria-label="Audio controls">
    <button id="mute-btn" aria-label="Toggle sound">🔈</button>
    <input id="volume-slider" type="range" min="0" max="1" step="0.01" value="0" aria-label="Volume slider" />
  </div>

  <audio id="ambient-audio" loop preload="auto">
    <source src="https://files.catbox.moe/03c47u.mp3" type="audio/mpeg" />
    Your browser does not support the audio element.
  </audio>

  <script>
    const audio = document.getElementById('ambient-audio');
    const muteBtn = document.getElementById('mute-btn');
    const volumeSlider = document.getElementById('volume-slider');

    // Start muted with volume 0 for autoplay compliance
    audio.volume = 0;
    audio.muted = false;
    audio.play().catch(() => {
      audio.muted = true;
      audio.play();
    });

    muteBtn.addEventListener('click', () => {
      if (audio.muted || audio.volume === 0) {
        audio.muted = false;
        audio.volume = volumeSlider.value;
        muteBtn.textContent = '🔊';
        if (audio.paused) audio.play();
      } else {
        audio.muted = true;
        muteBtn.textContent = '🔈';
      }
    });

    volumeSlider.addEventListener('input', (e) => {
      const volume = parseFloat(e.target.value);
      audio.volume = volume;
      if (volume === 0) {
        audio.muted = true;
        muteBtn.textContent = '🔈';
      } else {
        audio.muted = false;
        muteBtn.textContent = '🔊';
      }
    });
  </script>
</body>
</html>
