<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Valentine Protocol 💘</title>
  <style>
    :root{
      --bg1:#0b0b14;
      --bg2:#1a0b25;
      --card: rgba(255,255,255,.08);
      --stroke: rgba(255,255,255,.14);
      --text: rgba(255,255,255,.92);
      --muted: rgba(255,255,255,.72);
      --hot:#ff3b7a;
      --hot2:#ffb3cc;
      --ok:#2ef2a5;
      --shadow: 0 30px 80px rgba(0,0,0,.45);
      --r: 22px;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      min-height:100vh;
      display:grid;
      place-items:center;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Arial;
      background:
        radial-gradient(1200px 700px at 20% 10%, rgba(255,59,122,.35), transparent 60%),
        radial-gradient(900px 600px at 90% 40%, rgba(46,242,165,.18), transparent 55%),
        radial-gradient(900px 700px at 60% 90%, rgba(255,179,204,.18), transparent 60%),
        linear-gradient(160deg, var(--bg1), var(--bg2));
      color: var(--text);
      overflow:hidden;
    }
    .noise{
      position:fixed; inset:0;
      background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='160' height='160'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='160' height='160' filter='url(%23n)' opacity='.25'/%3E%3C/svg%3E");
      opacity:.07;
      pointer-events:none;
      mix-blend-mode:overlay;
    }
    .wrap{
      width:min(860px, calc(100vw - 32px));
      display:grid;
      gap:16px;
      grid-template-columns: 1.15fr .85fr;
      align-items:stretch;
    }
    @media (max-width: 860px){
      .wrap{ grid-template-columns:1fr; }
    }
    .card{
      background: var(--card);
      border:1px solid var(--stroke);
      border-radius: var(--r);
      box-shadow: var(--shadow);
      backdrop-filter: blur(12px);
      padding: 22px;
      position:relative;
      overflow:hidden;
    }
    .badge{
      display:inline-flex;
      gap:10px;
      align-items:center;
      padding:8px 12px;
      border:1px solid rgba(255,255,255,.16);
      border-radius:999px;
      color:var(--muted);
      font-weight:650;
      font-size:12px;
      letter-spacing:.08em;
      text-transform:uppercase;
    }
    .pulse{
      width:8px; height:8px; border-radius:50%;
      background: var(--hot);
      box-shadow: 0 0 0 0 rgba(255,59,122,.6);
      animation: ping 1.6s infinite;
    }
    @keyframes ping{
      0%{ box-shadow: 0 0 0 0 rgba(255,59,122,.55); }
      70%{ box-shadow: 0 0 0 12px rgba(255,59,122,0); }
      100%{ box-shadow: 0 0 0 0 rgba(255,59,122,0); }
    }

    h1{
      margin:14px 0 8px;
      font-size: clamp(28px, 4.6vw, 46px);
      letter-spacing:-0.03em;
      line-height:1.05;
    }
    .sub{
      margin:0 0 18px;
      color:var(--muted);
      font-size: 15px;
      line-height:1.55;
    }
    .type{
      font-weight:750;
      color: rgba(255,255,255,.96);
      text-shadow: 0 10px 30px rgba(255,59,122,.22);
    }
    .caret{
      display:inline-block;
      width:10px;
      animation: blink 1s steps(1) infinite;
      color: var(--hot2);
    }
    @keyframes blink{ 50%{opacity:0} }

    .btnRow{
      display:flex;
      gap:12px;
      flex-wrap:wrap;
      align-items:center;
      margin-top: 16px;
    }
    button{
      border:0;
      border-radius: 14px;
      padding: 14px 16px;
      font-weight: 850;
      font-size: 16px;
      cursor:pointer;
      color:white;
      transition: transform .08s ease, filter .15s ease;
      user-select:none;
      -webkit-tap-highlight-color: transparent;
    }
    button:active{ transform: translateY(1px) scale(.99); }
    .yes{
      background: linear-gradient(135deg, var(--hot), #ff6aa0);
      box-shadow: 0 14px 40px rgba(255,59,122,.25);
      transition: transform .3s ease, filter .15s ease, font-size .3s ease;
    }
    .yes:hover{ filter: brightness(1.05); }
    .no{
      background: rgba(255,255,255,.10);
      border:1px solid rgba(255,255,255,.18);
      color: rgba(255,255,255,.90);
      transition: transform .08s ease, filter .15s ease, background .3s ease;
    }
    .no:hover{ filter: brightness(1.1); }
    
    @keyframes shake{
      0%, 100%{ transform: translateX(0); }
      25%{ transform: translateX(-8px) rotate(-5deg); }
      75%{ transform: translateX(8px) rotate(5deg); }
    }
    
    @keyframes shrinkGrow{
      0%, 100%{ transform: scale(1); }
      50%{ transform: scale(0.85); }
    }
    
    .no.shaking{ animation: shake 0.4s ease; }
    .no.shrinking{ animation: shrinkGrow 0.5s ease; }

    .sideTitle{
      font-size: 14px;
      letter-spacing:.12em;
      text-transform:uppercase;
      color: rgba(255,255,255,.70);
      font-weight:800;
      margin: 2px 0 10px;
    }
    .panel{
      display:grid;
      gap:12px;
    }
    .mini{
      background: rgba(255,255,255,.06);
      border:1px solid rgba(255,255,255,.12);
      border-radius: 18px;
      padding: 14px;
    }
    .mini b{ color: rgba(255,255,255,.94); }
    .pillRow{
      display:flex;
      flex-wrap:wrap;
      gap:10px;
      margin-top:10px;
    }
    .pill{
      border-radius:999px;
      padding:10px 12px;
      background: rgba(255,255,255,.08);
      border:1px solid rgba(255,255,255,.12);
      color: rgba(255,255,255,.86);
      font-weight:750;
      font-size: 13px;
      cursor:pointer;
      user-select:none;
      transition: transform .08s ease, background .15s ease;
    }
    .pill:active{ transform: scale(.99); }
    .pill.active{
      background: rgba(255,59,122,.22);
      border-color: rgba(255,59,122,.35);
    }

    .receipt{
      margin-top:12px;
      padding:14px;
      border-radius:18px;
      background: rgba(0,0,0,.26);
      border:1px dashed rgba(255,255,255,.22);
      font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
      color: rgba(255,255,255,.88);
      display:none;
      white-space: pre-wrap;
    }

    /* Floating hearts */
    canvas#fx{ position:fixed; inset:0; pointer-events:none; z-index:1; }
    .wrap, .card{ z-index:2; }

    /* Confetti */
    .confetti{
      position:fixed; inset:0; pointer-events:none; z-index:60;
    }

    /* Love letter modal */
    .modal{
      position:fixed; inset:0;
      background: rgba(0,0,0,.55);
      display:none;
      place-items:center;
      z-index:70;
      padding:18px;
    }
    .modal .sheet{
      width:min(520px, calc(100vw - 28px));
      background: rgba(255,255,255,.10);
      border:1px solid rgba(255,255,255,.18);
      border-radius: 24px;
      padding: 18px;
      box-shadow: var(--shadow);
      backdrop-filter: blur(12px);
      position:relative;
      overflow:hidden;
    }
    .modal h2{ margin: 6px 0 6px; font-size: 26px; letter-spacing:-0.02em; }
    .modal p{ margin:0; color: var(--muted); line-height:1.55; }
    .x{
      position:absolute; top:12px; right:12px;
      width:38px; height:38px; border-radius:12px;
      border:1px solid rgba(255,255,255,.16);
      background: rgba(255,255,255,.08);
      color:white;
      font-weight:900;
      cursor:pointer;
    }
  </style>
</head>
<body>
  <div class="noise"></div>
  <canvas id="fx"></canvas>

  <div class="wrap">
    <div class="card" id="mainCard">
      <div class="badge"><span class="pulse"></span> CELL SIGNALING PROTOCOL</div>

      <h1>
        <span id="type" class="type"></span><span class="caret">▍</span>
      </h1>

      <p class="sub" id="subtitle">
        I've been wanting to ask you this for a while now… 🫶
      </p>

      <div class="btnRow">
        <button class="yes" id="yesBtn">YES ✅</button>
        <button class="no" id="noBtn">No 🙃</button>
      </div>

      <div class="receipt" id="receipt"></div>
    </div>

    <div class="card">
      <div class="sideTitle">If you say yes…</div>
      <div class="panel">
        <div class="mini">
          <b>Pick the vibe</b>
          <div class="pillRow" id="vibes">
            <div class="pill active" data-v="Dinner somewhere nice 🍰">Dinner somewhere nice 🍰</div>
            <div class="pill" data-v="Coffee & walk ☕️">Coffee & walk ☕️</div>
            <div class="pill" data-v="Movie + snacks 🎬">Movie + snacks 🎬</div>
            <div class="pill" data-v="Surprise me 🚗">Surprise me 🚗</div>
          </div>
        </div>

        <div class="mini">
          <b>Pick the time</b>
          <div class="pillRow" id="times">
            <div class="pill active" data-t="This weekend ✨">This weekend ✨</div>
            <div class="pill" data-t="Whenever works 😌">Whenever works 😌</div>
            <div class="pill" data-t="Valentine's Day 💘">Valentine's Day 💘</div>
          </div>
        </div>

        <div class="mini">
          <b>Bonus perk</b><br/>
          Saying "Yes" grants: <span style="color:var(--ok); font-weight:900;">Unregulated dopamine signaling</span> (side effect: can't stop smiling).
        </div>
      </div>
    </div>
  </div>

  <canvas class="confetti" id="confetti"></canvas>

  <div class="modal" id="modal">
    <div class="sheet">
      <button class="x" id="close">✕</button>
      <div class="badge" style="margin-bottom:10px;"><span class="pulse"></span> POSITIVE RESULTS</div>
      <h2>Okay… I'm smiling like an idiot 💖</h2>
      <p id="letter">
        I'm so happy you said yes. Honestly wasn't sure if you'd feel the same way, 
        but I'm really glad you do. You're like the wildtype to my mutation—you just make everything right. 
        Pick whatever sounds fun and I'll make it happen. Can't wait. 😊
      </p>
      <div style="margin-top:14px; display:flex; gap:10px; flex-wrap:wrap;">
        <button class="yes" id="copyBtn">Copy confirmation</button>
        <button class="no" id="againBtn">Replay animation</button>
      </div>
    </div>
  </div>

  <script>
    // ---------- Typewriter ----------
    const lines = [
      "Will you be my valentine? 💘",
      "This took more courage than p53 fighting mutations… 😊",
      "My feelings are proliferating uncontrollably ✨"
    ];
    const typeEl = document.getElementById("type");
    const subtitle = document.getElementById("subtitle");
    let li = 0, ci = 0, deleting = false;

    function typeLoop(){
      const current = lines[li];
      if(!deleting){
        typeEl.textContent = current.slice(0, ci++);
        if(ci > current.length + 18){
          deleting = true;
        }
      }else{
        typeEl.textContent = current.slice(0, ci--);
        if(ci <= 0){
          deleting = false;
          li = (li + 1) % lines.length;
          ci = 0;
        }
      }
      setTimeout(typeLoop, deleting ? 26 : 44);
    }
    typeLoop();

    // ---------- Vibe/time selection ----------
    function setupPills(containerId, cls){
      const box = document.getElementById(containerId);
      box.addEventListener("click", (e) => {
        const pill = e.target.closest(".pill");
        if(!pill) return;
        [...box.querySelectorAll(".pill")].forEach(p => p.classList.remove("active"));
        pill.classList.add("active");
      });
    }
    setupPills("vibes");
    setupPills("times");

    function getActiveText(containerId, attr){
      const box = document.getElementById(containerId);
      const active = box.querySelector(".pill.active");
      return active?.getAttribute(attr) || "";
    }

    // ---------- No button fun stuff ----------
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const receipt = document.getElementById("receipt");

    const noPhrases = [
      "No 🙃",
      "Wait, really? 🤔",
      "Give me another chance? 💭",
      "Come onnn 😊",
      "I promise it'll be fun! 🥺",
      "Pretty please? 🥹",
      "You're killing me here 💔",
      "Okay but hear me out… 😅",
      "Just click YES, trust me 😌"
    ];
    
    const noColors = [
      "rgba(255,255,255,.10)",
      "rgba(255,100,100,.15)",
      "rgba(255,150,50,.15)",
      "rgba(150,100,255,.15)",
      "rgba(100,150,255,.15)"
    ];
    
    let noClickCount = 0;
    let yesFontSize = 16;

    noBtn.addEventListener("click", (e) => {
      e.preventDefault();
      noClickCount++;
      
      // Shake the No button
      noBtn.classList.add("shaking");
      setTimeout(() => noBtn.classList.remove("shaking"), 400);
      
      // Change No button text
      const phraseIndex = Math.min(noClickCount - 1, noPhrases.length - 1);
      noBtn.textContent = noPhrases[phraseIndex];
      
      // Change No button color randomly
      const colorIndex = Math.floor(Math.random() * noColors.length);
      noBtn.style.background = noColors[colorIndex];
      
      // Grow the Yes button progressively
      yesFontSize += 3;
      yesBtn.style.fontSize = yesFontSize + "px";
      yesBtn.style.transform = `scale(${1 + (noClickCount * 0.08)})`;
      
      // Add shrinking animation to No button
      noBtn.classList.add("shrinking");
      setTimeout(() => noBtn.classList.remove("shrinking"), 500);
      
      // Spawn hearts around the No button
      sparkleHearts(5);
      
      // Show increasingly desperate subtitle messages
      const messages = [
        "I've been wanting to ask you this for a while now… 🫶",
        "The No button looks apoptotic… maybe try the other one? 💘",
        "My feelings have metastasized straight to my heart ✨",
        "The Yes button is growing like benign cells (in a good way) 💖",
        "Unlike cancer cells, I have healthy boundaries… but I really like you 🎯",
        "This isn't chemotherapy—no pressure, but… say yes? 😌",
        "You're the CRISPR to my genome… you just make everything better ⭐",
        "Let's be each other's targeted therapy 💕"
      ];
      
      if(noClickCount <= messages.length) {
        subtitle.textContent = messages[Math.min(noClickCount, messages.length - 1)];
      }
      
      // After many clicks, make No button almost disappear
      if(noClickCount >= 7) {
        noBtn.style.opacity = Math.max(0.3, 1 - (noClickCount - 6) * 0.15);
        noBtn.style.transform = `scale(${Math.max(0.6, 1 - (noClickCount - 6) * 0.08)})`;
      }
    });
    
    // Hover effect - make Yes button pulse
    noBtn.addEventListener("mouseenter", () => {
      yesBtn.style.filter = "brightness(1.15) drop-shadow(0 0 20px rgba(255,59,122,.6))";
    });
    
    noBtn.addEventListener("mouseleave", () => {
      yesBtn.style.filter = "";
    });

    // ---------- YES behavior ----------
    yesBtn.addEventListener("click", () => {
      const vibe = getActiveText("vibes","data-v");
      const time = getActiveText("times","data-t");

      subtitle.textContent = "Access granted. Valentine protocol accepted. ✅";

      receipt.style.display = "block";
      receipt.textContent =
`— VALENTINE CONFIRMATION RECEIPT —
Status: APPROVED ✅
Vibe:   ${vibe}
Time:   ${time}

Perk:   Unregulated dopamine signaling
Note:   You're the cure I've been researching 💖`;

      // Disable the No button
      noBtn.disabled = true;
      noBtn.style.opacity = "0.3";
      noBtn.style.cursor = "not-allowed";
      noBtn.textContent = "Too late! 😊";

      blastConfetti();
      openModal();
    });

    // ---------- Modal ----------
    const modal = document.getElementById("modal");
    const close = document.getElementById("close");
    const againBtn = document.getElementById("againBtn");
    const copyBtn = document.getElementById("copyBtn");

    function openModal(){ modal.style.display = "grid"; }
    function closeModal(){ modal.style.display = "none"; }

    close.addEventListener("click", closeModal);
    modal.addEventListener("click", (e) => { if(e.target === modal) closeModal(); });

    againBtn.addEventListener("click", () => {
      blastConfetti();
      sparkleHearts(18);
    });

    copyBtn.addEventListener("click", async () => {
      try{
        await navigator.clipboard.writeText(receipt.textContent);
        copyBtn.textContent = "Copied ✅";
        setTimeout(()=> copyBtn.textContent="Copy confirmation", 1100);
      }catch{
        copyBtn.textContent = "Copy failed";
        setTimeout(()=> copyBtn.textContent="Copy confirmation", 1100);
      }
    });

    // ---------- Floating hearts background ----------
    const fx = document.getElementById("fx");
    const fctx = fx.getContext("2d");
    let W=0, H=0, DPR=1;
    let hearts = [];

    function resizeFx(){
      DPR = devicePixelRatio || 1;
      W = window.innerWidth; H = window.innerHeight;
      fx.width = Math.floor(W * DPR);
      fx.height = Math.floor(H * DPR);
      fctx.setTransform(DPR,0,0,DPR,0,0);
    }
    window.addEventListener("resize", resizeFx);
    resizeFx();

    function makeHeart(){
      return {
        x: Math.random()*W,
        y: H + Math.random()*200,
        s: 10 + Math.random()*18,
        vy: 0.8 + Math.random()*2.2,
        vx: -0.35 + Math.random()*0.7,
        a: 0.35 + Math.random()*0.55,
        r: Math.random()*Math.PI,
        spin: (-0.012 + Math.random()*0.024)
      };
    }
    for(let i=0;i<26;i++) hearts.push(makeHeart());

    function drawHeart(x,y,size,rot,alpha){
      fctx.save();
      fctx.translate(x,y);
      fctx.rotate(rot);
      fctx.globalAlpha = alpha;
      fctx.beginPath();
      const s = size/16;
      fctx.moveTo(0,0);
      fctx.bezierCurveTo(-16*s,-14*s,-18*s, 6*s,0,16*s);
      fctx.bezierCurveTo( 18*s, 6*s, 16*s,-14*s,0,0);
      fctx.fillStyle = "#ff3b7a";
      fctx.fill();
      fctx.restore();
    }

    function fxLoop(){
      fctx.clearRect(0,0,W,H);
      hearts.forEach(h=>{
        h.x += h.vx;
        h.y -= h.vy;
        h.r += h.spin;

        drawHeart(h.x,h.y,h.s,h.r,h.a);

        if(h.y < -60 || h.x < -60 || h.x > W+60){
          Object.assign(h, makeHeart());
        }
      });
      requestAnimationFrame(fxLoop);
    }
    fxLoop();

    function sparkleHearts(n=12){
      for(let i=0;i<n;i++){
        hearts.push({
          x: W*0.5 + (Math.random()-0.5)*180,
          y: H*0.55 + (Math.random()-0.5)*120,
          s: 16 + Math.random()*22,
          vy: 1.6 + Math.random()*2.4,
          vx: -1.1 + Math.random()*2.2,
          a: 0.75 + Math.random()*0.25,
          r: Math.random()*Math.PI,
          spin:(-0.03 + Math.random()*0.06)
        });
      }
      // keep it bounded
      if(hearts.length > 90) hearts.splice(0, hearts.length-90);
    }

    // ---------- Confetti ----------
    const conf = document.getElementById("confetti");
    const cctx = conf.getContext("2d");
    let confetti = [];
    let cW=0,cH=0,cDPR=1;
    function resizeConf(){
      cDPR = devicePixelRatio || 1;
      cW = window.innerWidth; cH = window.innerHeight;
      conf.width = Math.floor(cW*cDPR);
      conf.height = Math.floor(cH*cDPR);
      cctx.setTransform(cDPR,0,0,cDPR,0,0);
    }
    window.addEventListener("resize", resizeConf);
    resizeConf();

    function blastConfetti(){
      // no custom colors specified—just random HSL
      const count = 160;
      for(let i=0;i<count;i++){
        confetti.push({
          x: cW/2,
          y: cH/2,
          vx: (Math.random()-0.5)*10,
          vy: (Math.random()-0.9)*10,
          g: 0.18 + Math.random()*0.18,
          r: Math.random()*Math.PI,
          vr: (Math.random()-0.5)*0.25,
          s: 4 + Math.random()*6,
          life: 120 + Math.random()*40,
          hue: Math.random()*360
        });
      }
      sparkleHearts(22);
      confLoop();
    }

    let confRunning=false;
    function confLoop(){
      if(confRunning) return;
      confRunning = true;

      function step(){
        cctx.clearRect(0,0,cW,cH);
        confetti = confetti.filter(p=>p.life>0);
        confetti.forEach(p=>{
          p.life -= 1;
          p.vy += p.g;
          p.x += p.vx;
          p.y += p.vy;
          p.r += p.vr;

          cctx.save();
          cctx.translate(p.x,p.y);
          cctx.rotate(p.r);
          cctx.fillStyle = `hsla(${p.hue}, 90%, 65%, .9)`;
          cctx.fillRect(-p.s/2,-p.s/2,p.s,p.s*0.8);
          cctx.restore();
        });

        if(confetti.length){
          requestAnimationFrame(step);
        }else{
          confRunning=false;
          cctx.clearRect(0,0,cW,cH);
        }
      }
      requestAnimationFrame(step);
    }
  </script>
</body>
</html>
