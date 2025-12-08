<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Happy Birthday ♡</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Inter:wght@300;400;500;600&family=Press+Start+2P&family=VT323&display=swap" rel="stylesheet" />

  <style>
    :root {
      --bg: #fdf8f5;
      --bg-alt: #f9f0ea;
      --accent: #f4b8c5;
      --accent-soft: rgba(244, 184, 197, 0.16);
      --text-main: #2b2220;
      --text-muted: #8a7470;
      --card-bg: #ffffff;
      --border-soft: #f0ddd4;
      --shadow-soft: 0 18px 45px rgba(0, 0, 0, 0.06);
      --radius-lg: 24px;
      --radius-pill: 999px;
      --transition: 220ms ease;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: "Inter", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      background: radial-gradient(circle at top left, #ffe9f0 0, #fdf8f5 35%, #fefefe 70%);
      color: var(--text-main);
      line-height: 1.7;
      -webkit-font-smoothing: antialiased;
    }

    main { max-width: 960px; margin: 0 auto; padding: 24px 16px 64px; }
    @media (min-width: 768px) { main { padding: 40px 24px 96px; } }

    /* LANDING (first screen) */
    .landing {
      min-height: 86vh;
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      text-align: center; gap: 18px;
    }
    .landing .hero-pill {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 8px 18px; border-radius: var(--radius-pill);
      background: var(--accent-soft);
      border: 1px solid rgba(244, 184, 197, 0.25);
      font-size: 0.85rem; color: var(--text-muted);
    }
    .pixel-title {
      font-family: "Press Start 2P", system-ui, monospace;
      font-size: clamp(1.2rem, 3.4vw, 2.1rem);
      line-height: 1.35;
      letter-spacing: 0.02em;
      text-transform: none;
    }
    .pixel-sub {
      font-family: "VT323", monospace;
      font-size: clamp(1.1rem, 3vw, 1.6rem);
      color: var(--text-muted);
    }
    .evo-gif {
      width: min(360px, 80vw);
      aspect-ratio: 1 / 1;
      object-fit: cover;
      border-radius: 22px;
      box-shadow: var(--shadow-soft);
      border: 1px solid var(--border-soft);
      display: block;
      margin: 6px auto 2px;
    }
    .start-btn {
      border: 1px solid var(--border-soft);
      background: #ffffff;
      padding: 12px 18px;
      border-radius: 12px;
      cursor: pointer;
      font-weight: 700;
      box-shadow: var(--shadow-soft);
      transition: transform var(--transition), box-shadow var(--transition), background var(--transition);
      font-family: "Press Start 2P", monospace;
      font-size: 0.78rem;
    }
    .start-btn:active { transform: translateY(1px); }
    .start-row { display: flex; gap: 12px; align-items: center; justify-content: center; margin-top: 6px; }

    /* STORY CARD PAGES */
    .section { padding: 24px 0; }
    .card {
      background: var(--card-bg);
      border-radius: var(--radius-lg);
      padding: 24px 20px;
      box-shadow: var(--shadow-soft);
      border: 1px solid var(--border-soft);
      max-width: 720px; margin: 0 auto;
      position: relative; overflow: hidden;
      opacity: 0; transform: translateY(8px);
      transition: opacity 260ms var(--transition), transform 260ms var(--transition);
    }
    .card.show { opacity: 1; transform: translateY(0); }
    .card::before {
      content: ""; position: absolute; inset: 0;
      background: radial-gradient(circle at top right, rgba(244,184,197,0.14), transparent 55%);
      pointer-events: none;
    }
    .card-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 12px; gap: 12px; }
    .card-tag {
      font-size: 0.78rem; padding: 4px 10px; border-radius: var(--radius-pill);
      background: rgba(244,184,197,0.09); border: 1px dashed rgba(244,184,197,0.6); color: var(--text-muted);
    }
    .card-page { font-size: 0.78rem; color: var(--text-muted); }
    .card h2 { font-family: "Playfair Display", serif; font-size: 1.25rem; margin-bottom: 10px; }
    .card p + p { margin-top: 10px; }
    .chips { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 6px; font-size: 0.8rem; }
    .chip { padding: 4px 9px; border-radius: var(--radius-pill); background: #fff; border: 1px solid #f0ddd4; color: var(--text-muted); }
    .muted { color: var(--text-muted); font-size: 0.9rem; }
    .center-note { text-align: center; margin-top: 10px; font-size: 0.9rem; color: var(--text-muted); }
    .divider { max-width: 72px; height: 1px; background: linear-gradient(to right, transparent, var(--border-soft), transparent); margin: 26px auto; }

    /* NAV */
    .nav { display: flex; align-items: center; justify-content: space-between; gap: 12px; max-width: 720px; margin: 16px auto 0; }
    .btn {
      border: 1px solid var(--border-soft); background: #fff; padding: 10px 16px; border-radius: 12px;
      cursor: pointer; font-weight: 500; transition: transform var(--transition), box-shadow var(--transition);
      box-shadow: var(--shadow-soft);
    }
    .btn[disabled] { opacity: 0.45; cursor: not-allowed; }
    .btn:active { transform: translateY(1px); }
    .progress { flex: 1; text-align: center; color: var(--text-muted); font-size: 0.92rem; }

    /* CERTIFICATE (Page 6) */
    .portfolio-header { text-align: center; margin-bottom: 20px; }
    .portfolio-header h2 { font-family: "Playfair Display", serif; font-size: 1.6rem; margin-bottom: 4px; }
    .portfolio-header p { font-size: 0.95rem; color: var(--text-muted); }
    .certificate {
      background: linear-gradient(135deg, #ffffff, #fdf4f6);
      border-radius: 26px; border: 1px solid rgba(219,188,178,0.7);
      padding: 24px 18px; box-shadow: var(--shadow-soft);
      max-width: 760px; margin: 0 auto;
    }
    .certificate-header { text-align: center; margin-bottom: 18px; }
    .certificate-title { font-family: "Playfair Display", serif; font-size: 1.4rem; letter-spacing: 0.06em; text-transform: uppercase; }
    .certificate-subtitle { font-size: 0.9rem; color: var(--text-muted); margin-top: 4px; }
    .certificate-meta { display: grid; grid-template-columns: 1fr 1fr; gap: 8px 16px; font-size: 0.9rem; margin-bottom: 16px; }
    .certificate-meta span { color: var(--text-muted); }
    .certificate-meta strong { color: var(--text-main); }
    @media (max-width: 600px) { .certificate-meta { grid-template-columns: 1fr; } }

    table { width: 100%; border-collapse: collapse; margin-top: 8px; font-size: 0.9rem; }
    thead { background: rgba(244,184,197,0.14); }
    th, td { padding: 8px 6px; text-align: left; border-bottom: 1px solid #f0ded8; }
    th { font-weight: 600; font-size: 0.85rem; text-transform: uppercase; letter-spacing: 0.04em; color: var(--text-muted); }
    .total-row td { border-top: 1px solid #e2c6bc; font-weight: 600; }

    /* Confetti GIF overlay (optional; requires confetti.gif in repo) */
    .confetti-overlay {
      position: fixed; inset: 0; background: url('confetti.gif') center/cover no-repeat;
      pointer-events: none; animation: confettiFade 2.2s ease-out forwards; z-index: 9999; display: none;
    }
    @keyframes confettiFade { 0%{opacity:0} 10%{opacity:1} 100%{opacity:0} }

    /* visibility toggles */
    #storySection { display: none; }
  </style>
</head>
<body>

<!-- Optional GIF overlay -->
<div class="confetti-overlay" id="gifConfetti" aria-hidden="true"></div>

<main>
  <!-- LANDING SCREEN -->
  <section class="landing" id="landing">
    <div class="hero-pill">🌙 softly dedicated to <strong>My Favourite Person</strong></div>

    <!-- Your Untitled design.gif -->
    <img src="Untitled design.gif" alt="His evolution phases" class="evo-gif" />

    <!-- Pixelated headline -->
    <h1 class="pixel-title">Happy 25th Birthday Baby Teo</h1>

    <!-- Pixelated subheading -->
    <div class="pixel-sub">Are you ready for this gift that I’ve prepared for you?</div>

    <!-- Start button -->
    <div class="start-row">
      <button class="start-btn" id="startBtn">Start ▶</button>
    </div>
  </section>

  <!-- STORY SECTION (hidden until Start) -->
  <section class="section" id="storySection">
    <article class="card show" id="card">
      <div class="card-header">
        <div class="card-tag" id="pageTag">Page 1 · The Start</div>
        <div class="card-page" id="pageCounter">1 / 6</div>
      </div>
      <div id="pageBody"></div>
    </article>

    <div class="nav">
      <button class="btn" id="prevBtn" disabled>← Back</button>
      <div class="progress" id="progressText">Page 1 of 6</div>
      <button class="btn" id="nextBtn">Next →</button>
    </div>
  </section>
</main>

<!-- Confetti (JS) -->
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
<script>
  // ---------- PAGE DATA ----------
  const PAGES = [
    {
      tag: "Page 1 · The Start",
      count: "1 / 6",
      html: `
        <h2>The million options that didn’t feel like you</h2>
        <p>I’ve thought of a million things to get you, but nothing really hit. Nothing felt right. Nothing felt like <strong>you</strong>.</p>
        <p>So instead of buying something random, I decided to make something that actually matches who you are — slow, intentional, growing over time.</p>
        <p class="center-note">When you’re ready, tap <em>Next</em>. The surprise is just getting started.</p>
      `
    },
    {
      tag: "Page 2 · Quarter Life",
      count: "2 / 6",
      html: `
        <h2>Twenty–five &amp; the so-called crisis</h2>
        <p>They say 25 is when your quarter-life crisis begins. But when I look at you, I don’t see a crisis at all.</p>
        <p>I see someone building a life with intention, courage, and so much heart. Someone who doesn’t rush, but thinks long-term.</p>
        <p>And yes… I also secretly want this to be the start of your little piggy bank — so that one day, I can retire early and live my dream as your stay-at-home girlfriend 😌</p>
        <p class="center-note">Tap <em>Next</em> whenever you’re ready to continue.</p>
      `
    },
    {
      tag: "Page 3 · Who You Are",
      count: "3 / 6",
      html: `
        <h2>The things I admire in you</h2>
        <p>You carry so much value in who you are, not because of what you have, but because of what you’re made of:</p>
        <ul class="chips">
          <li class="chip">Genuine</li>
          <li class="chip">Not following the norm</li>
          <li class="chip">Grounded</li>
          <li class="chip">Caring</li>
        </ul>
        <p>These aren’t trends. They’re your fundamentals.</p>
        <p>I hope these parts of you keep compounding every day, the same way you’ve grown into the person I love now.</p>
      `
    },
    {
      tag: "Page 4 · The Quiet Days",
      count: "4 / 6",
      html: `
        <h2>For the days that feel heavy</h2>
        <p>I know some days are hard. Some days you just want to do nothing and not be responsible for anything at all.</p>
        <p>And that’s okay.</p>
        <p>Even on those days, your kindness still shows. Your heart still shows. Your presence still matters.</p>
        <p>You’re allowed to rest. You’re allowed to pause. You’re still you — and you are still worth investing in, even on your lowest days.</p>
      `
    },
    {
      tag: "Page 5 · 25 Years of You",
      count: "5 / 6",
      html: `
        <h2>The glow &amp; the growth</h2>
        <p>Thinking back on your journey to 25, I know it wasn’t always steady.</p>
        <p>Sometimes you were rejected. Sometimes you failed. Sometimes things just didn’t go how you hoped.</p>
        <p>But looking at you now, you’ve glowed and grown in the best way possible.</p>
        <p class="skincare-note">(Next time can apply skincare also? I’ll help you — your personal skincare ETF manager 🧴)</p>
        <p>You’ve become someone stronger, softer, and wiser over time. And this birthday present is something I feel truly reflects who you are.</p>
        <p class="center-note">Hit <em>Next</em>. This is where it all comes together.</p>
      `
    },
    {
      tag: "Page 6 · Your Birthday Present",
      count: "6 / 6",
      html: `
        <div class="portfolio-header">
          <h2>A portfolio that grows with you</h2>
          <p>Not just something to use once and forget, but something that grows quietly in the background — the same way you’ve been growing, year after year.</p>
        </div>

        <article class="certificate">
          <div class="certificate-header">
            <div class="certificate-title">Portfolio Gift Certificate</div>
            <div class="certificate-subtitle">A small start to your compounding future (&amp; my stay-at-home girlfriend agenda).</div>
          </div>

          <div class="certificate-meta">
            <div><span>Presented to</span><br /><strong>Derrick Teo Chen Wei</strong></div>
            <div><span>From</span><br /><strong>Yu Yuen Choong</strong></div>
            <div><span>Occasion</span><br /><strong>25th Birthday</strong></div>
            <div><span>Date</span><br /><strong>11th December 2025</strong></div>
          </div>

          <table>
            <thead>
              <tr><th>Investment</th><th>Ticker</th><th>Amount</th><th>Why this?</th></tr>
            </thead>
            <tbody>
              <tr><td>U.S. Market (S&amp;P 500)</td><td>VOO</td><td>$____</td><td>Steady long-term growth, like your consistency.</td></tr>
              <tr><td>Tech Growth (Nasdaq 100)</td><td>QQQ</td><td>$____</td><td>Your curious, future-focused brain in ETF form.</td></tr>
              <tr><td>Gold / Hedge</td><td>—</td><td>$____</td><td>Stability when life (or the markets) feel uncertain.</td></tr>
              <tr><td>Extra / Tech Stock</td><td>—</td><td>$____</td><td>A fun, higher-upside piece that feels like your playful, bold side.</td></tr>
              <tr class="total-row"><td colspan="2"><strong>Total Portfolio Value</strong></td><td colspan="2">$________</td></tr>
            </tbody>
          </table>

          <div class="certificate-footer" style="margin-top:12px;">
            <p>This isn’t just money. It’s a quiet reminder that:</p>
            <p style="margin-top:6px;">Your future matters. Your values are solid. You are someone worth investing in.</p>
            <p style="margin-top:6px;">No matter where life takes you, I hope this reminds you that I believe in your future, your choices, and the life you’re building.</p>

            <div class="signature" style="margin-top:14px;">
              <div class="sig-block">
                <div class="sig-line">Signature</div>
                <div class="muted">From me, with way too much love.</div>
              </div>
              <div class="sig-block">
                <div class="sig-line">For</div>
                <div class="muted">The birthday boy &amp; future millionaire. 💛📈</div>
              </div>
            </div>
          </div>
        </article>
      `
    }
  ];

  // ---------- DOM ----------
  const landing = document.getElementById('landing');
  const storySection = document.getElementById('storySection');
  const startBtn = document.getElementById('startBtn');

  const card = document.getElementById('card');
  const pageTag = document.getElementById('pageTag');
  const pageCounter = document.getElementById('pageCounter');
  const pageBody = document.getElementById('pageBody');
  const prevBtn = document.getElementById('prevBtn');
  const nextBtn = document.getElementById('nextBtn');
  const progressText = document.getElementById('progressText');
  const gifConfetti = document.getElementById('gifConfetti');

  let i = 0;

  function render(idx) {
    const p = PAGES[idx];
    pageTag.textContent = p.tag;
    pageCounter.textContent = p.count;
    pageBody.innerHTML = p.html;
    progressText.textContent = `Page ${idx + 1} of ${PAGES.length}`;

    prevBtn.disabled = idx === 0;
    nextBtn.textContent = idx === PAGES.length - 1 ? 'Finish' : 'Next →';

    card.classList.remove('show');
    requestAnimationFrame(() => requestAnimationFrame(() => card.classList.add('show')));

    if (idx === PAGES.length - 1) {
      fireConfetti(1200, true);
      if (gifConfetti) {
        gifConfetti.style.display = 'block';
        setTimeout(() => { gifConfetti.style.display = 'none'; }, 2200);
      }
    }
  }

  function next() { if (i < PAGES.length - 1) { i++; render(i); } }
  function prev() { if (i > 0) { i--; render(i); } }

  prevBtn.addEventListener('click', prev);
  nextBtn.addEventListener('click', () => {
    if (i === PAGES.length - 1) { i = 0; } else { i++; }
    render(i);
  });

  // Start button: hide landing, show story, confetti, render first page
  startBtn.addEventListener('click', () => {
    landing.style.display = 'none';
    storySection.style.display = 'block';
    render(0);
    fireConfetti(900, false);
    storySection.scrollIntoView({ behavior: 'smooth' });
  });

  // Keyboard nav after start
  window.addEventListener('keydown', (e) => {
    if (storySection.style.display !== 'block') return;
    if (e.key === 'ArrowRight') next();
    if (e.key === 'ArrowLeft') prev();
  });

  // ---------- Confetti helper ----------
  function fireConfetti(durationMs = 1200, big = false) {
    const end = Date.now() + durationMs;
    (function frame() {
      confetti({
        particleCount: big ? 8 : 4,
        angle: 60, spread: big ? 75 : 55, scalar: big ? 1.1 : 1,
        origin: { x: 0 }
      });
      confetti({
        particleCount: big ? 8 : 4,
        angle: 120, spread: big ? 75 : 55, scalar: big ? 1.1 : 1,
        origin: { x: 1 }
      });
      if (Date.now() < end) requestAnimationFrame(frame);
    })();
  }
</script>
</body>
</html>
