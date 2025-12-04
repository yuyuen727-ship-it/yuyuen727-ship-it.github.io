<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Happy Birthday ♡</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <!-- Optional Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />

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

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: "Inter", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      background: radial-gradient(circle at top left, #ffe9f0 0, #fdf8f5 35%, #fefefe 70%);
      color: var(--text-main);
      line-height: 1.7;
      -webkit-font-smoothing: antialiased;
    }

    main {
      max-width: 960px;
      margin: 0 auto;
      padding: 24px 16px 64px;
    }

    @media (min-width: 768px) {
      main {
        padding: 40px 24px 96px;
      }
    }

    .hero {
      min-height: 80vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      gap: 24px;
    }

    .hero-pill {
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

    .hero-title {
      font-family: "Playfair Display", serif;
      font-size: clamp(2.1rem, 4vw, 2.9rem);
      letter-spacing: 0.03em;
    }

    .hero-subtitle {
      max-width: 480px;
      margin: 0 auto;
      font-size: 0.98rem;
      color: var(--text-muted);
    }

    .scroll-indicator {
      margin-top: 12px;
      display: inline-flex;
      flex-direction: column;
      align-items: center;
      gap: 4px;
      font-size: 0.9rem;
      color: var(--text-muted);
      cursor: pointer;
      text-decoration: none;
    }

    .scroll-indicator span {
      font-size: 1.4rem;
      animation: bounce 1.2s infinite;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(4px); }
    }

    .section {
      padding: 32px 0;
      scroll-margin-top: 80px;
    }

    .card {
      background: var(--card-bg);
      border-radius: var(--radius-lg);
      padding: 24px 20px;
      box-shadow: var(--shadow-soft);
      border: 1px solid var(--border-soft);
      max-width: 720px;
      margin: 0 auto;
      position: relative;
      overflow: hidden;
    }

    .card::before {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at top right, rgba(244, 184, 197, 0.14), transparent 55%);
      pointer-events: none;
    }

    .card-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 12px;
      gap: 12px;
    }

    .card-tag {
      font-size: 0.78rem;
      padding: 4px 10px;
      border-radius: var(--radius-pill);
      background: rgba(244, 184, 197, 0.09);
      border: 1px dashed rgba(244, 184, 197, 0.6);
      color: var(--text-muted);
    }

    .card-page {
      font-size: 0.78rem;
      color: var(--text-muted);
    }

    .card h2 {
      font-family: "Playfair Display", serif;
      font-size: 1.25rem;
      margin-bottom: 10px;
    }

    .card p + p {
      margin-top: 10px;
    }

    .muted {
      color: var(--text-muted);
      font-size: 0.9rem;
    }

    .skincare-note {
      font-size: 0.9rem;
      margin-top: 8px;
      color: var(--text-muted);
    }

    .center-note {
      text-align: center;
      margin-top: 10px;
      font-size: 0.9rem;
      color: var(--text-muted);
    }

    .divider {
      max-width: 72px;
      height: 1px;
      background: linear-gradient(to right, transparent, var(--border-soft), transparent);
      margin: 26px auto;
    }

    .portfolio-section {
      padding-top: 40px;
    }

    .portfolio-header {
      text-align: center;
      margin-bottom: 20px;
    }

    .portfolio-header h2 {
      font-family: "Playfair Display", serif;
      font-size: 1.6rem;
      margin-bottom: 4px;
    }

    .portfolio-header p {
      font-size: 0.95rem;
      color: var(--text-muted);
    }

    .certificate {
      background: linear-gradient(135deg, #ffffff, #fdf4f6);
      border-radius: 26px;
      border: 1px solid rgba(219, 188, 178, 0.7);
      padding: 24px 18px;
      box-shadow: var(--shadow-soft);
      max-width: 760px;
      margin: 0 auto;
    }

    .certificate-header {
      text-align: center;
      margin-bottom: 18px;
    }

    .certificate-title {
      font-family: "Playfair Display", serif;
      font-size: 1.4rem;
      letter-spacing: 0.06em;
      text-transform: uppercase;
    }

    .certificate-subtitle {
      font-size: 0.9rem;
      color: var(--text-muted);
      margin-top: 4px;
    }

    .certificate-meta {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 8px 16px;
      font-size: 0.9rem;
      margin-bottom: 16px;
    }

    .certificate-meta span {
      color: var(--text-muted);
    }

    .certificate-meta strong {
      color: var(--text-main);
    }

    @media (max-width: 600px) {
      .certificate-meta {
        grid-template-columns: 1fr;
      }
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 8px;
      font-size: 0.9rem;
    }

    table thead {
      background: rgba(244, 184, 197, 0.14);
    }

    table th, table td {
      padding: 8px 6px;
      text-align: left;
      border-bottom: 1px solid #f0ded8;
    }

    table th {
      font-weight: 600;
      font-size: 0.85rem;
      text-transform: uppercase;
      letter-spacing: 0.04em;
      color: var(--text-muted);
    }

    .total-row td {
      border-top: 1px solid #e2c6bc;
      font-weight: 600;
    }

    .certificate-footer {
      margin-top: 16px;
      font-size: 0.9rem;
      color: var(--text-muted);
    }

    .signature {
      margin-top: 18px;
      display: flex;
      justify-content: space-between;
      gap: 16px;
      font-size: 0.9rem;
      flex-wrap: wrap;
    }

    .sig-line {
      border-top: 1px solid #d9b9b0;
      margin-top: 22px;
      padding-top: 4px;
      min-width: 160px;
    }

    .chips {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 6px;
      font-size: 0.8rem;
    }

    .chip {
      padding: 4px 9px;
      border-radius: var(--radius-pill);
      background: #fff;
      border: 1px solid #f0ddd4;
      color: var(--text-muted);
    }

    a {
      color: inherit;
    }
  </style>
</head>
<body>

<main>
  <!-- HERO -->
  <section class="hero">
    <div class="hero-pill">
      🌙 softly dedicated to
      <strong><!-- His name here --> Your Favourite Person</strong>
    </div>
    <h1 class="hero-title">Happy Birthday to my favourite person</h1>
    <p class="hero-subtitle">
      A little scroll, a little chaos, and a birthday present that grows with you every year.
    </p>
    <a href="#page1" class="scroll-indicator">
      <div>scroll to begin</div>
      <span>↓</span>
    </a>
  </section>

  <!-- PAGE 1 -->
  <section class="section" id="page1">
    <article class="card">
      <div class="card-header">
        <div class="card-tag">Page 1 · The Start</div>
        <div class="card-page">1 / 6</div>
      </div>
      <h2>The million options that didn't feel like you</h2>
      <p>
        I’ve thought of a million things to get you, but nothing really hit. Nothing felt right. Nothing felt like <strong>you</strong>.
      </p>
      <p>
        So I decided to make something that does.
      </p>
      <p class="center-note">Keep scrolling. The surprise is building. ↓</p>
    </article>
  </section>

  <div class="divider"></div>

  <!-- PAGE 2 -->
  <section class="section" id="page2">
    <article class="card">
      <div class="card-header">
        <div class="card-tag">Page 2 · Quarter Life</div>
        <div class="card-page">2 / 6</div>
      </div>
      <h2>Twenty–five &amp; the so-called crisis</h2>
      <p>
        They say 25 is when your quarter-life crisis begins. But when I look at you, I don’t see a crisis at all.
      </p>
      <p>
        I see someone building a life with intention, courage, and so much heart.
      </p>
      <p>
        And yes, I also want this to be the start of your little <em>piggy bank</em>—
        so that one day, I can live my dream as a stay-at-home girlfriend�
      </p>
      <p class="center-note">Scroll, the story’s not done yet. ↓</p>
    </article>
  </section>

  <div class="divider"></div>

  <!-- PAGE 3 -->
  <section class="section" id="page3">
    <article class="card">
      <div class="card-header">
        <div class="card-tag">Page 3 · Who You Are</div>
        <div class="card-page">3 / 6</div>
      </div>
      <h2>The things I admire in you</h2>
      <p>
        You carry so much value in who you are, not because of what you have, but because of what you’re made of:
      </p>
      <ul class="chips">
        <li class="chip">Genuine</li>
        <li class="chip">Not following the norm</li>
        <li class="chip">Grounded</li>
        <li class="chip">Caring</li>
      </ul>
      <p>
        These are all things I truly admire about you.
      </p>
      <p>
        I hope all these values continue to grow every single day, the same way you’ve grown into the person I love now.
      </p>
    </article>
  </section>

  <div class="divider"></div>

  <!-- PAGE 4 -->
  <section class="section" id="page4">
    <article class="card">
      <div class="card-header">
        <div class="card-tag">Page 4 · The Quiet Days</div>
        <div class="card-page">4 / 6</div>
      </div>
      <h2>For the days that feel heavy</h2>
      <p>
        I know some days are hard. Some days you just want to do absolutely nothing and not be responsible for anything at all.
      </p>
      <p>
        And that’s okay.
      </p>
      <p>
        Even in those moments, your kindness and your heart still show through. You’re allowed to rest. You’re allowed to pause. You’re still you.
      </p>
    </article>
  </section>

  <div class="divider"></div>

  <!-- PAGE 5 -->
  <section class="section" id="page5">
    <article class="card">
      <div class="card-header">
        <div class="card-tag">Page 5 · 25 Years of You</div>
        <div class="card-page">5 / 6</div>
      </div>
      <h2>The glow &amp; the growth</h2>
      <p>
        Reflecting back on the past 25 years, I’m not sure what kind of person you were then. But from the stories you’ve told me and the way you look now, you’ve definitely glowed in the best way possible.
      </p>
      <p class="skincare-note">
        (Maybe next time can apply skincare also? I’ll help you hahah 🧴)
      </p>
      <p>
        I’m sure your journey to 25 hasn’t always been steady. Sometimes you faced rejections. Sometimes you failed. Sometimes things just didn’t go the way you hoped.
      </p>
      <p>
        But looking back now, you glow &amp; you grow each year.
      </p>
      <p>
        And this birthday present is something that I feel truly reflects who you are as a person.
      </p>
      <p class="center-note">One more scroll. This is where it all comes together. ↓</p>
    </article>
  </section>

  <div class="divider"></div>

  <!-- PAGE 6 · PORTFOLIO -->
  <section class="section portfolio-section" id="page6">
    <div class="portfolio-header">
      <h2>Your birthday present</h2>
      <p>A portfolio that grows with you, the way you’ve grown into you.</p>
    </div>

    <article class="certificate">
      <div class="certificate-header">
        <div class="certificate-title">Portfolio Gift Certificate</div>
        <div class="certificate-subtitle">
          A small start to your compounding future (&amp; my stay-at-home girlfriend agenda).
        </div>
      </div>

      <div class="certificate-meta">
        <div>
          <span>Presented to</span><br />
          <strong><!-- His name --> Derrick Teo Chen Wei</strong>
        </div>
        <div>
          <span>From</span><br />
          <strong><!-- Your name --> Yu Yuen Choong</strong>
        </div>
        <div>
          <span>Occasion</span><br />
          <strong>25th Birthday</strong>
        </div>
        <div>
          <span>Date</span><br />
          <strong><!-- e.g. 03 December 2025 --> 11th December 2025</strong>
        </div>
      </div>

      <table>
        <thead>
          <tr>
            <th>Investment</th>
            <th>Ticker</th>
            <th>Amount</th>
            <th>Why this?</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>U.S. Market (S&amp;P 500)</td>
            <td>VOO</td>
            <td>$____</td>
            <td>Steady long-term growth, like your consistency.</td>
          </tr>
          <tr>
            <td>Tech Growth (Nasdaq 100)</td>
            <td>QQQ</td>
            <td>$____</td>
            <td>Your curious, future-focused brain in ETF form.</td>
          </tr>
          <tr>
            <td>Gold / Hedge</td>
            <td><!-- e.g. GLD --></td>
            <td>$____</td>
            <td>Stability when life feels uncertain.</td>
          </tr>
          <tr>
            <td>Extra / Tech Stock</td>
            <td><!-- e.g. AAPL / NVDA --></td>
            <td>$____</td>
            <td>A fun, high-upside piece that feels like you.</td>
          </tr>
          <tr class="total-row">
            <td colspan="2"><strong>Total Portfolio Value</strong></td>
            <td colspan="2">$________</td>
          </tr>
        </tbody>
      </table>

      <div class="certificate-footer">
        <p>
          This isn’t just money. It’s the start of something that grows quietly in the background,
          the way you’ve been growing as a person—year after year.
        </p>
        <p style="margin-top: 6px;">
          No matter where life takes you, I hope this reminds you that I believe in your future, your choices,
          and the life you’re building.
        </p>

        <div class="signature">
          <div class="sig-block">
            <div class="sig-line">Signature</div>
            <div class="muted">From me, with way too much love</div>
          </div>
          <div class="sig-block">
            <div class="sig-line">For</div>
            <div class="muted">The birthday boy &amp; future millionaire</div>
          </div>
        </div>
      </div>
    </article>
  </section>
</main>

</body>
</html>
