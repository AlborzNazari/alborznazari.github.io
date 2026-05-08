
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Alborz Nazari — Cybersecurity Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;900&family=JetBrains+Mono:wght@300;400;600&display=swap" rel="stylesheet">
<style>
:root {
  --green: #2db84d;
  --green-dim: #1a7a2e;
  --green-glow: rgba(45,184,77,0.18);
  --green-faint: rgba(45,184,77,0.06);
  --bg: #060e08;
  --bg2: #0a160c;
  --bg3: #0d1f10;
  --text: #e8f5ea;
  --text-dim: #7aaa84;
  --text-muted: #3a6645;
  --border: rgba(45,184,77,0.18);
  --border-bright: rgba(45,184,77,0.45);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Poppins', sans-serif;
  overflow-x: hidden;
  cursor: none;
}

/* Custom cursor */
#cursor {
  position: fixed;
  width: 10px; height: 10px;
  background: var(--green);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9999;
  transition: transform 0.1s;
  mix-blend-mode: screen;
}
#cursor-ring {
  position: fixed;
  width: 36px; height: 36px;
  border: 1px solid rgba(45,184,77,0.5);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9998;
  transition: transform 0.18s, width 0.2s, height 0.2s;
}

/* Canvas BG */
#bg-canvas {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  z-index: 0;
  opacity: 0.55;
}

/* NAV */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  padding: 1.2rem 3rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid rgba(45,184,77,0.08);
  backdrop-filter: blur(18px);
  background: rgba(6,14,8,0.7);
}
.nav-logo {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.85rem;
  color: var(--green);
  letter-spacing: 0.12em;
  text-decoration: none;
}
.nav-links { display: flex; gap: 2.2rem; list-style: none; }
.nav-links a {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem;
  color: var(--text-dim);
  text-decoration: none;
  letter-spacing: 0.1em;
  transition: color 0.2s;
  position: relative;
}
.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -3px; left: 0; right: 0;
  height: 1px;
  background: var(--green);
  transform: scaleX(0);
  transition: transform 0.25s;
}
.nav-links a:hover { color: var(--green); }
.nav-links a:hover::after { transform: scaleX(1); }

/* SECTIONS */
section {
  position: relative;
  z-index: 1;
}

/* HERO */
#hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 8rem 2rem 4rem;
}
.hero-eyebrow {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem;
  color: var(--green);
  letter-spacing: 0.25em;
  margin-bottom: 1.8rem;
  opacity: 0;
  animation: fadeUp 0.8s 0.2s forwards;
}
.hero-name {
  font-size: clamp(3.5rem, 8vw, 7.5rem);
  font-weight: 900;
  letter-spacing: -0.02em;
  line-height: 1;
  margin-bottom: 1.2rem;
  opacity: 0;
  animation: fadeUp 0.9s 0.4s forwards;
}
.hero-name span { color: var(--green); }
.hero-role {
  font-family: 'JetBrains Mono', monospace;
  font-size: clamp(0.85rem, 2vw, 1.1rem);
  color: var(--text-dim);
  letter-spacing: 0.08em;
  margin-bottom: 2.8rem;
  opacity: 0;
  animation: fadeUp 0.9s 0.6s forwards;
}

/* Terminal */
.terminal {
  background: rgba(10,22,12,0.9);
  border: 1px solid var(--border-bright);
  border-radius: 10px;
  width: min(680px, 92vw);
  text-align: left;
  overflow: hidden;
  opacity: 0;
  animation: fadeUp 0.9s 0.8s forwards;
  box-shadow: 0 0 60px rgba(45,184,77,0.08), 0 0 120px rgba(45,184,77,0.04);
}
.terminal-bar {
  background: rgba(20,42,22,0.9);
  padding: 0.65rem 1rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  border-bottom: 1px solid var(--border);
}
.t-dot { width: 10px; height: 10px; border-radius: 50%; }
.t-dot.r { background: #ff5f57; }
.t-dot.y { background: #febc2e; }
.t-dot.g { background: #28c840; }
.terminal-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.7rem;
  color: var(--text-muted);
  margin-left: auto; margin-right: auto;
  letter-spacing: 0.08em;
}
.terminal-body { padding: 1.4rem 1.6rem; }
.terminal-body p {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.78rem;
  line-height: 1.9;
  color: var(--text-dim);
}
.terminal-body .prompt { color: var(--green); margin-right: 0.5rem; }
.terminal-body .val { color: var(--text); }
.terminal-body .key { color: #6bd98a; }
.terminal-body .comment { color: var(--text-muted); }
.cursor-blink {
  display: inline-block;
  width: 8px; height: 1em;
  background: var(--green);
  vertical-align: text-bottom;
  animation: blink 1s step-end infinite;
}

.hero-ctas {
  display: flex; gap: 1rem; flex-wrap: wrap; justify-content: center;
  margin-top: 2.4rem;
  opacity: 0;
  animation: fadeUp 0.9s 1.2s forwards;
}
.btn {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.78rem;
  letter-spacing: 0.12em;
  padding: 0.75rem 1.8rem;
  border-radius: 4px;
  text-decoration: none;
  transition: all 0.25s;
  cursor: none;
}
.btn-primary {
  background: var(--green);
  color: #040a05;
  font-weight: 600;
  border: 1px solid var(--green);
}
.btn-primary:hover {
  background: transparent;
  color: var(--green);
  box-shadow: 0 0 24px var(--green-glow);
}
.btn-outline {
  background: transparent;
  color: var(--green);
  border: 1px solid var(--border-bright);
}
.btn-outline:hover {
  background: var(--green-faint);
  border-color: var(--green);
  box-shadow: 0 0 18px var(--green-glow);
}

/* SECTION COMMON */
.section-inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 6rem 2rem;
}
.section-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem;
  color: var(--green);
  letter-spacing: 0.22em;
  margin-bottom: 0.8rem;
  display: flex;
  align-items: center;
  gap: 0.8rem;
}
.section-label::after {
  content: '';
  flex: 1;
  height: 1px;
  background: var(--border);
  max-width: 80px;
}
.section-title {
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 3rem;
  line-height: 1.1;
}

/* ABOUT */
#about { background: linear-gradient(180deg, var(--bg) 0%, var(--bg2) 100%); }
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}
.about-text p {
  color: var(--text-dim);
  font-size: 1rem;
  line-height: 1.85;
  margin-bottom: 1.2rem;
}
.about-text strong { color: var(--text); font-weight: 600; }
.stat-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}
.stat-card {
  background: var(--bg3);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 1.4rem;
  transition: border-color 0.25s, box-shadow 0.25s;
}
.stat-card:hover {
  border-color: var(--border-bright);
  box-shadow: 0 0 24px var(--green-glow);
}
.stat-num {
  font-size: 2.2rem;
  font-weight: 900;
  color: var(--green);
  line-height: 1;
  margin-bottom: 0.3rem;
}
.stat-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.7rem;
  color: var(--text-muted);
  letter-spacing: 0.1em;
}

/* PROJECTS */
#projects { background: var(--bg2); }
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.5rem;
}
.project-card {
  background: var(--bg3);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 2rem;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
  cursor: none;
}
.project-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: var(--green);
  transform: scaleX(0);
  transition: transform 0.3s;
}
.project-card:hover {
  border-color: var(--border-bright);
  box-shadow: 0 8px 48px rgba(45,184,77,0.12);
  transform: translateY(-4px);
}
.project-card:hover::before { transform: scaleX(1); }
.project-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.65rem;
  color: var(--green);
  background: var(--green-faint);
  border: 1px solid var(--border);
  padding: 0.2rem 0.6rem;
  border-radius: 3px;
  letter-spacing: 0.1em;
  display: inline-block;
  margin-bottom: 1rem;
}
.project-name {
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 0.6rem;
  color: var(--text);
}
.project-desc {
  font-size: 0.88rem;
  color: var(--text-dim);
  line-height: 1.7;
  margin-bottom: 1.4rem;
}
.project-stack {
  display: flex; flex-wrap: wrap; gap: 0.4rem;
  margin-bottom: 1.5rem;
}
.stack-pill {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.62rem;
  color: var(--text-muted);
  border: 1px solid rgba(45,184,77,0.12);
  padding: 0.18rem 0.55rem;
  border-radius: 3px;
  letter-spacing: 0.06em;
}
.project-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem;
  color: var(--green);
  text-decoration: none;
  letter-spacing: 0.08em;
  transition: opacity 0.2s;
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
}
.project-link:hover { opacity: 0.75; }
.project-link::after { content: '→'; }

/* SKILLS */
#skills { background: linear-gradient(180deg, var(--bg2) 0%, var(--bg) 100%); }
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.5rem;
}
.skill-group {
  background: var(--bg3);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 1.6rem;
  transition: border-color 0.25s;
}
.skill-group:hover { border-color: var(--border-bright); }
.skill-group-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem;
  color: var(--green);
  letter-spacing: 0.15em;
  margin-bottom: 1.2rem;
  padding-bottom: 0.7rem;
  border-bottom: 1px solid var(--border);
}
.skill-bar-item { margin-bottom: 1rem; }
.skill-bar-label {
  display: flex;
  justify-content: space-between;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem;
  color: var(--text-dim);
  margin-bottom: 0.4rem;
}
.skill-bar-track {
  height: 3px;
  background: rgba(45,184,77,0.08);
  border-radius: 2px;
  overflow: hidden;
}
.skill-bar-fill {
  height: 100%;
  background: var(--green);
  border-radius: 2px;
  width: 0;
  transition: width 1.2s cubic-bezier(0.4,0,0.2,1);
}

/* CONTACT */
#contact { background: var(--bg); }
.contact-inner {
  max-width: 700px;
  margin: 0 auto;
  padding: 6rem 2rem;
  text-align: center;
}
.contact-inner .section-label { justify-content: center; }
.contact-inner .section-label::after { display: none; }
.contact-desc {
  color: var(--text-dim);
  font-size: 1rem;
  line-height: 1.8;
  margin-bottom: 2.5rem;
}
.contact-links {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
}
.contact-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem;
  color: var(--text-dim);
  text-decoration: none;
  border: 1px solid var(--border);
  padding: 0.7rem 1.4rem;
  border-radius: 4px;
  letter-spacing: 0.1em;
  transition: all 0.25s;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  cursor: none;
}
.contact-link:hover {
  color: var(--green);
  border-color: var(--border-bright);
  box-shadow: 0 0 18px var(--green-glow);
}

/* FOOTER */
footer {
  border-top: 1px solid var(--border);
  padding: 1.8rem 3rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
  z-index: 1;
}
footer p {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.68rem;
  color: var(--text-muted);
  letter-spacing: 0.08em;
}

/* SCROLL REVEAL */
.reveal {
  opacity: 0;
  transform: translateY(28px);
  transition: opacity 0.7s, transform 0.7s;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* ANIMATIONS */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes blink {
  50% { opacity: 0; }
}

/* RESPONSIVE */
@media (max-width: 768px) {
  nav { padding: 1rem 1.2rem; }
  .nav-links { gap: 1.2rem; }
  .about-grid { grid-template-columns: 1fr; gap: 2rem; }
  footer { flex-direction: column; gap: 0.5rem; text-align: center; }
}
</style>
</head>
<body>

<div id="cursor"></div>
<div id="cursor-ring"></div>

<canvas id="bg-canvas"></canvas>

<nav>
  <a href="#" class="nav-logo">AN://</a>
  <ul class="nav-links">
    <li><a href="#about">about</a></li>
    <li><a href="#projects">projects</a></li>
    <li><a href="#skills">skills</a></li>
    <li><a href="#contact">contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <p class="hero-eyebrow">// Barcelona, Spain &nbsp;·&nbsp; Open to EU Roles</p>
  <h1 class="hero-name">Alborz<br><span>Nazari</span></h1>
  <p class="hero-role">Threat Intelligence &nbsp;·&nbsp; DevSecOps &nbsp;·&nbsp; Security Engineering</p>

  <div class="terminal">
    <div class="terminal-bar">
      <div class="t-dot r"></div>
      <div class="t-dot y"></div>
      <div class="t-dot g"></div>
      <span class="terminal-title">whoami.sh</span>
    </div>
    <div class="terminal-body" id="terminal-output"></div>
  </div>

  <div class="hero-ctas">
    <a href="#projects" class="btn btn-primary">View Projects</a>
    <a href="https://github.com/AlborzNazari" target="_blank" class="btn btn-outline">GitHub</a>
    <a href="https://linkedin.com/in/AlborzNazari" target="_blank" class="btn btn-outline">LinkedIn</a>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-inner">
    <p class="section-label reveal">01 // ABOUT</p>
    <h2 class="section-title reveal">Engineer who builds<br>and <span style="color:var(--green)">secures.</span></h2>
    <div class="about-grid">
      <div class="about-text reveal">
        <p>Software engineer turned cybersecurity specialist. I build threat intelligence platforms, OSINT tools, and security pipelines from scratch — then harden them with real test suites and CI/CD security gates.</p>
        <p>My background spans <strong>3D pipeline engineering</strong> at Left Mountains and FunPlus, an <strong>M.Sc. from FX Barcelona</strong>, and a <strong>B.Sc. in Computer Engineering</strong> from BNUT. I bring systems thinking from production VFX pipelines into security engineering.</p>
        <p>Full EU work authorization. Based in Barcelona.</p>
      </div>
      <div class="stat-grid reveal">
        <div class="stat-card">
          <div class="stat-num">109+</div>
          <div class="stat-label">pytest tests · OIL v0.6</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">116</div>
          <div class="stat-label">security tests · OIL v0.7</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">5</div>
          <div class="stat-label">CI/CD pipeline stages</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">3</div>
          <div class="stat-label">languages spoken</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-inner">
    <p class="section-label reveal">02 // PROJECTS</p>
    <h2 class="section-title reveal">What I've <span style="color:var(--green)">built.</span></h2>
    <div class="projects-grid">

      <div class="project-card reveal">
        <span class="project-tag">FLAGSHIP · ACTIVE</span>
        <div class="project-name">Open Intelligence Lab</div>
        <div class="project-desc">Graph-based cyber threat intelligence platform. STIX 2.1 + TAXII 2.1 compliant. Integrates MISP live feeds, MITRE ATT&CK, and SIEM connectors for Splunk, Sentinel, QRadar, and OpenCTI. Deployed on Fly.io with full CI/CD.</div>
        <div class="project-stack">
          <span class="stack-pill">FastAPI</span>
          <span class="stack-pill">NetworkX</span>
          <span class="stack-pill">STIX 2.1</span>
          <span class="stack-pill">TAXII</span>
          <span class="stack-pill">MISP</span>
          <span class="stack-pill">Docker</span>
          <span class="stack-pill">GitLab CI</span>
          <span class="stack-pill">Fly.io</span>
        </div>
        <a href="https://github.com/AlborzNazari/open-intelligence-lab" target="_blank" class="project-link">View Repository</a>
      </div>

      <div class="project-card reveal">
        <span class="project-tag">OSINT · GEOSPATIAL</span>
        <div class="project-name">Shadowbroker</div>
        <div class="project-desc">Real-time geospatial OSINT dashboard. 2,400+ CCTV feeds across Spain and USA, GPS jamming detection, alert pipeline, and STIX 2.1 export. Extended from open-source base with substantial new integrations.</div>
        <div class="project-stack">
          <span class="stack-pill">Python</span>
          <span class="stack-pill">STIX 2.1</span>
          <span class="stack-pill">Geospatial</span>
          <span class="stack-pill">OSINT</span>
          <span class="stack-pill">Alert Pipeline</span>
        </div>
        <a href="https://github.com/AlborzNazari" target="_blank" class="project-link">View Repository</a>
      </div>

      <div class="project-card reveal">
        <span class="project-tag">CRYPTOGRAPHY · CIVIC</span>
        <div class="project-name">Secure Apportionment System</div>
        <div class="project-desc">Huntington-Hill parliamentary seat allocation with AES-256-CBC encryption. Full Docker containerization, Tkinter + Flask UI, and comprehensive PDF documentation.</div>
        <div class="project-stack">
          <span class="stack-pill">Python</span>
          <span class="stack-pill">AES-256</span>
          <span class="stack-pill">Flask</span>
          <span class="stack-pill">Docker</span>
          <span class="stack-pill">Tkinter</span>
        </div>
        <a href="https://github.com/AlborzNazari/Secure-Apportionment-System" target="_blank" class="project-link">View Repository</a>
      </div>

      <div class="project-card reveal">
        <span class="project-tag">RESEARCH · WRITING</span>
        <div class="project-name">Kettle Pool — Race Conditions</div>
        <div class="project-desc">Scientific article on concurrency, race conditions, and non-determinism built from first principles using the "Kettle Pool" metaphor. Companion: Vault Heist Simulator — a coding project demonstrating race conditions by design and by bug.</div>
        <div class="project-stack">
          <span class="stack-pill">Concurrency</span>
          <span class="stack-pill">Python</span>
          <span class="stack-pill">Technical Writing</span>
          <span class="stack-pill">Systems Design</span>
        </div>
        <a href="https://medium.com/@alborznazari4" target="_blank" class="project-link">Read on Medium</a>
      </div>

    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-inner">
    <p class="section-label reveal">03 // SKILLS</p>
    <h2 class="section-title reveal">The <span style="color:var(--green)">stack.</span></h2>
    <div class="skills-grid">

      <div class="skill-group reveal">
        <div class="skill-group-title">// THREAT INTELLIGENCE</div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>STIX 2.1 / TAXII</span><span>95%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="95"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>MISP</span><span>88%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="88"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>MITRE ATT&CK</span><span>85%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="85"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>OpenCTI</span><span>80%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="80"></div></div>
        </div>
      </div>

      <div class="skill-group reveal">
        <div class="skill-group-title">// DEVSECOPS</div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Docker / CI/CD</span><span>90%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="90"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>GitLab / GitHub Actions</span><span>88%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="88"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Splunk / Sentinel</span><span>78%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="78"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Fly.io / Cloud Deploy</span><span>82%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="82"></div></div>
        </div>
      </div>

      <div class="skill-group reveal">
        <div class="skill-group-title">// ENGINEERING</div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Python / FastAPI</span><span>92%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="92"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Linux / Bash</span><span>88%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="88"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>NetworkX / Graph DB</span><span>84%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="84"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>pytest / Test Design</span><span>86%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" data-w="86"></div></div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-inner">
    <p class="section-label reveal">04 // CONTACT</p>
    <h2 class="section-title reveal">Let's <span style="color:var(--green)">connect.</span></h2>
    <p class="contact-desc reveal">Open to cybersecurity engineering roles across the EU. DevSecOps, threat intelligence, security engineering. Full EU work authorization. Remote-friendly.</p>
    <div class="contact-links reveal">
      <a href="mailto:alborznazari4@gmail.com" class="contact-link">✉ Email</a>
      <a href="https://github.com/AlborzNazari" target="_blank" class="contact-link">⌥ GitHub</a>
      <a href="https://linkedin.com/in/AlborzNazari" target="_blank" class="contact-link">◈ LinkedIn</a>
      <a href="https://medium.com/@alborznazari4" target="_blank" class="contact-link">◎ Medium</a>
    </div>
  </div>
</section>

<footer>
  <p>© 2026 Alborz Nazari</p>
  <p>Built from scratch · Barcelona</p>
</footer>

<script>
// --- Cursor ---
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursor-ring');
let mx = 0, my = 0, rx = 0, ry = 0;
document.addEventListener('mousemove', e => {
  mx = e.clientX; my = e.clientY;
  cursor.style.left = (mx - 5) + 'px';
  cursor.style.top  = (my - 5) + 'px';
});
(function animRing() {
  rx += (mx - rx) * 0.12;
  ry += (my - ry) * 0.12;
  ring.style.left = (rx - 18) + 'px';
  ring.style.top  = (ry - 18) + 'px';
  requestAnimationFrame(animRing);
})();
document.querySelectorAll('a,button').forEach(el => {
  el.addEventListener('mouseenter', () => {
    ring.style.width = '52px'; ring.style.height = '52px';
  });
  el.addEventListener('mouseleave', () => {
    ring.style.width = '36px'; ring.style.height = '36px';
  });
});

// --- Canvas grid + particle BG ---
const canvas = document.getElementById('bg-canvas');
const ctx = canvas.getContext('2d');
let W, H, particles = [];

function resize() {
  W = canvas.width  = window.innerWidth;
  H = canvas.height = window.innerHeight;
}
resize();
window.addEventListener('resize', resize);

class Particle {
  constructor() { this.reset(); }
  reset() {
    this.x = Math.random() * W;
    this.y = Math.random() * H;
    this.vx = (Math.random() - 0.5) * 0.18;
    this.vy = (Math.random() - 0.5) * 0.18;
    this.r = Math.random() * 1.4 + 0.3;
    this.a = Math.random() * 0.5 + 0.1;
  }
  update() {
    this.x += this.vx; this.y += this.vy;
    if (this.x < 0 || this.x > W || this.y < 0 || this.y > H) this.reset();
  }
  draw() {
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.r, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(45,184,77,${this.a})`;
    ctx.fill();
  }
}
for (let i = 0; i < 90; i++) particles.push(new Particle());

function drawGrid() {
  const gs = 48;
  ctx.strokeStyle = 'rgba(30,110,50,0.12)';
  ctx.lineWidth = 0.5;
  for (let x = 0; x < W; x += gs) {
    ctx.beginPath(); ctx.moveTo(x, 0); ctx.lineTo(x, H); ctx.stroke();
  }
  for (let y = 0; y < H; y += gs) {
    ctx.beginPath(); ctx.moveTo(0, y); ctx.lineTo(W, y); ctx.stroke();
  }
  ctx.fillStyle = 'rgba(45,184,77,0.18)';
  for (let x = 0; x < W; x += gs)
    for (let y = 0; y < H; y += gs) {
      ctx.beginPath(); ctx.arc(x, y, 1, 0, Math.PI*2); ctx.fill();
    }
}

function drawConnections() {
  for (let i = 0; i < particles.length; i++)
    for (let j = i+1; j < particles.length; j++) {
      const d = Math.hypot(particles[i].x - particles[j].x, particles[i].y - particles[j].y);
      if (d < 110) {
        ctx.strokeStyle = `rgba(45,184,77,${0.07 * (1 - d/110)})`;
        ctx.lineWidth = 0.5;
        ctx.beginPath();
        ctx.moveTo(particles[i].x, particles[i].y);
        ctx.lineTo(particles[j].x, particles[j].y);
        ctx.stroke();
      }
    }
}

function animate() {
  ctx.clearRect(0, 0, W, H);
  drawGrid();
  particles.forEach(p => { p.update(); p.draw(); });
  drawConnections();
  requestAnimationFrame(animate);
}
animate();

// --- Terminal typing ---
const lines = [
  ['prompt', '❯ ', 'cmd', 'cat whoami.json'],
  ['json', '{'],
  ['kv', '  "name"', ':', '"Alborz Nazari"'],
  ['kv', '  "role"', ':', '"Cybersecurity Engineer"'],
  ['kv', '  "location"', ':', '"Barcelona, Spain"'],
  ['kv', '  "stack"', ':', '["STIX", "TAXII", "MISP", "FastAPI", "Docker"]'],
  ['kv', '  "certs"', ':', '["TryHackMe Cyber 101", "Pre-Security"]'],
  ['kv', '  "status"', ':', '"Actively seeking EU cybersecurity roles"'],
  ['json', '}'],
];

const out = document.getElementById('terminal-output');
let li = 0, ci = 0;
let currentEl = null;

function typeNext() {
  if (li >= lines.length) {
    const blink = document.createElement('span');
    blink.className = 'cursor-blink';
    out.appendChild(blink);
    return;
  }
  const line = lines[li];
  if (ci === 0) {
    const p = document.createElement('p');
    if (line[0] === 'prompt') {
      p.innerHTML = `<span class="prompt">${line[1]}</span>`;
      currentEl = p;
      out.appendChild(p);
      const txt = document.createTextNode('');
      p.appendChild(txt);
      ci = 1;
      typeChar(line[2] === 'cmd' ? line[3] : '', p.lastChild);
      return;
    } else if (line[0] === 'json') {
      p.innerHTML = `<span class="comment">${line[1]}</span>`;
      out.appendChild(p);
      li++; ci = 0;
      setTimeout(typeNext, 40);
      return;
    } else {
      p.innerHTML = `<span class="key">${line[1]}</span><span class="comment">${line[2]}</span> <span class="val">${line[3]}</span>`;
      out.appendChild(p);
      li++; ci = 0;
      setTimeout(typeNext, 55);
      return;
    }
  }
}

function typeChar(str, node) {
  let i = 0;
  function tick() {
    if (i < str.length) {
      node.textContent += str[i++];
      setTimeout(tick, 38 + Math.random() * 30);
    } else {
      li++; ci = 0;
      setTimeout(typeNext, 120);
    }
  }
  tick();
}

setTimeout(typeNext, 1400);

// --- Scroll reveal ---
const revealEls = document.querySelectorAll('.reveal');
const obs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); }
  });
}, { threshold: 0.12 });
revealEls.forEach(el => obs.observe(el));

// --- Skill bars ---
const bars = document.querySelectorAll('.skill-bar-fill');
const barObs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.style.width = e.target.dataset.w + '%';
      barObs.unobserve(e.target);
    }
  });
}, { threshold: 0.3 });
bars.forEach(b => barObs.observe(b));
</script>
</body>
</html>
