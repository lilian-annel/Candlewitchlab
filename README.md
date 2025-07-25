<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Candle Witch Lab</title>
  <style>
    body {
      font-family: 'Georgia', serif;
      background-color: #0f0f0f;
      color: #e8e6e3;
      margin: 0;
      padding: 0;
    }

    header {
      background-color: #1a1a1a;
      padding: 2rem;
      text-align: center;
      border-bottom: 2px solid #444;
    }

    h1 {
      font-size: 2.5rem;
      color: #f5c518;
      margin: 0;
    }

    p.tagline {
      font-style: italic;
      margin-top: 0.5rem;
      color: #ccc;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1rem;
      padding: 2rem;
    }

    .product {
      background-color: #1a1a1a;
      padding: 1rem;
      border: 1px solid #333;
      text-align: center;
      border-radius: 8px;
    }

    .product img {
      max-width: 100%;
      border-radius: 4px;
    }

    footer {
      background-color: #1a1a1a;
      color: #aaa;
      text-align: center;
      padding: 1rem;
      font-size: 0.9rem;
      border-top: 1px solid #444;
    }

    a {
      color: #f5c518;
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <header>
    <h1>Candlewitchlab</h1>
    <p class="tagline">Handmade spells in wax & flame</p>
  </header>

  <section class="gallery">
    <div class="product">
      <img src="https://via.placeholder.com/200x200?text=Spell+Jar+Candle" alt="Spell Jar Candle">
      <p>Spell Jar Candle</p>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/200x200?text=Full+Moon+Ritual" alt="Full Moon Ritual">
      <p>Full Moon Ritual Candle</p>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/200x200?text=Protection+Blend" alt="Protection Blend">
      <p>Protection Blend</p>
    </div>
  </section>

  <footer>
    <p>Contact: candlewitchlab@gmail.com |  
      <a href="https://instagram.com/YOURUSERNAME" target="_blank">Instagram</a>
    </p>
    <p>&copy; 2025 Candlewitchlab. All rights reserved.</p>
  </footer>
</body>
</html>
