<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate">
<title>Alborz Nazari — Cybersecurity Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;900&family=JetBrains+Mono:wght@300;400;600&display=swap" rel="stylesheet">
<style>
/* ==========================================================================
   TOKENS — edit these to re-theme the whole site
   ========================================================================== */
:root {
  --g: #2db84d;
  --gg: rgba(45,184,77,0.18);
  --gf: rgba(45,184,77,0.06);
  --bg: #060e08;
  --bg2: #0a160c;
  --bg3: #0d1f10;
  --tx: #e8f5ea;
  --td: #7aaa84;
  --tm: #3a6645;
  --br: rgba(45,184,77,0.18);
  --bb: rgba(45,184,77,0.45);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
html{scroll-behavior:smooth;}
body{background:var(--bg);color:var(--tx);font-family:'Poppins',sans-serif;overflow-x:hidden;cursor:none;}

/* ==========================================================================
   CURSOR — self-contained, removable without affecting layout
   ========================================================================== */
#cur{position:fixed;width:10px;height:10px;background:var(--g);border-radius:50%;pointer-events:none;z-index:9999;mix-blend-mode:screen;transform:translate(-50%,-50%);}
#cur-r{position:fixed;width:36px;height:36px;border:1px solid rgba(45,184,77,0.5);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:width .2s,height .2s;}

/* ==========================================================================
   BACKGROUND CANVAS
   ========================================================================== */
#bgc{position:fixed;inset:0;z-index:0;opacity:.55;pointer-events:none;}

/* ==========================================================================
   INTRO SEAL — self-contained loading sequence
   ========================================================================== */
#seal{
  position:fixed;inset:0;z-index:10000;
  background:#030a04;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  transition:opacity 1.2s ease;
}
#seal.gone{opacity:0;visibility:hidden;pointer-events:none;}
.sw{position:relative;width:min(500px,88vmin);height:min(500px,88vmin);display:flex;align-items:center;justify-content:center;}
.sv{position:absolute;inset:0;width:100%;height:100%;}
.cw{animation:cw 38s linear infinite;}
.ccw{animation:ccw 26s linear infinite;}
.sigw{position:absolute;width:42%;display:flex;align-items:center;justify-content:center;background:transparent;}
.sigw img{width:100%;height:auto;background:transparent;opacity:0;transform:scale(0.93);filter:blur(12px);transition:opacity 2.4s .5s ease,transform 2.6s .5s cubic-bezier(.16,1,.3,1),filter 2.2s .5s ease;}
.sigw img.in{opacity:1;transform:scale(1);filter:blur(0px);}
.sl{margin-top:2rem;font-family:'JetBrains Mono',monospace;font-size:.72rem;letter-spacing:.3em;color:rgba(45,184,77,.55);opacity:0;animation:up .6s 1.4s forwards;}
.ss{margin-top:.4rem;font-family:'JetBrains Mono',monospace;font-size:.55rem;letter-spacing:.2em;color:rgba(45,184,77,.25);opacity:0;animation:up .5s 1.6s forwards;}
.sbw{width:140px;height:1px;margin-top:1.8rem;background:rgba(45,184,77,.08);opacity:0;animation:up .4s 1.8s forwards;}
.sb{height:100%;width:0;background:rgba(45,184,77,.5);transition:width 2.4s 1.9s ease;}
@keyframes cw{to{transform:rotate(360deg);}}
@keyframes ccw{to{transform:rotate(-360deg);}}
@keyframes up{from{opacity:0;transform:translateY(8px);}to{opacity:1;transform:none;}}
@keyframes fu{from{opacity:0;transform:translateY(24px);}to{opacity:1;transform:none;}}
@keyframes bl{50%{opacity:0;}}

/* ==========================================================================
   NAV
   ========================================================================== */
nav{position:fixed;top:0;left:0;right:0;z-index:100;padding:1.2rem 3rem;display:flex;justify-content:space-between;align-items:center;border-bottom:1px solid rgba(45,184,77,.08);backdrop-filter:blur(18px);background:rgba(6,14,8,.7);opacity:0;transition:opacity .9s;}
nav.show{opacity:1;}
.nl{font-family:'JetBrains Mono',monospace;font-size:.85rem;color:var(--g);letter-spacing:.12em;text-decoration:none;}
.nm{display:flex;gap:2.2rem;list-style:none;}
.nm a{font-family:'JetBrains Mono',monospace;font-size:.75rem;color:var(--td);text-decoration:none;letter-spacing:.1em;transition:color .2s;position:relative;cursor:none;}
.nm a::after{content:'';position:absolute;bottom:-3px;left:0;right:0;height:1px;background:var(--g);transform:scaleX(0);transition:transform .25s;}
.nm a:hover{color:var(--g);}.nm a:hover::after{transform:scaleX(1);}

/* ==========================================================================
   HERO
   ========================================================================== */
section{position:relative;z-index:1;}
#hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;padding:8rem 2rem 4rem;}
.he{font-family:'JetBrains Mono',monospace;font-size:.75rem;color:var(--g);letter-spacing:.25em;margin-bottom:1.8rem;opacity:0;animation:fu .8s .2s forwards;}
.hn{font-size:clamp(3.5rem,8vw,7.5rem);font-weight:900;letter-spacing:-.02em;line-height:1;margin-bottom:1.2rem;opacity:0;animation:fu .9s .4s forwards;}
.hn span{color:var(--g);}
.hr{font-family:'JetBrains Mono',monospace;font-size:clamp(.85rem,2vw,1.1rem);color:var(--td);letter-spacing:.08em;margin-bottom:2.8rem;opacity:0;animation:fu .9s .6s forwards;}
.term{background:rgba(10,22,12,.9);border:1px solid var(--bb);border-radius:10px;width:min(680px,92vw);text-align:left;overflow:hidden;opacity:0;animation:fu .9s .8s forwards;box-shadow:0 0 60px rgba(45,184,77,.08);}
.tb{background:rgba(20,42,22,.9);padding:.65rem 1rem;display:flex;align-items:center;gap:.5rem;border-bottom:1px solid var(--br);}
.td{width:10px;height:10px;border-radius:50%;}
.td.r{background:#ff5f57;}.td.y{background:#febc2e;}.td.g{background:#28c840;}
.tt{font-family:'JetBrains Mono',monospace;font-size:.7rem;color:var(--tm);margin:0 auto;letter-spacing:.08em;}
.tbody{padding:1.4rem 1.6rem;}
.tbody p{font-family:'JetBrains Mono',monospace;font-size:.78rem;line-height:1.9;color:var(--td);}
.tp{color:var(--g);margin-right:.5rem;}.tv{color:var(--tx);}.tk{color:#6bd98a;}.tc{color:var(--tm);}
.bc{display:inline-block;width:8px;height:1em;background:var(--g);vertical-align:text-bottom;animation:bl 1s step-end infinite;}
.hc{display:flex;gap:1rem;flex-wrap:wrap;justify-content:center;margin-top:2.4rem;opacity:0;animation:fu .9s 1.2s forwards;}
.btn{font-family:'JetBrains Mono',monospace;font-size:.78rem;letter-spacing:.12em;padding:.75rem 1.8rem;border-radius:4px;text-decoration:none;transition:all .25s;cursor:none;}
.bp{background:var(--g);color:#040a05;font-weight:600;border:1px solid var(--g);}
.bp:hover{background:transparent;color:var(--g);box-shadow:0 0 24px var(--gg);}
.bo{background:transparent;color:var(--g);border:1px solid var(--bb);}
.bo:hover{background:var(--gf);border-color:var(--g);box-shadow:0 0 18px var(--gg);}

/* ==========================================================================
   SHARED SECTION SHELL — every section below uses this frame
   ========================================================================== */
.si{max-width:1100px;margin:0 auto;padding:6rem 2rem;}
.sl2{font-family:'JetBrains Mono',monospace;font-size:.72rem;color:var(--g);letter-spacing:.22em;margin-bottom:.8rem;display:flex;align-items:center;gap:.8rem;}
.sl2::after{content:'';flex:1;height:1px;background:var(--br);max-width:80px;}
.sh{font-size:clamp(2rem,4vw,3rem);font-weight:700;letter-spacing:-.02em;margin-bottom:3rem;line-height:1.1;}

/* ==========================================================================
   ABOUT
   ========================================================================== */
#about{background:linear-gradient(180deg,var(--bg) 0%,var(--bg2) 100%);}
.ag{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:start;}
.at p{color:var(--td);font-size:1rem;line-height:1.85;margin-bottom:1.2rem;}
.at strong{color:var(--tx);font-weight:600;}
.sg{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
.sc{background:var(--bg3);border:1px solid var(--br);border-radius:8px;padding:1.4rem;transition:border-color .25s,box-shadow .25s;}
.sc:hover{border-color:var(--bb);box-shadow:0 0 24px var(--gg);}
.sn{font-size:2.2rem;font-weight:900;color:var(--g);line-height:1;margin-bottom:.3rem;}
.sk{font-family:'JetBrains Mono',monospace;font-size:.7rem;color:var(--tm);letter-spacing:.1em;}

/* ==========================================================================
   PROJECTS — self-contained card grid module
   ========================================================================== */
#projects{background:var(--bg2);}
.pg{display:grid;grid-template-columns:repeat(auto-fit,minmax(320px,1fr));gap:1.5rem;}
.pc{background:var(--bg3);border:1px solid var(--br);border-radius:10px;padding:2rem;transition:all .3s;position:relative;overflow:hidden;cursor:none;display:flex;flex-direction:column;}
.pc::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:var(--g);transform:scaleX(0);transition:transform .3s;}
.pc:hover{border-color:var(--bb);box-shadow:0 8px 48px rgba(45,184,77,.12);transform:translateY(-4px);}
.pc:hover::before{transform:scaleX(1);}
.ptag{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:var(--g);background:var(--gf);border:1px solid var(--br);padding:.2rem .6rem;border-radius:3px;letter-spacing:.1em;display:inline-block;margin-bottom:1rem;align-self:flex-start;}
.pn{font-size:1.2rem;font-weight:700;margin-bottom:.6rem;}
.pd{font-size:.88rem;color:var(--td);line-height:1.7;margin-bottom:1.4rem;flex:1;}
.ps{display:flex;flex-wrap:wrap;gap:.4rem;margin-bottom:1.5rem;}
.pi{font-family:'JetBrains Mono',monospace;font-size:.62rem;color:var(--tm);border:1px solid rgba(45,184,77,.12);padding:.18rem .55rem;border-radius:3px;}
.plr{display:flex;gap:1.4rem;flex-wrap:wrap;}
.pl{font-family:'JetBrains Mono',monospace;font-size:.72rem;color:var(--g);text-decoration:none;letter-spacing:.08em;transition:opacity .2s;display:inline-flex;align-items:center;gap:.4rem;cursor:none;}
.pl:hover{opacity:.75;}.pl::after{content:'→';}

/* ==========================================================================
   WRITING — self-contained sequential list module (independent of PROJECTS)
   ========================================================================== */
#writing{background:linear-gradient(180deg,var(--bg2) 0%,var(--bg) 100%);}
.wl{display:flex;flex-direction:column;}
.wi{display:grid;grid-template-columns:64px 1fr auto;gap:1.6rem;align-items:start;padding:2.1rem 0;border-top:1px solid var(--br);transition:padding-left .25s;cursor:none;}
.wi:last-child{border-bottom:1px solid var(--br);}
.wi:hover{padding-left:.6rem;}
.wnum{font-family:'JetBrains Mono',monospace;font-size:.95rem;color:var(--tm);letter-spacing:.05em;padding-top:.15rem;}
.wbody .wmeta{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:var(--g);letter-spacing:.12em;margin-bottom:.6rem;}
.wbody .wtitle{font-size:1.15rem;font-weight:700;line-height:1.4;margin-bottom:.55rem;color:var(--tx);}
.wbody .wdesc{font-size:.86rem;color:var(--td);line-height:1.7;max-width:640px;}
.wextra{margin-top:.9rem;}
.wlink{font-family:'JetBrains Mono',monospace;font-size:.72rem;color:var(--g);text-decoration:none;letter-spacing:.08em;white-space:nowrap;padding-top:.15rem;transition:opacity .2s;}
.wlink:hover{opacity:.7;}
.wlink::after{content:' →';}
@media(max-width:640px){
  .wi{grid-template-columns:32px 1fr;}
  .wlink{grid-column:2;margin-top:.4rem;}
}

/* ==========================================================================
   SKILLS
   ========================================================================== */
#skills{background:var(--bg);}
.kg{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1.5rem;}
.kg2{background:var(--bg3);border:1px solid var(--br);border-radius:10px;padding:1.6rem;transition:border-color .25s;}
.kg2:hover{border-color:var(--bb);}
.kt{font-family:'JetBrains Mono',monospace;font-size:.72rem;color:var(--g);letter-spacing:.15em;margin-bottom:1.2rem;padding-bottom:.7rem;border-bottom:1px solid var(--br);}
.kb{margin-bottom:1rem;}
.kl{display:flex;justify-content:space-between;font-family:'JetBrains Mono',monospace;font-size:.72rem;color:var(--td);margin-bottom:.4rem;}
.ktr{height:3px;background:rgba(45,184,77,.08);border-radius:2px;overflow:hidden;}
.kf{height:100%;background:var(--g);border-radius:2px;width:0;transition:width 1.2s cubic-bezier(.4,0,.2,1);}

/* ==========================================================================
   CONTACT
   ========================================================================== */
#contact{background:linear-gradient(180deg,var(--bg) 0%,var(--bg2) 100%);}
.ci{max-width:700px;margin:0 auto;padding:6rem 2rem;text-align:center;}
.ci .sl2{justify-content:center;}.ci .sl2::after{display:none;}
.cd{color:var(--td);font-size:1rem;line-height:1.8;margin-bottom:2.5rem;}
.cc{display:flex;justify-content:center;gap:1rem;flex-wrap:wrap;}
.ca{font-family:'JetBrains Mono',monospace;font-size:.75rem;color:var(--td);text-decoration:none;border:1px solid var(--br);padding:.7rem 1.4rem;border-radius:4px;letter-spacing:.1em;transition:all .25s;display:flex;align-items:center;gap:.5rem;cursor:none;}
.ca:hover{color:var(--g);border-color:var(--bb);box-shadow:0 0 18px var(--gg);}

/* ==========================================================================
   FOOTER
   ========================================================================== */
footer{border-top:1px solid var(--br);padding:1.8rem 3rem;display:flex;justify-content:space-between;align-items:center;position:relative;z-index:1;background:var(--bg2);}
footer p{font-family:'JetBrains Mono',monospace;font-size:.68rem;color:var(--tm);letter-spacing:.08em;}

/* ==========================================================================
   REVEAL — shared scroll-in utility
   ========================================================================== */
.rv{opacity:0;transform:translateY(28px);transition:opacity .7s,transform .7s;}
.rv.on{opacity:1;transform:none;}

@media(max-width:768px){
  nav{padding:1rem 1.2rem;}.nm{gap:1.2rem;}
  .ag{grid-template-columns:1fr;gap:2rem;}
  footer{flex-direction:column;gap:.5rem;text-align:center;}
}
</style>
</head>
<body>

<div id="cur"></div>
<div id="cur-r"></div>

<!-- ============================== INTRO SEAL ============================== -->
<div id="seal">
  <div class="sw">
    <svg class="sv cw" viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
      <circle cx="250" cy="250" r="240" fill="none" stroke="rgba(45,184,77,0.18)" stroke-width="0.8"/>
      <circle cx="250" cy="250" r="226" fill="none" stroke="rgba(45,184,77,0.06)" stroke-width="0.5" stroke-dasharray="2 8"/>
      <defs><path id="ot" d="M250,250 m-210,0 a210,210 0 1,1 420,0 a210,210 0 1,1 -420,0"/></defs>
      <text font-family="JetBrains Mono,monospace" font-size="10.5" fill="rgba(45,184,77,0.38)" letter-spacing="5.5">
        <textPath href="#ot">CYBERSECURITY &nbsp;·&nbsp; THREAT INTELLIGENCE &nbsp;·&nbsp; DEVSECOPS &nbsp;·&nbsp; OSINT &nbsp;·&nbsp; BARCELONA &nbsp;·&nbsp; </textPath>
      </text>
    </svg>
    <svg class="sv ccw" viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
      <circle cx="250" cy="250" r="165" fill="none" stroke="rgba(45,184,77,0.15)" stroke-width="0.8"/>
      <circle cx="250" cy="250" r="152" fill="none" stroke="rgba(45,184,77,0.05)" stroke-width="0.5" stroke-dasharray="1 5"/>
      <defs><path id="it" d="M250,250 m-158,0 a158,158 0 1,1 316,0 a158,158 0 1,1 -316,0"/></defs>
      <text font-family="JetBrains Mono,monospace" font-size="8.5" fill="rgba(45,184,77,0.2)" letter-spacing="3.8">
        <textPath href="#it">STIX 2.1 &nbsp;·&nbsp; TAXII &nbsp;·&nbsp; MISP &nbsp;·&nbsp; MITRE ATT&amp;CK &nbsp;·&nbsp; CRAFTING INTERPRETERS &nbsp;·&nbsp; JLOX &nbsp;·&nbsp; </textPath>
      </text>
    </svg>
    <svg class="sv" viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <radialGradient id="dg" cx="50%" cy="50%" r="50%">
          <stop offset="0%" stop-color="rgba(45,184,77,0.08)"/>
          <stop offset="100%" stop-color="rgba(0,0,0,0)"/>
        </radialGradient>
      </defs>
      <circle cx="250" cy="250" r="130" fill="url(#dg)"/>
      <circle cx="250" cy="250" r="130" fill="none" stroke="rgba(45,184,77,0.1)" stroke-width="0.5"/>
    </svg>
  </div>
  <div class="sl">ALBORZ NAZARI</div>
  <div class="ss">CYBERSECURITY ENGINEER &nbsp;·&nbsp; BARCELONA</div>
  <div class="sbw"><div class="sb" id="sbar"></div></div>
</div>

<canvas id="bgc"></canvas>

<!-- ============================== NAV ============================== -->
<nav id="nav">
  <a href="#" class="nl">AN://</a>
  <ul class="nm">
    <li><a href="#about">about</a></li>
    <li><a href="#projects">projects</a></li>
    <li><a href="#writing">writing</a></li>
    <li><a href="#skills">skills</a></li>
    <li><a href="#contact">contact</a></li>
  </ul>
</nav>

<!-- ============================== HERO ============================== -->
<section id="hero">
  <p class="he">// Barcelona, Spain &nbsp;·&nbsp; Open to EU Roles</p>
  <h1 class="hn">Alborz<br><span>Nazari</span></h1>
  <p class="hr">Threat Intelligence &nbsp;·&nbsp; DevSecOps &nbsp;·&nbsp; Security Engineering</p>
  <div class="term">
    <div class="tb">
      <div class="td r"></div><div class="td y"></div><div class="td g"></div>
      <span class="tt">whoami.sh</span>
    </div>
    <div class="tbody" id="tout"></div>
  </div>
  <div class="hc">
    <a href="#projects" class="btn bp">View Projects</a>
    <a href="#writing" class="btn bo">Read Writing</a>
    <a href="https://github.com/AlborzNazari" target="_blank" class="btn bo">GitHub</a>
  </div>
</section>

<!-- ============================== ABOUT ============================== -->
<section id="about">
  <div class="si">
    <p class="sl2 rv">01 // ABOUT</p>
    <h2 class="sh rv">Engineer who builds<br>and <span style="color:var(--g)">secures.</span></h2>
    <div class="ag">
      <div class="at rv">
        <p>Mathematics and computer science do not cease to exist. New technologies emerge, and the curiosity to understand logic becomes the most durable skill you can carry. I have worked with thousands of international clients and learned how people communicate, how they think, and how they approach problems. That experience taught me to connect things others keep separate and to bring analytical clarity to DevSecOps, threat intelligence, and software development.
I ran the gamut from 3D technical art, VFX, and DCC tools. Studied for a B.Sc. in Computer Engineering, and built original systems from scratch. During my studies at FX Barcelona, I worked at FunPlus in the gaming industry and found a lively and supportive community.</p>
        <p>I can translate complex threat data into clear, actionable intelligence for both technical and non-technical audiences, a skill shaped by years of client-facing engineering work. I bring strong soft skills and an entrepreneurial mindset: I build things independently, take ownership end to end, and know how to move in environments where the structure is not handed to you. Based in Barcelona and open to remote or hybrid roles in Threat Intelligence, Security Development, and SOC Analysis. If your team values depth, rigorous documentation, and open-source credibility, I would be glad to connect.</p>
      </div>
      <div class="sg rv">
        <div class="sc"><div class="sn">116</div><div class="sk">pytest tests · OIL v0.7</div></div>
        <div class="sc"><div class="sn">8,000+</div><div class="sk">forks handled · Shadowbroker incident</div></div>
        <div class="sc"><div class="sn">3</div><div class="sk">deep-dive technical articles</div></div>
        <div class="sc"><div class="sn">Top 3%</div><div class="sk">TryHackMe community</div></div>
      </div>
    </div>
  </div>
</section>

<!-- ============================== PROJECTS (independent module) ============================== -->
<section id="projects">
  <div class="si">
    <p class="sl2 rv">02 // PROJECTS</p>
    <h2 class="sh rv">What I've <span style="color:var(--g)">built.</span></h2>
    <div class="pg">

      <div class="pc rv">
        <span class="ptag">FLAGSHIP · ACTIVE</span>
        <div class="pn">Open Intelligence Lab</div>
        <div class="pd">Graph-based cyber threat intelligence platform. STIX 2.1 + TAXII 2.1 compliant. Integrates MISP live feeds, MITRE ATT&CK, and SIEM connectors for Splunk, Sentinel, QRadar, and OpenCTI. 116-test pytest suite, deployed on Fly.io with full CI/CD. Rebuilt on GitLab as a transparent, modular, fully open-source model.</div>
        <div class="ps"><span class="pi">FastAPI</span><span class="pi">NetworkX</span><span class="pi">STIX 2.1</span><span class="pi">TAXII</span><span class="pi">MISP</span><span class="pi">Docker</span><span class="pi">GitLab CI</span><span class="pi">Fly.io</span></div>
        <div class="plr">
          <a href="https://github.com/AlborzNazari/open-intelligence-lab" target="_blank" class="pl">Repository</a>
          <a href="https://medium.com/@alborznazari4/open-intelligence-lab-on-git-from-a-black-box-to-a-transparent-modular-and-open-source-model-ffa154962964" target="_blank" class="pl">Writeup</a>
        </div>
      </div>

      <div class="pc rv">
        <span class="ptag">OSINT · GEOSPATIAL</span>
        <div class="pn">Shadowbroker</div>
        <div class="pd">Real-time geospatial OSINT dashboard. Spain and USA CCTV intelligence layers, GPS jamming detection, pixel-level change-detection alert pipeline, and STIX 2.1 export. Fork grew past 8,000 during a live incident that turned into a supply-chain attribution case study.</div>
        <div class="ps"><span class="pi">Python</span><span class="pi">STIX 2.1</span><span class="pi">Geospatial</span><span class="pi">OSINT</span><span class="pi">Alert Pipeline</span></div>
        <div class="plr">
          <a href="https://github.com/AlborzNazari/Shadowbroker" target="_blank" class="pl">Repository</a>
          <a href="https://medium.com/@alborznazari4/shadowbroker-how-open-source-intelligence-layers-turn-raw-signals-into-analyst-findings-a54c770b3dac" target="_blank" class="pl">Writeup</a>
        </div>
      </div>

      <div class="pc rv">
        <span class="ptag">CRYPTOGRAPHY · CIVIC</span>
        <div class="pn">Secure Apportionment System</div>
        <div class="pd">Huntington-Hill parliamentary seat allocation with AES-256-CBC encryption. Full Docker containerization, Tkinter + Flask UI, and comprehensive PDF documentation.</div>
        <div class="ps"><span class="pi">Python</span><span class="pi">AES-256</span><span class="pi">Flask</span><span class="pi">Docker</span><span class="pi">Tkinter</span></div>
        <div class="plr">
          <a href="https://github.com/AlborzNazari/Secure-Apportionment-System" target="_blank" class="pl">Repository</a>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ============================== WRITING (independent module, sequential list) ============================== -->
<section id="writing">
  <div class="si">
    <p class="sl2 rv">03 // WRITING</p>
    <h2 class="sh rv">Notes from <span style="color:var(--g)">the field.</span></h2>
    <div class="wl">

      <div class="wi rv">
        <span class="wnum">01</span>
        <div class="wbody">
          <p class="wmeta">LANGUAGE DESIGN · SECURITY ANALYSIS · JUL 2026</p>
          <p class="wtitle">Lox Under the Microscope: Design Trade-offs, Measurable Faults, and What Real Languages Do Differently</p>
          <p class="wdesc">A three-chapter deep dive into interpreter design using Lox from Crafting Interpreters as the lens — typing, memory management, mutability, and macros, followed by static analysis (SpotBugs, cppcheck), fuzzing, and AFL++ against jlox and clox to see where a toy language's design choices become real attack surfaces.</p>
          <div class="plr wextra">
            <a href="https://github.com/AlborzNazari/Robert_Nystrom_craftinginterpreters" target="_blank" class="pl">Repository</a>
          </div>
        </div>
        <a href="https://medium.com/@alborznazari4/lox-under-the-microscope-design-trade-offs-measurable-faults-and-what-real-languages-do-e01637e5fd7f" target="_blank" class="wlink">Read</a>
      </div>

      <div class="wi rv">
        <span class="wnum">02</span>
        <div class="wbody">
          <p class="wmeta">INCIDENT REPORT · SUPPLY CHAIN · MAY 2026</p>
          <p class="wtitle">Thundering Herd via Inherited Scheduler: How My Fork Became Someone Else's Threat Feed</p>
          <p class="wdesc">A live incident write-up: an inherited hardcoded scheduler in a forked OSINT repo synchronized thousands of independent machines onto a single endpoint at the same second each day, producing a DDoS-shaped signature and a supply-chain attribution failure — plus the five-line jitter fix and the patches applied along the way.</p>
          <div class="plr wextra">
            <a href="https://github.com/AlborzNazari/Shadowbroker/releases" target="_blank" class="pl">Releases</a>
          </div>
        </div>
        <a href="https://medium.com/@alborznazari4/thundering-herd-via-inherited-scheduler-how-my-fork-became-someone-elses-threat-feed-584db81a8ae4" target="_blank" class="wlink">Read</a>
      </div>

      <div class="wi rv">
        <span class="wnum">03</span>
        <div class="wbody">
          <p class="wmeta">CONCURRENCY · SYSTEMS DESIGN</p>
          <p class="wtitle">Threading the Needle: Race Conditions, Atomic Violations, and the Concurrency Flaws That Break Systems</p>
          <p class="wdesc">A technical article on race conditions built from first principles — TOCTOU, atomicity violations, GIL internals, and mutex design — grounded in a companion Vault Heist Simulator that demonstrates the same failure both by design and by bug.</p>
          <div class="plr wextra">
            <a href="https://github.com/AlborzNazari/SECURE_ATM_BANK_SYSTEM/tree/main/atm-bank" target="_blank" class="pl">Repository</a>
          </div>
        </div>
        <a href="https://medium.com/@alborznazari4/threading-the-needle-race-conditions-atomic-violations-and-the-concurrency-flaws-that-break-b7bfdc2f7993" target="_blank" class="wlink">Read</a>
      </div>

    </div>
  </div>
</section>

<!-- ============================== SKILLS ============================== -->
<section id="skills">
  <div class="si">
    <p class="sl2 rv">04 // SKILLS</p>
    <h2 class="sh rv">The <span style="color:var(--g)">stack.</span></h2>
    <div class="kg">
      <div class="kg2 rv">
        <div class="kt">// THREAT INTELLIGENCE</div>
        <div class="kb"><div class="kl"><span>STIX 2.1 / TAXII</span><span>95%</span></div><div class="ktr"><div class="kf" data-w="95"></div></div></div>
        <div class="kb"><div class="kl"><span>MISP</span><span>88%</span></div><div class="ktr"><div class="kf" data-w="88"></div></div></div>
        <div class="kb"><div class="kl"><span>MITRE ATT&amp;CK</span><span>85%</span></div><div class="ktr"><div class="kf" data-w="85"></div></div></div>
        <div class="kb"><div class="kl"><span>OpenCTI</span><span>80%</span></div><div class="ktr"><div class="kf" data-w="80"></div></div></div>
      </div>
      <div class="kg2 rv">
        <div class="kt">// DEVSECOPS</div>
        <div class="kb"><div class="kl"><span>Docker / CI/CD</span><span>90%</span></div><div class="ktr"><div class="kf" data-w="90"></div></div></div>
        <div class="kb"><div class="kl"><span>GitLab / GitHub Actions</span><span>88%</span></div><div class="ktr"><div class="kf" data-w="88"></div></div></div>
        <div class="kb"><div class="kl"><span>Splunk / Sentinel</span><span>78%</span></div><div class="ktr"><div class="kf" data-w="78"></div></div></div>
        <div class="kb"><div class="kl"><span>Fly.io / Cloud Deploy</span><span>82%</span></div><div class="ktr"><div class="kf" data-w="82"></div></div></div>
      </div>
      <div class="kg2 rv">
        <div class="kt">// ENGINEERING</div>
        <div class="kb"><div class="kl"><span>Python / FastAPI</span><span>92%</span></div><div class="ktr"><div class="kf" data-w="92"></div></div></div>
        <div class="kb"><div class="kl"><span>Linux / Bash</span><span>88%</span></div><div class="ktr"><div class="kf" data-w="88"></div></div></div>
        <div class="kb"><div class="kl"><span>Compilers / Interpreters</span><span>84%</span></div><div class="ktr"><div class="kf" data-w="84"></div></div></div>
        <div class="kb"><div class="kl"><span>pytest / Test Design</span><span>86%</span></div><div class="ktr"><div class="kf" data-w="86"></div></div></div>
      </div>
    </div>
  </div>
</section>

<!-- ============================== CONTACT ============================== -->
<section id="contact">
  <div class="ci">
    <p class="sl2 rv">05 // CONTACT</p>
    <h2 class="sh rv">Let's <span style="color:var(--g)">connect.</span></h2>
    <p class="cd rv">Open to cybersecurity engineering roles across the EU. DevSecOps, threat intelligence, security engineering. Full EU work authorization. Remote-friendly.</p>
    <div class="cc rv">
      <a href="mailto:alborznazari4@gmail.com" class="ca">✉ Email</a>
      <a href="https://github.com/AlborzNazari" target="_blank" class="ca">⌥ GitHub</a>
      <a href="https://linkedin.com/in/AlborzNazari" target="_blank" class="ca">◈ LinkedIn</a>
      <a href="https://medium.com/@alborznazari4" target="_blank" class="ca">◎ Medium</a>
    </div>
  </div>
</section>

<footer>
  <p>© 2026 Alborz Nazari</p>
  <p>Barcelona</p>
</footer>

<script>
(function() {
  var seal = document.getElementById('seal');
  var nav  = document.getElementById('nav');
  var sbar = document.getElementById('sbar');

  document.body.style.overflow = 'hidden';

  setTimeout(function() { sbar.style.width = '100%'; }, 80);

  setTimeout(function() {
    seal.classList.add('gone');
    document.body.style.overflow = '';
    nav.classList.add('show');
  }, 2600);

  // Cursor
  var cur  = document.getElementById('cur');
  var curR = document.getElementById('cur-r');
  var mx=0, my=0, rx=0, ry=0;
  document.addEventListener('mousemove', function(e) {
    mx = e.clientX; my = e.clientY;
    cur.style.left = mx+'px'; cur.style.top = my+'px';
  });
  (function loop() {
    rx += (mx-rx)*0.12; ry += (my-ry)*0.12;
    curR.style.left = rx+'px'; curR.style.top = ry+'px';
    requestAnimationFrame(loop);
  })();
  document.querySelectorAll('a,button').forEach(function(el) {
    el.addEventListener('mouseenter', function() { curR.style.width='52px'; curR.style.height='52px'; });
    el.addEventListener('mouseleave', function() { curR.style.width='36px'; curR.style.height='36px'; });
  });

  // BG canvas
  var cv = document.getElementById('bgc');
  var ctx = cv.getContext('2d');
  var W, H, pts = [];
  function resize() { W = cv.width = window.innerWidth; H = cv.height = window.innerHeight; }
  resize(); window.addEventListener('resize', resize);
  function Pt() { this.x=Math.random()*W; this.y=Math.random()*H; this.vx=(Math.random()-.5)*.18; this.vy=(Math.random()-.5)*.18; this.r=Math.random()*1.4+.3; this.a=Math.random()*.5+.1; }
  Pt.prototype.tick = function() { this.x+=this.vx; this.y+=this.vy; if(this.x<0||this.x>W||this.y<0||this.y>H){this.x=Math.random()*W;this.y=Math.random()*H;} };
  for(var i=0;i<90;i++) pts.push(new Pt());
  function grid() {
    var g=48; ctx.strokeStyle='rgba(30,110,50,.12)'; ctx.lineWidth=.5;
    for(var x=0;x<W;x+=g){ctx.beginPath();ctx.moveTo(x,0);ctx.lineTo(x,H);ctx.stroke();}
    for(var y=0;y<H;y+=g){ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(W,y);ctx.stroke();}
    ctx.fillStyle='rgba(45,184,77,.18)';
    for(var x=0;x<W;x+=g) for(var y=0;y<H;y+=g){ctx.beginPath();ctx.arc(x,y,1,0,Math.PI*2);ctx.fill();}
  }
  function lines() {
    for(var i=0;i<pts.length;i++) for(var j=i+1;j<pts.length;j++) {
      var d=Math.hypot(pts[i].x-pts[j].x,pts[i].y-pts[j].y);
      if(d<110){ctx.strokeStyle='rgba(45,184,77,'+(0.07*(1-d/110))+')';ctx.lineWidth=.5;ctx.beginPath();ctx.moveTo(pts[i].x,pts[i].y);ctx.lineTo(pts[j].x,pts[j].y);ctx.stroke();}
    }
  }
  function draw() {
    ctx.clearRect(0,0,W,H); grid();
    pts.forEach(function(p){p.tick();ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);ctx.fillStyle='rgba(45,184,77,'+p.a+')';ctx.fill();});
    lines(); requestAnimationFrame(draw);
  }
  draw();

  // Terminal
  var lines2=[
    ['p','❯ ','cat whoami.json'],
    ['j','{'],
    ['k','  "name"',':','"Alborz Nazari"'],
    ['k','  "role"',':','"Cybersecurity Engineer"'],
    ['k','  "location"',':','"Barcelona, Spain"'],
    ['k','  "stack"',':', '["STIX","TAXII","MISP","FastAPI","Docker"]'],
    ['k','  "currently"',':','"Fuzzing jlox, patching OIL"'],
    ['k','  "status"',':','"Seeking EU cybersecurity roles"'],
    ['j','}'],
  ];
  var tout=document.getElementById('tout'), li=0;
  function typeNext() {
    if(li>=lines2.length){var b=document.createElement('span');b.className='bc';tout.appendChild(b);return;}
    var ln=lines2[li], p=document.createElement('p');
    if(ln[0]==='p'){
      p.innerHTML='<span class="tp">'+ln[1]+'</span>';
      var t=document.createTextNode('');p.appendChild(t);tout.appendChild(p);
      var s=ln[2],idx=0;
      (function tick(){if(idx<s.length){t.textContent+=s[idx++];setTimeout(tick,38+Math.random()*28);}else{li++;setTimeout(typeNext,100);}})();
    } else if(ln[0]==='j'){
      p.innerHTML='<span class="tc">'+ln[1]+'</span>';tout.appendChild(p);li++;setTimeout(typeNext,40);
    } else {
      p.innerHTML='<span class="tk">'+ln[1]+'</span><span class="tc">'+ln[2]+'</span> <span class="tv">'+ln[3]+'</span>';tout.appendChild(p);li++;setTimeout(typeNext,55);
    }
  }
  setTimeout(typeNext, 3000);

  // Scroll reveal
  var rvs=document.querySelectorAll('.rv');
  var obs=new IntersectionObserver(function(es){es.forEach(function(e){if(e.isIntersecting){e.target.classList.add('on');obs.unobserve(e.target);}})},{threshold:.12});
  rvs.forEach(function(el){obs.observe(el);});

  // Skill bars
  var brs=document.querySelectorAll('.kf');
  var bObs=new IntersectionObserver(function(es){es.forEach(function(e){if(e.isIntersecting){e.target.style.width=e.target.dataset.w+'%';bObs.unobserve(e.target);}})},{threshold:.3});
  brs.forEach(function(b){bObs.observe(b);});
})();
</script>
</body>
</html>
