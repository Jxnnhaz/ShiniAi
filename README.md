
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Comandos Aternos - Estilo Minecraft</title>
  <style>
    body {
      background-color: #2b2b2b;
      color: #00ff00;
      font-family: "Lucida Console", Monaco, monospace;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #1a1a1a;
      padding: 15px;
      text-align: center;
      font-size: 24px;
      color: #00ff00;
      border-bottom: 2px solid #00ff00;
    }
    nav {
      display: flex;
      justify-content: center;
      background-color: #333;
      padding: 10px 0;
    }
    nav button {
      background-color: #444;
      color: #00ff00;
      border: none;
      margin: 0 10px;
      padding: 10px 20px;
      cursor: pointer;
      font-size: 16px;
    }
    nav button:hover {
      background-color: #555;
    }
    .section {
      display: none;
      padding: 20px;
    }
    .active {
      display: block;
    }
    code {
      background-color: #111;
      padding: 4px 6px;
      border-radius: 4px;
      color: #0ff;
      display: block;
      margin-bottom: 10px;
    }
  </style>
  <script>
    function showSection(id) {
      const sections = document.querySelectorAll('.section');
      sections.forEach(sec => sec.classList.remove('active'));
      document.getElementById(id).classList.add('active');
    }
    window.onload = () => showSection('basicos');
  </script>
</head>
<body>
  <header>
    Comandos para Servidores Aternos - Guía Minecraft
  </header>
  <nav>
    <button onclick="showSection('basicos')">🧱 Básicos</button>
    <button onclick="showSection('troll')">👻 Trolleo</button>
    <button onclick="showSection('efectos')">✨ Efectos</button>
    <button onclick="showSection('invocaciones')">💀 Invocaciones</button>
  </nav>

  <div id="basicos" class="section">
    <h2>🧱 Comandos Básicos</h2>
    <code>/gamemode creative</code>
    <code>/tp [jugador] [coordenadas]</code>
    <code>/give @p minecraft:diamond_sword</code>
  </div>

  <div id="troll" class="section">
    <h2>👻 Comandos de Trolleo</h2>
    <code>/title @a title {"text":"null null null","color":"dark_red"}</code>
    <code>/summon minecraft:zombie ~ ~ ~ {NoAI:1b,Silent:1b,CustomName:'{"text":"Null","color":"dark_red"}'}</code>
    <code>/effect give @a minecraft:blindness 10 1 true</code>
  </div>

  <div id="efectos" class="section">
    <h2>✨ Comandos de Efectos</h2>
    <code>/effect give @a minecraft:levitation 5 1</code>
    <code>/effect clear @a</code>
    <code>/weather thunder</code>
    <code>/time set night</code>
  </div>

  <div id="invocaciones" class="section">
    <h2>💀 Comandos de Invocaciones</h2>
    <code>/summon minecraft:lightning_bolt ~ ~ ~</code>
    <code>/summon minecraft:zombie ~ ~ ~ {CustomName:'"Null"',Silent:1b,NoAI:1b}</code>
    <code>/summon minecraft:cod ~ ~5 ~</code>
  </div>
</body>
</html>
