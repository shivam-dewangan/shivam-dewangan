<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shivam Dewangan — MERN & DevSecOps Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050810;
    --surface: #0c1120;
    --surface2: #111827;
    --accent: #00f5c4;
    --accent2: #7c3aed;
    --accent3: #f59e0b;
    --text: #e2e8f0;
    --muted: #64748b;
    --border: rgba(0,245,196,0.12);
    --glow: 0 0 30px rgba(0,245,196,0.25);
  }

  * { margin:0; padding:0; box-sizing:border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom Cursor */
  #cursor {
    width: 12px; height: 12px;
    background: var(--accent);
    border-radius: 50%;
    position: fixed; pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
    transition: width 0.2s, height 0.2s, background 0.2s;
    mix-blend-mode: screen;
  }
  #cursor-ring {
    width: 40px; height: 40px;
    border: 1.5px solid rgba(0,245,196,0.5);
    border-radius: 50%;
    position: fixed; pointer-events: none;
    z-index: 9998;
    transform: translate(-50%, -50%);
    transition: all 0.12s ease-out;
  }
  body:hover #cursor { opacity: 1; }

  /* Grid BG */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image:
      linear-gradient(rgba(0,245,196,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,196,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none; z-index: 0;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 20px 48px;
    display: flex; align-items: center; justify-content: space-between;
    background: rgba(5,8,16,0.7);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    font-family: 'Space Mono', monospace;
    font-size: 14px;
    color: var(--accent);
    letter-spacing: 2px;
    text-transform: uppercase;
  }
  .nav-links { display: flex; gap: 32px; list-style: none; }
  .nav-links a {
    font-size: 13px; font-weight: 600;
    color: var(--muted); text-decoration: none;
    letter-spacing: 1px; text-transform: uppercase;
    transition: color 0.2s;
    position: relative;
  }
  .nav-links a::after {
    content: ''; position: absolute;
    bottom: -4px; left: 0; right: 100%;
    height: 1px; background: var(--accent);
    transition: right 0.3s;
  }
  .nav-links a:hover { color: var(--accent); }
  .nav-links a:hover::after { right: 0; }

  /* HERO */
  #hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 120px 48px 80px;
    position: relative; z-index: 1;
  }
  .hero-inner { max-width: 900px; }

  .hero-tag {
    display: inline-flex; align-items: center; gap: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 11px; color: var(--accent);
    letter-spacing: 3px; text-transform: uppercase;
    margin-bottom: 28px;
  }
  .hero-tag::before {
    content: ''; width: 32px; height: 1px; background: var(--accent);
  }

  h1.hero-name {
    font-size: clamp(52px, 8vw, 96px);
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -2px;
    margin-bottom: 24px;
  }
  h1.hero-name span {
    background: linear-gradient(135deg, var(--accent) 0%, #00b4ff 100%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-desc {
    font-size: 18px; color: var(--muted);
    max-width: 560px; line-height: 1.7;
    margin-bottom: 48px;
    font-weight: 400;
  }

  .hero-motto {
    font-family: 'Space Mono', monospace;
    font-size: 13px; color: var(--accent);
    border-left: 2px solid var(--accent);
    padding-left: 16px; margin-bottom: 48px;
    opacity: 0.8;
  }

  .hero-ctas { display: flex; gap: 16px; flex-wrap: wrap; }
  .btn-primary {
    padding: 14px 32px;
    background: var(--accent);
    color: #050810;
    font-weight: 700; font-size: 13px;
    letter-spacing: 1px; text-transform: uppercase;
    text-decoration: none;
    transition: all 0.25s;
    clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
  }
  .btn-primary:hover {
    background: #fff;
    box-shadow: var(--glow);
    transform: translateY(-2px);
  }
  .btn-ghost {
    padding: 13px 32px;
    border: 1px solid var(--border);
    color: var(--text);
    font-weight: 600; font-size: 13px;
    letter-spacing: 1px; text-transform: uppercase;
    text-decoration: none;
    transition: all 0.25s;
    clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
  }
  .btn-ghost:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

  /* Animated orbs */
  .orb {
    position: absolute; border-radius: 50%;
    pointer-events: none; filter: blur(80px); opacity: 0.15;
    animation: float 8s ease-in-out infinite;
  }
  .orb1 { width:500px; height:500px; background: var(--accent2); top:-200px; right:-100px; animation-delay: 0s; }
  .orb2 { width:300px; height:300px; background: var(--accent); bottom:0; right:200px; animation-delay: 3s; }
  @keyframes float {
    0%,100% { transform: translateY(0px) scale(1); }
    50% { transform: translateY(-30px) scale(1.05); }
  }

  /* SECTIONS */
  section { padding: 100px 48px; position: relative; z-index: 1; }
  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px; color: var(--accent);
    letter-spacing: 4px; text-transform: uppercase;
    display: flex; align-items: center; gap: 12px;
    margin-bottom: 16px;
  }
  .section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }
  h2.section-title {
    font-size: clamp(32px, 5vw, 52px);
    font-weight: 800; letter-spacing: -1px;
    margin-bottom: 60px;
  }

  /* TECH STACK */
  #stack { background: var(--surface); }

  .stack-tabs {
    display: flex; gap: 4px; flex-wrap: wrap;
    margin-bottom: 40px;
  }
  .stack-tab {
    padding: 8px 20px;
    font-size: 12px; font-weight: 700;
    letter-spacing: 1px; text-transform: uppercase;
    cursor: pointer; border: 1px solid transparent;
    color: var(--muted); background: transparent;
    font-family: 'Syne', sans-serif;
    transition: all 0.2s;
  }
  .stack-tab:hover { color: var(--text); border-color: var(--border); }
  .stack-tab.active { color: var(--bg); background: var(--accent); border-color: var(--accent); }

  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 12px;
  }
  .tech-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    padding: 20px 16px;
    text-align: center;
    cursor: pointer;
    transition: all 0.25s;
    position: relative; overflow: hidden;
  }
  .tech-card::before {
    content: ''; position: absolute;
    inset: 0; opacity: 0;
    background: linear-gradient(135deg, rgba(0,245,196,0.06), transparent);
    transition: opacity 0.3s;
  }
  .tech-card:hover { border-color: var(--accent); transform: translateY(-4px); box-shadow: var(--glow); }
  .tech-card:hover::before { opacity: 1; }
  .tech-icon { font-size: 28px; margin-bottom: 10px; display: block; }
  .tech-name { font-size: 12px; font-weight: 700; letter-spacing: 0.5px; color: var(--text); }
  .tech-type { font-size: 10px; color: var(--muted); margin-top: 4px; font-family: 'Space Mono', monospace; }

  .stack-panel { display: none; }
  .stack-panel.active { display: block; }

  /* PRINCIPLES */
  #principles { }
  .principles-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 24px;
  }
  .principle-card {
    padding: 36px 28px;
    border: 1px solid var(--border);
    background: var(--surface);
    position: relative; overflow: hidden;
    transition: all 0.3s;
  }
  .principle-card::after {
    content: ''; position: absolute;
    bottom: 0; left: 0; right: 100%;
    height: 2px; background: var(--accent);
    transition: right 0.4s;
  }
  .principle-card:hover { border-color: rgba(0,245,196,0.3); transform: translateY(-4px); }
  .principle-card:hover::after { right: 0; }
  .p-number {
    font-family: 'Space Mono', monospace;
    font-size: 48px; font-weight: 700;
    color: rgba(0,245,196,0.08);
    position: absolute; top: 16px; right: 20px;
    line-height: 1;
  }
  .p-icon { font-size: 32px; margin-bottom: 16px; }
  .p-title { font-size: 18px; font-weight: 700; margin-bottom: 10px; }
  .p-desc { font-size: 14px; color: var(--muted); line-height: 1.6; }

  /* JOURNEY / TIMELINE */
  #journey { background: var(--surface); }
  .timeline { position: relative; padding-left: 32px; }
  .timeline::before {
    content: ''; position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 1px; background: var(--border);
  }
  .timeline-item {
    position: relative; padding: 0 0 48px 40px;
    opacity: 0; transform: translateX(-20px);
    transition: all 0.5s;
  }
  .timeline-item.visible { opacity: 1; transform: none; }
  .timeline-dot {
    position: absolute; left: -32px;
    width: 12px; height: 12px;
    border-radius: 50%; background: var(--bg);
    border: 2px solid var(--accent);
    top: 6px;
    box-shadow: 0 0 12px rgba(0,245,196,0.4);
  }
  .t-date {
    font-family: 'Space Mono', monospace;
    font-size: 10px; color: var(--accent);
    letter-spacing: 2px; text-transform: uppercase;
    margin-bottom: 8px;
  }
  .t-title { font-size: 20px; font-weight: 700; margin-bottom: 8px; }
  .t-desc { font-size: 14px; color: var(--muted); line-height: 1.6; max-width: 600px; }

  /* MOTTO BANNER */
  #motto-banner {
    padding: 60px 48px;
    background: var(--accent);
    overflow: hidden; position: relative;
  }
  .motto-scroll {
    display: flex; gap: 80px;
    white-space: nowrap;
    animation: scroll-left 12s linear infinite;
  }
  .motto-word {
    font-size: clamp(28px, 4vw, 48px);
    font-weight: 800;
    color: var(--bg);
    letter-spacing: -1px;
    flex-shrink: 0;
  }
  .motto-sep {
    font-size: 24px;
    color: rgba(5,8,16,0.4);
    flex-shrink: 0; align-self: center;
  }
  @keyframes scroll-left {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  /* CONTACT */
  #contact { text-align: center; }
  .contact-inner { max-width: 600px; margin: 0 auto; }
  .contact-inner p { font-size: 18px; color: var(--muted); line-height: 1.7; margin-bottom: 48px; }
  .contact-links { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; }
  .contact-link {
    display: flex; align-items: center; gap: 10px;
    padding: 14px 28px;
    border: 1px solid var(--border);
    color: var(--text); text-decoration: none;
    font-weight: 600; font-size: 13px;
    letter-spacing: 1px; text-transform: uppercase;
    transition: all 0.25s;
  }
  .contact-link:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-3px); box-shadow: var(--glow); }
  .contact-link svg { width: 16px; height: 16px; fill: currentColor; }

  /* FOOTER */
  footer {
    padding: 32px 48px;
    border-top: 1px solid var(--border);
    display: flex; justify-content: space-between; align-items: center;
    font-family: 'Space Mono', monospace; font-size: 11px; color: var(--muted);
  }

  /* FADE IN */
  .fade-in {
    opacity: 0; transform: translateY(24px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .fade-in.visible { opacity: 1; transform: none; }

  /* TOOLTIP */
  .tooltip {
    position: fixed; z-index: 1000;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text);
    padding: 8px 14px;
    font-size: 12px; font-family: 'Space Mono', monospace;
    pointer-events: none; opacity: 0;
    transition: opacity 0.15s;
    white-space: nowrap;
  }

  /* Status badge */
  .status-badge {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 14px;
    background: rgba(0,245,196,0.1);
    border: 1px solid rgba(0,245,196,0.2);
    border-radius: 0;
    font-family: 'Space Mono', monospace;
    font-size: 10px; color: var(--accent);
    letter-spacing: 2px; text-transform: uppercase;
    margin-bottom: 32px;
  }
  .status-dot {
    width: 6px; height: 6px;
    border-radius: 50%; background: var(--accent);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0%,100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.4; transform: scale(0.8); }
  }

  /* Glitch text effect on hover */
  .glitch {
    position: relative;
    display: inline-block;
  }
  .glitch:hover {
    animation: glitch 0.3s steps(2) forwards;
  }
  @keyframes glitch {
    0% { text-shadow: 2px 0 var(--accent2), -2px 0 var(--accent); }
    25% { text-shadow: -2px 0 var(--accent2), 2px 0 var(--accent); }
    50% { text-shadow: 2px 2px var(--accent2), -2px -2px var(--accent); }
    75% { text-shadow: -2px 2px var(--accent2), 2px -2px var(--accent); }
    100% { text-shadow: none; }
  }

  @media (max-width: 768px) {
    nav { padding: 16px 24px; }
    .nav-links { display: none; }
    section, #hero { padding: 80px 24px; }
    footer { flex-direction: column; gap: 8px; text-align: center; }
    #motto-banner { padding: 40px 24px; }
  }
</style>
</head>
<body>

<div id="cursor"></div>
<div id="cursor-ring"></div>
<div class="tooltip" id="tooltip"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">SD_</div>
  <ul class="nav-links">
    <li><a href="#stack">Stack</a></li>
    <li><a href="#principles">Principles</a></li>
    <li><a href="#journey">Journey</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>
  <div class="hero-inner">
    <div class="status-badge"><span class="status-dot"></span> Available for opportunities</div>
    <div class="hero-tag">Portfolio 2025</div>
    <h1 class="hero-name glitch">Shivam<br><span>Dewangan</span></h1>
    <p class="hero-desc">
      MERN Stack Developer & DevSecOps Engineer building scalable, secure, cloud-native systems that don't break at 3am.
    </p>
    <div class="hero-motto">⚡ Automate → Optimize → Secure → Scale</div>
    <div class="hero-ctas">
      <a href="mailto:shivamdewangan310@gmail.com" class="btn-primary">Get in Touch</a>
      <a href="https://linkedin.com/in/shivamdewangan2005" class="btn-ghost" target="_blank">LinkedIn ↗</a>
    </div>
  </div>
</section>

<!-- MOTTO BANNER -->
<div id="motto-banner">
  <div class="motto-scroll" id="motto-scroll">
    <span class="motto-word">Automate</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Optimize</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Secure</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Scale</span>
    <span class="motto-sep">//</span>
    <span class="motto-word">Automate</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Optimize</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Secure</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Scale</span>
    <span class="motto-sep">//</span>
    <span class="motto-word">Automate</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Optimize</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Secure</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Scale</span>
    <span class="motto-sep">//</span>
    <span class="motto-word">Automate</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Optimize</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Secure</span>
    <span class="motto-sep">→</span>
    <span class="motto-word">Scale</span>
    <span class="motto-sep">//</span>
  </div>
</div>

<!-- TECH STACK -->
<section id="stack">
  <div class="section-label">02 — Tech Stack</div>
  <h2 class="section-title fade-in">Tools of the Trade</h2>

  <div class="stack-tabs">
    <button class="stack-tab active" data-panel="all">All</button>
    <button class="stack-tab" data-panel="core">Core</button>
    <button class="stack-tab" data-panel="mern">MERN</button>
    <button class="stack-tab" data-panel="cloud">Cloud</button>
    <button class="stack-tab" data-panel="devops">DevOps</button>
    <button class="stack-tab" data-panel="security">Security</button>
    <button class="stack-tab" data-panel="monitoring">Monitoring</button>
  </div>

  <div class="stack-panel active" id="panel-all">
    <div class="stack-grid" id="grid-all"></div>
  </div>
  <div class="stack-panel" id="panel-core">
    <div class="stack-grid" id="grid-core"></div>
  </div>
  <div class="stack-panel" id="panel-mern">
    <div class="stack-grid" id="grid-mern"></div>
  </div>
  <div class="stack-panel" id="panel-cloud">
    <div class="stack-grid" id="grid-cloud"></div>
  </div>
  <div class="stack-panel" id="panel-devops">
    <div class="stack-grid" id="grid-devops"></div>
  </div>
  <div class="stack-panel" id="panel-security">
    <div class="stack-grid" id="grid-security"></div>
  </div>
  <div class="stack-panel" id="panel-monitoring">
    <div class="stack-grid" id="grid-monitoring"></div>
  </div>
</section>

<!-- PRINCIPLES -->
<section id="principles">
  <div class="section-label">03 — Engineering Principles</div>
  <h2 class="section-title fade-in">How I Build</h2>
  <div class="principles-grid">
    <div class="principle-card fade-in">
      <span class="p-number">01</span>
      <div class="p-icon">🔐</div>
      <div class="p-title">Security First</div>
      <p class="p-desc">DevSecOps integrated into every pipeline stage — Trivy, SonarQube, OWASP ZAP, Snyk — not bolted on at the end.</p>
    </div>
    <div class="principle-card fade-in">
      <span class="p-number">02</span>
      <div class="p-icon">⚡</div>
      <div class="p-title">Automate Everything</div>
      <p class="p-desc">If you're doing it twice, it should be a script. CI/CD pipelines, infrastructure provisioning, testing — all automated.</p>
    </div>
    <div class="principle-card fade-in">
      <span class="p-number">03</span>
      <div class="p-icon">☁️</div>
      <div class="p-title">Cloud-Native by Design</div>
      <p class="p-desc">Applications built for the cloud from day one — containerized, distributed, and resilient across AWS & Azure.</p>
    </div>
    <div class="principle-card fade-in">
      <span class="p-number">04</span>
      <div class="p-icon">📊</div>
      <div class="p-title">Observe, Don't Guess</div>
      <p class="p-desc">Full observability stack: Prometheus metrics, Grafana dashboards, ELK logging. You can't fix what you can't measure.</p>
    </div>
    <div class="principle-card fade-in">
      <span class="p-number">05</span>
      <div class="p-icon">🏗️</div>
      <div class="p-title">Infrastructure as Code</div>
      <p class="p-desc">Terraform for immutable infra. GitOps workflows with ArgoCD. No snowflakes, no drift, no surprises.</p>
    </div>
    <div class="principle-card fade-in">
      <span class="p-number">06</span>
      <div class="p-icon">🚀</div>
      <div class="p-title">Ship Fast, Safely</div>
      <p class="p-desc">Trunk-based development, feature flags, canary deployments. Velocity without sacrificing stability.</p>
    </div>
  </div>
</section>

<!-- JOURNEY -->
<section id="journey">
  <div class="section-label">04 — Journey</div>
  <h2 class="section-title fade-in">The Path So Far</h2>
  <div class="timeline">
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="t-date">Foundation</div>
      <div class="t-title">Mastered the MERN Stack</div>
      <p class="t-desc">Built full-stack applications with MongoDB, Express, React, and Node.js. Introduced Redux for state management and JWT for secure auth flows.</p>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="t-date">Level Up</div>
      <div class="t-title">Containerization & Orchestration</div>
      <p class="t-desc">Deep-dived into Docker and Kubernetes. Started deploying production containerized workloads, writing Helm charts, and managing multi-container systems.</p>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="t-date">Cloud Journey</div>
      <div class="t-title">AWS & Azure Infrastructure</div>
      <p class="t-desc">Deployed distributed, highly-available apps on AWS and Azure. Learned cloud-native patterns: auto-scaling, load balancing, managed databases, and CDN configs.</p>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="t-date">Specialization</div>
      <div class="t-title">DevSecOps Engineering</div>
      <p class="t-desc">Integrated security scanning into CI/CD pipelines. Trivy for containers, SonarQube for code quality, OWASP ZAP for DAST, Snyk for dependency auditing.</p>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="t-date">Now</div>
      <div class="t-title">Building Production-Ready Systems</div>
      <p class="t-desc">Combining full observability (Prometheus + Grafana + ELK), GitOps with ArgoCD, IaC with Terraform, and end-to-end security for production-grade architectures.</p>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-label">05 — Contact</div>
  <div class="contact-inner">
    <h2 class="section-title fade-in">Let's Build<br><span style="color: var(--accent)">Something Real</span></h2>
    <p>Open to roles, collaborations, and interesting engineering challenges. If you're building something that needs to be secure, scalable, and automated — let's talk.</p>
    <div class="contact-links">
      <a href="mailto:shivamdewangan310@gmail.com" class="contact-link">
        <svg viewBox="0 0 24 24"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
        Email Me
      </a>
      <a href="https://linkedin.com/in/shivamdewangan2005" target="_blank" class="contact-link">
        <svg viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.32 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.79M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg>
        LinkedIn
      </a>
      <a href="https://github.com/shivam-dewangan" target="_blank" class="contact-link">
        <svg viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        GitHub
      </a>
    </div>
  </div>
</section>

<footer>
  <span>© 2025 Shivam Dewangan</span>
  <span>MERN · DevSecOps · Cloud-Native</span>
</footer>

<script>
// Cursor
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursor-ring');
let mx = 0, my = 0, rx = 0, ry = 0;
document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; });
function animateCursor() {
  rx += (mx - rx) * 0.15;
  ry += (my - ry) * 0.15;
  cursor.style.left = mx + 'px'; cursor.style.top = my + 'px';
  ring.style.left = rx + 'px'; ring.style.top = ry + 'px';
  requestAnimationFrame(animateCursor);
}
animateCursor();
document.querySelectorAll('a, button, .tech-card, .principle-card').forEach(el => {
  el.addEventListener('mouseenter', () => {
    cursor.style.width = '20px'; cursor.style.height = '20px';
    ring.style.width = '60px'; ring.style.height = '60px';
    ring.style.borderColor = 'rgba(0,245,196,0.8)';
  });
  el.addEventListener('mouseleave', () => {
    cursor.style.width = '12px'; cursor.style.height = '12px';
    ring.style.width = '40px'; ring.style.height = '40px';
    ring.style.borderColor = 'rgba(0,245,196,0.5)';
  });
});

// Tech data
const techData = {
  core: [
    { icon: '🟨', name: 'JavaScript', type: 'Language' },
    { icon: '🔷', name: 'TypeScript', type: 'Language' },
    { icon: '🐍', name: 'Python', type: 'Language' },
    { icon: '💲', name: 'Bash', type: 'Scripting' },
  ],
  mern: [
    { icon: '🍃', name: 'MongoDB', type: 'Database' },
    { icon: '🚂', name: 'Express.js', type: 'Framework' },
    { icon: '⚛️', name: 'React', type: 'UI Library' },
    { icon: '🟩', name: 'Node.js', type: 'Runtime' },
    { icon: '🔴', name: 'Redux', type: 'State Mgmt' },
    { icon: '🔑', name: 'JWT', type: 'Auth' },
    { icon: '🔌', name: 'Socket.io', type: 'Real-time' },
  ],
  cloud: [
    { icon: '☁️', name: 'AWS', type: 'Cloud' },
    { icon: '🔵', name: 'Azure', type: 'Cloud' },
    { icon: '▲', name: 'Vercel', type: 'Deploy' },
    { icon: '🌐', name: 'Netlify', type: 'Deploy' },
    { icon: '🌿', name: 'Nginx', type: 'Web Server' },
  ],
  devops: [
    { icon: '🐳', name: 'Docker', type: 'Container' },
    { icon: '☸️', name: 'Kubernetes', type: 'Orchestration' },
    { icon: '🏗️', name: 'Terraform', type: 'IaC' },
    { icon: '🤖', name: 'Jenkins', type: 'CI/CD' },
    { icon: '⚙️', name: 'GitHub Actions', type: 'CI/CD' },
    { icon: '🐙', name: 'ArgoCD', type: 'GitOps' },
  ],
  security: [
    { icon: '🕷️', name: 'OWASP ZAP', type: 'DAST' },
    { icon: '🔬', name: 'Trivy', type: 'Scanner' },
    { icon: '🎯', name: 'SonarQube', type: 'Code Quality' },
    { icon: '🐍', name: 'Snyk', type: 'Dependency Audit' },
  ],
  monitoring: [
    { icon: '🔥', name: 'Prometheus', type: 'Metrics' },
    { icon: '📊', name: 'Grafana', type: 'Dashboards' },
    { icon: '🦔', name: 'ELK Stack', type: 'Logging' },
  ]
};

function buildCard(tech, category) {
  const div = document.createElement('div');
  div.className = 'tech-card';
  div.dataset.tooltip = `${tech.name} — ${tech.type}`;
  div.innerHTML = `<span class="tech-icon">${tech.icon}</span><div class="tech-name">${tech.name}</div><div class="tech-type">${tech.type}</div>`;
  return div;
}

// Populate grids
const allTechs = [];
for (const [cat, items] of Object.entries(techData)) {
  const grid = document.getElementById('grid-' + cat);
  items.forEach(t => {
    grid.appendChild(buildCard(t));
    allTechs.push(t);
  });
}
const allGrid = document.getElementById('grid-all');
allTechs.forEach(t => allGrid.appendChild(buildCard(t)));

// Tab switching
document.querySelectorAll('.stack-tab').forEach(tab => {
  tab.addEventListener('click', () => {
    document.querySelectorAll('.stack-tab').forEach(t => t.classList.remove('active'));
    document.querySelectorAll('.stack-panel').forEach(p => p.classList.remove('active'));
    tab.classList.add('active');
    document.getElementById('panel-' + tab.dataset.panel).classList.add('active');
  });
});

// Tooltip
const tooltip = document.getElementById('tooltip');
document.addEventListener('mouseover', e => {
  const card = e.target.closest('.tech-card');
  if (card && card.dataset.tooltip) {
    tooltip.textContent = card.dataset.tooltip;
    tooltip.style.opacity = '1';
  }
});
document.addEventListener('mouseout', e => {
  if (e.target.closest('.tech-card')) tooltip.style.opacity = '0';
});
document.addEventListener('mousemove', e => {
  tooltip.style.left = (e.clientX + 16) + 'px';
  tooltip.style.top = (e.clientY - 10) + 'px';
});

// Scroll animations
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      // Stagger children if it's principles-grid
      if (e.target.classList.contains('section-title') || e.target.classList.contains('timeline-item')) return;
    }
  });
}, { threshold: 0.15 });

document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
document.querySelectorAll('.timeline-item').forEach((el, i) => {
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 150);
      }
    });
  }, { threshold: 0.2 });
  obs.observe(el);
});

// Stagger principle cards
const principleObs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      const cards = e.target.querySelectorAll('.principle-card');
      cards.forEach((c, i) => {
        setTimeout(() => c.classList.add('visible'), i * 100);
      });
    }
  });
}, { threshold: 0.1 });
const pg = document.querySelector('.principles-grid');
if (pg) principleObs.observe(pg);

// Add visible class directly for fade-in using intersection observer
const fadeObs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) e.target.classList.add('visible');
  });
}, { threshold: 0.1 });
document.querySelectorAll('.fade-in').forEach(el => fadeObs.observe(el));

// Principle cards start invisible
document.querySelectorAll('.principle-card').forEach(c => c.style.opacity = '0');
const pcObs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      const cards = document.querySelectorAll('.principle-card');
      cards.forEach((c, i) => {
        setTimeout(() => { c.style.opacity = '1'; c.style.transform = 'none'; }, i * 100);
      });
    }
  });
}, { threshold: 0.2 });
if (pg) pcObs.observe(pg);
document.querySelectorAll('.principle-card').forEach(c => {
  c.style.transform = 'translateY(20px)';
  c.style.transition = 'opacity 0.5s ease, transform 0.5s ease, border-color 0.3s, box-shadow 0.3s';
});
</script>
</body>
</html>
