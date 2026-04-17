<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Manjula M J — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Syne:wght@700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --bg2: #111118;
    --bg3: #16161f;
    --card: #1a1a26;
    --border: rgba(139,92,246,0.15);
    --purple: #8b5cf6;
    --violet: #7c3aed;
    --pink: #ec4899;
    --cyan: #06b6d4;
    --green: #10b981;
    --amber: #f59e0b;
    --text: #f1f0ff;
    --muted: #8b8aa0;
    --glow: rgba(139,92,246,0.3);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom cursor */
  .cursor {
    width: 12px; height: 12px;
    background: var(--purple);
    border-radius: 50%;
    position: fixed;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s, width 0.2s, height 0.2s, background 0.2s;
    mix-blend-mode: screen;
  }
  .cursor-ring {
    width: 36px; height: 36px;
    border: 1px solid rgba(139,92,246,0.5);
    border-radius: 50%;
    position: fixed;
    pointer-events: none;
    z-index: 9998;
    transform: translate(-50%, -50%);
    transition: all 0.15s ease;
  }
  body:hover .cursor { opacity: 1; }

  /* Animated bg grid */
  .bg-grid {
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(139,92,246,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(139,92,246,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* Floating orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
    animation: floatOrb 8s ease-in-out infinite;
  }
  .orb-1 { width: 400px; height: 400px; background: rgba(139,92,246,0.12); top: -100px; right: -100px; animation-delay: 0s; }
  .orb-2 { width: 300px; height: 300px; background: rgba(236,72,153,0.08); bottom: 20%; left: -80px; animation-delay: -3s; }
  .orb-3 { width: 250px; height: 250px; background: rgba(6,182,212,0.07); top: 50%; right: 10%; animation-delay: -5s; }

  @keyframes floatOrb {
    0%, 100% { transform: translateY(0) scale(1); }
    50% { transform: translateY(-30px) scale(1.05); }
  }

  /* Scroll reveal */
  .reveal {
    opacity: 0;
    transform: translateY(40px);
    transition: opacity 0.7s cubic-bezier(0.16,1,0.3,1), transform 0.7s cubic-bezier(0.16,1,0.3,1);
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }
  .reveal-left {
    opacity: 0;
    transform: translateX(-40px);
    transition: opacity 0.7s cubic-bezier(0.16,1,0.3,1), transform 0.7s cubic-bezier(0.16,1,0.3,1);
  }
  .reveal-left.visible { opacity: 1; transform: translateX(0); }
  .reveal-right {
    opacity: 0;
    transform: translateX(40px);
    transition: opacity 0.7s cubic-bezier(0.16,1,0.3,1), transform 0.7s cubic-bezier(0.16,1,0.3,1);
  }
  .reveal-right.visible { opacity: 1; transform: translateX(0); }
  .reveal-scale {
    opacity: 0;
    transform: scale(0.85);
    transition: opacity 0.6s cubic-bezier(0.16,1,0.3,1), transform 0.6s cubic-bezier(0.16,1,0.3,1);
  }
  .reveal-scale.visible { opacity: 1; transform: scale(1); }

  /* Stagger children */
  .stagger > * { opacity: 0; transform: translateY(20px); transition: opacity 0.5s ease, transform 0.5s ease; }
  .stagger.visible > *:nth-child(1) { opacity:1; transform:none; transition-delay: 0.05s; }
  .stagger.visible > *:nth-child(2) { opacity:1; transform:none; transition-delay: 0.1s; }
  .stagger.visible > *:nth-child(3) { opacity:1; transform:none; transition-delay: 0.15s; }
  .stagger.visible > *:nth-child(4) { opacity:1; transform:none; transition-delay: 0.2s; }
  .stagger.visible > *:nth-child(5) { opacity:1; transform:none; transition-delay: 0.25s; }
  .stagger.visible > *:nth-child(6) { opacity:1; transform:none; transition-delay: 0.3s; }
  .stagger.visible > *:nth-child(7) { opacity:1; transform:none; transition-delay: 0.35s; }

  /* Layout */
  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 0 24px;
    position: relative;
    z-index: 1;
  }

  /* ---- HERO ---- */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 80px 24px 60px;
    position: relative;
  }

  .avatar-ring {
    width: 120px; height: 120px;
    border-radius: 50%;
    position: relative;
    margin-bottom: 28px;
    animation: heroEntry 0.8s cubic-bezier(0.16,1,0.3,1) both;
  }
  .avatar-ring::before {
    content: '';
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--purple), var(--pink), var(--cyan));
    animation: spinRing 4s linear infinite;
    z-index: -1;
  }
  .avatar-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: linear-gradient(135deg, #1a1a26, #2a1f4a);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 42px;
    font-weight: 800;
    color: var(--purple);
    border: 3px solid var(--bg);
  }

  @keyframes spinRing {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  @keyframes heroEntry {
    from { opacity: 0; transform: scale(0.7) translateY(20px); }
    to { opacity: 1; transform: scale(1) translateY(0); }
  }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(36px, 7vw, 64px);
    font-weight: 800;
    line-height: 1.1;
    background: linear-gradient(135deg, #fff 30%, var(--purple), var(--pink));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
    animation: heroEntry 0.9s 0.1s cubic-bezier(0.16,1,0.3,1) both;
  }

  .hero-sub {
    font-size: 18px;
    color: var(--muted);
    margin-bottom: 20px;
    animation: heroEntry 0.9s 0.2s cubic-bezier(0.16,1,0.3,1) both;
  }

  /* Typing animation */
  .typing-wrap {
    height: 36px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 32px;
    animation: heroEntry 0.9s 0.3s cubic-bezier(0.16,1,0.3,1) both;
  }
  .typing-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: 15px;
    color: var(--cyan);
    border-right: 2px solid var(--cyan);
    padding-right: 4px;
    animation: blink 0.8s step-end infinite;
    white-space: nowrap;
    overflow: hidden;
  }
  @keyframes blink { 0%,100% { border-color: var(--cyan); } 50% { border-color: transparent; } }

  /* Social pills */
  .socials {
    display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;
    animation: heroEntry 0.9s 0.4s cubic-bezier(0.16,1,0.3,1) both;
  }
  .social-pill {
    display: flex; align-items: center; gap: 8px;
    padding: 8px 18px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 50px;
    text-decoration: none;
    color: var(--text);
    font-size: 13px;
    font-weight: 500;
    transition: all 0.25s ease;
    position: relative;
    overflow: hidden;
  }
  .social-pill::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(139,92,246,0.15), rgba(236,72,153,0.1));
    opacity: 0;
    transition: opacity 0.3s;
  }
  .social-pill:hover::before { opacity: 1; }
  .social-pill:hover { border-color: var(--purple); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(139,92,246,0.2); }
  .social-dot { width: 8px; height: 8px; border-radius: 50%; }

  /* Scroll indicator */
  .scroll-hint {
    position: absolute;
    bottom: 32px;
    left: 50%;
    transform: translateX(-50%);
    display: flex; flex-direction: column; align-items: center; gap: 8px;
    color: var(--muted);
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    animation: heroEntry 1s 0.7s both, pulseDown 2s 1.7s ease-in-out infinite;
  }
  .scroll-line {
    width: 1px; height: 40px;
    background: linear-gradient(to bottom, var(--purple), transparent);
    animation: scrollPulse 2s ease-in-out infinite;
  }
  @keyframes scrollPulse { 0%,100% { transform: scaleY(1); opacity: 0.6; } 50% { transform: scaleY(1.3); opacity: 1; } }
  @keyframes pulseDown { 0%,100% { transform: translateX(-50%) translateY(0); } 50% { transform: translateX(-50%) translateY(5px); } }

  /* ---- SECTIONS ---- */
  section { padding: 80px 0; }

  .section-label {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--purple);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 8px;
  }
  .section-label::before {
    content: '';
    width: 24px; height: 1px;
    background: var(--purple);
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: clamp(26px, 4vw, 36px);
    font-weight: 800;
    margin-bottom: 40px;
    color: var(--text);
  }
  .section-title span {
    background: linear-gradient(135deg, var(--purple), var(--pink));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  /* ---- ABOUT ---- */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
  @media (max-width: 600px) { .about-grid { grid-template-columns: 1fr; } }

  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 20px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s, box-shadow 0.3s;
  }
  .about-card:hover {
    border-color: rgba(139,92,246,0.4);
    transform: translateY(-4px);
    box-shadow: 0 16px 40px rgba(139,92,246,0.12);
  }
  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--purple), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .about-card:hover::before { opacity: 1; }
  .about-card-icon {
    font-size: 28px;
    margin-bottom: 10px;
    display: block;
  }
  .about-card h4 {
    font-size: 14px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 4px;
  }
  .about-card p {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
  }

  /* ---- SKILLS ---- */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
    gap: 10px;
  }

  .skill-badge {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 10px 14px;
    font-size: 12px;
    font-weight: 500;
    color: var(--muted);
    text-align: center;
    transition: all 0.25s ease;
    cursor: default;
    position: relative;
    overflow: hidden;
  }
  .skill-badge::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--purple), var(--pink));
    transform: scaleX(0);
    transition: transform 0.3s ease;
  }
  .skill-badge:hover {
    color: var(--text);
    border-color: rgba(139,92,246,0.4);
    transform: translateY(-3px) scale(1.03);
    box-shadow: 0 8px 24px rgba(139,92,246,0.15);
  }
  .skill-badge:hover::after { transform: scaleX(1); }
  .skill-dot {
    display: inline-block;
    width: 6px; height: 6px;
    border-radius: 50%;
    margin-right: 6px;
    background: var(--purple);
    vertical-align: middle;
  }

  /* ---- PROJECTS ---- */
  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 28px;
    margin-bottom: 16px;
    position: relative;
    overflow: hidden;
    transition: all 0.35s cubic-bezier(0.16,1,0.3,1);
  }
  .project-card:hover {
    border-color: rgba(139,92,246,0.5);
    transform: translateY(-6px);
    box-shadow: 0 24px 60px rgba(139,92,246,0.15);
  }
  .project-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(139,92,246,0.05) 0%, transparent 60%);
    opacity: 0;
    transition: opacity 0.35s;
  }
  .project-card:hover::before { opacity: 1; }

  .project-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: rgba(139,92,246,0.5);
    margin-bottom: 8px;
    letter-spacing: 0.1em;
  }
  .project-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 16px;
    margin-bottom: 10px;
  }
  .project-title {
    font-family: 'Syne', sans-serif;
    font-size: 20px;
    font-weight: 800;
    color: var(--text);
  }
  .project-live {
    display: flex; align-items: center; gap: 6px;
    font-size: 11px;
    color: var(--green);
    background: rgba(16,185,129,0.1);
    border: 1px solid rgba(16,185,129,0.25);
    border-radius: 50px;
    padding: 4px 12px;
    white-space: nowrap;
    flex-shrink: 0;
  }
  .live-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--green);
    animation: livePulse 2s ease-in-out infinite;
  }
  @keyframes livePulse {
    0%,100% { box-shadow: 0 0 0 0 rgba(16,185,129,0.5); }
    50% { box-shadow: 0 0 0 5px rgba(16,185,129,0); }
  }
  .project-desc {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.7;
    margin-bottom: 16px;
  }
  .project-tags {
    display: flex; flex-wrap: wrap; gap: 6px;
    margin-bottom: 16px;
  }
  .tag {
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 6px;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 500;
  }
  .tag-purple { background: rgba(139,92,246,0.15); color: #a78bfa; border: 1px solid rgba(139,92,246,0.2); }
  .tag-cyan { background: rgba(6,182,212,0.12); color: #67e8f9; border: 1px solid rgba(6,182,212,0.2); }
  .tag-green { background: rgba(16,185,129,0.12); color: #6ee7b7; border: 1px solid rgba(16,185,129,0.2); }
  .tag-pink { background: rgba(236,72,153,0.12); color: #f9a8d4; border: 1px solid rgba(236,72,153,0.2); }
  .tag-amber { background: rgba(245,158,11,0.12); color: #fcd34d; border: 1px solid rgba(245,158,11,0.2); }

  .project-link {
    display: inline-flex; align-items: center; gap: 6px;
    font-size: 12px;
    color: var(--purple);
    text-decoration: none;
    font-weight: 500;
    transition: gap 0.2s;
  }
  .project-link:hover { gap: 10px; }
  .project-link span { font-size: 14px; }

  /* ---- STATS ---- */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }
  @media (max-width: 500px) { .stats-grid { grid-template-columns: 1fr 1fr; } }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px 16px;
    text-align: center;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  .stat-card:hover {
    border-color: rgba(139,92,246,0.4);
    transform: translateY(-4px);
    box-shadow: 0 16px 40px rgba(139,92,246,0.12);
  }
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--purple), var(--pink));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: block;
  }
  .stat-label {
    font-size: 12px;
    color: var(--muted);
    margin-top: 4px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  /* ---- CERT & EXP ---- */
  .timeline {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  .timeline-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 20px;
    display: flex;
    gap: 16px;
    align-items: flex-start;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  .timeline-item:hover {
    border-color: rgba(139,92,246,0.4);
    transform: translateX(6px);
    box-shadow: 0 8px 30px rgba(139,92,246,0.1);
  }
  .timeline-icon {
    width: 40px; height: 40px;
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
    background: rgba(139,92,246,0.1);
    border: 1px solid rgba(139,92,246,0.2);
  }
  .timeline-title { font-size: 14px; font-weight: 600; color: var(--text); margin-bottom: 2px; }
  .timeline-sub { font-size: 12px; color: var(--muted); }

  /* ---- CONTACT ---- */
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }
  @media (max-width: 500px) { .contact-grid { grid-template-columns: 1fr; } }

  .contact-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 20px;
    text-decoration: none;
    color: var(--text);
    display: flex;
    align-items: center;
    gap: 14px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  .contact-card:hover {
    border-color: rgba(139,92,246,0.5);
    transform: translateY(-4px);
    box-shadow: 0 16px 40px rgba(139,92,246,0.15);
  }
  .contact-icon {
    width: 44px; height: 44px;
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
  }
  .contact-label { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: 0.08em; }
  .contact-value { font-size: 13px; font-weight: 500; color: var(--text); }

  /* ---- FOOTER ---- */
  footer {
    text-align: center;
    padding: 40px 0 60px;
    font-size: 12px;
    color: rgba(139,138,160,0.5);
    position: relative;
    z-index: 1;
  }
  footer .heart {
    color: var(--pink);
    animation: heartbeat 1.2s ease-in-out infinite;
    display: inline-block;
  }
  @keyframes heartbeat {
    0%,100% { transform: scale(1); }
    25% { transform: scale(1.2); }
    45% { transform: scale(0.95); }
  }

  /* Progress bar for skills */
  .progress-bar {
    width: 100%;
    height: 3px;
    background: rgba(255,255,255,0.05);
    border-radius: 2px;
    overflow: hidden;
    margin-top: 8px;
  }
  .progress-fill {
    height: 100%;
    border-radius: 2px;
    background: linear-gradient(90deg, var(--purple), var(--pink));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 1.2s cubic-bezier(0.16,1,0.3,1);
  }
  .progress-fill.animated { transform: scaleX(1); }

  /* divider */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(139,92,246,0.3), transparent);
    margin: 20px 0;
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>
<div class="bg-grid"></div>
<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<!-- HERO -->
<section class="hero">
  <div class="avatar-ring">
    <div class="avatar-inner">MJ</div>
  </div>
  <h1 class="hero-name">Manjula M J</h1>
  <p class="hero-sub">Java Full Stack Developer · Chennai, India</p>
  <div class="typing-wrap">
    <span class="typing-text" id="typingEl"></span>
  </div>
  <div class="socials">
    <a href="https://linkedin.com/in/manjula-m-j-02aa53356" class="social-pill" target="_blank">
      <span class="social-dot" style="background:#0077b5"></span> LinkedIn
    </a>
    <a href="mailto:manjulamanju1042004@gmail.com" class="social-pill">
      <span class="social-dot" style="background:#ea4335"></span> Gmail
    </a>
    <a href="https://github.com/Manjula1042004" class="social-pill" target="_blank">
      <span class="social-dot" style="background:#8b5cf6"></span> GitHub
    </a>
  </div>
  <div class="scroll-hint">
    <span>Scroll</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- ABOUT -->
<section>
  <div class="container">
    <div class="reveal">
      <div class="section-label">About</div>
      <h2 class="section-title">Who I <span>am</span></h2>
    </div>
    <div class="about-grid stagger">
      <div class="about-card">
        <span class="about-card-icon">🎓</span>
        <h4>Education</h4>
        <p>B.E. CSE — Vivekanandha College of Engineering for Women (2021–2025) · CGPA 7.56</p>
      </div>
      <div class="about-card">
        <span class="about-card-icon">🏅</span>
        <h4>Certified</h4>
        <p>Java Full Stack Developer · GUVI (HCL & IIT Madras) · Feb 2026</p>
      </div>
      <div class="about-card">
        <span class="about-card-icon">💼</span>
        <h4>Experience</h4>
        <p>ML Intern · Izeon Innovative Pvt Ltd, Chennai · June 2024</p>
      </div>
      <div class="about-card">
        <span class="about-card-icon">🚀</span>
        <h4>Building</h4>
        <p>Real-world full-stack apps using Spring Boot, Next.js, MySQL & Docker</p>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section>
  <div class="container">
    <div class="reveal">
      <div class="section-label">Skills</div>
      <h2 class="section-title">Tech <span>Stack</span></h2>
    </div>

    <div class="reveal" style="margin-bottom: 24px;">
      <p style="font-size: 12px; color: var(--muted); margin-bottom: 12px; font-family: 'JetBrains Mono', monospace; letter-spacing: 0.05em;">— BACKEND</p>
      <div style="display: flex; flex-direction: column; gap: 10px;">
        <div class="skill-row reveal-left">
          <div style="display:flex; justify-content: space-between; font-size:13px; margin-bottom:4px;">
            <span>Java · Spring Boot</span><span style="color:var(--purple)">90%</span>
          </div>
          <div class="progress-bar"><div class="progress-fill" data-width="0.90"></div></div>
        </div>
        <div class="skill-row reveal-left" style="transition-delay:0.1s">
          <div style="display:flex; justify-content: space-between; font-size:13px; margin-bottom:4px;">
            <span>JWT · Spring Security</span><span style="color:var(--purple)">80%</span>
          </div>
          <div class="progress-bar"><div class="progress-fill" data-width="0.80"></div></div>
        </div>
        <div class="skill-row reveal-left" style="transition-delay:0.2s">
          <div style="display:flex; justify-content: space-between; font-size:13px; margin-bottom:4px;">
            <span>MySQL · Spring Data JPA</span><span style="color:var(--purple)">82%</span>
          </div>
          <div class="progress-bar"><div class="progress-fill" data-width="0.82"></div></div>
        </div>
      </div>
    </div>

    <div class="reveal">
      <p style="font-size: 12px; color: var(--muted); margin-bottom: 12px; font-family: 'JetBrains Mono', monospace; letter-spacing: 0.05em;">— FRONTEND</p>
      <div style="display: flex; flex-direction: column; gap: 10px;">
        <div class="skill-row reveal-right">
          <div style="display:flex; justify-content: space-between; font-size:13px; margin-bottom:4px;">
            <span>HTML · CSS · JavaScript</span><span style="color:var(--cyan)">85%</span>
          </div>
          <div class="progress-bar"><div class="progress-fill" style="background: linear-gradient(90deg, var(--cyan), var(--purple));" data-width="0.85"></div></div>
        </div>
        <div class="skill-row reveal-right" style="transition-delay:0.1s">
          <div style="display:flex; justify-content: space-between; font-size:13px; margin-bottom:4px;">
            <span>TypeScript · Next.js</span><span style="color:var(--cyan)">75%</span>
          </div>
          <div class="progress-bar"><div class="progress-fill" style="background: linear-gradient(90deg, var(--cyan), var(--purple));" data-width="0.75"></div></div>
        </div>
      </div>
    </div>

    <div class="divider" style="margin: 32px 0;"></div>

    <div class="skills-grid stagger">
      <div class="skill-badge"><span class="skill-dot" style="background:#ea4335"></span>Java</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#6db33f"></span>Spring Boot</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#06b6d4"></span>TypeScript</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#000"></span>Next.js</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#005c84"></span>MySQL</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#2ca5e0"></span>Docker</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#3982ce"></span>Prisma</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#ff6c37"></span>Postman</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#f05032"></span>Git</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#8b5cf6"></span>WebSocket</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#000000"></span>JWT</div>
      <div class="skill-badge"><span class="skill-dot" style="background:#c71a36"></span>Maven</div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section>
  <div class="container">
    <div class="reveal">
      <div class="section-label">Work</div>
      <h2 class="section-title">Featured <span>Projects</span></h2>
    </div>

    <div class="project-card reveal">
      <div class="project-num">01 — FEATURED</div>
      <div class="project-header">
        <div class="project-title">Quiz Application</div>
        <div class="project-live"><div class="live-dot"></div> Live</div>
      </div>
      <p class="project-desc">Full-featured online quiz platform with real-time capabilities. JWT auth, role-based access (Admin, Teacher, Student), WebSocket live sessions, admin analytics dashboard, Docker containerization and Swagger docs.</p>
      <div class="project-tags">
        <span class="tag tag-purple">Spring Boot 3.2</span>
        <span class="tag tag-purple">Java 17</span>
        <span class="tag tag-cyan">MySQL</span>
        <span class="tag tag-green">WebSocket</span>
        <span class="tag tag-amber">Docker</span>
        <span class="tag tag-pink">Swagger</span>
      </div>
      <a href="https://online-quiz-app.onrender.com" target="_blank" class="project-link">View Live Demo <span>→</span></a>
    </div>

    <div class="project-card reveal">
      <div class="project-num">02 — FEATURED</div>
      <div class="project-header">
        <div class="project-title">Pastebin Lite</div>
        <div class="project-live"><div class="live-dot"></div> Live</div>
      </div>
      <p class="project-desc">Minimal, fast text-sharing web application. Built with modern TypeScript stack using Next.js and Prisma ORM. Deployed on Vercel for instant global availability.</p>
      <div class="project-tags">
        <span class="tag tag-cyan">TypeScript</span>
        <span class="tag tag-cyan">Next.js</span>
        <span class="tag tag-purple">Prisma</span>
      </div>
      <a href="https://pastebin-lite-sigma-three.vercel.app" target="_blank" class="project-link">View Live Demo <span>→</span></a>
    </div>

    <div class="project-card reveal">
      <div class="project-num">03</div>
      <div class="project-title" style="margin-bottom:10px;">Learning Management System</div>
      <p class="project-desc">Full-stack LMS with 3 user roles — Admin, Instructor, Student. Complete authentication and authorization flows for each role type.</p>
      <div class="project-tags">
        <span class="tag tag-purple">Spring Boot</span>
        <span class="tag tag-cyan">MySQL</span>
        <span class="tag tag-green">Java</span>
      </div>
    </div>

    <div class="project-card reveal">
      <div class="project-num">04</div>
      <div class="project-title" style="margin-bottom:10px;">Hotel Booking System</div>
      <p class="project-desc">End-to-end hotel reservation platform covering search, availability check, booking confirmation and cancellation with full relational DB schema.</p>
      <div class="project-tags">
        <span class="tag tag-purple">Spring Boot</span>
        <span class="tag tag-cyan">MySQL</span>
        <span class="tag tag-green">Java</span>
      </div>
    </div>

    <div class="project-card reveal">
      <div class="project-num">05</div>
      <div class="project-title" style="margin-bottom:10px;">Ecommerce REST API</div>
      <p class="project-desc">RESTful backend API for an ecommerce platform. Product, order, cart and user management with clean endpoint architecture.</p>
      <div class="project-tags">
        <span class="tag tag-purple">Spring Boot</span>
        <span class="tag tag-pink">REST API</span>
        <span class="tag tag-amber">Postman</span>
      </div>
    </div>
  </div>
</section>

<!-- STATS -->
<section>
  <div class="container">
    <div class="reveal">
      <div class="section-label">Numbers</div>
      <h2 class="section-title">By the <span>Numbers</span></h2>
    </div>
    <div class="stats-grid stagger">
      <div class="stat-card">
        <span class="stat-num" data-target="9">0</span>
        <span class="stat-label">Repositories</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-target="2">0</span>
        <span class="stat-label">Live Projects</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-target="4">0</span>
        <span class="stat-label">Languages</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-target="2">0</span>
        <span class="stat-label">Certifications</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-target="1">0</span>
        <span class="stat-label">Internship</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" style="font-size:24px" data-target="756">0</span>
        <span class="stat-label">CGPA (×100)</span>
      </div>
    </div>
  </div>
</section>

<!-- CERTS & EXP -->
<section>
  <div class="container">
    <div class="reveal">
      <div class="section-label">Background</div>
      <h2 class="section-title">Certs & <span>Experience</span></h2>
    </div>
    <div class="timeline">
      <div class="timeline-item reveal-left">
        <div class="timeline-icon">🏅</div>
        <div>
          <div class="timeline-title">Certified Java Full Stack Developer</div>
          <div class="timeline-sub">GUVI — HCL & IIT Madras · Feb 2026</div>
        </div>
      </div>
      <div class="timeline-item reveal-left" style="transition-delay:0.1s">
        <div class="timeline-icon">☕</div>
        <div>
          <div class="timeline-title">Java Programming Certification</div>
          <div class="timeline-sub">Aalan Techsoft · Jan 2025</div>
        </div>
      </div>
      <div class="timeline-item reveal-left" style="transition-delay:0.2s">
        <div class="timeline-icon">🤖</div>
        <div>
          <div class="timeline-title">Machine Learning Intern</div>
          <div class="timeline-sub">Izeon Innovative Pvt Ltd, Chennai · June 2024 · Book Sales Analysis & Forecasting</div>
        </div>
      </div>
      <div class="timeline-item reveal-left" style="transition-delay:0.3s">
        <div class="timeline-icon">🎓</div>
        <div>
          <div class="timeline-title">B.E. Computer Science & Engineering</div>
          <div class="timeline-sub">Vivekanandha College of Engineering for Women · 2021–2025 · CGPA 7.56</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section>
  <div class="container">
    <div class="reveal">
      <div class="section-label">Connect</div>
      <h2 class="section-title">Get in <span>Touch</span></h2>
    </div>
    <div class="contact-grid stagger">
      <a href="https://linkedin.com/in/manjula-m-j-02aa53356" target="_blank" class="contact-card">
        <div class="contact-icon" style="background:rgba(0,119,181,0.15);">💼</div>
        <div>
          <div class="contact-label">LinkedIn</div>
          <div class="contact-value">manjula-m-j-02aa53356</div>
        </div>
      </a>
      <a href="mailto:manjulamanju1042004@gmail.com" class="contact-card">
        <div class="contact-icon" style="background:rgba(234,67,53,0.15);">📧</div>
        <div>
          <div class="contact-label">Email</div>
          <div class="contact-value">manjulamanju1042004@gmail.com</div>
        </div>
      </a>
      <a href="https://github.com/Manjula1042004" target="_blank" class="contact-card">
        <div class="contact-icon" style="background:rgba(139,92,246,0.15);">💻</div>
        <div>
          <div class="contact-label">GitHub</div>
          <div class="contact-value">Manjula1042004</div>
        </div>
      </a>
      <div class="contact-card" style="cursor:default;">
        <div class="contact-icon" style="background:rgba(16,185,129,0.15);">📍</div>
        <div>
          <div class="contact-label">Location</div>
          <div class="contact-value">Chennai, Tamil Nadu, India</div>
        </div>
      </div>
    </div>
  </div>
</section>

<footer>
  <p>Designed with <span class="heart">♥</span> by Manjula M J &nbsp;·&nbsp; Open to opportunities</p>
</footer>

<script>
/* ---- Cursor ---- */
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursorRing');
let mx = 0, my = 0, rx = 0, ry = 0;
document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; cursor.style.left = mx+'px'; cursor.style.top = my+'px'; });
function animRing() {
  rx += (mx - rx) * 0.12;
  ry += (my - ry) *.12;
  ring.style.left = rx+'px'; ring.style.top = ry+'px';
  requestAnimationFrame(animRing);
}
animRing();
document.querySelectorAll('a, button, .project-card, .about-card, .skill-badge').forEach(el => {
  el.addEventListener('mouseenter', () => { cursor.style.width = '20px'; cursor.style.height = '20px'; ring.style.width = '50px'; ring.style.height = '50px'; });
  el.addEventListener('mouseleave', () => { cursor.style.width = '12px'; cursor.style.height = '12px'; ring.style.width = '36px'; ring.style.height = '36px'; });
});

/* ---- Typing ---- */
const phrases = [
  'Java Full Stack Developer',
  'Spring Boot · Next.js · MySQL',
  'Building real-world apps 🚀',
  'Open to opportunities ✨'
];
let pi = 0, ci = 0, deleting = false;
const el = document.getElementById('typingEl');
function type() {
  const word = phrases[pi];
  if (!deleting) {
    el.textContent = word.slice(0, ++ci);
    if (ci === word.length) { deleting = true; setTimeout(type, 1600); return; }
  } else {
    el.textContent = word.slice(0, --ci);
    if (ci === 0) { deleting = false; pi = (pi+1) % phrases.length; }
  }
  setTimeout(type, deleting ? 40 : 80);
}
type();

/* ---- Scroll reveal ---- */
const revealEls = document.querySelectorAll('.reveal, .reveal-left, .reveal-right, .reveal-scale, .stagger');
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      /* animate progress bars */
      e.target.querySelectorAll('.progress-fill').forEach(bar => bar.classList.add('animated'));
      /* animate counters */
      e.target.querySelectorAll('[data-target]').forEach(counter => animateCount(counter));
      observer.unobserve(e.target);
    }
  });
}, { threshold: 0.12 });
revealEls.forEach(el => observer.observe(el));

/* also trigger progress bars inside already-visible parents */
document.querySelectorAll('.progress-fill').forEach(bar => {
  const parent = bar.closest('.reveal, .reveal-left, .reveal-right');
  if (!parent) return;
  const barObserver = new IntersectionObserver(entries => {
    if (entries[0].isIntersecting) {
      setTimeout(() => bar.classList.add('animated'), 200);
      barObserver.unobserve(bar);
    }
  }, { threshold: 0.5 });
  barObserver.observe(bar);
});

/* ---- Counter animation ---- */
function animateCount(el) {
  const target = parseInt(el.dataset.target);
  const duration = 1200;
  const start = performance.now();
  function step(now) {
    const p = Math.min((now - start) / duration, 1);
    const ease = 1 - Math.pow(1 - p, 3);
    el.textContent = Math.round(ease * target);
    if (p < 1) requestAnimationFrame(step);
  }
  requestAnimationFrame(step);
}

/* Also observe stat cards individually */
document.querySelectorAll('.stat-card').forEach(card => {
  const cObs = new IntersectionObserver(entries => {
    if (entries[0].isIntersecting) {
      card.querySelectorAll('[data-target]').forEach(animateCount);
      cObs.unobserve(card);
    }
  }, { threshold: 0.5 });
  cObs.observe(card);
});
</script>
</body>
</html>
