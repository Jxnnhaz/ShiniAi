
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Comandos Aternos - Proyecto Lyn</title>
  <style>
    /* Tipografía y fondo Minecraft */
    body {
      margin: 0;
      padding: 0;
      font-family: "Lucida Console", Monaco, monospace;
      color: #00ff00;
      background-image: url('https://i.imgur.com/7N2TtFb.png');
      background-size: 32px 32px;
      overflow-y: auto;
      -webkit-overflow-scrolling: touch;
    }
    header {
      background-color: #000;
      padding: 12px;
      text-align: center;
      font-size: 20px;
      color: #0f0;
      border-bottom: 2px solid #0f0;
    }
    nav {
      display: flex;
      overflow-x: auto;
      white-space: nowrap;
      background-color: #111;
      padding: 8px 0;
      -webkit-overflow-scrolling: touch;
    }
    nav button {
      flex: 0 0 auto;
      background-color: #222;
      color: #0f0;
      border: 1px solid #0f0;
      margin: 0 5px;
      padding: 8px 16px;
      font-size: 14px;
      cursor: pointer;
    }
    nav button:hover {
      background-color: #333;
    }
    .section {
      display: none;
      padding: 16px;
      background-color: rgba(0,0,0,0.8);
    }
    .active {
      display: block;
    }
    code {
      display: block;
      background-color: #111;
      padding: 6px 8px;
      border-radius: 4px;
      margin: 8px 0;
      color: #0ff;
      word-break: break-all;
    }
    button.copy {
      margin: 4px 0 12px 0;
      font-size: 12px;
      cursor: pointer;
      background: #0f0;
      color: #000;
      border: none;
      padding: 4px 8px;
      border-radius: 3px;
    }
    /* Asegurar que input y textarea sean responsivos */
    input, textarea {
      width: 100%;
      box-sizing: border-box;
      font-family: monospace;
      padding: 6px;
      margin: 8px 0;
      border: 1px solid #0f0;
      border-radius: 4px;
      background-color: #222;
      color: #0f0;
    }
  </style>
  <script>
    function showSection(id) {
      document.querySelectorAll('.section').forEach(sec => sec.classList.remove('active'));
      document.getElementById(id).classList.add('active');
    }
    function copiar(id) {
      const texto = document.getElementById(id).textContent;
      navigator.clipboard.writeText(texto).then(() => alert("Comando copiado"));
    }
    function responderIA() {
      const input = document.getElementById("userInput").value.toLowerCase();
      let respuesta = "No entendí, intenta otra vez.";
      if (input.includes("espada")) respuesta = "/give @p minecraft:diamond_sword";
      else if (input.includes("rayo")) respuesta = "/summon minecraft:lightning_bolt ~ ~ ~";
      else if (input.includes("invisible")) respuesta = "/effect give @p minecraft:invisibility 30 1";
      document.getElementById("respuestaIA").textContent = respuesta;
    }
    window.onload = () => showSection('basicos');
  </script>
</head>
<body>
  <header>🧱 Comandos Aternos - Proyecto Lyn</header>
  <nav>
    <button onclick="showSection('basicos')">Básicos</button>
    <button onclick="showSection('efectos')">Efectos</button>
    <button onclick="showSection('trolleo')">Trolleo</button>
    <button onclick="showSection('invocaciones')">Invocaciones</button>
    <button onclick="showSection('paranormal')">Paranormales</button>
    <button onclick="showSection('shini')">Shini (IA)</button>
  </nav>
  <div id="basicos" class="section">
    <h2>🛠 Comandos Básicos</h2>
    <code id="c1">/gamemode creative</code><button class="copy" onclick="copiar('c1')">Copiar</button>
    <code id="c2">/tp [jugador] [x] [y] [z]</code><button class="copy" onclick="copiar('c2')">Copiar</button>
    <code id="c3">/give @p minecraft:diamond_sword</code><button class="copy" onclick="copiar('c3')">Copiar</button>
  </div>
  <div id="efectos" class="section">
    <h2>✨ Efectos</h2>
    <code id="e1">/effect give @a minecraft:levitation 5 1</code><button class="copy" onclick="copiar('e1')">Copiar</button>
    <code id="e2">/effect clear @a</code><button class="copy" onclick="copiar('e2')">Copiar</button>
    <code id="e3">/weather thunder</code><button class="copy" onclick="copiar('e3')">Copiar</button>
  </div>
  <div id="trolleo" class="section">
    <h2>👻 Comandos de Trolleo</h2>
    <code id="t1">/title @a title {"text":"null null null","color":"dark_red"}</code><button class="copy" onclick="copiar('t1')">Copiar</button>
    <code id="t2">/summon minecraft:cod ~ ~5 ~</code><button class="copy" onclick="copiar('t2')">Copiar</button>
    <code id="t3">/playsound minecraft:entity.ghast.scream master @a</code><button class="copy" onclick="copiar('t3')">Copiar</button>
  </div>
  <div id="invocaciones" class="section">
    <h2>💀 Invocaciones</h2>
    <code id="i1">/summon minecraft:lightning_bolt ~ ~ ~</code><button class="copy" onclick="copiar('i1')">Copiar</button>
    <code id="i2">/summon minecraft:zombie ~ ~ ~ {CustomName:'{"text":"Lyn","color":"red"}',NoAI:1b,Silent:1b}</code><button class="copy" onclick="copiar('i2')">Copiar</button>
  </div>
  <div id="paranormal" class="section">
    <h2>🌑 Paranormales</h2>
    <code id="p1">/title @a title {"text":"null está aquí...","color":"dark_red"}</code><button class="copy" onclick="copiar('p1')">Copiar</button>
    <code id="p2">/effect give @a minecraft:blindness 10 1 true</code><button class="copy" onclick="copiar('p2')">Copiar</button>
    <code id="p3">/say Una entidad desconocida ha entrado al mundo...</code><button class="copy" onclick="copiar('p3')">Copiar</button>
  </div>
  <div id="shini" class="section">
    <h2>🤖 Shini (IA)</h2>
    <p>Escribe tu duda:</p>
    <input type="text" id="userInput" placeholder="¿Cómo darme una espada?"/>
    <button onclick="responderIA()" class="copy">Preguntar</button>
    <p id="respuestaIA"></p>
  </div>
</body>
</html>
