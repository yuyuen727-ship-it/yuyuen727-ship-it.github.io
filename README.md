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
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      gap: 18px;
    }

    .landing .hero-pill {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 18px;
      border-radius: var(--radius-pill);
      background: var(--accent-soft);
      border: 1px solid rgba(244, 184, 197, 0.25);
      font-size: 0.85rem;
      color: var(--text-muted);
    }

    .pixel-title {
      font-family: "Press Start 2P", system-ui, monospace;
      font-size: clamp(1.2rem, 3.4vw, 2.1rem);
      line-height: 1.35;
      letter-spacing: 0.02em;
    }

    .pixel-sub {
      font-family: "VT323", monospace;
      font-size: clamp(1.1rem, 3vw, 1.6rem);
      color: var(--text-muted);
    }

    /* floating transparent image */
    .evo-gif {
      width: min(360px, 80vw);
      height: auto;
      display: block;
      margin: 24px auto 6px;
      border: none;
      box-shadow: none;
      background: transparent;
      border-radius: 0;
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

    /* CERTIFICATE (Page 5) */
    .portfolio-header { text-align: center; margin-bottom: 20px; }
    .portfolio-header h2 { font-family: "Playfair Display", serif; font-size: 1.6rem; margin-bottom: 4px; }
    .portfolio-header p { font-size: 0.95rem; color: var(--text-muted); }
    .certificate {
      background: linear-gradient(135deg, #ffffff, #fdf4f6);
      border-radius: 26px; border: 1px solid rgba(219,188,178,0.7);
      padding: 24px 18px; box-shadow: var(--shadow-soft);
      max-width: 760px; margin: 14px auto 0;
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

    /* Pinterest-style resources grid (Page 6) */
    .resources-grid {
      margin-top: 16px;
      display: grid;
      gap: 12px;
    }
    @media (min-width: 640px) {
      .resources-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
    }
    @media (min-width: 900px) {
      .resources-grid {
        grid-template-columns: repeat(3, minmax(0, 1fr));
      }
    }
    .resource-card {
      background: #ffffff;
      border-radius: 18px;
      border: 1px solid #f0ddd4;
      box-shadow: var(--shadow-soft);
      padding: 14px 14px 16px;
      text-align: left;
    }
    .resource-tag {
      display: inline-block;
      font-size: 0.74rem;
      padding: 3px 9px;
      border-radius: 999px;
      background: rgba(244,184,197,0.14);
      border: 1px solid rgba(244,184,197,0.4);
      color: var(--text-muted);
      margin-bottom: 6px;
    }
    .resource-card h3 {
      font-size: 0.98rem;
      margin-bottom: 4px;
      font-weight: 600;
    }
    .resource-card p {
      font-size: 0.88rem;
      color: var(--text-muted);
    }

    /* Accordion (Page 6) */
    .accordion {
      margin-top: 22px;
      border-radius: 18px;
      border: 1px solid #f0ddd4;
      background: #ffffff;
      overflow: hidden;
      box-shadow: var(--shadow-soft);
    }
    .accordion-item + .accordion-item {
      border-top: 1px solid #f0ddd4;
    }
    .accordion-header {
      width: 100%;
      padding: 10px 16px;
      background: transparent;
      border: none;
      display: flex;
      align-items: center;
      justify-content: space-between;
      cursor: pointer;
      font-size: 0.9rem;
      text-align: left;
    }
    .accordion-header span:first-child {
      color: var(--text-main);
      font-weight: 500;
    }
    .accordion-icon {
      font-size: 1rem;
      transition: transform 160ms ease;
    }
    .accordion-panel {
      max-height: 0;
      overflow: hidden;
      padding: 0 16px;
      transition: max-height 220ms ease, padding 220ms ease;
    }
    .accordion-panel ul {
      list-style: disc;
      padding-left: 18px;
      margin: 6px 0 10px;
    }
    .accordion-panel li {
      font-size: 0.88rem;
      color: var(--text-muted);
      margin-bottom: 3px;
    }
    .accordion-panel a {
      color: inherit;
      text-decoration: underline;
      text-decoration-thickness: 1px;
    }
    .accordion-item.open .accordion-panel {
      max-height: 320px;
      padding: 8px 16px 12px;
    }
    .accordion-item.open .accordion-icon {
      transform: rotate(45deg);
    }

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
    <div class="hero-pill">
      🌙 softly dedicated to <strong>My Favourite Person</strong>
    </div>

    <!-- evolution image (replace filename if needed) -->
    <img src="BackgroundDFace.png" alt="His evolution phases" class="evo-gif" />

    <h1 class="pixel-title">Happy 25th Birthday Baby Teo</h1>

    <div class="pixel-sub">
      Are you ready to receive your birthday present?
    </div>

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
        <h2>Happy Birthday, Baby Teo</h2>
        <p>You’re finally turning 25. I hope you like this gift I prepared for you (with a tiny bit of help from your bestie too 🫢).</p>
        <p>It’s something that relates to what you’re doing now, reflects your personality, and hopefully becomes something that grows over time, just like you.</p>
        <p>25 is such a confusing age. People expect us to suddenly be financially independent, but no one really teaches us how. There’s a lot of trial and error, a lot of learning on the go, and maybe even a little bit of feeling lost as you try to figure out your direction in life… or start pampering your girlfriend (aka me 😌).</p>
        <p class="center-note">Tap <em>Next</em> when you’re ready. The surprise is just beginning.</p>
      `
    },
    {
      tag: "Page 2 · Quarter Life",
      count: "2 / 6",
      html: `
        <h2>Twenty–five and the so-called crisis</h2>
        <p>Being 25 also means you now have all the “adult money” to buy whatever you want, including every Ben 10 watch you didn’t get to have as a kid 🤭.</p>
        <p>But beyond the jokes, I want you to know something. When I look at you, I don’t see someone struggling through a quarter-life crisis.</p>
        <p>I see someone building a life with intention, courage, and so much heart. Someone who moves with purpose. Someone who takes their time to think about the long run, even when the present feels messy.</p>
        <p>And that’s something I admire deeply in you.</p>
      `
    },
    {
      tag: "Page 3 · Who You Are",
      count: "3 / 6",
      html: `
        <h2>The things I admire in you</h2>
        <p>These are the things I love most about you, not because of what you have, but because of what you’re made of:</p>
        <ul class="chips">
          <li class="chip">Genuine</li>
          <li class="chip">Not following the norm</li>
          <li class="chip">Grounded</li>
          <li class="chip">Caring</li>
          <li class="chip">Guailan</li>
        </ul>
        <p>These characteristics aren’t temporary phases. They are your foundations, the traits that make you, <strong>you</strong>.</p>
        <p>I hope these parts of you continue to grow and compound every day, the same way you’ve become the person I love now.</p>
      `
    },
    {
      tag: "Page 4 · The Quiet Days",
      count: "4 / 6",
      html: `
        <h2>For the days that feel heavy</h2>
        <p>25 isn’t just another birthday. It’s a milestone, a chance to pause and look at how far you’ve come.</p>
        <p>Your journey wasn’t always smooth. There were moments where things didn’t go your way, times where you felt rejected, unsure, or disappointed.</p>
        <p>But each of those moments shaped you. And looking at you today, you’ve grown and glowed in the best possible way.</p>
        <p>You’re becoming someone stronger, softer, and wiser, and someone I’m genuinely proud of.</p>
        <p>As you move forward, I hope you learn to be gentle with yourself, to lean on the people who make you feel safe, and to allow yourself to create spaces where you feel supported and understood.</p>
      `
    },
    {
      tag: "Page 5 · Your Birthday Present",
      count: "5 / 6",
      html: `
        <h2>Your birthday present</h2>
        <p>Your birthday present today is something that reflects who you are as a person.</p>
        <p>(Yes, just like your birthday cake, the character development is real 🍰✨)</p>

        <article class="certificate">
          <div class="certificate-header">
            <div class="certificate-title">Portfolio Gift Certificate</div>
            <div class="certificate-subtitle">A small start to your compounding future (and my stay-at-home girlfriend agenda).</div>
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
        </article>

        <p style="margin-top:14px;">This gift grows quietly in the background, the same way you have.</p>
        <p>Life isn’t always stable, just like the stock market. When things feel shaky, you don’t panic; you pause, analyse your choices, check your heart, and stay grounded.</p>
        <p>You don’t make decisions based on temporary circumstances.</p>
        <p>And I don’t ever want you to treat investing, or your life, like a gamble. It’s not about luck. It’s about learning, trusting, studying, and believing in long-term value.</p>
        <p>Even when things dip, if you understand the foundation, the growth plan, and the potential, you don’t walk away.</p>
        <p>Because stability doesn’t come from the market. It comes from <strong>you</strong>.</p>
      `
    },
    {
      tag: "Page 6 · Your Next Steps",
      count: "6 / 6",
      html: `
        <h2>Your next steps</h2>
        <p>Here’s a small head start. I’ve gathered a few places and ideas for you to explore, learn, and track the things you’re curious about. Think of this as your mini resource board.</p>

        <div class="resources-grid">
          <article class="resource-card">
            <div class="resource-tag">News</div>
            <h3>Market &amp; ETF updates</h3>
            <p>Pick one or two reliable sources to check in with regularly so you’re aware of what’s happening in the world and in the markets.</p>
          </article>

          <article class="resource-card">
            <div class="resource-tag">Learning</div>
            <h3>Beginner-friendly explainers</h3>
            <p>Short videos, blog posts, or threads that break down concepts like ETFs, diversification, and compounding in simple language.</p>
          </article>

          <article class="resource-card">
            <div class="resource-tag">Mindset</div>
            <h3>Long-term investing brain</h3>
            <p>Content that reminds you to zoom out, focus on the big picture, and stay grounded when things feel noisy.</p>
          </article>
        </div>

        <div class="accordion">
          <div class="accordion-item">
            <button class="accordion-header">
              <span>Beginner-friendly investing guides</span>
              <span class="accordion-icon">＋</span>
            </button>
            <div class="accordion-panel">
              <ul>
                <li><a href="https://example.com/guide-1" target="_blank" rel="noopener">Guide 1 (replace this with your own link)</a></li>
                <li><a href="https://example.com/guide-2" target="_blank" rel="noopener">Guide 2 (replace this with your own link)</a></li>
              </ul>
            </div>
          </div>

          <div class="accordion-item">
            <button class="accordion-header">
              <span>ETF &amp; stock research</span>
              <span class="accordion-icon">＋</span>
            </button>
            <div class="accordion-panel">
              <ul>
                <li><a href="https://example.com/etf-research" target="_blank" rel="noopener">ETF screener / factsheets</a></li>
                <li><a href="https://example.com/stock-research" target="_blank" rel="noopener">Stock research or analysis site</a></li>
              </ul>
            </div>
          </div>

          <div class="accordion-item">
            <button class="accordion-header">
              <span>Videos, podcasts, and notes from me</span>
              <span class="accordion-icon">＋</span>
            </button>
            <div class="accordion-panel">
              <ul>
                <li><a href="https://example.com/video" target="_blank" rel="noopener">A video I think you’ll like</a></li>
                <li><a href="https://example.com/notes" target="_blank" rel="noopener">My own notes or a PDF I’ve saved for you</a></li>
              </ul>
            </div>
          </div>
        </div>

        <p class="center-note" style="margin-top:18px;">
          PS: Even Moomoo wants to celebrate you. Don’t forget to claim all your free cash vouchers and stocks before they expire tomorrow 😌
        </p>
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

    setupAccordion();

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
    if (i === PAGES.length - 1) {
      i = 0;
    } else {
      i++;
    }
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

  // Accordion setup (Page 6)
  function setupAccordion() {
    const items = pageBody.querySelectorAll('.accordion-item');
    if (!items.length) return;
    items.forEach(item => {
      const header = item.querySelector('.accordion-header');
      const panel = item.querySelector('.accordion-panel');
      if (!header || !panel) return;
      header.onclick = () => {
        const isOpen = item.classList.contains('open');
        items.forEach(i => i.classList.remove('open'));
        if (!isOpen) item.classList.add('open');
      };
    });
  }

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
