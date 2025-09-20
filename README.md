# Nebiory-
Something better 
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Surpresa 💖</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      overflow: hidden;
      padding: 20px;
    }
    .card {
      background: #ffffff;
      padding: 28px;
      border-radius: 18px;
      text-align: center;
      box-shadow: 0 6px 24px rgba(0,0,0,0.18);
      max-width: 460px;
      width: 100%;
      position: relative;
    }
    h1 { margin: 0 0 10px; color: #ff3b6b; font-size: 26px; }
    p { margin: 0 0 14px; color: #333; line-height: 1.4; }
    button {
      margin-top: 10px;
      padding: 10px 20px;
      background: #ff3b6b;
      color: #fff;
      border: none;
      border-radius: 24px;
      cursor: pointer;
      font-weight: 600;
      font-size: 15px;
    }
    button:active { transform: scale(.99); }
    .hidden-message {
      margin-top: 18px;
      display: none;
      font-size: 16px;
      color: #222;
      text-align: left;
      background: rgba(255,255,255,0.9);
      padding: 12px;
      border-radius: 10px;
      line-height: 1.45;
    }
    .heart {
      position: absolute;
      top: -40px;
      font-size: 20px;
      pointer-events: none;
      user-select: none;
      animation: fall linear forwards;
      opacity: 0.95;
    }
    @keyframes fall {
      0% { transform: translateY(-10vh) rotate(0deg); opacity: 1; }
      100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
    }
    .footer {
      position: fixed;
      left: 12px;
      right: 12px;
      bottom: 12px;
      text-align: center;
      font-size: 13px;
      color: rgba(36,18,36,0.8);
    }
  </style>
</head>
<body>
  <div class="card" role="main" aria-labelledby="title">
    <h1 id="title">Para você 💖</h1>
    <p>Mila — toca no botão para ver a mensagem que eu guardei só pra ti.</p>
    <button id="btn">Descobrir</button>

    <div id="message" class="hidden-message" aria-live="polite">
      🌹 Bae — Eu aceito o teu perdão, meu amor. Tu és a parte mais importante da minha vida, muito acima de qualquer erro ou fase difícil. Eu confio em ti de todo o coração e sei que isso não nos define. O que sentimos um pelo outro é maior do que qualquer obstáculo, e eu escolho sempre caminhar contigo, porque és o meu tudo. HABIBE ❤🥺
    </div>
  </div>

  <div class="footer">Toca no botão — e espera a surpresa ✨</div>

  <script>
    const btn = document.getElementById('btn');
    const msg = document.getElementById('message');

    function mostrarMensagem() {
      if (msg.style.display === 'block') return;
      msg.style.display = 'block';
      btn.disabled = true;
      btn.innerText = 'Feito';
      msg.scrollIntoView({behavior: 'smooth', block: 'center'});
    }

    btn.addEventListener('click', mostrarMensagem);

    // corações caindo
    function soltarCoracoes(){
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.textContent = '❤️';
      const size = Math.floor(Math.random()*28) + 14;
      heart.style.fontSize = size + 'px';
      heart.style.left = Math.random()*100 + 'vw';
      const duration = Math.random()*4 + 4;
      heart.style.animationDuration = duration + 's';
      document.body.appendChild(heart);
      setTimeout(()=> heart.remove(), (duration*1000)+200);
    }

    const interval = setInterval(soltarCoracoes, 450);
    // parar após 90s para poupar recurso em dispositivos fracos
    setTimeout(()=> clearInterval(interval), 90000);
  </script>
</body>
</html>
