
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

to   { transform: rotate(360deg); }
}



/* Outer geometry ring */
.si-ring {
  position: absolute; border-radius: 50%;
  border: 1px solid rgba(45,184,77,0.25);
}
.si-ring-1 { inset: 0; animation: rotateCW 22s linear infinite; }
.si-ring-2 { inset: 18px; border-style: dashed; border-color: rgba(45,184,77,0.12); animation: rotateCCW 16s linear infinite; }
.si-ring-3 { inset: 36px; border-color: rgba(45,184,77,0.18); }

/* Notch ticks on outer ring */
.si-ticks {
  position: absolute; inset: 0; border-radius: 50%;
  animation: rotateCW 22s linear infinite;
}

/* Circular text SVGs */
.si-textring { position: absolute; inset: 0; }
.si-textring-inner { position: absolute; inset: 0; animation: rotateCCW 28s linear infinite; }

/* Center stage */
.si-center {
  position: absolute; inset: 64px;
  border-radius: 50%;
  background: radial-gradient(circle at 50% 50%, rgba(45,184,77,0.055) 0%, transparent 72%);
  border: 0.5px solid rgba(45,184,77,0.12);
}

/* Signature */
.si-sig {
  position: relative; z-index: 3;
  width: 200px; height: auto;
  opacity: 0; transform: scale(0.88) translateY(6px);
  transition: opacity 0.9s 0.6s cubic-bezier(0.16,1,0.3,1),
              transform 0.9s 0.6s cubic-bezier(0.16,1,0.3,1);
  filter: drop-shadow(0 2px 18px rgba(45,184,77,0.22));
}
.si-sig.in { opacity: 1; transform: scale(1) translateY(0); }

/* Horizontal rule flanked lines */
.si-rule {
  display: flex; align-items: center; gap: 12px;
  margin-top: 2rem;
  opacity: 0; animation: siUp 0.6s 1.1s forwards;
}
.si-rule-line { width: 52px; height: 0.5px; background: rgba(45,184,77,0.3); }
.si-rule-dot  { width: 4px; height: 4px; border-radius: 50%; background: rgba(45,184,77,0.55); }

/* Labels */
.si-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem; letter-spacing: 0.3em; font-weight: 600;
  color: rgba(45,184,77,0.75);
  margin-top: 0.65rem;
  opacity: 0; animation: siUp 0.6s 1.25s forwards;
}
.si-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.55rem; letter-spacing: 0.2em;
  color: rgba(45,184,77,0.3);
  margin-top: 0.35rem;
  opacity: 0; animation: siUp 0.5s 1.4s forwards;
}

/* Progress */
.si-progress {
  width: 160px; height: 0.5px; margin-top: 1.8rem;
  background: rgba(45,184,77,0.08);
  opacity: 0; animation: siUp 0.4s 1.55s forwards;
}
.si-progress-fill {
  height: 100%; width: 0; background: rgba(45,184,77,0.6);
  transition: width 2.2s 1.6s cubic-bezier(0.4,0,0.2,1);
}

@keyframes rotateCW  { to { transform: rotate(360deg);  } }
@keyframes rotateCCW { to { transform: rotate(-360deg); } }
@keyframes siUp {
  from { opacity: 0; transform: translateY(8px); }
  to   { opacity: 1; transform: translateY(0); }
}


#seal-intro {
  position: fixed; inset: 0; z-index: 10000;
  background: #030a04;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  transition: opacity 1.2s cubic-bezier(0.4,0,0.2,1), visibility 1.2s;
}
#seal-intro.gone { opacity: 0; visibility: hidden; pointer-events: none; }

.seal-wrap {
  position: relative;
  width: min(480px, 82vw);
  height: min(480px, 82vw);
  display: flex; align-items: center; justify-content: center;
}

/* Clock rings */
.seal-wrap svg.ring-svg {
  position: absolute; inset: 0; width: 100%; height: 100%;
}

/* Signature center */
.seal-sig-wrap {
  position: absolute;
  inset: 22%;
  display: flex; align-items: center; justify-content: center;
  border-radius: 50%;
  overflow: hidden;
}
.seal-sig {
  width: 88%;
  height: auto;
  opacity: 0;
  transform: scale(0.9);
  transition: opacity 1s 0.7s cubic-bezier(0.16,1,0.3,1),
              transform 1s 0.7s cubic-bezier(0.16,1,0.3,1);
  filter: drop-shadow(0 0 14px rgba(45,184,77,0.3));
}
.seal-sig.in { opacity: 1; transform: scale(1); }

/* Below seal */
.seal-rule {
  display: flex; align-items: center; gap: 14px;
  margin-top: 2.2rem;
  opacity: 0; animation: sealUp 0.7s 1.3s forwards;
}
.seal-rule-line { width: 60px; height: 0.5px; background: rgba(45,184,77,0.28); }
.seal-rule-gem {
  width: 5px; height: 5px; border-radius: 50%;
  background: rgba(45,184,77,0.6);
  box-shadow: 0 0 8px rgba(45,184,77,0.4);
}
.seal-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem; letter-spacing: 0.32em; font-weight: 600;
  color: rgba(45,184,77,0.75); margin-top: 0.7rem;
  opacity: 0; animation: sealUp 0.6s 1.45s forwards;
}
.seal-role {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.56rem; letter-spacing: 0.2em;
  color: rgba(45,184,77,0.28); margin-top: 0.4rem;
  opacity: 0; animation: sealUp 0.5s 1.6s forwards;
}
.seal-bar-wrap {
  width: 140px; height: 1px; margin-top: 2rem;
  background: rgba(45,184,77,0.08);
  opacity: 0; animation: sealUp 0.4s 1.75s forwards;
}
.seal-bar-fill {
  height: 100%; width: 0;
  background: rgba(45,184,77,0.55);
  transition: width 2.4s 1.8s cubic-bezier(0.4,0,0.2,1);
}
@keyframes sealUp {
  from { opacity:0; transform:translateY(10px); }
  to   { opacity:1; transform:translateY(0); }
}
@keyframes cwSpin  { to { transform: rotate(360deg);  } }
@keyframes ccwSpin { to { transform: rotate(-360deg); } }



#seal-intro {{
  position: fixed; inset: 0; z-index: 10000;
  background: #030a04;
  display: flex; align-items: center; justify-content: center;
  overflow: hidden;
  transition: opacity 1.2s 0.2s ease, visibility 1.2s 0.2s;
}}
#seal-intro.gone {{ opacity:0; visibility:hidden; pointer-events:none; }}
body.intro-active {{ overflow: hidden; }}

.si-seal {{
  position: relative;
  width: min(500px, 90vmin);
  height: min(500px, 90vmin);
  display: flex; align-items: center; justify-content: center;
}}
.si-svg {{
  position: absolute; inset: 0;
  width: 100%; height: 100%;
}}
.si-center {{
  position: absolute;
  inset: 28%;
  display: flex; align-items: center; justify-content: center;
  border-radius: 50%;
}}
.si-sig {{
  width: 100%; height: auto;
  opacity: 0;
  transform: scale(0.85);
  transition: opacity 1.1s 0.5s cubic-bezier(0.16,1,0.3,1),
              transform 1.1s 0.5s cubic-bezier(0.16,1,0.3,1);
  filter: drop-shadow(0 0 12px rgba(45,184,77,0.25));
}}
.si-sig.in {{ opacity:1; transform:scale(1); }}

@keyframes siCW  {{ to {{ transform: rotate(360deg);  }} }}
@keyframes siCCW {{ to {{ transform: rotate(-360deg); }} }}


/* ══ SEAL INTRO ══ */

* { margin:0; padding:0; box-sizing:border-box; }
html, body { width:100%; height:100%; background:#030a04; overflow:hidden; }

#seal {
  position: fixed; inset: 0;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  background: #030a04;
  z-index: 9999;
  transition: opacity 1.2s ease;
}
#seal.gone { opacity: 0; pointer-events: none; }

.wrap {
  position: relative;
  width: min(500px, 88vmin);
  height: min(500px, 88vmin);
  display: flex; align-items: center; justify-content: center;
}

.ring-svg {
  position: absolute;
  inset: 0; width: 100%; height: 100%;
}

.ring-cw  { animation: cw  38s linear infinite; }
.ring-ccw { animation: ccw 26s linear infinite; }

.sig-wrap {
  position: absolute;
  inset: 27%;
  display: flex; align-items: center; justify-content: center;
}
.sig-wrap img {
  width: 100%; height: auto;
  opacity: 0;
  transform: scale(0.94);
  filter: blur(10px) drop-shadow(0 0 16px rgba(45,184,77,0.15));
  transition: opacity 2.2s 0.5s cubic-bezier(0.4,0,0.2,1),
              transform 2.4s 0.5s cubic-bezier(0.16,1,0.3,1),
              filter 2s 0.5s cubic-bezier(0.4,0,0.2,1);
}
.sig-wrap img.in {
  opacity: 1;
  transform: scale(1);
  filter: blur(0px) drop-shadow(0 0 18px rgba(45,184,77,0.28));
}

.label {
  margin-top: 2rem;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem; letter-spacing: 0.3em;
  color: rgba(45,184,77,0.55);
  opacity: 0; animation: up 0.6s 1.2s forwards;
}
.sub {
  margin-top: 0.4rem;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.55rem; letter-spacing: 0.2em;
  color: rgba(45,184,77,0.25);
  opacity: 0; animation: up 0.6s 1.4s forwards;
}
.bar-wrap {
  width: 140px; height: 1px; margin-top: 1.8rem;
  background: rgba(45,184,77,0.08);
  opacity: 0; animation: up 0.4s 1.6s forwards;
}
.bar { height: 100%; width: 0; background: rgba(45,184,77,0.5); transition: width 2.4s 1.7s ease; }

@keyframes cw  { to { transform: rotate(360deg);  } }
@keyframes ccw { to { transform: rotate(-360deg); } }
@keyframes up  {
  from { opacity:0; transform:translateY(8px); }
  to   { opacity:1; transform:translateY(0);   }
}

</style>
</head>
<body>

<!-- SEAL INTRO -->
<div id="seal">
  <div class="wrap">

    <!-- Outer ring: CW, ticks + text -->
    <svg class="ring-svg ring-cw" viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
      <circle cx="250" cy="250" r="240" fill="none" stroke="rgba(45,184,77,0.18)" stroke-width="0.8"/>
      <circle cx="250" cy="250" r="226" fill="none" stroke="rgba(45,184,77,0.06)" stroke-width="0.5" stroke-dasharray="2 8"/>
      <line x1="250.0" y1="22.0" x2="250.0" y2="8.0" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="364.0" y1="52.5" x2="371.0" y2="40.4" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="447.5" y1="136.0" x2="459.6" y2="129.0" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="478.0" y1="250.0" x2="492.0" y2="250.0" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="447.5" y1="364.0" x2="459.6" y2="371.0" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="364.0" y1="447.5" x2="371.0" y2="459.6" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="250.0" y1="478.0" x2="250.0" y2="492.0" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="136.0" y1="447.5" x2="129.0" y2="459.6" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="52.5" y1="364.0" x2="40.4" y2="371.0" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="22.0" y1="250.0" x2="8.0" y2="250.0" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="52.5" y1="136.0" x2="40.4" y2="129.0" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/><line x1="136.0" y1="52.5" x2="129.0" y2="40.4" stroke="rgba(45,184,77,0.7)" stroke-width="1.8" stroke-linecap="round"/>
      <line x1="250.0" y1="16.0" x2="250.0" y2="8.0" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="274.5" y1="17.3" x2="275.3" y2="9.3" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="298.7" y1="21.1" x2="300.3" y2="13.3" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="322.3" y1="27.5" x2="324.8" y2="19.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="345.2" y1="36.2" x2="348.4" y2="28.9" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="367.0" y1="47.4" x2="371.0" y2="40.4" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="387.5" y1="60.7" x2="392.2" y2="54.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="406.6" y1="76.1" x2="411.9" y2="70.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="423.9" y1="93.4" x2="429.8" y2="88.1" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="439.3" y1="112.5" x2="445.8" y2="107.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="452.6" y1="133.0" x2="459.6" y2="129.0" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="463.8" y1="154.8" x2="471.1" y2="151.6" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="472.5" y1="177.7" x2="480.2" y2="175.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="478.9" y1="201.3" x2="486.7" y2="199.7" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="482.7" y1="225.5" x2="490.7" y2="224.7" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="484.0" y1="250.0" x2="492.0" y2="250.0" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="482.7" y1="274.5" x2="490.7" y2="275.3" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="478.9" y1="298.7" x2="486.7" y2="300.3" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="472.5" y1="322.3" x2="480.2" y2="324.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="463.8" y1="345.2" x2="471.1" y2="348.4" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="452.6" y1="367.0" x2="459.6" y2="371.0" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="439.3" y1="387.5" x2="445.8" y2="392.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="423.9" y1="406.6" x2="429.8" y2="411.9" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="406.6" y1="423.9" x2="411.9" y2="429.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="387.5" y1="439.3" x2="392.2" y2="445.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="367.0" y1="452.6" x2="371.0" y2="459.6" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="345.2" y1="463.8" x2="348.4" y2="471.1" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="322.3" y1="472.5" x2="324.8" y2="480.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="298.7" y1="478.9" x2="300.3" y2="486.7" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="274.5" y1="482.7" x2="275.3" y2="490.7" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="250.0" y1="484.0" x2="250.0" y2="492.0" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="225.5" y1="482.7" x2="224.7" y2="490.7" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="201.3" y1="478.9" x2="199.7" y2="486.7" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="177.7" y1="472.5" x2="175.2" y2="480.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="154.8" y1="463.8" x2="151.6" y2="471.1" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="133.0" y1="452.6" x2="129.0" y2="459.6" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="112.5" y1="439.3" x2="107.8" y2="445.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="93.4" y1="423.9" x2="88.1" y2="429.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="76.1" y1="406.6" x2="70.2" y2="411.9" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="60.7" y1="387.5" x2="54.2" y2="392.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="47.4" y1="367.0" x2="40.4" y2="371.0" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="36.2" y1="345.2" x2="28.9" y2="348.4" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="27.5" y1="322.3" x2="19.8" y2="324.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="21.1" y1="298.7" x2="13.3" y2="300.3" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="17.3" y1="274.5" x2="9.3" y2="275.3" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="16.0" y1="250.0" x2="8.0" y2="250.0" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="17.3" y1="225.5" x2="9.3" y2="224.7" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="21.1" y1="201.3" x2="13.3" y2="199.7" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="27.5" y1="177.7" x2="19.8" y2="175.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="36.2" y1="154.8" x2="28.9" y2="151.6" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="47.4" y1="133.0" x2="40.4" y2="129.0" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="60.7" y1="112.5" x2="54.2" y2="107.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="76.1" y1="93.4" x2="70.2" y2="88.1" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="93.4" y1="76.1" x2="88.1" y2="70.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="112.5" y1="60.7" x2="107.8" y2="54.2" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="133.0" y1="47.4" x2="129.0" y2="40.4" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="154.8" y1="36.2" x2="151.6" y2="28.9" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="177.7" y1="27.5" x2="175.2" y2="19.8" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="201.3" y1="21.1" x2="199.7" y2="13.3" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/><line x1="225.5" y1="17.3" x2="224.7" y2="9.3" stroke="rgba(45,184,77,0.25)" stroke-width="0.7" stroke-linecap="round"/>
      <defs><path id="ot" d="M250,250 m-210,0 a210,210 0 1,1 420,0 a210,210 0 1,1 -420,0"/></defs>
      <text font-family="JetBrains Mono,monospace" font-size="10.5" fill="rgba(45,184,77,0.38)" letter-spacing="5.5">
        <textPath href="#ot">CYBERSECURITY &nbsp;·&nbsp; THREAT INTELLIGENCE &nbsp;·&nbsp; DEVSECOPS &nbsp;·&nbsp; OSINT &nbsp;·&nbsp; BARCELONA &nbsp;·&nbsp; </textPath>
      </text>
    </svg>

    <!-- Inner ring: CCW, stack text -->
    <svg class="ring-svg ring-ccw" viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
      <circle cx="250" cy="250" r="165" fill="none" stroke="rgba(45,184,77,0.15)" stroke-width="0.8"/>
      <circle cx="250" cy="250" r="152" fill="none" stroke="rgba(45,184,77,0.05)" stroke-width="0.5" stroke-dasharray="1 5"/>
      <line x1="250.0" y1="94.0" x2="250.0" y2="85.0" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="270.4" y1="95.3" x2="271.5" y2="86.4" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="290.4" y1="99.3" x2="292.7" y2="90.6" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="309.7" y1="105.9" x2="313.1" y2="97.6" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="328.0" y1="114.9" x2="332.5" y2="107.1" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="345.0" y1="126.2" x2="350.4" y2="119.1" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="360.3" y1="139.7" x2="366.7" y2="133.3" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="373.8" y1="155.0" x2="380.9" y2="149.6" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="385.1" y1="172.0" x2="392.9" y2="167.5" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="394.1" y1="190.3" x2="402.4" y2="186.9" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="400.7" y1="209.6" x2="409.4" y2="207.3" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="404.7" y1="229.6" x2="413.6" y2="228.5" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="406.0" y1="250.0" x2="415.0" y2="250.0" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="404.7" y1="270.4" x2="413.6" y2="271.5" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="400.7" y1="290.4" x2="409.4" y2="292.7" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="394.1" y1="309.7" x2="402.4" y2="313.1" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="385.1" y1="328.0" x2="392.9" y2="332.5" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="373.8" y1="345.0" x2="380.9" y2="350.4" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="360.3" y1="360.3" x2="366.7" y2="366.7" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="345.0" y1="373.8" x2="350.4" y2="380.9" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="328.0" y1="385.1" x2="332.5" y2="392.9" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="309.7" y1="394.1" x2="313.1" y2="402.4" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="290.4" y1="400.7" x2="292.7" y2="409.4" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="270.4" y1="404.7" x2="271.5" y2="413.6" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="250.0" y1="406.0" x2="250.0" y2="415.0" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="229.6" y1="404.7" x2="228.5" y2="413.6" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="209.6" y1="400.7" x2="207.3" y2="409.4" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="190.3" y1="394.1" x2="186.9" y2="402.4" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="172.0" y1="385.1" x2="167.5" y2="392.9" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="155.0" y1="373.8" x2="149.6" y2="380.9" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="139.7" y1="360.3" x2="133.3" y2="366.7" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="126.2" y1="345.0" x2="119.1" y2="350.4" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="114.9" y1="328.0" x2="107.1" y2="332.5" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="105.9" y1="309.7" x2="97.6" y2="313.1" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="99.3" y1="290.4" x2="90.6" y2="292.7" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="95.3" y1="270.4" x2="86.4" y2="271.5" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="94.0" y1="250.0" x2="85.0" y2="250.0" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="95.3" y1="229.6" x2="86.4" y2="228.5" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="99.3" y1="209.6" x2="90.6" y2="207.3" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="105.9" y1="190.3" x2="97.6" y2="186.9" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="114.9" y1="172.0" x2="107.1" y2="167.5" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="126.2" y1="155.0" x2="119.1" y2="149.6" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="139.7" y1="139.7" x2="133.3" y2="133.3" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="155.0" y1="126.2" x2="149.6" y2="119.1" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="172.0" y1="114.9" x2="167.5" y2="107.1" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="190.3" y1="105.9" x2="186.9" y2="97.6" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="209.6" y1="99.3" x2="207.3" y2="90.6" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/><line x1="229.6" y1="95.3" x2="228.5" y2="86.4" stroke="rgba(45,184,77,0.14)" stroke-width="0.6" stroke-linecap="round"/>
      <line x1="250.0" y1="96.0" x2="250.0" y2="85.0" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="327.0" y1="116.6" x2="332.5" y2="107.1" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="383.4" y1="173.0" x2="392.9" y2="167.5" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="404.0" y1="250.0" x2="415.0" y2="250.0" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="383.4" y1="327.0" x2="392.9" y2="332.5" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="327.0" y1="383.4" x2="332.5" y2="392.9" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="250.0" y1="404.0" x2="250.0" y2="415.0" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="173.0" y1="383.4" x2="167.5" y2="392.9" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="116.6" y1="327.0" x2="107.1" y2="332.5" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="96.0" y1="250.0" x2="85.0" y2="250.0" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="116.6" y1="173.0" x2="107.1" y2="167.5" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/><line x1="173.0" y1="116.6" x2="167.5" y2="107.1" stroke="rgba(45,184,77,0.38)" stroke-width="1.2" stroke-linecap="round"/>
      <defs><path id="it" d="M250,250 m-158,0 a158,158 0 1,1 316,0 a158,158 0 1,1 -316,0"/></defs>
      <text font-family="JetBrains Mono,monospace" font-size="8.5" fill="rgba(45,184,77,0.2)" letter-spacing="3.8">
        <textPath href="#it">STIX 2.1 &nbsp;·&nbsp; TAXII &nbsp;·&nbsp; MISP &nbsp;·&nbsp; MITRE ATT&amp;CK &nbsp;·&nbsp; SPLUNK &nbsp;·&nbsp; SENTINEL &nbsp;·&nbsp; QRADAR &nbsp;·&nbsp; </textPath>
      </text>
    </svg>

    <!-- Static inner glow -->
    <svg class="ring-svg" viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <radialGradient id="glow" cx="50%" cy="50%" r="50%">
          <stop offset="0%" stop-color="rgba(45,184,77,0.08)"/>
          <stop offset="100%" stop-color="rgba(0,0,0,0)"/>
        </radialGradient>
      </defs>
      <circle cx="250" cy="250" r="130" fill="url(#glow)"/>
      <circle cx="250" cy="250" r="130" fill="none" stroke="rgba(45,184,77,0.1)" stroke-width="0.5"/>
    </svg>

    <!-- Signature -->
    <div class="sig-wrap">
      <img id="sig" src="data:image/png;base64,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fL6gUspxnETz8jXLF6c22Rkngy2TpRCC8BtrNnbIBt6mx0REHnX44bndyitGGKZlEJELAOxqrdavXzfjgwkTmrdFMkhlZSVWVVXxyDEju2aGMrowg4vIEhBBIEpCAURkN7c2r37yvkcXpgb3neMGALbAzAYQISElOo6jlbYTqXHqayuv7X3MUcf8saxzl5GmaboE2tpUXz/r5f+89PCCmQtqajfWrikuLBljGRZ1617e9+XXX8aePXofXVpaOsI0TVaOSw6pGDKE7UQiZjvO5nAkvL5u06bVceU0b25srnv5n89tmjlzZiukEpM6xAK3lDkJIVRaJAGSQnnjjTeKqqoq+pZryt+871//KyAD79SW4bbCE0yPHYrUl50vvfrSXhUVFeMMaaCrXZ9lGhCOhGPTp3/2ASQnCgRIWn0333wz9O7Zu6tlmCFXOVHHdaKGYfgj0WhNGMJN6R6zKQuBbr/r9uHl3buNFoBxV7sSvqq3+95xISKfct4pJdmZGf0kSgkSMtpb27782w1/2wCwTayhX4vvEklz1KhROWddfF6vQCiQvXLN0lU3XX7Tym198C1W/skn7JmbkzPMlNJ0iDQAU0try/r//vftT7fVsdJegZz8nHyUMkBMCWYwBYDFwCAAMe447vIVK2dMmzZt61bGMMASUhgIAJZpigGDBh32yquvqLyigq5dysrGZmRl5whEh4j8dZtrZ//rX/++76G77qthZnz13dc3S4mGFFZwUP8BZyilOCOUkamUhs1NmxevW7d+Sktr46oE69bZH3zS+Pjjj7cAQAK+ytoFgC0iuWWlj28JN3wtaxsR+Se3mkNghF1bKNN4gumxw8HMcNhhRxyen5vXnYgSwEiQbML9+fTVq5czsxg/fjxUciWmty/r1mU307JEPGHXS0P4BWBWw+a6tRMemRDBR7bMGwIAfKPHjj4uM5iRo7RuUlrZinRkK4aFAMBjRozpGQpldCKguNKKa+vrv2xubg7vBKnxmG4fmPJLA6REcu+998694porRvTo2eeAgN9XlpGVUWwZVsbw3XZv6NG5992nHHfih9vy/FJ9XaFHj4rdLdPnI82EAEQIsq6+dt6/Hn20ehsejwEAuvfo3sNvWZmImFCuE1WAUYloCYEcDrdteuPfr35vGzyArzJDm1tbG0mphPD7g0qTzs/N67vPmH0HSoGIKKKk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" alt=""/>
    </div>

  </div>

  <div class="label">ALBORZ NAZARI</div>
  <div class="sub">CYBERSECURITY ENGINEER &nbsp;·&nbsp; BARCELONA</div>
  <div class="bar-wrap"><div class="bar" id="bar"></div></div>
</div>



<nav id="main-nav" style="opacity:0;transition:opacity 0.9s;">
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
        <a href="https://github.com/AlborzNazari/Shadowbroker" target="_blank" class="project-link">View Repository</a>
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
        <a href="https://medium.com/@alborznazari4/threading-the-needle-race-conditions-atomic-violations-and-the-concurrency-flaws-that-break-b7bfdc2f7993" target="_blank" class="project-link">Read on Medium</a>
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
      <a href="https://medium.com/@alborznazari4/threading-the-needle-race-conditions-atomic-violations-and-the-concurrency-flaws-that-break-b7bfdc2f7993" target="_blank" class="contact-link">◎ Medium</a>
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
      


// ── Seal intro ──
(function() {
  document.body.style.overflow = 'hidden';
  var seal = document.getElementById('seal');
  var nav  = document.getElementById('main-nav');
  var sig  = document.getElementById('sig');
  var bar  = document.getElementById('bar');

  setTimeout(function() {
    sig.classList.add('in');
    bar.style.width = '100%';
  }, 80);

  setTimeout(function() {
    seal.classList.add('gone');
    document.body.style.overflow = '';
    if (nav) nav.style.opacity = '1';
  }, 4400);
})();

setTimeout(typeNext, 5000);
      return;
    } else {
      p.innerHTML = `<span class="key">${line[1]}</span><span class="comment">${line[2]}</span> <span class="val">${line[3]}</span>`;
      out.appendChild(p);
      li++; ci = 0;
      
setTimeout(typeNext, 1400);
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
      
setTimeout(typeNext, 1400);
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
