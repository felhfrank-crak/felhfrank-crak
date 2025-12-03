
<html lang="es">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Feliz Cumpleaños - Mi Amor</title>

<!-- =========================
     ESTILOS (CSS)
========================= -->
<style>
  :root{
    --pink:#ff6fb4;
    --pink-2:#ff8aa6;
    --bg1:#fff7fb;
    --bg2:#fff1f6;
    --text:#2b1630;
    --card:#ffffffcc;
    --glass: rgba(255,255,255,0.12);
  }

  /* dark mode variables will be toggled by .dark on body */
  body {
    margin:0;
    font-family: "Segoe UI", Roboto, Arial, sans-serif;
    background: linear-gradient(180deg,var(--bg1),var(--bg2));
    color: var(--text);
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    min-height:100vh;
    overflow-x:hidden;
  }

  body.dark{
    --pink:#ff92c3;
    --pink-2:#ffb3d6;
    --bg1:#0f0b10;
    --bg2:#1a0f17;
    --text:#ffeef8;
    --card: rgba(20,14,18,0.62);
    --glass: rgba(255,255,255,0.03);
    background: linear-gradient(180deg,#0b0810,#1e1220);
  }

  /* page container */
  .page {
    display:flex;
    justify-content:center;
    padding:28px;
    position:relative;
  }

  .card {
    width:100%;
    max-width:1100px;
    background:var(--card);
    border-radius:18px;
    padding:22px;
    box-shadow: 0 14px 40px rgba(120,40,80,0.08);
    display:grid;
    grid-template-columns: 1fr 420px;
    gap:20px;
    align-items:start;
    position:relative;
    overflow:visible;
  }

  @media (max-width:980px){
    .card{ grid-template-columns:1fr; padding:18px; }
  }

  /* header & title */
  .header {
    display:flex;
    align-items:center;
    gap:14px;
    margin-bottom:8px;
  }
  .logo {
    width:56px;height:56px;border-radius:50%;overflow:hidden;flex:0 0 56px;
    box-shadow:0 8px 20px rgba(200,80,140,0.12);
  }
  .logo img{ width:100%; height:100%; object-fit:cover; display:block; }

  .title {
    font-size:26px;
    font-weight:700;
    color:var(--pink-2);
    display:flex;
    flex-direction:column;
    line-height:1;
  }
  .subtitle { font-size:14px; font-weight:600; color:var(--text); opacity:0.85; margin-top:6px; }

  /* left content */
  .left {
    padding-right:10px;
  }

  .message-box {
    background: var(--glass);
    padding:16px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,0.06);
    box-shadow: 0 8px 20px rgba(0,0,0,0.04);
  }

  .typed {
    font-size:18px;
    color:var(--text);
    min-height:72px;
    white-space:pre-wrap;
  }

  .typed .extra { color:var(--pink); font-weight:700; }

  .controls { margin-top:12px; display:flex; gap:10px; flex-wrap:wrap; }

  .btn {
    padding:10px 14px;
    border-radius:10px;
    border:none;
    cursor:pointer;
    font-weight:700;
    background: linear-gradient(90deg,var(--pink),var(--pink-2));
    color:white;
    box-shadow: 0 8px 20px rgba(200,60,120,0.12);
  }
  .btn.ghost {
    background:transparent;
    border:2px solid rgba(255,255,255,0.12);
    color:var(--text);
  }

  /* secret message panel (animated 3D open) */
  .letter-wrap { margin-top:18px; perspective:1200px; }
  .letter {
    width:100%;
    max-width:680px;
    margin:0 auto;
    transform-style:preserve-3d;
    position:relative;
  }
  .envelope {
    width:100%;
    height:120px;
    background:linear-gradient(180deg,#ffeef6,#fff7fb);
    border-radius:12px;
    display:flex;
    align-items:center;
    justify-content:center;
    color:var(--pink-2);
    font-weight:800;
    box-shadow: 0 14px 44px rgba(200,20,80,0.08);
    position:relative;
    transition: transform 0.8s cubic-bezier(.2,.9,.3,1), box-shadow .4s;
    transform-origin:top center;
    cursor:pointer;
  }
  .envelope.open {
    transform: rotateX(-170deg) translateY(-8px);
    box-shadow: 0 28px 64px rgba(200,20,80,0.12);
  }

  .letter-body {
    margin-top:12px;
    padding:16px;
    border-radius:10px;
    background: linear-gradient(180deg,#fff,#fff3f8);
    color:var(--text);
    display:none;
  }
  .letter.show { display:block; animation: floatIn .7s ease; }
  @keyframes floatIn { from{ transform: translateY(12px); opacity:0 } to{ transform:none; opacity:1 } }

  /* right sidebar */
  .side {
    padding:10px;
    display:flex;
    flex-direction:column;
    gap:12px;
    align-items:center;
  }

  .photo {
    width:100%;
    max-width:360px;
    height:220px;
    border-radius:12px;
    overflow:hidden;
    background:linear-gradient(135deg,#ffd9ec,#fff1f6);
    display:flex;
    align-items:center;
    justify-content:center;
    box-shadow:0 10px 30px rgba(120,40,80,0.06);
  }
  .photo img{ width:100%; height:100%; object-fit:cover; display:block; }

  .notes {
    width:100%;
    display:flex;
    flex-direction:column;
    gap:8px;
  }
  .note {
    padding:10px;
    border-radius:10px;
    background: linear-gradient(90deg,#fff,#fff3f8);
    border: 1px solid rgba(160,80,120,0.06);
    color:var(--text);
    font-weight:600;
    text-align:left;
  }

  /* carousel */
  .carousel { width:100%; margin-top:6px; position:relative; overflow:hidden; border-radius:12px; }
  .carousel-track { display:flex; gap:8px; transition: transform .5s ease; will-change:transform; }
  .carousel-item { min-width: 100%; flex:0 0 100%; height:160px; border-radius:10px; overflow:hidden; }
  .carousel-item img{ width:100%; height:100%; object-fit:cover; display:block; }

  .carousel-controls { display:flex; gap:8px; margin-top:8px; justify-content:center; }

  .small-btn { padding:8px 10px; border-radius:8px; border:none; background:var(--pink-2); color:white; cursor:pointer; font-weight:700; }

  /* music button */
  #musicBtn { position:fixed; bottom:18px; right:18px; border-radius:999px; width:56px; height:56px; font-size:18px; display:flex; align-items:center; justify-content:center; background:linear-gradient(90deg,var(--pink),var(--pink-2)); color:white; border:none; box-shadow:0 10px 30px rgba(200,80,140,0.18); z-index:60; }

  /* fireworks canvas and petals canvas */
  canvas#fireworks, canvas#petals { position:fixed; left:0; top:0; width:100%; height:100%; pointer-events:none; z-index:10; }

  /* touch hearts */
  .touch-heart {
    position:fixed;
    pointer-events:none;
    width:18px;height:18px; transform:rotate(-45deg); border-radius:4px; z-index:70;
    background:var(--pink);
  }
  .touch-heart::before,.touch-heart::after{ content:""; position:absolute; width:18px;height:18px; background:var(--pink); border-radius:50%; }
  .touch-heart::before{ top:-9px; left:0 } .touch-heart::after{ left:9px; top:0 }

  /* "Toca aquí" special */
  #specialModal {
    position:fixed; inset:0; display:flex; align-items:center; justify-content:center; background: rgba(0,0,0,0.4); z-index:120; opacity:0; pointer-events:none; transition:opacity .3s ease;
  }
  #specialModal.show{ opacity:1; pointer-events:auto; }
  #specialCard {
    width:calc(100% - 40px); max-width:680px; background:var(--card); border-radius:16px; padding:18px; text-align:center; box-shadow:0 30px 80px rgba(0,0,0,0.36);
  }
  #specialCard h2{ color:var(--pink-2); margin-bottom:8px; }
  #specialCard p{ color:var(--text); font-size:16px; line-height:1.5; }

  /* video box */
  .videoBox {
    margin-top:10px; width:100%; height:220px; border-radius:12px; overflow:hidden; background:#000; display:flex; align-items:center; justify-content:center;
  }
  .videoBox iframe, .videoBox video{ width:100%; height:100%; border:0; display:block; }

  /* petal parameters small screens fix */
  @media (max-width:420px){
    .photo{height:180px}
    .videoBox{height:160px}
  }

  /* accessibility: focus visible */
  button:focus{ outline:3px solid rgba(255,111,180,0.22); outline-offset:2px; }

</style>
</head>
<body>

<!-- CANVASES -->
<canvas id="fireworks"></canvas>
<canvas id="petals"></canvas>

<!-- MUSIC BUTTON -->
<button id="musicBtn" aria-label="Reproducir música">🎵</button>
<audio id="bgMusic" loop preload="auto">
  <!-- Puedes reemplazar con una URL propia -->
  <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_5f52fce66a.mp3" type="audio/mpeg">
</audio>

<div class="page">
  <div class="card" role="main" aria-labelledby="mainTitle">

    <!-- IZQUIERDA -->
    <div class="left">
      <div class="header">
        <div class="logo" aria-hidden="true">
          <!-- Imagen del título (icono/emoji). Cambia la URL por tu imagen -->
          <img src="https://cdn-icons-png.flaticon.com/512/833/833472.png" alt="corazon">
        </div>
        <div>
          <div class="title" id="mainTitle">Feliz cumpleaños, <span id="her-name">Sheyla</span> 🎉</div>
          <div class="subtitle">Este día es todo tuyo — te dedico mi corazón.</div>
        </div>
      </div>

      <div class="message-box" role="region" aria-label="Mensaje romántico">
        <!-- Efecto de escritura "Te amo..." ya incluido -->
        <div class="typed" id="typedText" aria-live="polite"></div>

        <div class="controls">
          <button class="btn" id="playTuneBtn">Reproducir melodía</button>
          <button class="btn ghost" id="confettiBtn">Fuegos artificiales</button>
          <button class="btn ghost" id="petalsBtn">Lluvia de pétalos</button>
          <button class="btn ghost" id="openLetterBtn">Abrir carta</button>
          <button class="btn ghost" id="darkToggleBtn" aria-pressed="false">Modo oscuro</button>
        </div>

        <!-- Carta 3D (se abre al hacer click en .envelope) -->
        <div class="letter-wrap">
          <div class="letter" id="letter">
            <div class="envelope" id="envelope" role="button" tabindex="0" aria-pressed="false" aria-label="Abrir carta">
              TO: <span style="margin-left:8px; font-weight:800;color:var(--text);">Mi princesa</span>
            </div>
            <div class="letter-body" id="letterBody">
              <p style="margin:0 0 8px 0; font-weight:700;">Mi amor,</p>
              <p style="margin:0 0 8px 0;">
                Hoy es tu día y quiero decirte cosas que a veces no digo: gracias por cada risa, por tu paciencia, por tu ternura.
                Eres la razón de mis mejores días. Te amo con todo lo que soy.
              </p>
              <p style="margin:0; font-weight:800; color:var(--pink);">— Tu enamorado</p>
            </div>
          </div>
        </div>

      </div>

      <!-- "Toca aquí" botón especial -->
      <div style="margin-top:14px;">
        <button class="btn" id="specialBtn">Toca aquí ❤️</button>
      </div>

      <!-- Video area -->
      <div style="margin-top:18px;">
        <div style="font-weight:800; margin-bottom:8px;">Video especial</div>
        <div class="videoBox" id="videoBox" role="region" aria-label="Video">
          <!-- Por defecto es un iframe de YouTube; reemplaza el src por tu video o usa una etiqueta <video> -->
          <iframe id="videoFrame" src="https://www.youtube.com/embed/2Vv-BfVoq4g?rel=0" title="Video" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>

    </div>

    <!-- DERECHA (sidebar) -->
    <aside class="side" aria-label="Detalles">
      <div class="photo" role="img" aria-label="Foto principal">
        <img id="mainPhoto" src="https://i.imgur.com/X0E2jMm.jpg" alt="Tu foto">
      </div>

      <div class="notes">
        <div class="note">💌 Feliz cumpleaños, mi princesa hermosa.</div>
        <div class="note">🌅 Tus ojos marrones brillan como el atardecer.</div>
        <div class="note">🎁 Pásalo lindo hoy; te lo mereces todo.</div>
      </div>

    </aside>

  </div>
</div>

<!-- SPECIAL MODAL -->
<div id="specialModal" role="dialog" aria-modal="true">
  <div id="specialCard">
    <h2>Para ti, mi vida</h2>
    <p id="specialText">Eres mi alegría diaria. Gracias por cada momento. ¿Quieres un abrazo ahora?</p>
    <div style="margin-top:12px;">
      <button class="btn" id="closeSpecial">Cerrar</button>
    </div>
  </div>
</div>

<!-- =========================
     SCRIPTS (JS)
========================= -->
<script>
/* -------------------------
   Variables iniciales
--------------------------*/
const herNameEl = document.getElementById('her-name');
const typedText = document.getElementById('typedText');
const playTuneBtn = document.getElementById('playTuneBtn');
const bgMusic = document.getElementById('bgMusic');
const musicBtn = document.getElementById('musicBtn');
const confettiBtn = document.getElementById('confettiBtn');
const petalsBtn = document.getElementById('petalsBtn');
const openLetterBtn = document.getElementById('openLetterBtn');
const envelope = document.getElementById('envelope');
const letterBody = document.getElementById('letterBody');
const letter = document.getElementById('letter');
const darkToggleBtn = document.getElementById('darkToggleBtn');

const specialBtn = document.getElementById('specialBtn');
const specialModal = document.getElementById('specialModal');
const closeSpecial = document.getElementById('closeSpecial');

const carouselTrack = document.getElementById('carouselTrack');
const prevBtn = document.getElementById('prevBtn');
const nextBtn = document.getElementById('nextBtn');

const fireworksCanvas = document.getElementById('fireworks');
const petalsCanvas = document.getElementById('petals');

let musicPlaying = false;

/* -------------------------
   Personalización rápida
   Cambia el nombre y el mensaje aquí
--------------------------*/
let herName = "Sheyla";
let typedMessage = "Hoy celebro que existes y cada momento que compartimos. Gracias por tu ternura, por tu risa y por los días que haces mejores. Te deseo lo mejor siempre. Te amo...";

/* Inicializar nombre visible */
herNameEl.textContent = herName;

/* -------------------------
   EFECTO DE ESCRITURA (loop)
--------------------------*/
function typeLoop(text, el, speed=35, pause=1200){
  let i = 0;
  let forward = true;
  function step(){
    if(forward){
      if(i < text.length){
        el.textContent += text.charAt(i);
        i++;
        setTimeout(step, speed);
      } else {
        forward = false;
        setTimeout(step, pause);
      }
    } else {
      // borrar lentamente
      if(i > 0){
        el.textContent = text.substring(0, i-1);
        i--;
        setTimeout(step, Math.max(12, speed/2));
      } else {
        forward = true;
        setTimeout(step, 400);
      }
    }
  }
  step();
}

typeLoop(typedMessage, typedText, 30, 1600);

/* -------------------------
   Musica de fondo (control)
--------------------------*/
musicBtn.addEventListener('click', ()=>{
  if(!musicPlaying){
    bgMusic.play().catch(()=>{ alert('Interacciona con la página para permitir sonido en tu navegador.'); });
    musicBtn.textContent = '⏸';
    musicPlaying = true;
  } else {
    bgMusic.pause();
    musicBtn.textContent = '🎵';
    musicPlaying = false;
  }
});

playTuneBtn.addEventListener('click', ()=>{
  // Play short melody using WebAudio (in-page), so user doesn't need external audio
  try {
    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const ctx = new AudioContext();
    const now = ctx.currentTime;
    const notes = [440, 523.25, 659.25, 880];
    const durs = [0.28,0.28,0.28,0.6];
    let t = now;
    for(let i=0;i<notes.length;i++){
      const o = ctx.createOscillator();
      const g = ctx.createGain();
      o.type = 'sine';
      o.frequency.value = notes[i];
      g.gain.value = 0.0001;
      o.connect(g); g.connect(ctx.destination);
      o.start(t);
      g.gain.exponentialRampToValueAtTime(0.12, t+0.02);
      g.gain.exponentialRampToValueAtTime(0.0001, t+durs[i]);
      o.stop(t + durs[i] + 0.02);
      t += durs[i];
    }
  } catch(e) {
    alert('No se pudo reproducir la melodía. Interactúa con la página antes (tap).');
  }
});

/* -------------------------
   FIREWORKS (canvas)
   - simple fireworks launch
--------------------------*/
(function(){
  const canvas = fireworksCanvas;
  const ctx = canvas.getContext('2d');
  let W, H;
  function resize(){ W = canvas.width = window.innerWidth; H = canvas.height = window.innerHeight; }
  window.addEventListener('resize', resize); resize();

  let rockets = [], particles = [];

  function rand(min,max){ return Math.random()*(max-min)+min; }

  function Rocket(){
    this.x = rand(W*0.2, W*0.8);
    this.y = H + rand(10,50);
    this.vx = rand(-1.5,1.5);
    this.vy = rand(-7,-4);
    this.explodeY = rand(H*0.25, H*0.5);
    this.color = `hsl(${Math.floor(rand(320,360))},90%,60%)`;
  }
  Rocket.prototype.update = function(){
    this.x += this.vx; this.y += this.vy; this.vy += 0.12;
    if(this.y <= this.explodeY){
      // explode
      for(let i=0;i<30;i++){
        particles.push(new Particle(this.x, this.y, this.color));
      }
      return false;
    }
    return true;
  };

  function Particle(x,y,color){
    this.x=x; this.y=y;
    const ang = rand(0,Math.PI*2);
    const sp = rand(1,6);
    this.vx = Math.cos(ang)*sp;
    this.vy = Math.sin(ang)*sp;
    this.alpha = 1;
    this.dec = rand(0.008,0.02);
    this.color = color;
  }
  Particle.prototype.update = function(){
    this.x += this.vx; this.y += this.vy; this.vy += 0.06; this.alpha -= this.dec;
    return this.alpha > 0;
  };

  let running = false;
  function render(){
    ctx.clearRect(0,0,W,H);
    // draw particles
    for(let i=particles.length-1;i>=0;i--){
      const p = particles[i];
      if(!p.update()) particles.splice(i,1);
      else{
        ctx.globalAlpha = Math.max(0,p.alpha);
        ctx.fillStyle = p.color;
        ctx.fillRect(p.x, p.y, 2, 2);
      }
    }
    // rockets
    for(let i=rockets.length-1;i>=0;i--){
      const r = rockets[i];
      if(!r.update()) rockets.splice(i,1);
      else{
        ctx.globalAlpha = 1;
        ctx.fillStyle = r.color;
        ctx.fillRect(r.x, r.y, 3, 6);
      }
    }
    if(running) requestAnimationFrame(render);
  }

  function launchBurst(){
    for(let i=0;i<3;i++) rockets.push(new Rocket());
    if(!running){ running = true; render(); setTimeout(()=>{ running=false; }, 4200); }
  }

  confettiBtn.addEventListener('click', launchBurst);
  // also launch fireworks on big click (double)
  document.addEventListener('dblclick', launchBurst);

})();

/* -------------------------
   PETALS (canvas) - falling petals
--------------------------*/
(function(){
  const canvas = petalsCanvas;
  const ctx = canvas.getContext('2d');
  let W,H;
  function resize(){ W = canvas.width = window.innerWidth; H = canvas.height = window.innerHeight; }
  window.addEventListener('resize', resize); resize();

  const petals = [];
  function Petal(){
    this.x = Math.random()*W;
    this.y = -10 - Math.random()*H;
    this.size = 8 + Math.random()*18;
    this.vx = (Math.random()-0.5)*0.8;
    this.vy = 1 + Math.random()*2;
    this.rot = Math.random()*Math.PI*2;
    this.rotSpeed = (Math.random()-0.5)*0.04;
    this.color = `rgba(255,${160+Math.floor(Math.random()*60)},${200+Math.floor(Math.random()*40)},0.95)`;
  }
  Petal.prototype.update = function(){
    this.x += this.vx;
    this.y += this.vy;
    this.rot += this.rotSpeed;
    if(this.y > H+50) { this.y = -20; this.x = Math.random()*W; }
  };

  let anim=false;
  function drawPetals(){
    ctx.clearRect(0,0,W,H);
    for(let i=0;i<petals.length;i++){
      const p = petals[i];
      p.update();
      ctx.save();
      ctx.translate(p.x,p.y);
      ctx.rotate(p.rot);
      ctx.fillStyle = p.color;
      ctx.beginPath();
      ctx.ellipse(0,0,p.size, p.size*0.6, 0, 0, Math.PI*2);
      ctx.fill();
      ctx.restore();
    }
    if(anim) requestAnimationFrame(drawPetals);
  }

  function startPetals(){
    if(petals.length===0){
      for(let i=0;i<80;i++) petals.push(new Petal());
    }
    if(!anim){ anim=true; drawPetals(); setTimeout(()=>{ anim=false; }, 8000); }
  }

  petalsBtn.addEventListener('click', startPetals);
})();

/* -------------------------
   LETTER open animation (3D)
--------------------------*/
openLetterBtn.addEventListener('click', ()=> toggleEnvelope());
envelope.addEventListener('click', ()=> toggleEnvelope());
envelope.addEventListener('keydown', (e)=>{ if(e.key==='Enter' || e.key===' ') toggleEnvelope(); });

function toggleEnvelope(){
  const isOpen = envelope.classList.contains('open');
  if(!isOpen){
    envelope.classList.add('open');
    envelope.setAttribute('aria-pressed','true');
    setTimeout(()=>{ letterBody.classList.add('show'); }, 700);
  } else {
    envelope.classList.remove('open');
    envelope.setAttribute('aria-pressed','false');
    letterBody.classList.remove('show');
  }
}

/* -------------------------
   DARK MODE toggle
--------------------------*/
darkToggleBtn.addEventListener('click', ()=>{
  const isDark = document.body.classList.toggle('dark');
  darkToggleBtn.setAttribute('aria-pressed', String(isDark));
  darkToggleBtn.textContent = isDark ? 'Modo claro' : 'Modo oscuro';
});

/* -------------------------
   Special modal "Toca aquí"
--------------------------*/
specialBtn.addEventListener('click', ()=>{
  specialModal.classList.add('show');
  // set focus for accessibility
  document.getElementById('closeSpecial').focus();
});
closeSpecial.addEventListener('click', ()=>{ specialModal.classList.remove('show'); });

specialModal.addEventListener('click', (e)=>{ if(e.target===specialModal) specialModal.classList.remove('show'); });

/* -------------------------
   Carousel simple
--------------------------*/
let currentIndex = 0;
const items = Array.from(document.querySelectorAll('.carousel-item'));
const total = items.length;
function updateCarousel(){
  const offset = -currentIndex * 100;
  carouselTrack.style.transform = `translateX(${offset}%)`;
}
prevBtn.addEventListener('click', ()=>{ currentIndex = (currentIndex-1+total)%total; updateCarousel(); });
nextBtn.addEventListener('click', ()=>{ currentIndex = (currentIndex+1)%total; updateCarousel(); });

let carouselAuto = setInterval(()=>{ currentIndex = (currentIndex+1)%total; updateCarousel(); }, 4000);
/* Pause on hover/touch */
document.getElementById('carousel').addEventListener('mouseenter', ()=>clearInterval(carouselAuto));
document.getElementById('carousel').addEventListener('mouseleave', ()=>{ carouselAuto = setInterval(()=>{ currentIndex = (currentIndex+1)%total; updateCarousel(); }, 4000); });

/* -------------------------
   Touch / Click hearts (touch friendly)
--------------------------*/
function spawnHeart(x,y){
  const h = document.createElement('div');
  h.className = 'touch-heart';
  h.style.left = (x-9) + 'px';
  h.style.top = (y-9) + 'px';
  document.body.appendChild(h);
  h.animate([
    { transform:'translateY(0) scale(1) rotate(-45deg)', opacity:1 },
    { transform:'translateY(-60px) scale(1.3) rotate(-45deg)', opacity:0 }
  ], { duration:700, easing:'ease-out' });
  setTimeout(()=> { h.remove(); }, 800);
}

['click','touchstart'].forEach(ev=>{
  document.addEventListener(ev, (e)=>{
    let x = (e.touches && e.touches[0]) ? e.touches[0].pageX : e.pageX;
    let y = (e.touches && e.touches[0]) ? e.touches[0].pageY : e.pageY;
    spawnHeart(x,y);
  }, {passive:true});
});

/* -------------------------
   Fireworks auto occasional (small show)
--------------------------*/
setInterval(()=>{
  // small automatic bursts (but not too often)
  // simulate user clicking confettiBtn every ~20-40s at random chance
  if(Math.random() < 0.06) document.getElementById('confettiBtn').click();
}, 3000);

/* -------------------------
   Accessibility: keyboard shortcuts
--------------------------*/
document.addEventListener('keydown', (e)=>{
  if(e.key === 'f') document.getElementById('confettiBtn').click();
  if(e.key === 'm') musicBtn.click();
  if(e.key === 'l') envelope.click();
});

/* -------------------------
   Small polish: prevent accidental selection
--------------------------*/
document.onselectstart = ()=>false;

</script>

</body>
</html>
