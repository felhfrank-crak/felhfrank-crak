
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Feliz Cumpleaños Mi Niña Hermosa ❤️</title>

  <!-- =========================
       ESTILOS (CSS)
       - Cambia colores/textos aquí si quieres
     ========================= -->
  <style>
    /* RESET mínimo */
    * { box-sizing: border-box; margin: 0; padding: 0; }
    html,body { height: 100%; font-family: "Segoe UI", Roboto, Arial, sans-serif; background: linear-gradient(180deg,#fff7fb 0%, #ffeef6 50%, #fffbe6 100%); color: #333; }

    /* CONTENEDOR CENTRAL */
    .page {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
      position: relative;
      overflow: hidden;
    }

    .card {
      width: 100%;
      max-width: 920px;
      background: rgba(255,255,255,0.9);
      border-radius: 18px;
      padding: 28px;
      box-shadow: 0 12px 40px rgba(120,40,80,0.12);
      display: grid;
      grid-template-columns: 1fr 360px;
      gap: 20px;
      align-items: center;
    }

    /* RESPONSIVE: en pantallas pequeñas se apila */
    @media (max-width:880px) {
      .card { grid-template-columns: 1fr; padding: 20px; }
      .side { order: 2; }
    }

    /* AREA DE MENSAJE */
    .hero {
      padding: 10px 12px;
    }

    .greeting {
      font-size: 28px;
      font-weight: 700;
      color: #b21f5a;
      letter-spacing: -0.4px;
      margin-bottom: 8px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .greeting .heart {
      width: 40px;
      height: 40px;
      transform: translateY(-3px);
      animation: beat 1s infinite;
    }
    @keyframes beat {
      0% { transform: scale(1) translateY(-3px); }
      30% { transform: scale(1.18) translateY(-6px); }
      60% { transform: scale(1) translateY(-3px); }
      100% { transform: scale(1) translateY(-3px); }
    }

    .message {
      margin-top: 12px;
      font-size: 16px;
      line-height: 1.6;
      color: #3a3a3a;
    }

    .message .name {
      color: #9e1650;
      font-weight: 700;
    }

    /* BOTONES */
    .actions { margin-top: 18px; display:flex; gap:10px; flex-wrap:wrap; }
    .btn {
      padding: 10px 14px;
      border-radius: 10px;
      border: none;
      cursor: pointer;
      font-weight: 600;
      box-shadow: 0 6px 18px rgba(120,40,80,0.08);
    }
    .btn-primary { background: linear-gradient(90deg,#ff6fb4,#ff8aa6); color: #fff; }
    .btn-ghost { background: transparent; border: 2px solid #ffd3e9; color:#b21f5a; }

    /* LADO DERECHO: foto + notas */
    .side {
      padding: 14px;
      display:flex;
      flex-direction:column;
      gap:12px;
      align-items:center;
    }
    .photo {
      width: 100%;
      max-width: 320px;
      height: 220px;
      border-radius: 12px;
      background: linear-gradient(135deg,#ffd9ec,#fff1f6);
      display:flex;
      align-items:center;
      justify-content:center;
      font-size:20px;
      color:#8a2a4a;
      text-align:center;
      padding:16px;
      box-shadow: 0 10px 24px rgba(120,40,80,0.06);
      position:relative;
      overflow:hidden;
    }

    /* FRASITOS decorativos */
    .notes {
      width:100%;
      display:flex;
      gap:8px;
      flex-direction:column;
    }
    .note {
      padding:10px;
      border-radius:10px;
      background: linear-gradient(90deg,#fff,#fff3f8);
      border: 1px solid rgba(160,80,120,0.06);
      font-size:14px;
      color:#6e2b48;
    }

    /* CORAZONES flotantes (decorativos) */
    .float-heart {
      position: absolute;
      width: 28px;
      height: 28px;
      background: #ff6fb4;
      transform: rotate(-45deg);
      border-radius: 6px 6px 0 0;
      opacity: 0.95;
      animation: floatUp linear infinite;
      box-shadow: 0 6px 18px rgba(160,60,100,0.12);
    }
    .float-heart:before, .float-heart:after {
      content: "";
      position: absolute;
      width: 28px; height: 28px;
      background: #ff6fb4;
      border-radius: 50%;
    }
    .float-heart:before { top: -14px; left: 0; }
    .float-heart:after  { left: 14px; top: 0; }

    @keyframes floatUp {
      0% { transform: translateY(20px) scale(0.9) rotate(-45deg); opacity: 0.95; }
      100% { transform: translateY(-360px) scale(1.15) rotate(-45deg); opacity: 0; }
    }

    /* PIE / creditos */
    .foot { margin-top: 8px; font-size:12px; color:#985066; opacity:0.9; }

    /* estilo para la caja de edición (oculta por defecto en presentación) */
    .edit-bar { margin-top:8px; display:flex; gap:8px; align-items:center; }

    /* CONFETTI: canvas ocupará toda la pantalla; pointer-events none para que no interfiera */
    canvas#confetti {
      position: fixed;
      left: 0; top: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 999;
    }

  </style>
</head>
<body>

  <!-- =========================
       CANVAS PARA CONFETTI (JS lo controla)
     ========================= -->
  <canvas id="confetti"></canvas>

  <div class="page">
    <!-- Corazones flotantes (se generan por JS también, estos están como ejemplo) -->
    <div class="float-heart" style="left:6%; bottom:12%; animation-duration:10s;"></div>
    <div class="float-heart" style="left:20%; bottom:6%; animation-duration:12s; width:36px; height:36px;"></div>
    <div class="float-heart" style="right:8%; bottom:20%; animation-duration:9s;"></div>

    <div class="card" role="main" aria-labelledby="titulo">
      <!-- ============= IZQUIERDA: Mensaje principal ============= -->
      <div class="hero">
        <div class="greeting" id="titulo">
          <!-- ICONO CORAZÓN SVG -->
          <svg class="heart" viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
            <path fill="#ff6fb4" d="M23.6 3.7c-2.5 0-4.5 1.8-5.6 3.3-1.1-1.5-3.1-3.3-5.6-3.3-3.6 0-6.4 3.1-6.4 7 0 9.2 12 12.9 12 21.3 0-8.4 12-12.1 12-21.3 0-3.9-2.8-7-6.4-7z"/>
          </svg>
          Feliz cumpleaños, <span id="her-name" class="name">[NOMBRE]</span>!
        </div>

        <div class="message" id="mainMessage">
          <!-- Mensaje editable por JS -->
          Hoy celebro que existes y cada momento que compartimos. Gracias por tu ternura, por tu risa y por los días que haces mejores.
          Quiero que hoy te rías mucho y que sientas todo mi cariño, talves esto no sea mucho pero aun asi te deseo lo mejor ,asi como te deseo lo mejor te deseo todas las noches.
        </div>

        <!-- Botones de interacción -->
        <div class="actions">
          <button class="btn btn-primary" id="playTuneBtn" title="Reproducir melodía">Reproducir melodía 🎵</button>
          <button class="btn btn-ghost" id="printBtn" title="Imprimir o guardar como PDF">Imprimir / Guardar</button>
          <button class="btn" id="confettiBtn" style="background:#fff1f6; border:2px solid #ffd3e9; color:#9e1650;">¡Lanzar confetti!</button>
          <button class="btn" id="editBtn" style="background:transparent; border:2px dashed #ffd3e9; color:#b21f5a;">Editar texto</button>
        </div>

        <!-- Barra de edición (oculta). Aquí puedes cambiar el nombre y el mensaje -->
        <div class="edit-bar" id="editBar" style="display:none;">
          <input id="inputName" placeholder="Sheyla" style="padding:8px;border-radius:8px;border:1px solid #ffddee;" />
          <textarea id="inputMsg" rows="3" placeholder="Escribe tu mensaje..." style="padding:8px;border-radius:8px;border:1px solid #ffddee; width:100%;"></textarea>
          <button class="btn btn-primary" id="saveEdit">Guardar</button>
          <button class="btn" id="cancelEdit" style="background:#fff; border:1px solid #f2cfe3">Cancelar</button>
        </div>

        <div class="foot">Consejo: personaliza el nombre y el mensaje antes de mostrarlo. Los detalles pequeños marcan la diferencia.</div>
      </div>

      <!-- ============= DERECHA: foto / notas ============= -->
      <aside class="side" aria-label="Detalles">
        <div class="photo" id="photoArea">
          <!-- Si quieres, reemplaza este texto con una foto usando background-image en CSS -->
          <div>
            ¡Tu foto aquí!<br>
            ![Imagen de WhatsApp 2025-11-19 a las 23 03 03_5ae7cd14](https://github.com/user-attachments/assets/2c1af59f-6b28-4ad8-bd0a-4d7081df893d)

          </div>
        </div>

        <div class="notes">
          <div class="note">💌 Sugerencia: prepara una sorpresa simple — un paseo, una carta, o un video corto.</div>
          <div class="note">🌅 Plan gratuito: un atardecer juntos y una playlist que le guste.</div>
        </div>

      </aside>
    </div>
  </div>

  <!-- =========================
       SCRIPTS (JS)
       - Aquí están todas las funcionalidades: confetti, melodía, edición, imprimir
     ========================= -->
  <script>
    /* =========================
       CONFIGURACIÓN: Cambia estos valores para personalizar rápido
       - herName: nombre que aparecerá en el título (Sheyla)
       - messageText: texto principal
     ========================= */
    let herName = "Mi Niña hermosa";
    let messageText = "Hoy celebro que existes y cada momento que compartimos. Gracias por tu ternura, por tu risa y por los días que haces mejores. gracias tanto asi como soportarme y aguantarme y te deseo lo mejor mi princesa y asi como te deseo lo mejor tambien te deseo y tu ya sabes a lo que me refiero😏🤣❤️.";

    // Inicializar textos en la página
    document.getElementById('her-name').textContent = herName;
    document.getElementById('mainMessage').textContent = messageText;
    document.getElementById('inputName').value = herName;
    document.getElementById('inputMsg').value = messageText;

    /* =========================
       BOTONES: imprimir / editar / guardar
     ========================= */
    const printBtn = document.getElementById('printBtn');
    const editBtn = document.getElementById('editBtn');
    const editBar = document.getElementById('editBar');
    const saveEdit = document.getElementById('saveEdit');
    const cancelEdit = document.getElementById('cancelEdit');
    const inputName = document.getElementById('inputName');
    const inputMsg = document.getElementById('inputMsg');

    printBtn.addEventListener('click', () => {
      window.print();
    });

    editBtn.addEventListener('click', () => {
      editBar.style.display = editBar.style.display === 'none' ? 'flex' : 'none';
    });

    cancelEdit.addEventListener('click', () => {
      editBar.style.display = 'none';
      inputName.value = herName;
      inputMsg.value = messageText;
    });

    saveEdit.addEventListener('click', () => {
      herName = inputName.value.trim() || "Amor";
      messageText = inputMsg.value.trim() || messageText;
      document.getElementById('her-name').textContent = herName;
      document.getElementById('mainMessage').textContent = messageText;
      editBar.style.display = 'none';
    });

    /* =========================
       CONFETTI SIMPLE con canvas
       - No necesita librerías
     ========================= */
    const confettiCanvas = document.getElementById('confetti');
    const ctx = confettiCanvas.getContext('2d');
    let confettiPieces = [];
    let confettiRunning = false;

    function resizeCanvas() {
      confettiCanvas.width = window.innerWidth;
      confettiCanvas.height = window.innerHeight;
    }
    window.addEventListener('resize', resizeCanvas);
    resizeCanvas();

    function random(min, max) { return Math.random() * (max - min) + min; }

    function createConfetti(count = 120) {
      confettiPieces = [];
      const colors = ['#ff6fb4','#ffd9ec','#ffd67a','#ff8aa6','#b21f5a','#ffb3dd'];
      for (let i=0; i<count; i++) {
        confettiPieces.push({
          x: random(0, confettiCanvas.width),
          y: random(-confettiCanvas.height, 0),
          size: random(6, 14),
          speedY: random(1.5, 6),
          speedX: random(-1.5, 1.5),
          rotation: random(0, Math.PI*2),
          rotateSpeed: random(-0.1, 0.1),
          color: colors[Math.floor(random(0, colors.length))],
        });
      }
    }

    function renderConfetti() {
      ctx.clearRect(0,0,confettiCanvas.width, confettiCanvas.height);
      for (const p of confettiPieces) {
        ctx.save();
        ctx.translate(p.x, p.y);
        ctx.rotate(p.rotation);
        ctx.fillStyle = p.color;
        ctx.fillRect(-p.size/2, -p.size/2, p.size, p.size * 0.6);
        ctx.restore();

        p.y += p.speedY;
        p.x += p.speedX;
        p.rotation += p.rotateSpeed;

        if (p.y > confettiCanvas.height + 20) {
          // reciclar por arriba
          p.y = random(-200, -50);
          p.x = random(0, confettiCanvas.width);
        }
      }
      if (confettiRunning) requestAnimationFrame(renderConfetti);
    }

    document.getElementById('confettiBtn').addEventListener('click', () => {
      if (!confettiRunning) {
        createConfetti(140);
        confettiRunning = true;
        renderConfetti();
        // detener después de 6s automáticamente
        setTimeout(() => confettiRunning = false, 6000);
      }
    });

    /* =========================
       MELODÍA: generar una melodía simple con WebAudio
     ========================= */
    const playTuneBtn = document.getElementById('playTuneBtn');
    let audioCtx = null;
    function playMelody() {
      try {
        if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        const now = audioCtx.currentTime;
        const notes = [440, 523.25, 659.25, 880]; // A4, C5, E5, A5 (simple arpegio)
        const durations = [0.35, 0.35, 0.35, 0.7];
        let t = now;
        for (let i=0;i<notes.length;i++) {
          const o = audioCtx.createOscillator();
          const g = audioCtx.createGain();
          o.type = 'sine';
          o.frequency.value = notes[i];
          g.gain.value = 0.0001;
          o.connect(g);
          g.connect(audioCtx.destination);
          o.start(t);
          // ramp up
          g.gain.exponentialRampToValueAtTime(0.15, t + 0.02);
          // ramp down
          g.gain.exponentialRampToValueAtTime(0.0001, t + durations[i]);
          o.stop(t + durations[i] + 0.02);
          t += durations[i];
        }
      } catch(e) {
        alert('Tu navegador no soporta WebAudio o hay una política de autoplay que lo bloquea. Intenta interactuar con la página primero.');
      }
    }

    playTuneBtn.addEventListener('click', playMelody);

    /* =========================
       Pequeña animación de aparición (accesibilidad)
     ========================= */
    window.addEventListener('load', () => {
      document.querySelector('.card').style.transform = 'translateY(6px)';
      document.querySelector('.card').style.opacity = '1';
    });

    /* =========================
       Sugerencia: permitir que al presionar 'Enter' en inputs se guarde (mejor UX)
     ========================= */
    inputName.addEventListener('keydown', (e)=>{ if (e.key === 'Enter') { saveEdit.click(); } });

    /* =========================
       FIN del script
     ========================= */

  </script>
</body>
</html>
