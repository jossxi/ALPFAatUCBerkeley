[index.html](https://github.com/user-attachments/files/27311342/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>ALPFA at UC Berkeley</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400;1,600&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --blue: #003262;
    --blue-deep: #001f3f;
    --gold: #C4820A;
    --gold-light: #e8a822;
    --cream: #faf8f4;
    --warm-gray: #f0ece4;
    --border: #e5e0d6;
    --text: #1a1612;
    --muted: #6b6560;
    --font-display: 'Cormorant Garamond', Georgia, serif;
    --font-body: 'DM Sans', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--font-body);
    background: #fff;
    color: var(--text);
    line-height: 1.75;
    -webkit-font-smoothing: antialiased;
  }

  /* ── NAV ── */
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.1rem 3rem;
    border-bottom: 1px solid var(--border);
    background: rgba(255,255,255,0.95);
    backdrop-filter: blur(8px);
    position: sticky;
    top: 0;
    z-index: 100;
  }
  .nav-brand {
    display: flex;
    align-items: center;
    gap: 10px;
    text-decoration: none;
  }
  .nav-badge {
    width: 34px; height: 34px;
    border-radius: 50%;
    background: var(--blue);
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
  }
  .nav-badge svg { width: 16px; height: 16px; fill: none; stroke: var(--gold); stroke-width: 1.8; stroke-linecap: round; stroke-linejoin: round; }
  .nav-logo {
    font-family: var(--font-body);
    font-weight: 600;
    font-size: 0.92rem;
    color: var(--blue);
    letter-spacing: 0.06em;
  }
  .nav-logo span { color: var(--gold); }
  nav ul {
    list-style: none;
    display: flex;
    gap: 2.5rem;
  }
  nav ul a {
    text-decoration: none;
    font-size: 0.75rem;
    color: var(--muted);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    font-weight: 500;
    transition: color 0.2s;
  }
  nav ul a:hover { color: var(--gold); }
  .nav-cta {
    background: var(--blue);
    color: #fff !important;
    padding: 0.45rem 1.1rem;
    border-radius: 2px;
    transition: background 0.2s !important;
  }
  .nav-cta:hover { background: var(--gold) !important; color: #fff !important; }

  /* ── HERO ── */
  .hero {
    background: var(--blue);
    padding: 7rem 3rem 6rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .hero-pattern {
    position: absolute; inset: 0;
    background-image:
      repeating-linear-gradient(0deg, transparent, transparent 59px, rgba(196,130,10,0.07) 59px, rgba(196,130,10,0.07) 60px),
      repeating-linear-gradient(90deg, transparent, transparent 59px, rgba(196,130,10,0.07) 59px, rgba(196,130,10,0.07) 60px);
    pointer-events: none;
  }
  .hero-inner { position: relative; z-index: 1; }
  .hero-kicker {
    display: inline-flex;
    align-items: center;
    gap: 0.6rem;
    font-size: 0.68rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    border: 1px solid rgba(196,130,10,0.35);
    padding: 0.35rem 1rem;
    margin-bottom: 2rem;
    font-weight: 500;
  }
  .hero-kicker::before,
  .hero-kicker::after {
    content: '';
    display: block;
    width: 16px; height: 1px;
    background: var(--gold);
    opacity: 0.5;
  }
  .hero h1 {
    font-family: var(--font-display);
    font-size: clamp(2.8rem, 6vw, 4.5rem);
    font-weight: 700;
    line-height: 1.1;
    color: #fff;
    margin-bottom: 1.5rem;
    letter-spacing: -0.01em;
  }
  .hero h1 em {
    color: var(--gold);
    font-style: italic;
  }
  .hero-sub {
    font-size: 1.02rem;
    color: rgba(255,255,255,0.65);
    max-width: 480px;
    margin: 0 auto 2.75rem;
    line-height: 1.8;
    font-weight: 300;
  }
  .hero-cta {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
  }
  .btn-primary {
    background: var(--gold);
    color: #fff;
    font-size: 0.75rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 0.85rem 2.25rem;
    text-decoration: none;
    transition: background 0.2s, transform 0.15s;
    display: inline-block;
  }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-1px); }
  .btn-ghost {
    background: transparent;
    color: rgba(255,255,255,0.75);
    font-size: 0.75rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 0.85rem 2.25rem;
    text-decoration: none;
    border: 1px solid rgba(255,255,255,0.25);
    transition: border-color 0.2s, color 0.2s;
    display: inline-block;
  }
  .btn-ghost:hover { border-color: rgba(255,255,255,0.6); color: #fff; }
  .hero-rule {
    width: 1px; height: 48px;
    background: rgba(196,130,10,0.4);
    margin: 3.5rem auto 0;
  }

  /* ── SECTIONS ── */
  .section { padding: 5.5rem 3rem; max-width: 900px; margin: 0 auto; }
  .section-eyebrow {
    font-size: 0.68rem;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--gold);
    font-weight: 500;
    margin-bottom: 0.6rem;
  }
  .section h2 {
    font-family: var(--font-display);
    font-size: clamp(1.9rem, 3.5vw, 2.6rem);
    color: var(--blue);
    font-weight: 700;
    margin-bottom: 1.25rem;
    line-height: 1.15;
    letter-spacing: -0.01em;
  }
  .section p {
    font-size: 0.97rem;
    color: var(--muted);
    max-width: 600px;
    line-height: 1.85;
    font-weight: 300;
  }

  .divider { border: none; border-top: 1px solid var(--border); max-width: 900px; margin: 0 auto; }

  /* ── PILLARS ── */
  .pillars {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    margin-top: 3rem;
    border: 1px solid var(--border);
  }
  .pillar {
    padding: 2rem 1.5rem;
    border-right: 1px solid var(--border);
    transition: background 0.2s;
  }
  .pillar:last-child { border-right: none; }
  .pillar:hover { background: var(--cream); }
  .pillar-num {
    font-size: 0.62rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    color: var(--gold);
    margin-bottom: 1rem;
  }
  .pillar h3 {
    font-family: var(--font-display);
    font-size: 1.15rem;
    color: var(--blue);
    margin-bottom: 0.5rem;
    font-weight: 700;
    line-height: 1.2;
  }
  .pillar p { font-size: 0.85rem; color: var(--muted); line-height: 1.65; font-weight: 300; }

  /* ── STEPS ── */
  .steps { margin-top: 3rem; }
  .step {
    display: grid;
    grid-template-columns: 56px 1fr;
    gap: 1.5rem;
    padding: 2rem 0;
    border-bottom: 1px solid var(--border);
    align-items: start;
  }
  .step:first-child { border-top: 1px solid var(--border); }
  .step-num {
    font-family: var(--font-display);
    font-size: 2.5rem;
    font-weight: 600;
    color: var(--border);
    line-height: 1;
    padding-top: 2px;
    letter-spacing: -0.03em;
  }
  .step-body h4 {
    font-family: var(--font-display);
    font-size: 1.25rem;
    color: var(--blue);
    margin-bottom: 0.35rem;
    font-weight: 700;
    line-height: 1.2;
  }
  .step-body p { font-size: 0.9rem; color: var(--muted); line-height: 1.75; font-weight: 300; }

  /* ── NOTE BOX ── */
  .note-box {
    margin-top: 2.25rem;
    padding: 1.25rem 1.5rem;
    background: var(--cream);
    border-left: 3px solid var(--gold);
    font-size: 0.88rem;
    color: var(--muted);
    line-height: 1.7;
    font-weight: 300;
  }
  .note-box a { color: var(--blue); font-weight: 500; text-decoration: none; }
  .note-box a:hover { color: var(--gold); text-decoration: underline; }

  /* ── CONTACT ── */
  .contact-list { margin-top: 2.5rem; border: 1px solid var(--border); }
  .contact-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.1rem 1.5rem;
    border-bottom: 1px solid var(--border);
    transition: background 0.15s;
  }
  .contact-item:last-child { border-bottom: none; }
  .contact-item:hover { background: var(--cream); }
  .contact-label {
    font-size: 0.68rem;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #bbb;
    font-weight: 500;
  }
  .contact-val {
    font-size: 0.92rem;
    font-weight: 500;
  }
  .contact-val a {
    color: var(--blue);
    text-decoration: none;
    transition: color 0.2s;
  }
  .contact-val a:hover { color: var(--gold); }

  /* ── FOOTER ── */
  footer {
    background: var(--blue-deep);
    padding: 2.5rem 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }
  .footer-brand {
    font-family: var(--font-body);
    font-size: 0.85rem;
    font-weight: 600;
    color: rgba(255,255,255,0.6);
    letter-spacing: 0.06em;
  }
  .footer-brand span { color: var(--gold); }
  .footer-copy {
    font-size: 0.75rem;
    color: rgba(255,255,255,0.3);
    letter-spacing: 0.04em;
  }
  footer nav ul { list-style: none; display: flex; gap: 1.75rem; }
  footer nav ul a {
    font-size: 0.72rem;
    color: rgba(255,255,255,0.35);
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
  footer nav ul a:hover { color: var(--gold); }

  /* ── RESPONSIVE ── */
  @media (max-width: 640px) {
    nav { padding: 1rem 1.25rem; }
    nav ul { gap: 1.25rem; }
    .nav-cta { display: none; }
    .hero { padding: 5rem 1.5rem 4rem; }
    .section { padding: 4rem 1.5rem; }
    .pillars { grid-template-columns: 1fr 1fr; }
    .pillar { border-right: none; border-bottom: 1px solid var(--border); }
    .pillar:nth-child(odd) { border-right: 1px solid var(--border); }
    footer { flex-direction: column; align-items: flex-start; padding: 2rem 1.5rem; }
    footer nav { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-brand" href="#">
    <div class="nav-badge">
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <polygon points="12,2 22,8.5 22,15.5 12,22 2,15.5 2,8.5"/>
      </svg>
    </div>
    <div class="nav-logo">ALPFA <span>·</span> UC Berkeley</div>
  </a>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#join">Join</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#join" class="nav-cta">Become a Member</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-pattern"></div>
  <div class="hero-inner">
    <div class="hero-kicker">Association of Latino Professionals For America</div>
    <h1>Empowering the Next<br>Generation of <em>Latino Leaders</em></h1>
    <p class="hero-sub">UC Berkeley's ALPFA chapter develops students of all majors and backgrounds into leaders ready to shape the professional world.</p>
    <div class="hero-cta">
      <a href="#join" class="btn-primary">Become a Member</a>
      <a href="#about" class="btn-ghost">Learn More</a>
    </div>
    <div class="hero-rule"></div>
  </div>
</section>

<!-- ABOUT -->
<div id="about">
  <div class="section">
    <p class="section-eyebrow">Who We Are</p>
    <h2>About ALPFA<br>at Berkeley</h2>
    <p>We are UC Berkeley's chapter of the Association of Latino Professionals For America. Our mission is to empower students of all majors and backgrounds to develop as leaders in the professional world.</p>
    <p style="margin-top: 1rem;">Our team — both local to the Bay Area and nationally — is dedicated to fostering a supportive community that promotes diversity, professional development, and networking opportunities.</p>
    <div class="pillars">
      <div class="pillar">
        <div class="pillar-num">01</div>
        <h3>Networking</h3>
        <p>Build lasting connections with professionals, alumni, and peers across every industry.</p>
      </div>
      <div class="pillar">
        <div class="pillar-num">02</div>
        <h3>Professional Development</h3>
        <p>Workshops, speaker events, and career resources to accelerate your growth.</p>
      </div>
      <div class="pillar">
        <div class="pillar-num">03</div>
        <h3>Community</h3>
        <p>A supportive familia that champions diversity, belonging, and shared ambition.</p>
      </div>
      <div class="pillar">
        <div class="pillar-num">04</div>
        <h3>Open to All</h3>
        <p>All majors and backgrounds welcome — no prior experience required.</p>
      </div>
    </div>
  </div>
</div>

<hr class="divider" />

<!-- JOIN -->
<div id="join">
  <div class="section">
    <p class="section-eyebrow">Get Involved</p>
    <h2>How to Join</h2>
    <p>Membership is open to all UC Berkeley students. To become an official member of ALPFA at UC Berkeley, complete the following two requirements:</p>
    <div class="steps">
      <div class="step">
        <div class="step-num">01</div>
        <div class="step-body">
          <h4>Pay Membership Dues</h4>
          <p>Pay your dues for the academic year to officially join the chapter and unlock full access to ALPFA events, resources, and the national network.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">02</div>
        <div class="step-body">
          <h4>Attend Our Events</h4>
          <p>Commit to attending our scheduled events to stay actively involved and benefit from all the networking and professional development opportunities we offer.</p>
        </div>
      </div>
    </div>
    <div class="note-box">
      Have questions about membership? Email us at <a href="mailto:ucberkeleyalpfa@gmail.com">ucberkeleyalpfa@gmail.com</a> and we'll get back to you as soon as possible.
    </div>
  </div>
</div>

<hr class="divider" />

<!-- CONTACT -->
<div id="contact">
  <div class="section">
    <p class="section-eyebrow">Stay Connected</p>
    <h2>Contact Us</h2>
    <p>Follow us on Instagram for the latest on events, opportunities, and ways to get involved. We'd love to hear from you.</p>
    <div class="contact-list">
      <div class="contact-item">
        <span class="contact-label">Email</span>
        <span class="contact-val"><a href="mailto:ucberkeleyalpfa@gmail.com">ucberkeleyalpfa@gmail.com</a></span>
      </div>
      <div class="contact-item">
        <span class="contact-label">Instagram</span>
        <span class="contact-val"><a href="https://www.instagram.com/alpfaucberkeley/" target="_blank" rel="noopener">@alpfaucberkeley</a></span>
      </div>
      <div class="contact-item">
        <span class="contact-label">Location</span>
        <span class="contact-val" style="color: var(--muted); font-weight: 300;">UC Berkeley · Berkeley, CA 94720</span>
      </div>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-brand">ALPFA <span>·</span> UC Berkeley</div>
  <div class="footer-copy">&copy; 2026 All rights reserved.</div>
  <nav>
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="#join">Join</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</footer>

</body>
</html>
