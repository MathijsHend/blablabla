<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Incredible India — 14 Dagen Rondreis</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=Crimson+Pro:ital,wght@0,300;0,400;0,600;1,300&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --saffron: #FF6B1A;
    --gold: #D4A017;
    --deep-red: #8B1A1A;
    --teal: #1A6B6B;
    --cream: #FDF6E3;
    --ink: #1C1208;
    --dust: #E8D5A3;
    --pink: #C2185B;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }

  body {
    background: var(--cream);
    color: var(--ink);
    font-family: 'Crimson Pro', Georgia, serif;
    font-size: 18px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    background: linear-gradient(160deg, #1C0A00 0%, #3D1200 40%, #8B1A1A 70%, #C2185B 100%);
    overflow: hidden;
    padding: 60px 20px;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background:
      radial-gradient(circle at 20% 50%, rgba(212,160,23,0.15) 0%, transparent 50%),
      radial-gradient(circle at 80% 30%, rgba(255,107,26,0.12) 0%, transparent 45%);
  }
  .mandala-bg {
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 700px; height: 700px;
    border-radius: 50%;
    border: 1px solid rgba(212,160,23,0.1);
    animation: spin 80s linear infinite;
  }
  .mandala-bg::before {
    content: '';
    position: absolute; inset: 40px;
    border-radius: 50%;
    border: 1px solid rgba(212,160,23,0.08);
  }
  .mandala-bg::after {
    content: '';
    position: absolute; inset: 80px;
    border-radius: 50%;
    border: 1px solid rgba(212,160,23,0.06);
  }
  @keyframes spin { to { transform: translate(-50%, -50%) rotate(360deg); } }

  .hero-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 6px;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 24px;
    opacity: 0;
    animation: fadeUp 1s 0.3s forwards;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(60px, 12vw, 130px);
    font-weight: 900;
    line-height: 0.9;
    color: var(--cream);
    letter-spacing: -2px;
    opacity: 0;
    animation: fadeUp 1s 0.6s forwards;
  }
  .hero h1 span {
    display: block;
    color: var(--gold);
    font-style: italic;
  }
  .hero-sub {
    font-family: 'Crimson Pro', serif;
    font-size: clamp(18px, 3vw, 26px);
    font-weight: 300;
    font-style: italic;
    color: rgba(253,246,227,0.75);
    margin-top: 20px;
    opacity: 0;
    animation: fadeUp 1s 0.9s forwards;
  }
  .hero-stats {
    display: flex;
    gap: 48px;
    margin-top: 60px;
    opacity: 0;
    animation: fadeUp 1s 1.2s forwards;
  }
  .stat { text-align: center; }
  .stat-num {
    display: block;
    font-family: 'Playfair Display', serif;
    font-size: 42px;
    font-weight: 700;
    color: var(--gold);
    line-height: 1;
  }
  .stat-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    color: rgba(253,246,227,0.5);
    text-transform: uppercase;
  }
  .scroll-hint {
    position: absolute;
    bottom: 40px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    color: rgba(253,246,227,0.4);
    text-transform: uppercase;
    animation: pulse 2s infinite;
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulse {
    0%, 100% { opacity: 0.4; }
    50% { opacity: 0.9; }
  }

  /* ── NAV ── */
  nav {
    position: sticky;
    top: 0;
    z-index: 100;
    background: var(--ink);
    display: flex;
    justify-content: center;
    gap: 0;
    overflow-x: auto;
  }
  nav a {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: rgba(253,246,227,0.6);
    text-decoration: none;
    padding: 16px 20px;
    border-bottom: 2px solid transparent;
    transition: all 0.2s;
    white-space: nowrap;
  }
  nav a:hover {
    color: var(--gold);
    border-bottom-color: var(--gold);
  }

  /* ── SECTIONS ── */
  section {
    padding: 100px 20px;
    max-width: 1100px;
    margin: 0 auto;
  }
  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 5px;
    text-transform: uppercase;
    color: var(--saffron);
    margin-bottom: 12px;
  }
  h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(36px, 6vw, 64px);
    font-weight: 900;
    line-height: 1.05;
    color: var(--ink);
    margin-bottom: 32px;
  }
  h2 em {
    font-style: italic;
    color: var(--deep-red);
  }

  /* ── ROUTE ── */
  #route {
    background: var(--ink);
    color: var(--cream);
    max-width: 100%;
    padding: 100px 20px;
  }
  #route > div { max-width: 1100px; margin: 0 auto; }
  #route h2 { color: var(--cream); }
  #route .section-label { color: var(--gold); }

  .map-container {
    position: relative;
    background: #0d1a12;
    border-radius: 4px;
    overflow: hidden;
    margin-top: 48px;
    border: 1px solid rgba(212,160,23,0.2);
  }
  .map-svg { width: 100%; height: auto; }

  .route-cities {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
    margin-top: 40px;
  }
  .city-chip {
    background: rgba(212,160,23,0.1);
    border: 1px solid rgba(212,160,23,0.3);
    border-radius: 2px;
    padding: 12px 16px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .city-num {
    font-family: 'Space Mono', monospace;
    font-size: 20px;
    font-weight: 700;
    color: var(--gold);
    line-height: 1;
  }
  .city-info strong {
    display: block;
    font-family: 'Playfair Display', serif;
    font-size: 16px;
    color: var(--cream);
  }
  .city-info span {
    font-size: 12px;
    color: rgba(253,246,227,0.5);
    font-family: 'Space Mono', monospace;
  }

  /* ── PROGRAMMA ── */
  .day-grid {
    display: flex;
    flex-direction: column;
    gap: 0;
    margin-top: 48px;
    border-left: 2px solid var(--dust);
  }
  .day-entry {
    display: grid;
    grid-template-columns: 80px 1fr;
    gap: 0;
    position: relative;
  }
  .day-entry::before {
    content: '';
    position: absolute;
    left: -2px;
    top: 24px;
    width: 12px;
    height: 12px;
    background: var(--saffron);
    border-radius: 50%;
    transform: translateX(-5px);
    transition: transform 0.2s;
  }
  .day-entry:hover::before { transform: translateX(-5px) scale(1.5); }
  .day-num-col {
    padding: 20px 24px 20px 20px;
    font-family: 'Playfair Display', serif;
    font-size: 13px;
    font-weight: 700;
    color: var(--saffron);
    text-align: right;
    padding-top: 20px;
  }
  .day-content {
    padding: 20px 0 20px 32px;
    border-bottom: 1px solid var(--dust);
  }
  .day-entry:last-child .day-content { border-bottom: none; }
  .day-title {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--ink);
    margin-bottom: 6px;
  }
  .day-location {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--teal);
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .day-text { color: #3D2B1F; font-size: 16px; }
  .day-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 10px;
  }
  .pill {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    letter-spacing: 1px;
    text-transform: uppercase;
    padding: 4px 10px;
    border-radius: 100px;
    border: 1px solid;
  }
  .pill-sleep { border-color: var(--teal); color: var(--teal); }
  .pill-eat { border-color: var(--saffron); color: var(--saffron); }
  .pill-travel { border-color: var(--gold); color: var(--gold); }
  .pill-act { border-color: var(--pink); color: var(--pink); }

  /* ── SEIZOEN ── */
  #seizoen { background: #FFF8EE; max-width: 100%; padding: 100px 20px; }
  #seizoen > div { max-width: 1100px; margin: 0 auto; }

  .season-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 2px;
    margin-top: 48px;
  }
  .month-card {
    padding: 24px 20px;
    background: var(--cream);
    border-top: 3px solid transparent;
    transition: transform 0.2s;
  }
  .month-card.good { border-top-color: var(--teal); }
  .month-card.ok { border-top-color: var(--gold); }
  .month-card.bad { border-top-color: var(--deep-red); }
  .month-card.best { border-top-color: var(--saffron); background: #FFF3E8; }
  .month-card:hover { transform: translateY(-4px); }
  .month-name {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    font-weight: 700;
    margin-bottom: 6px;
  }
  .month-desc { font-size: 14px; color: #5C4033; line-height: 1.5; }
  .month-tag {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-top: 8px;
  }
  .good .month-tag { color: var(--teal); }
  .best .month-tag { color: var(--saffron); }
  .ok .month-tag { color: var(--gold); }
  .bad .month-tag { color: var(--deep-red); }

  .season-highlight {
    background: var(--saffron);
    color: white;
    padding: 32px 40px;
    margin-top: 40px;
    display: flex;
    align-items: center;
    gap: 24px;
  }
  .season-highlight strong {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    display: block;
  }

  /* ── TIPS ── */
  .tips-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 32px;
    margin-top: 48px;
  }
  @media (max-width: 680px) { .tips-grid { grid-template-columns: 1fr; } }
  .tip-card {
    padding: 32px;
    border: 1px solid var(--dust);
    position: relative;
    overflow: hidden;
  }
  .tip-card::after {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 4px;
    height: 100%;
    background: var(--saffron);
  }
  .tip-icon { font-size: 32px; margin-bottom: 16px; display: block; }
  .tip-title {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    font-weight: 700;
    margin-bottom: 12px;
    color: var(--ink);
  }
  .tip-body { font-size: 15px; color: #3D2B1F; }
  .tip-body ul { padding-left: 18px; }
  .tip-body li { margin-bottom: 6px; }

  /* ── PAKLIJST ── */
  #paklijst { background: var(--ink); max-width: 100%; padding: 100px 20px; }
  #paklijst > div { max-width: 1100px; margin: 0 auto; }
  #paklijst h2 { color: var(--cream); }
  #paklijst .section-label { color: var(--gold); }

  .pack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 32px;
    margin-top: 48px;
  }
  .pack-cat h3 {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 16px;
    padding-bottom: 8px;
    border-bottom: 1px solid rgba(212,160,23,0.3);
  }
  .pack-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    padding: 8px 0;
    border-bottom: 1px solid rgba(253,246,227,0.06);
    font-size: 15px;
    color: rgba(253,246,227,0.8);
  }
  .pack-item::before {
    content: '◦';
    color: var(--saffron);
    flex-shrink: 0;
    margin-top: 2px;
  }

  /* ── MEDIA ── */
  .media-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 24px;
    margin-top: 48px;
  }
  .media-card {
    position: relative;
    overflow: hidden;
    aspect-ratio: 4/3;
    background: var(--dust);
    cursor: pointer;
  }
  .media-card img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.4s; display: block; }
  .media-card:hover img { transform: scale(1.05); }
  .media-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to top, rgba(28,8,0,0.85) 0%, transparent 50%);
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 20px;
    opacity: 0;
    transition: opacity 0.3s;
  }
  .media-card:hover .media-overlay { opacity: 1; }
  .media-overlay a {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--gold);
    text-decoration: none;
    background: rgba(28,8,0,0.6);
    padding: 8px 14px;
    border: 1px solid rgba(212,160,23,0.4);
    width: fit-content;
    margin-top: 8px;
    transition: background 0.2s;
  }
  .media-overlay a:hover { background: var(--saffron); color: white; border-color: transparent; }
  .media-label {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    font-weight: 700;
    color: var(--cream);
    margin-bottom: 6px;
  }
  .media-img-placeholder {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-size: 48px;
    background: linear-gradient(135deg, var(--dust) 0%, #D4B896 100%);
    color: var(--ink);
  }

  /* ── CULTUUR ── */
  .culture-strip {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    margin-top: 48px;
  }
  @media (max-width: 700px) { .culture-strip { grid-template-columns: 1fr; } }
  .culture-block {
    padding: 40px 28px;
    background: var(--ink);
    color: var(--cream);
    transition: background 0.2s;
  }
  .culture-block:nth-child(2) { background: var(--deep-red); }
  .culture-block:nth-child(3) { background: var(--teal); }
  .culture-block:hover { filter: brightness(1.1); }
  .culture-block h3 {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 700;
    margin-bottom: 12px;
  }
  .culture-block p { font-size: 15px; line-height: 1.65; opacity: 0.85; }

  /* ── GEOGRAPHY ── */
  .geo-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
    margin-top: 40px;
  }
  @media (max-width: 600px) { .geo-list { grid-template-columns: 1fr; } }
  .geo-item {
    display: flex;
    gap: 16px;
    padding: 20px;
    background: white;
    border: 1px solid var(--dust);
  }
  .geo-icon { font-size: 28px; flex-shrink: 0; }
  .geo-item h4 {
    font-family: 'Playfair Display', serif;
    font-size: 17px;
    font-weight: 700;
    margin-bottom: 4px;
  }
  .geo-item p { font-size: 14px; color: #5C4033; }

  /* ── FOOTER ── */
  footer {
    background: #0D0804;
    color: rgba(253,246,227,0.4);
    text-align: center;
    padding: 48px 20px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
  }
  footer .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    font-style: italic;
    color: var(--gold);
    margin-bottom: 16px;
  }

  /* ── DIVIDERS ── */
  .ornament { text-align: center; font-size: 24px; color: var(--gold); margin: 40px 0; opacity: 0.4; }
  blockquote {
    font-family: 'Playfair Display', serif;
    font-size: clamp(22px, 4vw, 36px);
    font-style: italic;
    font-weight: 400;
    line-height: 1.4;
    color: var(--deep-red);
    border-left: 3px solid var(--saffron);
    padding-left: 32px;
    margin: 48px 0;
  }

  @media (max-width: 600px) {
    .hero-stats { gap: 24px; }
    .stat-num { font-size: 28px; }
    .tips-grid { grid-template-columns: 1fr; }
    .day-entry { grid-template-columns: 60px 1fr; }
  }
</style>
</head>
<body>

<!-- HERO -->
<header class="hero">
  <div class="mandala-bg"></div>
  <p class="hero-label">✦ Digitale Reisbrochure ✦</p>
  <h1>Incredible<span>India</span></h1>
  <p class="hero-sub">14 dagen — een wereld aan contrasten, kleuren & cultuur</p>
  <div class="hero-stats">
    <div class="stat">
      <span class="stat-num">14</span>
      <span class="stat-label">Dagen</span>
    </div>
    <div class="stat">
      <span class="stat-num">7</span>
      <span class="stat-label">Steden</span>
    </div>
    <div class="stat">
      <span class="stat-num">∞</span>
      <span class="stat-label">Indrukken</span>
    </div>
  </div>
  <p class="scroll-hint">↓ Scroll om te ontdekken ↓</p>
</header>

<!-- NAV -->
<nav>
  <a href="#route">Route</a>
  <a href="#programma">Programma</a>
  <a href="#seizoen">Seizoen</a>
  <a href="#landschap">Landschappen</a>
  <a href="#cultuur">Cultuur</a>
  <a href="#tips">Reisinformatie</a>
  <a href="#paklijst">Paklijst</a>
  <a href="#media">Bekijk & Beleef</a>
</nav>

<!-- ROUTE -->
<section id="route">
  <div>
    <p class="section-label">✦ De Route</p>
    <h2>Van de Gangesvlakte<br>naar de Thar-woestijn</h2>
    <p style="color:rgba(253,246,227,0.7); max-width:620px; font-size:17px;">
      Onze route slingert van de miljoenenstad Delhi via de heilige Ganges in Varanasi naar de forten van Rajasthan. We eindigen op de zilverwitte stranden van Goa. Een doorsnede van het subcontinent: van het noordelijke Indo-Gangetisch laagland tot de Deccan-hoogvlakte.
    </p>
    <div class="map-container">
      <svg class="map-svg" viewBox="0 0 500 580" xmlns="http://www.w3.org/2000/svg" style="max-width:600px; display:block; margin:0 auto; padding:20px;">
        <path d="M180,30 L230,25 L280,35 L330,50 L360,80 L380,110 L390,150 L400,190 L410,220 L420,260 L415,300 L400,330 L380,360 L360,390 L340,420 L310,450 L280,470 L260,490 L250,510 L240,490 L220,470 L200,450 L175,420 L155,390 L140,360 L125,330 L115,300 L110,260 L115,220 L120,180 L130,140 L140,110 L155,80 L165,55 Z"
          fill="#1a2e1a" stroke="rgba(212,160,23,0.3)" stroke-width="1.5"/>
        <path d="M115,260 L80,240 L60,210 L70,180 L90,160 L115,150" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1" stroke-dasharray="4,4"/>
        <path d="M280,35 L310,20 L350,25 L370,40 L360,80" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1" stroke-dasharray="4,4"/>
        <path d="M200,120 Q240,140 280,155 Q320,168 350,185 Q380,200 390,220" fill="none" stroke="#4A9ECC" stroke-width="2" opacity="0.6"/>
        <text x="270" y="148" fill="#4A9ECC" font-size="9" opacity="0.7" font-style="italic">Ganges</text>
        <path d="M240,95 L310,185 L270,200 L200,240 L215,300 L185,400" fill="none" stroke="#FF6B1A" stroke-width="2.5" stroke-dasharray="6,4" opacity="0.9"/>
        <circle cx="240" cy="95" r="10" fill="#FF6B1A" opacity="0.9"/>
        <text x="255" y="93" fill="#FDF6E3" font-size="13" font-weight="bold" font-family="serif">Delhi</text>
        <text x="255" y="106" fill="#D4A017" font-size="10" font-family="monospace">①</text>
        <circle cx="265" cy="140" r="8" fill="#D4A017" opacity="0.9"/>
        <text x="278" y="138" fill="#FDF6E3" font-size="12" font-family="serif">Agra</text>
        <text x="278" y="150" fill="#D4A017" font-size="10" font-family="monospace">②</text>
        <circle cx="330" cy="185" r="8" fill="#C2185B" opacity="0.9"/>
        <text x="342" y="182" fill="#FDF6E3" font-size="12" font-family="serif">Varanasi</text>
        <text x="342" y="195" fill="#D4A017" font-size="10" font-family="monospace">③</text>
        <circle cx="200" cy="155" r="8" fill="#8B1A1A" opacity="0.9"/>
        <text x="140" y="152" fill="#FDF6E3" font-size="12" font-family="serif">Jaipur</text>
        <text x="140" y="165" fill="#D4A017" font-size="10" font-family="monospace">④</text>
        <circle cx="175" cy="195" r="6" fill="#D4A017" opacity="0.85"/>
        <text x="115" y="192" fill="#FDF6E3" font-size="11" font-family="serif">Pushkar</text>
        <text x="115" y="204" fill="#D4A017" font-size="10" font-family="monospace">⑤</text>
        <circle cx="220" cy="225" r="6" fill="#1A6B6B" opacity="0.9"/>
        <text x="228" y="222" fill="#FDF6E3" font-size="11" font-family="serif">Ranthambore</text>
        <text x="228" y="234" fill="#D4A017" font-size="10" font-family="monospace">⑥</text>
        <circle cx="185" cy="400" r="10" fill="#4CAF50" opacity="0.9"/>
        <text x="198" y="397" fill="#FDF6E3" font-size="13" font-weight="bold" font-family="serif">Goa</text>
        <text x="198" y="410" fill="#D4A017" font-size="10" font-family="monospace">⑦</text>
        <text x="295" y="260" fill="rgba(212,160,23,0.5)" font-size="16">✈</text>
        <text x="270" y="270" fill="rgba(212,160,23,0.35)" font-size="9" font-family="monospace">vlucht</text>
        <g transform="translate(440,50)">
          <circle r="22" fill="none" stroke="rgba(212,160,23,0.3)" stroke-width="1"/>
          <text y="-10" text-anchor="middle" fill="#D4A017" font-size="11" font-family="monospace">N</text>
          <text y="15" text-anchor="middle" fill="rgba(212,160,23,0.4)" font-size="9">S</text>
          <line y1="-6" y2="6" stroke="rgba(212,160,23,0.5)" stroke-width="1"/>
        </g>
        <rect x="20" y="490" width="200" height="75" fill="rgba(0,0,0,0.4)" rx="2"/>
        <circle cx="36" cy="508" r="5" fill="#FF6B1A"/>
        <text x="48" y="513" fill="#FDF6E3" font-size="10" font-family="monospace">Start/eind stad</text>
        <line x1="30" y1="527" x2="48" y2="527" stroke="#FF6B1A" stroke-width="2" stroke-dasharray="4,2"/>
        <text x="54" y="531" fill="#FDF6E3" font-size="10" font-family="monospace">Route</text>
        <line x1="30" y1="545" x2="48" y2="545" stroke="#4A9ECC" stroke-width="2"/>
        <text x="54" y="549" fill="#FDF6E3" font-size="10" font-family="monospace">Ganges rivier</text>
        <text x="54" y="562" fill="rgba(212,160,23,0.5)" font-size="10" font-family="monospace">✈ Binnenl. vlucht</text>
      </svg>
    </div>
    <div class="route-cities">
      <div class="city-chip"><span class="city-num">01</span><div class="city-info"><strong>Delhi</strong><span>Dag 1–2 · Vliegtuig AMS</span></div></div>
      <div class="city-chip"><span class="city-num">02</span><div class="city-info"><strong>Agra</strong><span>Dag 3 · Trein/bus</span></div></div>
      <div class="city-chip"><span class="city-num">03</span><div class="city-info"><strong>Varanasi</strong><span>Dag 4–5 · Trein</span></div></div>
      <div class="city-chip"><span class="city-num">04</span><div class="city-info"><strong>Jaipur</strong><span>Dag 6–7 · Vlucht + bus</span></div></div>
      <div class="city-chip"><span class="city-num">05</span><div class="city-info"><strong>Pushkar</strong><span>Dag 8 · Bus</span></div></div>
      <div class="city-chip"><span class="city-num">06</span><div class="city-info"><strong>Ranthambore</strong><span>Dag 9–10 · Bus/jeep</span></div></div>
      <div class="city-chip"><span class="city-num">07</span><div class="city-info"><strong>Goa</strong><span>Dag 11–14 · Vlucht</span></div></div>
    </div>
  </div>
</section>

<!-- PROGRAMMA -->
<section id="programma">
  <p class="section-label">✦ Dag-tot-dag Programma</p>
  <h2>Elke dag een<br><em>nieuw India</em></h2>
  <blockquote>"India is not just a country. It is a civilisation."</blockquote>

  <div class="day-grid">
    <div class="day-entry">
      <div class="day-num-col">Dag<br>1–2</div>
      <div class="day-content">
        <div class="day-location">New Delhi · Indo-Gangetisch laagland</div>
        <div class="day-title">Aankomst in de chaos & pracht van de hoofdstad</div>
        <p class="day-text">Je vliegt vanuit Amsterdam (AMS) met KLM of Air India naar Indira Gandhi International Airport. Na aankomst check je in in een hotel in het bruisende Paharganj. Dag 2 staat volledig in het teken van Old Delhi en New Delhi. Bezoek het <strong>Rode Fort</strong> (Lal Qila) — een UNESCO-werelderfgoed gebouwd door Mughal-keizer Shah Jahan in 1648 — en de gigantische <strong>Jama Masjid-moskee</strong>, de grootste van India. Sluit de dag af in de overweldigende kruidenmarkt <strong>Chandni Chowk</strong> en proef straatvoedsel zoals samosa's en chaat. De stad ligt in de <em>Indo-Gangetische vlakte</em>, een van de vruchtbaarste alluviale vlakten ter wereld.</p>
        <div class="day-pills">
          <span class="pill pill-sleep">🏨 Zostel Delhi of Hotel Ajanta</span>
          <span class="pill pill-eat">🍛 Karim's Old Delhi</span>
          <span class="pill pill-travel">✈ KLM AMS→DEL ~8u</span>
          <span class="pill pill-act">🕌 Rode Fort · Jama Masjid · Chandni Chowk</span>
        </div>
      </div>
    </div>

    <div class="day-entry">
      <div class="day-num-col">Dag<br>3</div>
      <div class="day-content">
        <div class="day-location">Agra · Yamuna-rivier · Uttar Pradesh</div>
        <div class="day-title">De Taj Mahal bij zonsopgang</div>
        <p class="day-text">Met de snelle Gatimaan Express-trein (2 uur) reis je vanuit Delhi naar Agra, gelegen aan de heilige <strong>Yamuna-rivier</strong>. 's Ochtends vroeg sta je voor het meest iconische bouwwerk ter wereld: de <strong>Taj Mahal</strong>. Dit ivoorwitte marmeren mausoleum, door Mughal-keizer Shah Jahan gebouwd ter nagedachtenis aan zijn vrouw Mumtaz Mahal, behoort tot de Zeven Wereldwonderen. Bezoek 's middags ook het <strong>Agra Fort</strong> en de verlaten rode Mughal-stad <strong>Fatehpur Sikri</strong>.</p>
        <div class="day-pills">
          <span class="pill pill-sleep">🏨 Coral Tree Homestay</span>
          <span class="pill pill-eat">🍛 Pinch of Spice restaurant</span>
          <span class="pill pill-travel">🚂 Gatimaan Express (2u)</span>
          <span class="pill pill-act">🕌 Taj Mahal · Agra Fort · Fatehpur Sikri</span>
        </div>
      </div>
    </div>

    <div class="day-entry">
      <div class="day-num-col">Dag<br>4–5</div>
      <div class="day-content">
        <div class="day-location">Varanasi · De Ganges · Heilige stad</div>
        <div class="day-title">Rituelen aan de heilige Ganges</div>
        <p class="day-text"><strong>Varanasi</strong> is een van de oudste steden ter wereld en de heiligste stad van het hindoeïsme. Hindoes geloven dat sterven in Varanasi verlossing (moksha) brengt. 's Ochtends vroeg maak je een boottocht langs de <em>ghats</em> waar gelovigen baden en bidden. 's Avonds woon je de <strong>Ganga Aarti</strong> bij: een indrukwekkende vuurceremonie bij de Dashashwamedh Ghat.</p>
        <div class="day-pills">
          <span class="pill pill-sleep">🏨 BrijRama Palace of guesthouse aan de ghats</span>
          <span class="pill pill-eat">🍛 Aum Café (rooftop Ganges-uitzicht)</span>
          <span class="pill pill-travel">🚂 Trein Agra→Varanasi (~6u)</span>
          <span class="pill pill-act">🛶 Boottocht · Ganga Aarti · Ghats</span>
        </div>
      </div>
    </div>

    <div class="day-entry">
      <div class="day-num-col">Dag<br>6–7</div>
      <div class="day-content">
        <div class="day-location">Jaipur · Rajasthan · Thar-woestijn rand</div>
        <div class="day-title">De Roze Stad van de Maharadja's</div>
        <p class="day-text">Met een binnenlandse vlucht vlieg je naar <strong>Jaipur</strong>, de hoofdstad van Rajasthan. Jaipur wordt de <em>Roze Stad</em> genoemd. Bezienswaardig: het <strong>Amber Fort</strong> (met olifantrit!), het <strong>Hawa Mahal</strong>, de <strong>City Palace</strong> en het <strong>Jantar Mantar</strong> astronomisch observatorium. Je bevindt je op de rand van de <em>Thar-woestijn</em>.</p>
        <div class="day-pills">
          <span class="pill pill-sleep">🏨 Pearl Palace Heritage</span>
          <span class="pill pill-eat">🍛 Laxmi Mishtan Bhandar</span>
          <span class="pill pill-travel">✈ Vlucht Varanasi→Jaipur (~1,5u)</span>
          <span class="pill pill-act">🏰 Amber Fort · Hawa Mahal · Jantar Mantar</span>
        </div>
      </div>
    </div>

    <div class="day-entry">
      <div class="day-num-col">Dag<br>8</div>
      <div class="day-content">
        <div class="day-location">Pushkar · Aravalligebergte · Rajasthan</div>
        <div class="day-title">Heilige stad in de woestijn</div>
        <p class="day-text"><strong>Pushkar</strong>, gelegen in een vallei van het <em>Aravalligebergte</em>, is een van de heiligste plaatsen van het hindoeïsme. Het <strong>Pushkarmeer</strong> is heilig met 52 ghats aan de oevers. De stad heeft de enige <strong>Brahmatempel</strong> ter wereld. Kleurrijke bazaars en yogastudio's maken Pushkar ook populair bij backpackers.</p>
        <div class="day-pills">
          <span class="pill pill-sleep">🏨 Hotel Everest (rooftop uitzicht)</span>
          <span class="pill pill-eat">🍛 Sunset Café aan het heilige meer</span>
          <span class="pill pill-travel">🚌 Bus vanuit Jaipur (~3u)</span>
          <span class="pill pill-act">🛕 Brahmatempel · Pushkarmeer · bazaars</span>
        </div>
      </div>
    </div>

    <div class="day-entry">
      <div class="day-num-col">Dag<br>9–10</div>
      <div class="day-content">
        <div class="day-location">Ranthambore Nationaal Park · Rajasthan</div>
        <div class="day-title">Op safari naar de Bengaalse tijger</div>
        <p class="day-text">Het <strong>Ranthambore Nationaal Park</strong> is een van de beste plekken ter wereld voor wilde <strong>Bengaalse tijgers</strong>. Het park ligt op de uitlopers van de Vindhya- en Aravalligebergten. Je maakt twee jeepsafari's: vroeg in de ochtend en laat in de middag. Naast tijgers zie je ook luipaarden, krokodillen en tientallen vogelsoorten.</p>
        <div class="day-pills">
          <span class="pill pill-sleep">🏨 Ranthambore Regency</span>
          <span class="pill pill-eat">🍛 Hotelrestaurant</span>
          <span class="pill pill-travel">🚌 Bus vanuit Pushkar (~5u)</span>
          <span class="pill pill-act">🐅 Ochtend- & middagsafari · Ranthambore Fort</span>
        </div>
      </div>
    </div>

    <div class="day-entry">
      <div class="day-num-col">Dag<br>11–14</div>
      <div class="day-content">
        <div class="day-location">Goa · Arabische Zee · Westelijke Ghats</div>
        <div class="day-title">Ontspannen aan de Arabische Zee</div>
        <p class="day-text">Met een vlucht vlieg je naar <strong>Goa</strong> aan de <em>Arabische Zee</em>. Goa was eeuwenlang een Portugese kolonie. Dag 11: strand bij <strong>Palolem Beach</strong>. Dag 12: historisch <strong>Old Goa</strong> met de Basiliek van Bom Jesus (UNESCO). Dag 13: watersport — kajakken, snorkelen of duiken. Dag 14: rustdag en vlucht terug naar Amsterdam.</p>
        <div class="day-pills">
          <span class="pill pill-sleep">🏨 Beach hut Palolem of Casa Palacio</span>
          <span class="pill pill-eat">🍛 Verse vis & zeevruchtencurry</span>
          <span class="pill pill-travel">✈ Vlucht Jaipur→Goa (~1,5u)</span>
          <span class="pill pill-act">🏄 Strand · Old Goa · Watersport · Basiliek</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SEIZOEN -->
<div id="seizoen">
  <div>
    <p class="section-label">✦ Wanneer Reizen</p>
    <h2>Klimaat & <em>Moesson</em></h2>
    <p style="max-width:680px; font-size:17px; color:#3D2B1F;">India heeft een monsoonsklimaat dat sterk verschilt per regio. De moesson trekt van juni tot september van zuidwest naar noordoost over het subcontinent.</p>
    <div class="season-grid">
      <div class="month-card ok"><div class="month-name">Januari</div><p class="month-desc">Aangenaam koel in het noorden (10–18°C), ideaal voor Rajasthan en Delhi.</p><p class="month-tag">✓ Goed</p></div>
      <div class="month-card ok"><div class="month-name">Februari</div><p class="month-desc">Lente begint. Holi-festival! Prettige temperaturen overal.</p><p class="month-tag">✓ Goed · Holi festival</p></div>
      <div class="month-card good"><div class="month-name">Maart</div><p class="month-desc">Warm en droog, goede zichtbaarheid voor tijgersafari's.</p><p class="month-tag">✓ Goed</p></div>
      <div class="month-card ok"><div class="month-name">April</div><p class="month-desc">Heet in het noorden (30–40°C), idealer voor de kust.</p><p class="month-tag">~ Warm</p></div>
      <div class="month-card bad"><div class="month-name">Mei</div><p class="month-desc">Snikhete temperaturen (45°C in Rajasthan). Afgeraden voor noorden.</p><p class="month-tag">✗ Erg heet</p></div>
      <div class="month-card bad"><div class="month-name">Juni</div><p class="month-desc">Moesson begint in Goa en Mumbai. Zwaar regen in het zuiden.</p><p class="month-tag">✗ Moesson start</p></div>
      <div class="month-card bad"><div class="month-name">Juli</div><p class="month-desc">Volle moesson. Overstromingen mogelijk. Nationaalparken gesloten.</p><p class="month-tag">✗ Moesson</p></div>
      <div class="month-card bad"><div class="month-name">Augustus</div><p class="month-desc">Moesson in volle gang. Onafhankelijkheidsdag feest!</p><p class="month-tag">✗ Moesson</p></div>
      <div class="month-card ok"><div class="month-name">September</div><p class="month-desc">Moesson trekt weg. Rajasthan wordt groen. Parken openen half oktober.</p><p class="month-tag">~ Transitie</p></div>
      <div class="month-card best"><div class="month-name">Oktober</div><p class="month-desc">Helder, fris na moesson. Diwali-festival. Parken heropenen. Top!</p><p class="month-tag">★ Aanbevolen</p></div>
      <div class="month-card best"><div class="month-name">November</div><p class="month-desc">De absolute topmaand: prachtig weer, festivals, groene natuur.</p><p class="month-tag">★ Beste reistijd</p></div>
      <div class="month-card good"><div class="month-name">December</div><p class="month-desc">Koel en zonnig. Populair (drukte), kerst in Goa is bijzonder!</p><p class="month-tag">✓ Goed</p></div>
    </div>
    <div class="season-highlight">
      <span style="font-size:48px;">🗓️</span>
      <div>
        <strong>Onze aanbeveling: vertrek begin november</strong>
        Begin november is de beste combinatie: de moesson is voorbij, de Diwali-sfeer hangt nog in de lucht, nationaalparken zijn open voor tijgersafari en de temperaturen zijn aangenaam (20–28°C).
      </div>
    </div>
  </div>
</div>

<!-- LANDSCHAPPEN -->
<section id="landschap">
  <p class="section-label">✦ Geografie</p>
  <h2>Welke landschappen<br><em>kom je tegen?</em></h2>
  <div class="geo-list">
    <div class="geo-item"><span class="geo-icon">🏙️</span><div><h4>Indo-Gangetische vlakte</h4><p>Het alluviale laagland rond de heilige Ganges en Yamuna. Delhi en Agra liggen hier. Bijzonder vruchtbaar door eeuwenlange rivierafzetting — broodkorf van India.</p></div></div>
    <div class="geo-item"><span class="geo-icon">🏜️</span><div><h4>Thar-woestijn (Rajasthan)</h4><p>De grootste woestijn van India met zandduinen en rotsige vlakten. Jaipur en Pushkar liggen op de rand van de Thar. Schaarse regenval (&lt;150mm/jaar).</p></div></div>
    <div class="geo-item"><span class="geo-icon">⛰️</span><div><h4>Aravalligebergte</h4><p>Een van de oudste gebergten ter wereld (&gt;1 miljard jaar oud). Loopt door Rajasthan. Pushkar ligt in een vallei ervan.</p></div></div>
    <div class="geo-item"><span class="geo-icon">🌿</span><div><h4>Droog tropisch bos</h4><p>Ranthambore Nationaal Park: droog decidueus bos op de uitlopers van de Vindhyagebergte. Biotoop van de Bengaalse tijger.</p></div></div>
    <div class="geo-item"><span class="geo-icon">🌊</span><div><h4>Kustvlakte & Arabische Zee</h4><p>Goa ligt aan de smalle kustvlakte langs de Arabische Zee. Witte stranden, palmbossen en mangrovemoerassen.</p></div></div>
    <div class="geo-item"><span class="geo-icon">🌄</span><div><h4>Westelijke Ghats</h4><p>UNESCO-werelderfgoed door uitzonderlijke biodiversiteit. Vanuit Goa zie je de groene heuvels aan de horizon.</p></div></div>
  </div>
</section>

<!-- CULTUUR -->
<div id="cultuur" style="background:#FFF8EE; padding: 0 0 100px;">
  <section style="padding-top:100px;">
    <p class="section-label">✦ Cultuur & Religie</p>
    <h2>Een subcontinent<br><em>vol diversiteit</em></h2>
    <p style="max-width:660px; font-size:17px; color:#3D2B1F; margin-bottom: 48px;">India herbergt meer dan 1,4 miljard mensen, honderden talen en alle grote wereldreligies. Tijdens onze route stoten we op vier compleet verschillende culturele werelden.</p>
  </section>
  <div class="culture-strip" style="max-width:1100px; margin: 0 auto;">
    <div class="culture-block">
      <h3>🕌 Islamitische Mughal-cultuur</h3>
      <p>In Delhi en Agra zie je de grandeur van het Mughal-rijk (16e–19e eeuw). Architectonische hoogtepunten: de Taj Mahal, het Rode Fort en de Jama Masjid. De Mughal-keuken — met rijke kruidensauzen, kebabs en biryani — leeft voort in restaurants als Karim's.</p>
    </div>
    <div class="culture-block">
      <h3>🛕 Hindoeïstische cultuur</h3>
      <p>Het hindoeïsme is de dominante religie (80% van de bevolking). In Varanasi beleven we de meest intense expressie: rituelen, crematies aan de ghats en de Ganga Aarti. In Pushkar aanbidden pelgrims in de unieke Brahmatempel.</p>
    </div>
    <div class="culture-block" style="background: var(--teal);">
      <h3>⚜️ Rajput & Portugese cultuur</h3>
      <p>In Rajasthan heerste de krijgshoogadel der Rajputs. In Goa zie je 450 jaar Portugees kolonialisme: barokke kerken, Latijnse architectuur en een unieke Goa-keuken.</p>
    </div>
  </div>
  <section style="padding-top: 60px; padding-bottom: 0;">
    <h3 style="font-family:'Playfair Display',serif; font-size:28px; font-weight:700; margin-bottom:24px; color:var(--deep-red);">🔱 Heilige steden & rivieren</h3>
    <div class="geo-list">
      <div class="geo-item"><span class="geo-icon">🛕</span><div><h4>Varanasi — heiligste stad</h4><p>Hindoes geloven dat wie sterft in Varanasi, moksha bereikt. De stad bestaat al minstens 3.000 jaar en is een van de oudste bewoonde plaatsen ter wereld.</p></div></div>
      <div class="geo-item"><span class="geo-icon">💧</span><div><h4>De Ganges — heilige rivier</h4><p>De Ganges is in het hindoeïsme de godin Ganga zelf. Baden in de rivier wast zonden weg. De rivier ontspringt in de Himalayas en mondt uit in de Golf van Bengalen.</p></div></div>
      <div class="geo-item"><span class="geo-icon">🌊</span><div><h4>Pushkarmeer — heilig meer</h4><p>Volgens de hindoeïstische mythologie ontstaan uit een lotusblad van Brahma. Er zijn 52 ghats omheen. Één bad zou je reinigen van alle zonden.</p></div></div>
      <div class="geo-item"><span class="geo-icon">🌊</span><div><h4>Yamuna-rivier — heilige zijrivier</h4><p>De Yamuna stroomt langs Agra en is heilig in het hindoeïsme. Ze is een godin in de Vaishnava-traditie.</p></div></div>
    </div>
    <div class="ornament">✦ ✦ ✦</div>
    <h3 style="font-family:'Playfair Display',serif; font-size:28px; font-weight:700; margin-bottom:24px; color:var(--deep-red);">🇮🇳 Typisch Indiase verschijnselen</h3>
    <div class="geo-list">
      <div class="geo-item"><span class="geo-icon">🛺</span><div><h4>De riksja</h4><p>De tuk-tuk is het meest geliefde vervoermiddel voor korte afstanden. Altijd onderhandelen over de prijs vóórdat je instapt!</p></div></div>
      <div class="geo-item"><span class="geo-icon">🐄</span><div><h4>Heilige koeien</h4><p>Koeien zijn heilig in het hindoeïsme en lopen vrij door steden. Ze bepalen letterlijk het verkeer.</p></div></div>
      <div class="geo-item"><span class="geo-icon">🎨</span><div><h4>Holi & Diwali</h4><p>India's kleurrijkste festivals. Bij Holi gooit men gekleurde poeders. Bij Diwali branden miljoenen olielampjes.</p></div></div>
      <div class="geo-item"><span class="geo-icon">🌶️</span><div><h4>Indiase keuken</h4><p>India kent tientallen regionale keukens. Van Mughal-curry's in het noorden tot kokosmelk-visgerechten in Goa.</p></div></div>
      <div class="geo-item"><span class="geo-icon">🕉️</span><div><h4>Meer dan 1.600 talen</h4><p>Hindi en Engels zijn de officiële talen, maar elke deelstaat heeft zijn eigen taal: Tamil, Marathi, Bengali, Gujarati…</p></div></div>
      <div class="geo-item"><span class="geo-icon">🚂</span><div><h4>Indiase spoorwegen</h4><p>Het op twee na grootste spoorwegnet ter wereld (68.000 km). Goedkoop, sociaal en avontuurlijk. Boek ruim van tevoren!</p></div></div>
    </div>
  </section>
</div>

<!-- REISINFORMATIE -->
<section id="tips">
  <p class="section-label">✦ Reisinformatie</p>
  <h2>Visa, Vaccinaties<br><em>& praktische tips</em></h2>
  <div class="tips-grid">
    <div class="tip-card">
      <span class="tip-icon">🛂</span>
      <div class="tip-title">Visum & Documenten</div>
      <div class="tip-body">
        <ul>
          <li><strong>E-Visum</strong> aanvragen via <a href="https://indianvisaonline.gov.in" target="_blank" style="color:var(--saffron);">indianvisaonline.gov.in</a></li>
          <li>Geldig paspoort voor nog <strong>minimaal 6 maanden</strong> na vertrek</li>
          <li>Binnen 72 uur voor aankomst een <strong>Arrival Card</strong> invullen van tevoren</li>
          <li>Kosten e-visum: circa €25–€35 — vraag minimaal 4 weken voor vertrek aan</li>
          <li>Print altijd je visumbevestiging en Arrival Card uit</li>
        </ul>
      </div>
    </div>
    <div class="tip-card">
      <span class="tip-icon">💉</span>
      <div class="tip-title">Vaccinaties</div>
      <div class="tip-body">
        <p><strong>Sterk aanbevolen (overleg GGD):</strong></p>
        <ul>
          <li><strong>DTP</strong> — Difterie, Tetanus en Polio</li>
          <li><strong>Hepatitis A</strong> — via besmet water en voedsel</li>
          <li><strong>Buiktyfus</strong> — via besmet water en voedsel</li>
          <li>Breng een <strong>vaccinatiepaspoort</strong> mee als bewijs</li>
          <li>Optioneel: Hepatitis B, Rabiës, Japanse encefalitis, Malaria</li>
        </ul>
        <p style="margin-top:10px;">Maak een afspraak bij GGD Reisvaccinaties uiterlijk 6–8 weken voor vertrek.</p>
      </div>
    </div>
    <div class="tip-card">
      <span class="tip-icon">🍽️</span>
      <div class="tip-title">Eten & Drinken</div>
      <div class="tip-body">
        <ul>
          <li>Pas op met welk water je eet en drinkt — <strong>neem nooit ijs</strong></li>
          <li>Kraanwater is <strong>NIET</strong> veilig — altijd flessenwater met verzegelde dop</li>
          <li>Rauwe salades en geschild fruit van straat vermijden</li>
          <li>Straateten is heerlijk maar kies drukke kraampjes met verse bereiding</li>
          <li>Indiase keuken is vaak pittig — vraag om "less spicy"</li>
        </ul>
      </div>
    </div>
    <div class="tip-card">
      <span class="tip-icon">⚠️</span>
      <div class="tip-title">Veiligheid & Gedrag</div>
      <div class="tip-body">
        <ul>
          <li>Pas op voor <strong>zakkenrollers en oplichters</strong>, vooral bij trekpleisters</li>
          <li>Bij tempels: neppriesters zijn een bekend fenomeen</li>
          <li>Schoen uitdoen bij tempels en heilige plaatsen</li>
          <li>Bescheiden kleding bij religieuze plekken</li>
          <li>Reisverzekering met medische en diefstalsdekking is essentieel</li>
          <li>Noodnummer India: 112 · Politie: 100 · Ambulance: 102</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- PAKLIJST -->
<div id="paklijst">
  <div>
    <p class="section-label">✦ Paklijst</p>
    <h2 style="color:var(--cream);">Wat neem je<br><em style="color:var(--gold);">mee naar India?</em></h2>
    <div class="pack-grid">
      <div class="pack-cat">
        <h3>Kleding</h3>
        <div class="pack-item">7–10 lichte T-shirts of luchtige hemden</div>
        <div class="pack-item">2–3 lange broeken van lichte stof</div>
        <div class="pack-item">2 korte broeken</div>
        <div class="pack-item">1 dun vest of lichte trui</div>
        <div class="pack-item">Ondergoed en sokken voor 14 dagen</div>
        <div class="pack-item">Pyjama of slaapkleding</div>
        <div class="pack-item">Regenjas of compacte poncho</div>
        <div class="pack-item">Comfortabele wandelschoenen</div>
        <div class="pack-item">Sandalen of slippers</div>
        <div class="pack-item">Pet of zonnehoed</div>
      </div>
      <div class="pack-cat">
        <h3>Toiletartikelen</h3>
        <div class="pack-item">Tandenborstel en tandpasta</div>
        <div class="pack-item">Deodorant</div>
        <div class="pack-item">Shampoo en douchegel (reisverpakking)</div>
        <div class="pack-item">Scheermesje indien nodig</div>
        <div class="pack-item">Zonnebrandcrème SPF 30–50</div>
        <div class="pack-item">Lippenbalsem met UV-bescherming</div>
        <div class="pack-item">Handdesinfectiegel</div>
        <div class="pack-item">Natte doekjes</div>
        <div class="pack-item">Zakdoekjes / toiletpapier voor onderweg</div>
      </div>
      <div class="pack-cat">
        <h3>Gezondheid</h3>
        <div class="pack-item">Persoonlijke medicatie</div>
        <div class="pack-item">ORS (oral rehydration salts) tegen uitdroging</div>
        <div class="pack-item">Paracetamol of ibuprofen</div>
        <div class="pack-item">Middel tegen diarree (bijv. loperamide)</div>
        <div class="pack-item">Pleisters</div>
        <div class="pack-item">Muggenspray met DEET of icaridine</div>
        <div class="pack-item">EHBO-setje</div>
      </div>
      <div class="pack-cat">
        <h3>Elektronica</h3>
        <div class="pack-item">Telefoon</div>
        <div class="pack-item">Oplader</div>
        <div class="pack-item">Powerbank</div>
        <div class="pack-item">Wereldstekker (type C, D en M)</div>
        <div class="pack-item">Eventueel e-reader of tablet</div>
        <div class="pack-item">Koptelefoon / oordopjes</div>
      </div>
      <div class="pack-cat">
        <h3>Documenten</h3>
        <div class="pack-item">Paspoort (minimaal 6 maanden geldig)</div>
        <div class="pack-item">Visum of e-visum (uitgeprint)</div>
        <div class="pack-item">Reisverzekeringgegevens</div>
        <div class="pack-item">Vluchtgegevens</div>
        <div class="pack-item">Kopieën van documenten (digitaal en papier)</div>
        <div class="pack-item">Bankpas en creditcard</div>
        <div class="pack-item">Wat contante Indiase roepies voor aankomst</div>
      </div>
      <div class="pack-cat">
        <h3>Handig voor India</h3>
        <div class="pack-item">Herbruikbare waterfles</div>
        <div class="pack-item">Kleine dagrugzak</div>
        <div class="pack-item">Zonnebril</div>
        <div class="pack-item">Wasmiddel voor handwas</div>
        <div class="pack-item">Ziplock-zakjes</div>
        <div class="pack-item">Snacks voor onderweg</div>
        <div class="pack-item">Klein slotje voor bagage</div>
      </div>
    </div>
  </div>
</div>

<!-- BEELDMATERIAAL -->
<section id="media">
  <p class="section-label">✦ Bekijk & Beleef</p>
  <h2>Laat je inspireren<br><em>voor vertrek</em></h2>
  <p style="max-width:600px; font-size:17px; color:#3D2B1F;">Bekijk de video's en foto's om een voorproefje te krijgen. Klik op een kaart voor meer informatie.</p>
  <div class="media-grid">
    <div class="media-card">
      <div class="media-img-placeholder"><span>🕌</span><span style="font-family:'Playfair Display',serif; font-size:18px; font-weight:700; margin-top:8px;">Taj Mahal</span><span style="font-size:12px; opacity:0.6; font-family:monospace; margin-top:4px;">Agra · Uttar Pradesh</span></div>
      <div class="media-overlay"><span class="media-label">Taj Mahal</span><a href="https://www.youtube.com/watch?v=fB18bkN1OEw" target="_blank">▶ Bekijk video</a><a href="https://whc.unesco.org/en/list/252/" target="_blank">🔗 UNESCO info</a></div>
    </div>
    <div class="media-card">
      <div class="media-img-placeholder"><span>🛶</span><span style="font-family:'Playfair Display',serif; font-size:18px; font-weight:700; margin-top:8px;">Ganga Aarti</span><span style="font-size:12px; opacity:0.6; font-family:monospace; margin-top:4px;">Varanasi · Ganges</span></div>
      <div class="media-overlay"><span class="media-label">Ganga Aarti Varanasi</span><a href="https://www.youtube.com/watch?v=LBwMjpJT6O8" target="_blank">▶ Bekijk ceremonie</a><a href="https://www.lonelyplanet.com/india/uttar-pradesh/varanasi" target="_blank">🔗 Lonelyplanet Varanasi</a></div>
    </div>
    <div class="media-card">
      <div class="media-img-placeholder"><span>🐅</span><span style="font-family:'Playfair Display',serif; font-size:18px; font-weight:700; margin-top:8px;">Tijger Safari</span><span style="font-size:12px; opacity:0.6; font-family:monospace; margin-top:4px;">Ranthambore · Rajasthan</span></div>
      <div class="media-overlay"><span class="media-label">Ranthambore Safari</span><a href="https://www.youtube.com/watch?v=qdBEOaZL3Ig" target="_blank">▶ Tijgers in het wild</a><a href="https://www.ranthambore.in" target="_blank">🔗 Park info & boeken</a></div>
    </div>
    <div class="media-card">
      <div class="media-img-placeholder"><span>🏰</span><span style="font-family:'Playfair Display',serif; font-size:18px; font-weight:700; margin-top:8px;">Amber Fort</span><span style="font-size:12px; opacity:0.6; font-family:monospace; margin-top:4px;">Jaipur · Rajasthan</span></div>
      <div class="media-overlay"><span class="media-label">Amber Fort Jaipur</span><a href="https://www.youtube.com/watch?v=v0PNQSmQO1c" target="_blank">▶ Videorondleiding</a><a href="https://www.jaipurtourism.gov.in" target="_blank">🔗 Jaipur toerisme</a></div>
    </div>
    <div class="media-card">
      <div class="media-img-placeholder"><span>🏖️</span><span style="font-family:'Playfair Display',serif; font-size:18px; font-weight:700; margin-top:8px;">Palolem Beach</span><span style="font-size:12px; opacity:0.6; font-family:monospace; margin-top:4px;">Goa · Arabische Zee</span></div>
      <div class="media-overlay"><span class="media-label">Goa stranden</span><a href="https://www.youtube.com/watch?v=GE_OifX6c78" target="_blank">▶ Goa reisfilm</a><a href="https://www.goatourism.gov.in" target="_blank">🔗 Goa toerisme</a></div>
    </div>
    <div class="media-card">
      <div class="media-img-placeholder"><span>🎨</span><span style="font-family:'Playfair Display',serif; font-size:18px; font-weight:700; margin-top:8px;">Holi Festival</span><span style="font-size:12px; opacity:0.6; font-family:monospace; margin-top:4px;">Heel India · Februari/Maart</span></div>
      <div class="media-overlay"><span class="media-label">Holi — Festival der kleuren</span><a href="https://www.youtube.com/watch?v=b97DpCsXCRY" target="_blank">▶ Holi in actie</a><a href="https://incredibleindia.org" target="_blank">🔗 Incredible India</a></div>
    </div>
  </div>
  <blockquote style="margin-top:64px;">"Not all those who wander are lost — but in India, getting a little lost is half the adventure."</blockquote>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Incredible India</div>
  <p>Digitale reisbrochure · Geografie Opdracht · 2026</p>
  <p style="margin-top:8px; opacity:0.3;">Route: Delhi → Agra → Varanasi → Jaipur → Pushkar → Ranthambore → Goa</p>
  <p style="margin-top:16px; opacity:0.25;">Brochure gemaakt voor schoolopdracht. Prijzen en informatie kunnen wijzigen.</p>
</footer>

</body>
</html>
