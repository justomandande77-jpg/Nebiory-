# Nebiory-M
Something better 
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Para Mila 💖</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ffdde1, #ee9ca7);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: "Segoe UI", sans-serif;
      overflow: hidden;
    }
    .card {
      background: rgba(255,255,255,0.95);
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 8px 28px rgba(0,0,0,0.25);
      max-width: 600px;
      z-index: 2;
    }
    h1 {
      color: #e63956;
      margin-bottom: 15px;
    }
    .message {
      font-size: 18px;
      color: #333;
      line-height: 1.5;
      display: none;
      margin-top: 20px;
    }
    button {
      padding: 12px 26px;
      background: #e63956;
      color: #fff;
      border: none;
      border-radius: 28px;
      font-size: 16px;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover { background: #c92f48; }
    .typewriter {
      margin-top: 18px;
      font-size: 17px;
      color: #444;
      min-height: 60px;
      white-space: pre-line;
    }
    .final {
      margin-top: 22px;
      font-size: 20px;
      color: #e63956;
      font-weight: bold;
      display: none;
    }
    .hearts {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 1;
    }
    .heart {
      position: absolute;
      color: #ff4d6d;
      font-size: 20px;
      animation: rise 6s linear forwards;
      opacity: 0.8;
    }
    @keyframes rise {
      from { transform: translateY(100vh) scale(1); opacity: 1; }
      to { transform: translateY(-10vh) scale(1.5); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Para Mila 💖</h1>
    <p>Tenho algo importante para te dizer...</p>
    <button id="btn">Abrir Mensagem</button>

    <div class="message" id="mainMsg">
      Mila, eu quero que saibas que eu <strong>te perdoo</strong> do fundo do meu coração.  
      Tu és a parte mais importante da minha vida e nada do que passou muda o que sinto.  
      O nosso amor é maior do que qualquer obstáculo. 💞
    </div>

    <div class="typewriter" id="typewriter"></div>

    <div class="final" id="finalMsg">
      Sempre teu, <strong>Habibe ❤️</strong>
    </div>
  </div>

  <div class="hearts" id="hearts"></div>

  <script>
    const btn = document.getElementById("btn");
    const msg = document.getElementById("mainMsg");
    const typewriter = document.getElementById("typewriter");
    const finalMsg = document.getElementById("finalMsg");

    const frases = [
      "Tu és o meu porto seguro 🌹",
      "Nada se compara ao que sinto por ti 💕",
      "Cometemos erros, mas o amor vence sempre 💖",
      "Eu escolho sempre caminhar ao teu lado ✨",
      "Tu és e sempre serás o meu tudo, Mila ❤️"
    ];

    function escrever(frases, i=0) {
      if (i >= frases.length) {
        finalMsg.style.display = "block";
        return;
      }
      let txt = frases[i];
      let j = 0;
      typewriter.textContent = "";
      let interval = setInterval(() => {
        typewriter.textContent += txt[j];
        j++;
        if (j >= txt.length) {
          clearInterval(interval);
          setTimeout(()=> escrever(frases, i+1), 1800);
        }
      }, 60);
    }

    btn.addEventListener("click", () => {
      btn.style.display = "none";
      msg.style.display = "block";
      escrever(frases);
    });

    // corações animados
    const heartsContainer = document.getElementById("hearts");
    function soltarCoracao(){
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.textContent = "❤️";
      heart.style.left = Math.random()*100 + "vw";
      heart.style.fontSize = (16 + Math.random()*24) + "px";
      heart.style.animationDuration = (4 + Math.random()*4) + "s";
      heartsContainer.appendChild(heart);
      setTimeout(()=> heart.remove(), 7000);
    }
    setInterval(soltarCoracao, 400);
  </script>
</body>
</html>
