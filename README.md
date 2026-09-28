<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="description" content="Alborz Nazari: cybersecurity engineer, 3D artist and writer in Barcelona. A portfolio in five reels.">
<meta property="og:title" content="Alborz Nazari">
<meta property="og:description" content="Cybersecurity engineer, 3D artist and writer in Barcelona.">
<meta property="og:url" content="https://alborznazari.github.io/">
<style>*,*::before,*::after{box-sizing:border-box}html,body{margin:0}img{max-width:100%}</style>
<title>Alborz Nazari</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Shrikhand&family=Spectral:ital,wght@0,400;0,600;1,400;1,600&family=IBM+Plex+Mono:wght@400;500&display=swap">
<style>
:root{
  color-scheme: dark;
  --ink:#0e090b;
  --bone:#f1e6d8;
  --bone-dim:#b9a99c;
  --flesh:#e98a74;
  --waters:#ff3f8e;
  --vhs:#5fd3cf;
  --robot:#ff2a3a;
  --teal:#3fc6c8;
  --accent:var(--waters);
  --display:"Shrikhand","Cooper Black","Georgia",serif;
  --body:"Spectral","Iowan Old Style","Georgia",serif;
  --mono:"IBM Plex Mono","SFMono-Regular","Consolas",monospace;
}
html{background:var(--ink)}
body{background:var(--ink);color:var(--bone);font-family:var(--body);font-size:18px;line-height:1.6;overflow-x:hidden}
a{color:inherit}
::selection{background:var(--waters);color:var(--ink)}
:focus-visible{outline:2px solid var(--vhs);outline-offset:3px}

#gl{position:fixed;inset:0;width:100%;height:100%;display:block;z-index:0;touch-action:pan-y}
.fx{position:fixed;inset:0;pointer-events:none;z-index:2}
.grain{opacity:.06;mix-blend-mode:overlay;background-size:160px 160px;animation:grain 1s steps(6) infinite}
@keyframes grain{0%{background-position:0 0}20%{background-position:-40px 20px}40%{background-position:30px -50px}60%{background-position:-60px -10px}80%{background-position:50px 40px}100%{background-position:0 0}}
.scan{background:repeating-linear-gradient(to bottom,rgba(0,0,0,0) 0 2px,rgba(0,0,0,.14) 2px 3px);opacity:.4}
.vignette{background:radial-gradient(ellipse at center,rgba(0,0,0,0) 48%,rgba(8,4,6,.82) 100%)}

.booth{position:fixed;top:0;left:0;right:0;z-index:5;display:flex;justify-content:space-between;align-items:center;gap:1rem;
  padding:calc(env(safe-area-inset-top,0px) + 12px) clamp(16px,4vw,40px) 12px;
  font-family:var(--mono);font-size:12px;letter-spacing:.14em;text-transform:uppercase;
  background:linear-gradient(to bottom,rgba(14,9,11,.92),rgba(14,9,11,0))}
.booth .mark{font-family:var(--display);letter-spacing:0;text-transform:none;font-size:20px;color:var(--waters);text-decoration:none}
.booth .tc{font-variant-numeric:tabular-nums;color:var(--bone-dim)}
.booth .tc b{color:var(--bone);font-weight:500}
.cue{position:fixed;z-index:6;top:calc(env(safe-area-inset-top,0px) + 58px);right:clamp(20px,4vw,44px);width:22px;height:22px;border-radius:50%;
  background:radial-gradient(circle,rgba(255,255,255,.95) 0 30%,rgba(255,220,200,.6) 55%,rgba(255,200,180,0) 70%);opacity:0;pointer-events:none}
.cue.on{animation:cue .5s steps(2) 2}
@keyframes cue{0%{opacity:1}50%{opacity:0}100%{opacity:0}}

.reels{position:fixed;z-index:5;right:clamp(12px,2.4vw,28px);top:50%;transform:translateY(-50%);display:flex;flex-direction:column;gap:14px;font-family:var(--mono);font-size:11px;letter-spacing:.12em}
.reels a{display:flex;align-items:center;justify-content:flex-end;gap:10px;text-decoration:none;color:var(--bone-dim);text-transform:uppercase}
.reels a span{opacity:0;transform:translateX(6px);transition:opacity .25s,transform .25s}
.reels a:hover span,.reels a:focus-visible span,.reels a.on span{opacity:1;transform:none}
.reels a i{width:9px;height:9px;border:1px solid var(--bone-dim);border-radius:50%;transition:background .25s,border-color .25s}
.reels a.on{color:var(--bone)}
.reels a.on i{background:var(--waters);border-color:var(--waters)}

main{position:relative;z-index:3;padding-inline:clamp(16px,5vw,80px)}
.reel{min-height:100vh;display:grid;grid-template-columns:minmax(0,35rem) minmax(0,1fr);gap:clamp(1.5rem,4vw,4rem);align-items:start;padding-block:12vh}
.reel.right{grid-template-columns:minmax(0,1fr) minmax(0,35rem);padding-right:clamp(0px,4vw,60px)}
.win{position:sticky;top:calc(env(safe-area-inset-top,0px) + 11vh);height:78vh;min-height:320px;pointer-events:none}

.hero{display:flex;min-height:100vh;flex-direction:column;align-items:flex-start;justify-content:flex-end;padding-block:18vh 8vh;gap:1.4rem}
.eyebrow{font-family:var(--mono);font-size:12px;letter-spacing:.2em;text-transform:uppercase;color:var(--vhs)}
.hero h1{font-family:var(--display);font-weight:400;font-size:clamp(3.4rem,11vw,10rem);line-height:.86;margin:0;color:var(--bone);
  text-shadow:3px 0 0 rgba(255,63,142,.75),-3px 0 0 rgba(95,211,207,.55);text-wrap:balance;transform:rotate(-3deg);transform-origin:left bottom}
.billing{font-family:var(--mono);font-size:13px;line-height:1.7;letter-spacing:.1em;text-transform:uppercase;max-width:44rem;color:var(--bone-dim);margin:0}
.billing strong{color:var(--bone);font-weight:500}
.hero .lede{max-width:36rem;font-size:clamp(1.05rem,1.6vw,1.25rem);margin:0}
.hint{font-family:var(--mono);font-size:12px;letter-spacing:.14em;text-transform:uppercase;color:var(--flesh)}
.marquee{width:100%;overflow:hidden;border-block:1px solid rgba(241,230,216,.2);padding-block:.55rem;margin-top:1rem}
.marquee div{display:flex;width:max-content;gap:2.2rem;animation:roll 38s linear infinite;font-family:var(--body);font-style:italic;font-size:1.05rem;color:var(--bone-dim);white-space:nowrap}
.marquee b{font-family:var(--mono);font-style:normal;font-weight:500;font-size:11px;letter-spacing:.2em;color:var(--waters);align-self:center}
@keyframes roll{to{transform:translateX(-50%)}}

.panel{position:relative;max-width:35rem;width:100%;background:rgba(14,9,11,.72);backdrop-filter:blur(7px);-webkit-backdrop-filter:blur(7px);
  border:1px solid rgba(241,230,216,.14)}
.slate{display:flex;flex-wrap:wrap;justify-content:space-between;gap:.4rem 1rem;padding:.55rem 1.1rem;background:var(--bone);color:var(--ink);
  font-family:var(--mono);font-size:11px;font-weight:500;letter-spacing:.16em;text-transform:uppercase;
  background-image:repeating-linear-gradient(-45deg,transparent 0 14px,rgba(14,9,11,.07) 14px 28px)}
.slate em{font-style:normal;color:var(--accent);filter:brightness(.7)}
.pbody{padding:1.5rem 1.6rem 1.7rem;display:flex;flex-direction:column;gap:1rem}
.panel h2{font-family:var(--display);font-weight:400;font-size:clamp(2.1rem,4.2vw,3.2rem);line-height:1;margin:0;color:var(--accent);text-wrap:balance}
.panel .kicker{font-family:var(--body);font-style:italic;font-size:1.2rem;margin:0;color:var(--bone)}
.panel p{margin:0}
.credits-list{list-style:none;margin:0;padding:0;display:flex;flex-direction:column;border-top:1px solid rgba(241,230,216,.14)}
.credits-list li{display:grid;grid-template-columns:minmax(0,1fr) auto;gap:.2rem 1rem;padding-block:.6rem;border-bottom:1px solid rgba(241,230,216,.14)}
.credits-list .who{font-weight:600}
.credits-list .who a{text-decoration:none;border-bottom:1px solid var(--accent)}
.credits-list .who a:hover{color:var(--accent)}
.credits-list .what{grid-column:1/-1;font-size:.95rem;color:var(--bone-dim)}
.credits-list .when{font-family:var(--mono);font-size:12px;letter-spacing:.08em;color:var(--accent);font-variant-numeric:tabular-nums;align-self:center}
.links{display:flex;flex-wrap:wrap;gap:.5rem}
.links a,.btn{font-family:var(--mono);font-size:12px;letter-spacing:.12em;text-transform:uppercase;text-decoration:none;color:var(--bone);
  border:1px solid rgba(241,230,216,.35);padding:.45rem .7rem;background:transparent;cursor:pointer;transition:background .2s,color .2s,border-color .2s}
.links a:hover,.btn:hover{background:var(--accent);border-color:var(--accent);color:var(--ink)}
.links a.solid{background:var(--accent);border-color:var(--accent);color:var(--ink)}
.btn[aria-pressed="true"]{background:var(--accent);border-color:var(--accent);color:var(--ink)}
.modes{display:flex;flex-wrap:wrap;gap:.4rem;align-items:center}
.modes small{font-family:var(--mono);font-size:11px;letter-spacing:.14em;text-transform:uppercase;color:var(--bone-dim);margin-right:.3rem}

.stats{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:1px;background:rgba(241,230,216,.14);border:1px solid rgba(241,230,216,.14)}
.stats div{background:rgba(14,9,11,.9);padding:.8rem .9rem}
.stats b{display:block;font-family:var(--display);font-weight:400;font-size:1.9rem;line-height:1;color:var(--accent);font-variant-numeric:tabular-nums}
.stats span{font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:var(--bone-dim)}

.placard{border:1px solid var(--accent);padding:.8rem 1rem;min-height:5.2rem}
.placard .ex{font-family:var(--mono);font-size:11px;letter-spacing:.16em;text-transform:uppercase;color:var(--accent)}
.placard .t{font-family:var(--display);font-size:1.4rem;line-height:1.1;margin-block:.2rem}
.placard .d{font-size:.98rem;color:var(--bone-dim)}
.readout{font-family:var(--mono);font-size:12px;letter-spacing:.06em;color:var(--robot);min-height:1.2em;word-break:break-all}

/* Mr Robot style glitch on the Lab title */
.glitch{position:relative}
.glitch::before,.glitch::after{content:attr(data-text);position:absolute;inset:0;pointer-events:none}
.glitch::before{color:var(--vhs);clip-path:inset(0 0 62% 0);animation:gl1 3.1s infinite steps(1)}
.glitch::after{color:var(--bone);clip-path:inset(58% 0 0 0);animation:gl2 2.7s infinite steps(1)}
@keyframes gl1{0%,86%,100%{transform:none;opacity:0}87%{transform:translate(-4px,1px);opacity:.9}90%{transform:translate(3px,-1px);opacity:.9}93%{transform:translate(-2px,0);opacity:.9}}
@keyframes gl2{0%,78%,100%{transform:none;opacity:0}79%{transform:translate(5px,0);opacity:.85}82%{transform:translate(-3px,1px);opacity:.85}}

.articles{list-style:none;margin:0;padding:0}
.articles li{padding-block:.55rem;border-bottom:1px dashed rgba(241,230,216,.2)}
.articles a{text-decoration:none;font-size:1.05rem;line-height:1.35;display:block}
.articles a:hover{color:var(--accent)}
.articles small{font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:var(--bone-dim)}

/* Mercor feature */
.feature{display:flex;flex-direction:column;gap:.55rem;padding:1.1rem 1.2rem;border:1px solid var(--teal);
  background:linear-gradient(135deg,rgba(255,63,142,.16),rgba(63,198,200,.1))}
.feature .who{font-family:var(--mono);font-size:12px;letter-spacing:.16em;text-transform:uppercase;color:var(--teal)}
.feature .role{font-family:var(--display);font-size:clamp(1.6rem,3vw,2.1rem);line-height:1.05;color:var(--bone)}
.feature ul{margin:0;padding-left:1.1rem;display:flex;flex-direction:column;gap:.3rem;font-size:.97rem}
.feature li::marker{color:var(--waters)}

.end{display:flex;flex-direction:column;justify-content:center;text-align:center;gap:2rem}
.end h2{font-family:var(--display);font-weight:400;font-size:clamp(2.6rem,7vw,5.5rem);margin:0;line-height:1;color:var(--bone);text-shadow:3px 0 0 rgba(255,63,142,.7),-3px 0 0 rgba(95,211,207,.5)}
.roll{display:grid;grid-template-columns:minmax(0,1fr) minmax(0,1fr);gap:.7rem 2rem;max-width:40rem;width:100%;margin-inline:auto;text-align:left;
  background:rgba(14,9,11,.72);backdrop-filter:blur(6px);-webkit-backdrop-filter:blur(6px);padding:1.4rem 1.6rem;border:1px solid rgba(241,230,216,.14)}
.roll dt{font-family:var(--mono);font-size:11px;letter-spacing:.16em;text-transform:uppercase;color:var(--bone-dim);text-align:right;align-self:center}
.roll dd{margin:0;display:flex;flex-wrap:wrap;gap:.3rem .9rem}
.roll dd a{text-decoration:none;border-bottom:1px solid rgba(255,63,142,.5)}
.roll dd a:hover{color:var(--waters)}
.mailrow{display:flex;flex-wrap:wrap;justify-content:center;align-items:center;gap:.6rem;font-family:var(--mono);font-size:14px}
.mailrow code{user-select:all;padding:.45rem .7rem;border:1px solid rgba(241,230,216,.35);background:rgba(14,9,11,.7)}
.soon{font-family:var(--mono);font-size:11px;letter-spacing:.14em;text-transform:uppercase;color:rgba(241,230,216,.45);max-width:34rem;margin-inline:auto}
.soon a{color:rgba(241,230,216,.6)}
.fin{font-family:var(--body);font-style:italic;color:var(--bone-dim)}

@media (max-width:960px){
  .reel,.reel.right{grid-template-columns:minmax(0,1fr);padding-block:9vh 7vh;padding-right:0;gap:1rem}
  .win{position:relative;top:auto;height:clamp(300px,56vh,540px);order:-1}
  .panel{margin-inline:auto}
}
@media (max-width:820px){
  body{font-size:17px}
  .reels{display:none}
  .hero{padding-block:30vh 6vh}
  .roll{grid-template-columns:minmax(0,1fr)}
  .roll dt{text-align:left}
}
@media (prefers-reduced-motion:reduce){
  .grain,.marquee div,.glitch::before,.glitch::after{animation:none}
  .cue.on{animation:none}
}
</style>
</head>
<body>

<canvas id="gl" aria-hidden="true"></canvas>
<div class="fx grain" id="grain"></div>
<div class="fx scan"></div>
<div class="fx vignette"></div>
<div class="cue" id="cue"></div>

<header class="booth">
  <a class="mark" href="#reel-0">Alborz</a>
  <span class="tc">Reel <b id="reelNo">0</b> &nbsp; TC <b id="tcv">00:00:00:00</b></span>
</header>

<nav class="reels" aria-label="Reels">
  <a href="#reel-0" data-i="0"><span>Titles</span><i></i></a>
  <a href="#reel-1" data-i="1"><span>I Pipeline</span><i></i></a>
  <a href="#reel-2" data-i="2"><span>II Museum</span><i></i></a>
  <a href="#reel-3" data-i="3"><span>III Lab</span><i></i></a>
  <a href="#reel-4" data-i="4"><span>IV Page</span><i></i></a>
  <a href="#reel-5" data-i="5"><span>V Conscience</span><i></i></a>
  <a href="#credits" data-i="6"><span>Credits</span><i></i></a>
</nav>

<main>

<section class="reel hero" id="reel-0">
  <span class="eyebrow">Barcelona · 2026 · A feature in five reels</span>
  <h1>Alborz<br>Nazari</h1>
  <p class="billing">Starring <strong>Alborz Nazari</strong> as the security engineer, the 3D artist, the pipeline engineer, the museum salesman, the writer and the red teamer</p>
  <p class="lede">A cybersecurity engineer who came to security by way of visual effects, video games and the shop floor of a very unusual museum. Scroll to roll film.</p>
  <span class="hint">Touch the flesh. Press down to go deeper.</span>
  <div class="marquee" aria-label="Influences">
    <div>
      <b>In the tradition of</b><span>David Cronenberg</span><span>Alejandro Jodorowsky</span><span>Pier Paolo Pasolini</span><span>John Waters</span><span>Divine</span><span>Harmony Korine</span><span>Karen Walton</span><span>Tom Six</span><span>queer and cult cinema</span><span>dark comedy with blunt corners</span>
      <b>In the tradition of</b><span>David Cronenberg</span><span>Alejandro Jodorowsky</span><span>Pier Paolo Pasolini</span><span>John Waters</span><span>Divine</span><span>Harmony Korine</span><span>Karen Walton</span><span>Tom Six</span><span>queer and cult cinema</span><span>dark comedy with blunt corners</span>
    </div>
  </div>
</section>

<section class="reel" id="reel-1" style="--accent:var(--vhs)">
  <article class="panel">
    <div class="slate"><span>Reel I</span><span>Sc. 1 · Take 1</span><em>3D · VFX · Games</em></div>
    <div class="pbody">
      <h2>The Pipeline</h2>
      <p class="kicker">Before the terminal there was the viewport.</p>
      <p>Six years and more as a senior 3D artist and pipeline engineer, building assets and the tools that move them from one department to the next. Motion design for the games industry. Look-dev, compositing, original cartoon characters, and a ray tracer I wrote in C to learn how light gets from a lamp to a pixel.</p>
      <div class="modes" role="group" aria-label="Viewport shading">
        <small>Viewport</small>
        <button class="btn" type="button" id="mode-wire" data-mode="wire" aria-pressed="false">Wireframe</button>
        <button class="btn" type="button" id="mode-normals" data-mode="normals" aria-pressed="false">Normals</button>
        <button class="btn" type="button" id="mode-shade" data-mode="shade" aria-pressed="true">Shaded</button>
      </div>
      <span class="hint">Press and hold on the model to lift it and see its wires</span>
      <ul class="credits-list">
        <li><span class="who">Left Mountains Ltd</span><span class="when">6+ yrs</span><span class="what">Senior 3D Artist and Pipeline Engineer</span></li>
        <li><span class="who"><a href="https://www.youtube.com/watch?v=EviEJOIwdqk&amp;list=PLTr1OrS7PuQS5SL0gisfcacFy7FBvgB5y" target="_blank" rel="noopener">FunPlus Spain</a></span><span class="when">Contract</span><span class="what">Motion design for video games, while studying at FX Barcelona. Watch the FunPlus videos.</span></li>
        <li><span class="who">FX Barcelona Film School</span><span class="when">M.Sc.</span><span class="what">Visual Effects and Production Pipeline</span></li>
        <li><span class="who">BNUT</span><span class="when">B.Sc.</span><span class="what">Computer Software Engineering</span></li>
      </ul>
      <div class="links">
        <a href="https://www.youtube.com/watch?v=EviEJOIwdqk&amp;list=PLTr1OrS7PuQS5SL0gisfcacFy7FBvgB5y" target="_blank" rel="noopener">FunPlus videos</a>
        <a href="https://www.artstation.com/alborznazariz" target="_blank" rel="noopener">ArtStation</a>
        <a href="https://vimeo.com/alborznazariz" target="_blank" rel="noopener">Vimeo</a>
        <a href="https://www.youtube.com/@alborznazari" target="_blank" rel="noopener">YouTube</a>
        <a href="https://github.com/AlborzNazari/raytracer" target="_blank" rel="noopener">C Ray Tracer</a>
      </div>
    </div>
  </article>
  <div class="win" aria-hidden="true"></div>
</section>

<section class="reel right" id="reel-2" style="--accent:var(--waters)">
  <div class="win" aria-hidden="true"></div>
  <article class="panel">
    <div class="slate"><span>Reel II</span><span>Sc. 2 · Take 1</span><em>Sales · Communication</em></div>
    <div class="pbody">
      <h2>The Museum</h2>
      <p class="kicker">One delicate subject. Visitors from every continent.</p>
      <p>Promoter and salesman at the Erotic Museum of Barcelona since December 2024, full time since May 2025. Thousands of international visitors, a subject most people giggle about, and a job that runs on charm, timing and discretion. It is the best communication school I have attended. Every threat briefing I write now is aimed at the same reader: a curious stranger who owes me nothing.</p>
      <div class="placard" aria-live="polite">
        <div class="ex" id="plEx">Hover an exhibit</div>
        <div class="t" id="plT">Five skills on pedestals</div>
        <div class="d" id="plD">Each object in the vitrine is one thing the museum floor taught me.</div>
      </div>
    </div>
  </article>
</section>

<section class="reel" id="reel-3" style="--accent:var(--robot)">
  <article class="panel">
    <div class="slate"><span>Reel III</span><span>Sc. 3 · Take 7</span><em>Security · OSINT · CTI</em></div>
    <div class="pbody">
      <h2 class="glitch" data-text="The Lab">The Lab</h2>
      <p class="kicker">Build it, break it, then write the report.</p>
      <div class="stats">
        <div><b>Top 2%</b><span>TryHackMe worldwide</span></div>
        <div><b>0xD</b><span>Legend rank</span></div>
        <div><b>8,000+</b><span>Shadowbroker forks</span></div>
        <div><b>116+</b><span>Security tests in OIL</span></div>
      </div>
      <ul class="credits-list">
        <li><span class="who"><a href="https://github.com/AlborzNazari/Shadowbroker" target="_blank" rel="noopener">Shadowbroker</a></span><span class="when">OSINT</span><span class="what">Real-time geospatial OSINT dashboard. I added the Spain and USA CCTV layers, a haversine alert pipeline with pixel-level change detection, and STIX 2.1 export. When the fork passed 8,000, an inherited scheduler made thousands of installs hit one endpoint at the same second. I traced it, wrote it up, and shipped the jitter fix.</span></li>
        <li><span class="who"><a href="https://github.com/AlborzNazari/open-intelligence-lab" target="_blank" rel="noopener">Open Intelligence Lab</a></span><span class="when">v0.8.0</span><span class="what">Graph-based threat intelligence platform. STIX 2.1 and TAXII 2.1, MISP feeds, MITRE ATT&amp;CK, JWT auth, GitLab CI/CD, deployed on Fly.io. The v0.8 sprint closed an SSRF in the MISP and TAXII clients and put auth on 13 open routes.</span></li>
        <li><span class="who"><a href="https://github.com/AlborzNazari/Secure-Apportionment-System" target="_blank" rel="noopener">Secure Apportionment System</a></span><span class="when">Crypto</span><span class="what">Huntington-Hill seat allocation with AES-256-CBC encryption.</span></li>
      </ul>
      <p class="readout" id="nodeOut">&gt; hover a node behind the monitor</p>
      <div class="links">
        <a href="https://tryhackme.com/p/alborznazari4" target="_blank" rel="noopener">TryHackMe</a>
        <a href="https://platform.cyberr.ai/u/alborz" target="_blank" rel="noopener">Cyberr</a>
        <a href="https://github.com/AlborzNazari" target="_blank" rel="noopener">GitHub</a>
        <a href="https://gitlab.com/alborznazari4" target="_blank" rel="noopener">GitLab</a>
      </div>
    </div>
  </article>
  <div class="win" aria-hidden="true"></div>
</section>

<section class="reel right" id="reel-4" style="--accent:var(--flesh)">
  <div class="win" aria-hidden="true"></div>
  <article class="panel">
    <div class="slate"><span>Reel IV</span><span>Sc. 4 · Take 3</span><em>Technical &amp; creative writing</em></div>
    <div class="pbody">
      <h2>The Page</h2>
      <p class="kicker">Technical writer by trade, creative writer by temperament.</p>
      <p>Literature and cult cinema taught me how to hold a reader. Compilers and incident reports taught me what to hold them with. The book beside this panel turns through the write-ups, from interpreter internals to a pigeon heist.</p>
      <ul class="articles">
        <li><small>Jul 2026 · Language security</small><a href="https://medium.com/@alborznazari4/lox-under-the-microscope-design-trade-offs-measurable-faults-and-what-real-languages-do-e01637e5fd7f" target="_blank" rel="noopener">Lox Under the Microscope</a></li>
        <li><small>May 2026 · Incident report</small><a href="https://medium.com/@alborznazari4/thundering-herd-via-inherited-scheduler-how-my-fork-became-someone-elses-threat-feed-584db81a8ae4" target="_blank" rel="noopener">Thundering Herd via Inherited Scheduler</a></li>
        <li><small>May 2026 · Concurrency</small><a href="https://medium.com/@alborznazari4/threading-the-needle-race-conditions-atomic-violations-and-the-concurrency-flaws-that-break-b7bfdc2f7993" target="_blank" rel="noopener">Threading the Needle</a></li>
        <li><small>Mar 2026 · OSINT</small><a href="https://medium.com/@alborznazari4/shadowbroker-how-open-source-intelligence-layers-turn-raw-signals-into-analyst-findings-a54c770b3dac" target="_blank" rel="noopener">Shadowbroker: Raw Signals into Analyst Findings</a></li>
        <li><small>Feb 2026 · Book outlet</small><a href="https://medium.com/@alborznazari4/the-tech-reads-that-changed-how-i-think-in-2026-e7fd6739c62a" target="_blank" rel="noopener">The Tech Reads That Changed How I Think</a></li>
        <li><small>Jan 2026 · Metadata</small><a href="https://medium.com/@alborznazari4/pigeon-thief-story-legality-metadata-lets-play-detective-502390fc586a" target="_blank" rel="noopener">Pigeon Thief Story: Let's Play Detective</a></li>
      </ul>
      <div class="links"><a href="https://medium.com/@alborznazari4" target="_blank" rel="noopener">All writing on Medium</a></div>
    </div>
  </article>
</section>

<section class="reel" id="reel-5" style="--accent:var(--waters)">
  <article class="panel">
    <div class="slate"><span>Reel V</span><span>Sc. 5 · Take 1</span><em>AI safety · Evaluation</em></div>
    <div class="pbody">
      <h2>The Conscience</h2>
      <p class="kicker">It is watching you. You are testing it.</p>
      <p>Red-teaming a model uses the same instinct as red-teaming code: assume the confident answer is wrong and go find out why.</p>
      <div class="feature">
        <span class="who">Mercor · Freelance · 2026</span>
        <span class="role">AI Safety Engineer</span>
        <ul>
          <li>Reviewed model-written code for bugs and security flaws, the same way I review a pull request.</li>
          <li>Judged model answers on safety and accuracy, and wrote the reasoning behind each call so it could train the next model.</li>
          <li>Brought a writer's ear to the job: spotting text that sounds right but says nothing.</li>
        </ul>
      </div>
      <ul class="credits-list">
        <li><span class="who">Alignerr (Labelbox network)</span><span class="when">2026</span><span class="what">Senior Software Engineer, AI Evaluation and Benchmarks. Contractor.</span></li>
        <li><span class="who">Microsoft</span><span class="when">Certified</span><span class="what">Agentic AI certification.</span></li>
        <li><span class="who"><a href="https://leftmountains.gumroad.com/l/Claude_Adversary_Prompts" target="_blank" rel="noopener">Adversary</a></span><span class="when">My product</span><span class="what">Five Claude system prompts for security engineers: vulnerability triage, code review, bug bounty reports, recon and threat intel. Each one makes the model try to disprove a finding before it agrees with it.</span></li>
      </ul>
      <div class="links">
        <a class="solid" href="https://leftmountains.gumroad.com/l/Claude_Adversary_Prompts" target="_blank" rel="noopener">Get Adversary on Gumroad</a>
        <a href="https://www.linkedin.com/in/alborznazari/" target="_blank" rel="noopener">LinkedIn</a>
      </div>
    </div>
  </article>
  <div class="win" aria-hidden="true"></div>
</section>

<section class="reel end" id="credits">
  <span class="eyebrow">End credits</span>
  <h2>Roll credits</h2>
  <dl class="roll">
    <dt>Code</dt><dd><a href="https://github.com/AlborzNazari" target="_blank" rel="noopener">GitHub</a><a href="https://gitlab.com/alborznazari4" target="_blank" rel="noopener">GitLab</a></dd>
    <dt>Hacking</dt><dd><a href="https://tryhackme.com/p/alborznazari4" target="_blank" rel="noopener">TryHackMe</a><a href="https://platform.cyberr.ai/u/alborz" target="_blank" rel="noopener">Cyberr</a></dd>
    <dt>Product</dt><dd><a href="https://leftmountains.gumroad.com/l/Claude_Adversary_Prompts" target="_blank" rel="noopener">Adversary</a></dd>
    <dt>Writing</dt><dd><a href="https://medium.com/@alborznazari4" target="_blank" rel="noopener">Medium</a></dd>
    <dt>3D &amp; film</dt><dd><a href="https://www.artstation.com/alborznazariz" target="_blank" rel="noopener">ArtStation</a><a href="https://vimeo.com/alborznazariz" target="_blank" rel="noopener">Vimeo</a><a href="https://www.youtube.com/@alborznazari" target="_blank" rel="noopener">YouTube</a></dd>
    <dt>Talk to me</dt><dd><a href="https://www.linkedin.com/in/alborznazari/" target="_blank" rel="noopener">LinkedIn</a><a href="https://x.com/Alborznazariz" target="_blank" rel="noopener">X</a><a href="https://bsky.app/profile/alborznazariz.bsky.social" target="_blank" rel="noopener">Bluesky</a><a href="https://www.reddit.com/user/AlborzPara/" target="_blank" rel="noopener">Reddit</a></dd>
  </dl>
  <div class="mailrow"><code id="mail">hello@alborznazari.tech</code><button class="btn" type="button" id="copyMail">Copy email</button></div>
  <p class="soon">Coming soon to a bounty program near you: <a href="https://hackerone.com/alborznazari" target="_blank" rel="noopener">HackerOne</a> · <a href="https://bugcrowd.com/h/alborznazari" target="_blank" rel="noopener">Bugcrowd</a></p>
  <p class="fin">Filmed in Barcelona. Written, directed and hacked by Alborz Nazari.</p>
</section>

</main>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
(function(){
"use strict";
const reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;

/* film grain */
(function(){
  const c=document.createElement('canvas');c.width=c.height=160;const x=c.getContext('2d');const d=x.createImageData(160,160);
  for(let i=0;i<d.data.length;i+=4){const v=Math.random()*255;d.data[i]=d.data[i+1]=d.data[i+2]=v;d.data[i+3]=255;}
  x.putImageData(d,0,0);document.getElementById('grain').style.backgroundImage='url('+c.toDataURL()+')';
})();

/* copy email */
document.getElementById('copyMail').addEventListener('click',function(){
  const b=this,el=document.getElementById('mail'),t=el.textContent;
  const done=()=>{b.textContent='Copied';setTimeout(()=>b.textContent='Copy email',1600);};
  const sel=()=>{const r=document.createRange();r.selectNodeContents(el);const s=getSelection();s.removeAllRanges();s.addRange(r);b.textContent='Selected, press copy';};
  try{navigator.clipboard.writeText(t).then(done,sel);}catch(e){sel();}
});

/* scroll bookkeeping */
const secs=[...document.querySelectorAll('main > section')];
const navs=[...document.querySelectorAll('.reels a')];
const reelNames=['0','I','II','III','IV','V','END'];
let f=0,active=-1;
function progress(){
  const mid=scrollY+innerHeight*0.5;
  for(let i=0;i<secs.length;i++){
    const t=secs[i].offsetTop,h=secs[i].offsetHeight;
    if(mid<t+h||i===secs.length-1)return Math.max(0,Math.min(secs.length-1,i+Math.min(Math.max((mid-t)/h,0),1)-0.5));
  }
  return 0;
}
const tcv=document.getElementById('tcv'),reelNo=document.getElementById('reelNo'),cue=document.getElementById('cue');
const pad=n=>String(n).padStart(2,'0');
function onScroll(){
  f=progress();
  const max=document.documentElement.scrollHeight-innerHeight;
  const run=(max>0?scrollY/max:0)*5880,s=Math.floor(run),fr=Math.floor((run%1)*24);
  tcv.textContent=pad(Math.floor(s/3600))+':'+pad(Math.floor(s/60)%60)+':'+pad(s%60)+':'+pad(fr);
  const a=Math.round(f);
  if(a!==active){
    active=a;reelNo.textContent=reelNames[a];
    navs.forEach((n,i)=>n.classList.toggle('on',i===a));
    if(!reduce){cue.classList.remove('on');void cue.offsetWidth;cue.classList.add('on');}
  }
}
addEventListener('scroll',onScroll,{passive:true});
onScroll();

/* ================= 3D ================= */
if(!window.THREE)return;
const canvas=document.getElementById('gl');
let R;
try{R=new THREE.WebGLRenderer({canvas,antialias:true,powerPreference:'high-performance'});}catch(e){return;}
R.setPixelRatio(Math.min(devicePixelRatio,1.75));
R.setClearColor(0x0e090b,1);
R.outputEncoding=THREE.sRGBEncoding;
const scene=new THREE.Scene();
scene.fog=new THREE.Fog(0x0e090b,9,21);
const cam=new THREE.PerspectiveCamera(40,1,0.1,60);
cam.position.set(0,0,9);
scene.add(new THREE.AmbientLight(0xffffff,0.35));
const key=new THREE.DirectionalLight(0xfff0e6,0.9);key.position.set(3,4,6);scene.add(key);

const GAP=16,groups=[];
function stage(i){const g=new THREE.Group();g.position.y=-i*GAP;scene.add(g);groups[i]=g;return g;}
const side=[0,1,-1,1,-1,1,0];
const tmpV=new THREE.Vector3(),inv=new THREE.Matrix4();

const NOISE=`
vec3 mod289(vec3 x){return x-floor(x*(1./289.))*289.;}
vec4 mod289(vec4 x){return x-floor(x*(1./289.))*289.;}
vec4 permute(vec4 x){return mod289(((x*34.)+1.)*x);}
vec4 taylorInvSqrt(vec4 r){return 1.79284291400159-0.85373472095314*r;}
float snoise(vec3 v){
 const vec2 C=vec2(1./6.,1./3.);const vec4 D=vec4(0.,.5,1.,2.);
 vec3 i=floor(v+dot(v,C.yyy));vec3 x0=v-i+dot(i,C.xxx);
 vec3 g=step(x0.yzx,x0.xyz);vec3 l=1.-g;vec3 i1=min(g.xyz,l.zxy);vec3 i2=max(g.xyz,l.zxy);
 vec3 x1=x0-i1+C.xxx;vec3 x2=x0-i2+C.yyy;vec3 x3=x0-D.yyy;
 i=mod289(i);
 vec4 p=permute(permute(permute(i.z+vec4(0.,i1.z,i2.z,1.))+i.y+vec4(0.,i1.y,i2.y,1.))+i.x+vec4(0.,i1.x,i2.x,1.));
 float n_=.142857142857;vec3 ns=n_*D.wyz-D.xzx;
 vec4 j=p-49.*floor(p*ns.z*ns.z);vec4 x_=floor(j*ns.z);vec4 y_=floor(j-7.*x_);
 vec4 x=x_*ns.x+ns.yyyy;vec4 y=y_*ns.x+ns.yyyy;vec4 h=1.-abs(x)-abs(y);
 vec4 b0=vec4(x.xy,y.xy);vec4 b1=vec4(x.zw,y.zw);
 vec4 s0=floor(b0)*2.+1.;vec4 s1=floor(b1)*2.+1.;vec4 sh=-step(h,vec4(0.));
 vec4 a0=b0.xzyw+s0.xzyw*sh.xxyy;vec4 a1=b1.xzyw+s1.xzyw*sh.zzww;
 vec3 p0=vec3(a0.xy,h.x);vec3 p1=vec3(a0.zw,h.y);vec3 p2=vec3(a1.xy,h.z);vec3 p3=vec3(a1.zw,h.w);
 vec4 norm=taylorInvSqrt(vec4(dot(p0,p0),dot(p1,p1),dot(p2,p2),dot(p3,p3)));
 p0*=norm.x;p1*=norm.y;p2*=norm.z;p3*=norm.w;
 vec4 m=max(.6-vec4(dot(x0,x0),dot(x1,x1),dot(x2,x2),dot(x3,x3)),0.);m=m*m;
 return 42.*dot(m*m,vec4(dot(p0,x0),dot(p1,x1),dot(p2,x2),dot(p3,x3)));
}`;

/* ---------- 0: the new flesh ---------- */
const g0=stage(0);
const RAD=1.9;
const fleshU={uTime:{value:0},uAmp:{value:0.13},uPoke:{value:new THREE.Vector3(0,0,RAD)},uWound:{value:0}};
const flesh=new THREE.Mesh(new THREE.IcosahedronGeometry(RAD,48),new THREE.ShaderMaterial({
  uniforms:fleshU,
  vertexShader:NOISE+`
  uniform float uTime,uAmp,uWound;uniform vec3 uPoke;
  varying vec3 vPos;varying vec3 vNorm;varying vec3 vView;varying float vD;varying float vW;
  float woundAt(vec3 p){return 1.-smoothstep(0.,.95,distance(p,uPoke));}
  float disp(vec3 p){
    vec3 n=normalize(p);
    float beat=pow(max(sin(uTime*2.6),0.),10.)*.035;
    float d=snoise(n*1.05+uTime*.05)*uAmp+snoise(n*2.3-uTime*.035)*uAmp*.3+beat;
    float w=woundAt(p);
    d-=w*w*.62*uWound;
    d+=smoothstep(.55,.2,abs(distance(p,uPoke)-.8))*.07*uWound;
    return d;
  }
  void main(){
    vec3 n=normalize(position);
    float d0=disp(position);
    vec3 p=position+n*d0;
    vec3 t=normalize(cross(n,vec3(0.,1.,.001)));vec3 b=cross(n,t);
    vec3 qa=normalize(position+t*.03)*${RAD.toFixed(2)};vec3 qb=normalize(position+b*.03)*${RAD.toFixed(2)};
    vec3 pa=qa+normalize(qa)*disp(qa);vec3 pb=qb+normalize(qb)*disp(qb);
    vec3 N=normalize(cross(pa-p,pb-p));
    vD=d0;vW=woundAt(position)*uWound;vPos=p;
    vec4 mv=modelViewMatrix*vec4(p,1.);
    vView=-mv.xyz;vNorm=normalMatrix*N;
    gl_Position=projectionMatrix*mv;
  }`,
  fragmentShader:NOISE+`
  uniform float uTime;
  varying vec3 vPos;varying vec3 vNorm;varying vec3 vView;varying float vD;varying float vW;
  void main(){
    vec3 N=normalize(vNorm);vec3 V=normalize(vView);
    vec3 L1=normalize(vec3(.5,.8,.6));vec3 L2=normalize(vec3(-.7,-.2,.4));
    vec3 blood=vec3(.20,.005,.025);vec3 meat=vec3(.55,.08,.10);vec3 skin=vec3(.86,.47,.40);vec3 pink=vec3(1.,.25,.56);
    vec3 base=mix(meat,skin,smoothstep(-.12,.16,vD));
    float veinA=pow(1.-abs(snoise(vPos*1.6+vec3(0.,uTime*.02,0.))),14.);
    float veinB=pow(1.-abs(snoise(vPos*4.2+7.)),18.);
    vec3 veinCol=vec3(.32,.05,.16);
    base=mix(base,veinCol,clamp(veinA*.75+veinB*.45,0.,1.));
    float pores=snoise(vPos*38.)*.5+.5;
    base*=.9+.1*pores;
    vec3 raw=mix(vec3(.75,.02,.06),blood,smoothstep(.2,.85,vW));
    base=mix(base,raw,smoothstep(.05,.35,vW));
    float crevice=smoothstep(.02,-.14,vD);
    base=mix(base,blood,crevice*.7);
    float wrap=(dot(N,L1)+.45)/1.45;
    float diff=max(wrap,0.)*.85+max(dot(N,L2),0.)*.18+.12;
    vec3 sss=vec3(1.,.18,.2)*pow(1.-abs(dot(N,V)),2.)*.45;
    float wet=.55+vW*.9+crevice*.3;
    vec3 H=normalize(L1+V);
    float spec=pow(max(dot(N,H),0.),90.)*1.6*wet+pow(max(dot(N,H),0.),14.)*.12;
    float fr=pow(1.-max(dot(N,V),0.),2.4);
    vec3 c=base*diff+sss*base*1.4+vec3(1.,.93,.9)*spec+pink*fr*.55;
    gl_FragColor=vec4(pow(c,vec3(.95)),1.);
  }`
}));
g0.add(flesh);
const fleshProxy=new THREE.Mesh(new THREE.IcosahedronGeometry(RAD,3),new THREE.MeshBasicMaterial());
fleshProxy.visible=false;flesh.add(fleshProxy);
let woundTarget=0;

/* ---------- 1: the pipeline viewport ---------- */
const g1=stage(1);
const knotGeo=new THREE.TorusKnotGeometry(1.1,0.34,220,32);
const mats={
  shade:new THREE.MeshStandardMaterial({color:0xe98a74,roughness:.32,metalness:.25}),
  wire:new THREE.MeshBasicMaterial({color:0x5fd3cf,wireframe:true}),
  normals:new THREE.MeshNormalMaterial()
};
const knotRig=new THREE.Group();g1.add(knotRig);
const knot=new THREE.Mesh(knotGeo,mats.shade);knotRig.add(knot);
const shell=new THREE.Mesh(new THREE.TorusKnotGeometry(1.1,0.34,110,16),new THREE.MeshBasicMaterial({color:0x5fd3cf,wireframe:true,transparent:true,opacity:0}));
knotRig.add(shell);
const core=new THREE.Mesh(new THREE.TorusKnotGeometry(1.1,0.1,160,12),new THREE.MeshNormalMaterial({transparent:true,opacity:0}));
knotRig.add(core);
const grid=new THREE.GridHelper(8,16,0x5fd3cf,0x3a2830);grid.position.y=-2.2;g1.add(grid);
const props=[];
[[0xff3f8e,new THREE.BoxGeometry(.32,.32,.32)],[0xf1e6d8,new THREE.SphereGeometry(.2,24,16)],[0x5fd3cf,new THREE.ConeGeometry(.2,.4,4)]].forEach((p,i)=>{
  const m=new THREE.Mesh(p[1],new THREE.MeshStandardMaterial({color:p[0],roughness:.4}));m.userData.a=i*2.1;g1.add(m);props.push(m);
});
document.querySelectorAll('[data-mode]').forEach(b=>b.addEventListener('click',()=>{
  knot.material=mats[b.dataset.mode];
  document.querySelectorAll('[data-mode]').forEach(o=>o.setAttribute('aria-pressed',String(o===b)));
}));
let lift=0;

/* ---------- 2: the museum vitrine (unchanged) ---------- */
const g2=stage(2);
const pinkL=new THREE.PointLight(0xff3f8e,2.2,9);pinkL.position.set(0,2.6,2.5);g2.add(pinkL);
const fleshL=new THREE.PointLight(0xe98a74,1.2,9);fleshL.position.set(-3,.5,2);g2.add(fleshL);
const floor=new THREE.Mesh(new THREE.CircleGeometry(3.4,64),new THREE.MeshStandardMaterial({color:0x2a0612,roughness:1}));
floor.rotation.x=-Math.PI/2;floor.position.y=-1.2;g2.add(floor);
const exhibits=[
  ['Exhibit A','Rapport','Strangers walk in curious and a little shy. The first ten seconds decide the next ten minutes.'],
  ['Exhibit B','Tact','The subject is adult. The tone never has to be crude. Humor carries the weight.'],
  ['Exhibit C','Timing','Knowing when to talk, and when to step back and let the collection talk.'],
  ['Exhibit D','Reading the room','Couples, stag parties, art students, grandparents. One museum, many different pitches.'],
  ['Exhibit E','The clean close','Tickets, tours and the gift shop. A clear yes, never a pushed one.']
];
const exGeos=[new THREE.TorusGeometry(.32,.12,20,48),new THREE.SphereGeometry(.34,32,24),new THREE.OctahedronGeometry(.38),new THREE.ConeGeometry(.28,.62,32),new THREE.DodecahedronGeometry(.35)];
const exObjs=[];
const pedMat=new THREE.MeshStandardMaterial({color:0x3a0a18,roughness:.9});
exGeos.forEach((geo,i)=>{
  const a=(i-2)*0.55;const x=Math.sin(a)*2.3,z=-Math.cos(a)*2.3+2.1;
  const ped=new THREE.Mesh(new THREE.CylinderGeometry(.3,.36,1.1,24),pedMat);ped.position.set(x,-.65,z);g2.add(ped);
  const o=new THREE.Mesh(geo,new THREE.MeshStandardMaterial({color:0xff3f8e,metalness:.55,roughness:.22,emissive:0x2a0010}));
  o.position.set(x,.3,z);o.userData={i,base:.3,hover:0};g2.add(o);exObjs.push(o);
});
const plEx=document.getElementById('plEx'),plT=document.getElementById('plT'),plD=document.getElementById('plD');
let lastEx=-1;
function showExhibit(i){if(i===lastEx)return;lastEx=i;const e=exhibits[i];plEx.textContent=e[0];plT.textContent=e[1];plD.textContent=e[2];}

/* ---------- 3: the lab (terminal + threat graph) ---------- */
const g3=stage(3);
const graph=new THREE.Group();graph.position.set(0,.2,-2);graph.scale.setScalar(1.35);g3.add(graph);
const types=[['threat-actor',0xff2a3a],['malware',0xe98a74],['indicator',0xf1e6d8],['attack-pattern',0x8d8288],['campaign',0xff3f8e]];
const nodeGeo=new THREE.SphereGeometry(.075,12,10);
const nodes=[];
function hex(n){let s='';for(let i=0;i<n;i++)s+='0123456789abcdef'[Math.floor(Math.random()*16)];return s;}
for(let i=0;i<48;i++){
  const t=types[i%5];
  const u=Math.random()*2-1,th=Math.random()*Math.PI*2,r=1.4+Math.random()*1.1;
  const m=new THREE.Mesh(nodeGeo,new THREE.MeshBasicMaterial({color:t[1]}));
  m.position.set(Math.sqrt(1-u*u)*Math.cos(th)*r*1.3,u*r,Math.sqrt(1-u*u)*Math.sin(th)*r);
  m.userData={label:t[0]+'--'+hex(8)+'-'+hex(4)+'-4'+hex(3)};graph.add(m);nodes.push(m);
}
const edgePts=[],edges=[];
nodes.forEach((a,i)=>{
  nodes.map((b,j)=>[j,a.position.distanceTo(b.position)]).filter(x=>x[0]!==i).sort((x,y)=>x[1]-y[1]).slice(0,2)
    .forEach(([j])=>{edgePts.push(a.position,nodes[j].position);edges.push([i,j]);});
});
graph.add(new THREE.LineSegments(new THREE.BufferGeometry().setFromPoints(edgePts),new THREE.LineBasicMaterial({color:0xff2a3a,transparent:true,opacity:.3})));
const pulses=[];
for(let k=0;k<14;k++){const m=new THREE.Mesh(new THREE.SphereGeometry(.035,8,6),new THREE.MeshBasicMaterial({color:0xffffff}));m.userData={e:edges[Math.floor(Math.random()*edges.length)],t:Math.random()};graph.add(m);pulses.push(m);}
const nodeOut=document.getElementById('nodeOut');let hovNode=null;

// CRT monitor with a live terminal
const monitor=new THREE.Group();monitor.rotation.y=-.28;monitor.position.set(0,.1,.4);g3.add(monitor);
const bodyMat=new THREE.MeshStandardMaterial({color:0x171214,roughness:.55,metalness:.2});
const body=new THREE.Mesh(new THREE.BoxGeometry(2.6,2.05,1.3),bodyMat);monitor.add(body);
const back=new THREE.Mesh(new THREE.BoxGeometry(1.8,1.4,.8),bodyMat);back.position.z=-.95;monitor.add(back);
const neck=new THREE.Mesh(new THREE.BoxGeometry(.35,.5,.35),bodyMat);neck.position.y=-1.25;monitor.add(neck);
const foot=new THREE.Mesh(new THREE.BoxGeometry(1.3,.08,.9),bodyMat);foot.position.y=-1.52;monitor.add(foot);
const led=new THREE.Mesh(new THREE.SphereGeometry(.03,8,6),new THREE.MeshBasicMaterial({color:0xff2a3a}));led.position.set(1.1,-.9,.66);monitor.add(led);
const TW=640,TH=480,tcan=document.createElement('canvas');tcan.width=TW;tcan.height=TH;const tx=tcan.getContext('2d');
const ttex=new THREE.CanvasTexture(tcan);ttex.encoding=THREE.sRGBEncoding;
const screen=new THREE.Mesh(new THREE.PlaneGeometry(2.24,1.68),new THREE.MeshBasicMaterial({map:ttex,toneMapped:false}));screen.position.z=.655;monitor.add(screen);
const redL=new THREE.PointLight(0xff2a3a,1.6,7);redL.position.set(0,.2,2);g3.add(redL);
const script=[
  ['c','whoami'],['o','red teamer. pipeline engineer. salesman.'],
  ['c','nmap -sV --top-ports 100 10.10.13.37'],
  ['o','PORT     STATE SERVICE VERSION'],['o','22/tcp   open  ssh     OpenSSH 8.9p1'],['o','80/tcp   open  http    nginx 1.24.0'],['o','8000/tcp open  http    uvicorn'],
  ['c','gobuster dir -u http://10.10.13.37 -w common.txt -q'],['o','/admin        (Status: 302)'],['o','/backup.zip   (Status: 200)'],
  ['c','curl -s -o /dev/null -w "%{http_code}" localhost:8000/taxii2/'],['r','401  <- auth holds'],
  ['c','pytest -q tests/security'],['o','........................................'],['g','116 passed in 4.21s'],
  ['c','echo "control is a config file"'],['r','control is a config file']
];
let term={line:0,ch:0,shown:[],acc:0,pause:0,glitch:0};
function drawTerm(t){
  tx.fillStyle='#070405';tx.fillRect(0,0,TW,TH);
  const grd=tx.createRadialGradient(TW/2,TH/2,40,TW/2,TH/2,TW*.7);grd.addColorStop(0,'rgba(255,42,58,.07)');grd.addColorStop(1,'rgba(0,0,0,.55)');
  tx.fillStyle=grd;tx.fillRect(0,0,TW,TH);
  tx.font='500 21px "IBM Plex Mono", monospace';tx.textBaseline='top';
  const lh=28,maxL=16,start=Math.max(0,term.shown.length-maxL);
  let y=18;
  for(let i=start;i<term.shown.length;i++){
    const [k,s]=term.shown[i];let xx=18;
    if(k==='c'){tx.fillStyle='#ff2a3a';tx.fillText('alborz@lab:~$ ',xx,y);xx+=tx.measureText('alborz@lab:~$ ').width;tx.fillStyle='#f1e6d8';}
    else tx.fillStyle=k==='r'?'#ff2a3a':k==='g'?'#5fd3cf':'#a59a95';
    tx.fillText(s,xx,y);
    if(i===term.shown.length-1&&k==='c'&&Math.floor(t*2.2)%2===0){tx.fillStyle='#f1e6d8';tx.fillRect(xx+tx.measureText(s).width+2,y+2,10,18);}
    y+=lh;
  }
  for(let yy=0;yy<TH;yy+=3){tx.fillStyle='rgba(0,0,0,.22)';tx.fillRect(0,yy,TW,1);}
  if(term.glitch>0){
    for(let k=0;k<7;k++){const gy=Math.random()*TH,gh=8+Math.random()*30,dx=(Math.random()-.5)*60;tx.drawImage(tcan,0,gy,TW,gh,dx,gy,TW,gh);}
    tx.fillStyle='rgba(255,42,58,.16)';tx.fillRect(0,0,TW,TH);
  }
  ttex.needsUpdate=true;
}
function stepTerm(dt){
  if(term.pause>0){term.pause-=dt;if(term.pause<=0&&term.line>=script.length){term={line:0,ch:0,shown:[],acc:0,pause:0,glitch:.3};}return;}
  if(term.line>=script.length){term.pause=3.5;return;}
  const [k,s]=script[term.line];
  if(k==='c'){
    if(term.ch===0)term.shown.push(['c','']);
    term.acc+=dt*26;
    while(term.acc>=1&&term.ch<s.length){term.ch++;term.acc--;}
    term.shown[term.shown.length-1][1]=s.slice(0,term.ch);
    if(term.ch>=s.length){term.line++;term.ch=0;term.pause=.35;}
  }else{term.shown.push([k,s]);term.line++;term.pause=.12;}
}
drawTerm(0);

/* ---------- 4: the open book ---------- */
const g4=stage(4);
const book=new THREE.Group();book.rotation.set(-.42,.12,0);g4.add(book);
const PW=1.45,PH=1.95;
const pagesData=[
  ['I','Lox Under the Microscope','Jul 2026 · Language security','Crafting Interpreters’ Lox, taken apart three ways: its design choices, its measurable faults under SpotBugs and cppcheck, and what AFL++ shook loose from jlox and clox.'],
  ['II','Thundering Herd via Inherited Scheduler','May 2026 · Incident report','An inherited scheduler in a forked OSINT repo lined thousands of machines up on one endpoint at the same second every day. How it looked like an attack, and the five-line fix.'],
  ['III','Threading the Needle','May 2026 · Concurrency','Race conditions from first principles: TOCTOU, atomicity violations, the GIL and mutexes, shown on a vault heist simulator that fails on purpose.'],
  ['IV','Shadowbroker','Mar 2026 · OSINT','GPS jamming detection, CCTV ground truth and STIX 2.1 export in one open-source dashboard, and how raw signals become findings an analyst can act on.'],
  ['V','The Tech Reads That Changed How I Think','Feb 2026 · Book outlet','The books that rearranged my thinking this year, from security engineering to building a renderer by hand, and what I took from each.'],
  ['VI','Pigeon Thief Story','Jan 2026 · Metadata','A stolen pigeon, a photograph and the law. A playful detective exercise in how much an image quietly gives away.']
];
const pageCanvases=[],mirrorCanvases=[],pageTex=[],pageTexBack=[];
function mirror(i){const s=pageCanvases[i],m=mirrorCanvases[i],x=m.getContext('2d');x.setTransform(-1,0,0,1,m.width,0);x.drawImage(s,0,0);x.setTransform(1,0,0,1,0,0);}
function drawPage(i){
  const c=pageCanvases[i],x=c.getContext('2d'),W=c.width,H=c.height,left=i%2===0,d=pagesData[i];
  const g=x.createLinearGradient(0,0,W,0);
  if(left){g.addColorStop(0,'#eadcc2');g.addColorStop(.85,'#f3e7d1');g.addColorStop(1,'#cdb99a');}
  else{g.addColorStop(0,'#cdb99a');g.addColorStop(.15,'#f3e7d1');g.addColorStop(1,'#eadcc2');}
  x.fillStyle=g;x.fillRect(0,0,W,H);
  for(let k=0;k<1400;k++){x.fillStyle='rgba(120,90,60,'+(Math.random()*.05)+')';x.fillRect(Math.random()*W,Math.random()*H,1.5,1.5);}
  const m=62;
  x.fillStyle='#8b6f5c';x.font='500 13px "IBM Plex Mono", monospace';
  const rh=left?'THE COLLECTED WRITE-UPS':'ALBORZ NAZARI';
  x.textAlign=left?'left':'right';x.fillText(rh.split('').join(' '),left?m:W-m,50);x.textAlign='left';
  x.strokeStyle='#b89a80';x.lineWidth=1;x.beginPath();x.moveTo(m,66);x.lineTo(W-m,66);x.stroke();
  x.fillStyle='#c2365a';x.font='italic 600 30px Spectral, Georgia, serif';x.fillText('No. '+d[0],m,118);
  x.fillStyle='#2a1a1c';x.font='italic 600 44px Spectral, Georgia, serif';
  let y=178,line='';
  d[1].split(' ').forEach(w=>{const t=line?line+' '+w:w;if(x.measureText(t).width>W-2*m){x.fillText(line,m,y);line=w;y+=50;}else line=t;});x.fillText(line,m,y);
  y+=34;x.fillStyle='#8b6f5c';x.font='13px "IBM Plex Mono", monospace';x.fillText(d[2].toUpperCase(),m,y);
  y+=36;x.fillStyle='#c2365a';x.font='22px Georgia, serif';x.textAlign='center';x.fillText('❦',W/2,y);x.textAlign='left';
  y+=46;
  const cap=d[3][0],rest=d[3].slice(1);
  x.fillStyle='#8a1030';x.font='600 92px Spectral, Georgia, serif';x.fillText(cap,m-4,y+62);
  const capW=x.measureText(cap).width+10;
  x.fillStyle='#2e2224';x.font='23px Spectral, Georgia, serif';
  const words=rest.split(' ');let ln='',row=0;const lh=34;
  words.forEach(w=>{
    const ind=row<3?capW:0,maxW=W-2*m-ind,t=ln?ln+' '+w:w;
    if(x.measureText(t).width>maxW){x.fillText(ln,m+ind,y+row*lh);ln=w;row++;}else ln=t;
  });
  x.fillText(ln,m+(row<3?capW:0),y+row*lh);
  x.fillStyle='#8b6f5c';x.font='italic 20px Spectral, Georgia, serif';x.textAlign='center';x.fillText(String(i*2+11),W/2,H-44);x.textAlign='left';
}
pagesData.forEach((d,i)=>{
  const c=document.createElement('canvas');c.width=600;c.height=806;pageCanvases.push(c);drawPage(i);
  const t=new THREE.CanvasTexture(c);t.encoding=THREE.sRGBEncoding;t.anisotropy=R.capabilities.getMaxAnisotropy();pageTex.push(t);
  const mc=document.createElement('canvas');mc.width=600;mc.height=806;mirrorCanvases.push(mc);mirror(i);
  const tb=new THREE.CanvasTexture(mc);tb.encoding=THREE.sRGBEncoding;tb.anisotropy=t.anisotropy;pageTexBack.push(tb);
});
if(document.fonts&&document.fonts.ready)document.fonts.ready.then(()=>{pageCanvases.forEach((c,i)=>{drawPage(i);mirror(i);});pageTex.forEach(t=>t.needsUpdate=true);pageTexBack.forEach(t=>t.needsUpdate=true);drawTerm(0);});
const leather=new THREE.MeshStandardMaterial({color:0x4a0c1c,roughness:.6,metalness:.1});
const coverL=new THREE.Mesh(new THREE.BoxGeometry(PW+.1,PH+.12,.05),leather);coverL.position.set(-PW/2-.03,0,-.09);book.add(coverL);
const coverR=coverL.clone();coverR.position.x=PW/2+.03;book.add(coverR);
const block=new THREE.MeshStandardMaterial({color:0xe6d6b8,roughness:.9});
const blkL=new THREE.Mesh(new THREE.BoxGeometry(PW,PH,.07),block);blkL.position.set(-PW/2,0,-.04);book.add(blkL);
const blkR=blkL.clone();blkR.position.x=PW/2;book.add(blkR);
const gold=new THREE.Mesh(new THREE.BoxGeometry(.04,PH+.14,.04),new THREE.MeshStandardMaterial({color:0xd9a441,metalness:.9,roughness:.3}));gold.position.z=-.08;book.add(gold);
const ribbon=new THREE.Mesh(new THREE.PlaneGeometry(.06,.9),new THREE.MeshBasicMaterial({color:0xff3f8e,side:THREE.DoubleSide}));ribbon.position.set(.25,-PH/2-.3,.01);book.add(ribbon);
const staticL=new THREE.Mesh(new THREE.PlaneGeometry(PW,PH),new THREE.MeshBasicMaterial({map:pageTex[0]}));staticL.position.set(-PW/2,0,0);book.add(staticL);
const staticR=new THREE.Mesh(new THREE.PlaneGeometry(PW,PH),new THREE.MeshBasicMaterial({map:pageTex[1]}));staticR.position.set(PW/2,0,0);book.add(staticR);
const SEG=28;
const flipGeo=new THREE.PlaneGeometry(PW,PH,SEG,1);
const flipFront=new THREE.Mesh(flipGeo,new THREE.MeshBasicMaterial({map:pageTex[1],side:THREE.FrontSide}));
const flipBack=new THREE.Mesh(flipGeo,new THREE.MeshBasicMaterial({map:pageTexBack[2],side:THREE.BackSide}));
book.add(flipFront);book.add(flipBack);
let spread=0,flipT=-2.2;
function layFlip(theta){
  const pos=flipGeo.attributes.position,dx=PW/SEG,bend=Math.sin(theta)*.55;
  let cx=0,cz=0;
  for(let c=0;c<=SEG;c++){
    if(c>0){const u=(c-.5)/SEG,a=theta-bend*u;cx+=Math.cos(a)*dx;cz+=Math.sin(a)*dx;}
    for(let r=0;r<2;r++){const idx=r*(SEG+1)+c;pos.setX(idx,cx);pos.setZ(idx,cz+.006);}
  }
  pos.needsUpdate=true;
}
function setSpread(k){
  const n=pagesData.length;
  staticL.material.map=pageTex[k%n];
  staticR.material.map=pageTex[(k+3)%n];
  flipFront.material.map=pageTex[(k+1)%n];
  flipBack.material.map=pageTexBack[(k+2)%n];
  [staticL,staticR,flipFront,flipBack].forEach(m=>m.material.needsUpdate=true);
}
setSpread(0);layFlip(0);

/* ---------- 5: the pink stage (built from Alborz's set design) ---------- */
const g5=stage(5);
const stageG=new THREE.Group();g5.add(stageG);
// sky: pink to teal, melting into the dark
const sky=new THREE.Mesh(new THREE.PlaneGeometry(14,9),new THREE.ShaderMaterial({
  transparent:true,depthWrite:false,
  vertexShader:'varying vec2 vUv;void main(){vUv=uv;gl_Position=projectionMatrix*modelViewMatrix*vec4(position,1.);}',
  fragmentShader:`varying vec2 vUv;void main(){
    vec3 top=vec3(.80,.46,.62),bot=vec3(.55,.83,.84);
    vec3 c=mix(bot,top,smoothstep(.15,.85,vUv.y));
    vec2 q=(vUv-.5)*vec2(1.5,1.);float a=1.-smoothstep(.2,.62,length(q));
    gl_FragColor=vec4(c,a*.8);}`
}));
sky.position.set(0,.6,-3.6);stageG.add(sky);
// ---- original set architecture: pink shells, slatted wall, tiles, neon crown ----
function ctxTex(w,h,draw){const c=document.createElement('canvas');c.width=w;c.height=h;draw(c.getContext('2d'),w,h);const t=new THREE.CanvasTexture(c);t.encoding=THREE.sRGBEncoding;t.anisotropy=4;return t;}
function flower(x,cx,cy,r,fill,vein){
  x.save();x.translate(cx,cy);
  for(let k=0;k<5;k++){x.save();x.rotate(k/5*Math.PI*2);x.fillStyle=fill;x.beginPath();x.moveTo(0,0);x.bezierCurveTo(-r*.55,-r*.35,-r*.4,-r*.95,0,-r);x.bezierCurveTo(r*.4,-r*.95,r*.55,-r*.35,0,0);x.fill();
    x.strokeStyle=vein;x.lineWidth=r*.05;x.beginPath();x.moveTo(0,-r*.15);x.lineTo(0,-r*.7);x.stroke();x.restore();}
  x.fillStyle=vein;x.beginPath();x.arc(0,0,r*.1,0,Math.PI*2);x.fill();x.restore();
}
// back wall
const wallTex=ctxTex(512,320,(x,w,h)=>{
  const g=x.createLinearGradient(0,0,0,h);g.addColorStop(0,'#f5b3d0');g.addColorStop(1,'#e98cb8');x.fillStyle=g;x.fillRect(0,0,w,h);
  x.fillStyle='#e0679f';for(let k=0;k<9;k++){const ww=90+Math.random()*260,xx=Math.random()*(w-ww);x.fillRect(xx,14+k*13,ww,6);}
  x.strokeStyle='#7fd6d6';x.lineWidth=5;x.beginPath();x.moveTo(0,150);x.lineTo(w,150);x.moveTo(0,238);x.lineTo(w,238);x.moveTo(150,150);x.lineTo(150,h);x.moveTo(362,150);x.lineTo(362,h);x.stroke();
  const cols=['#ff4d97','#a6e0e0','#f9cde0','#c7a4dd'];
  for(let r=0;r<5;r++)for(let c=0;c<2;c++){x.fillStyle=cols[(r+c*2)%4];x.fillRect(214+c*48,160+r*30,30,22);x.fillStyle=cols[(r+c+1)%4];x.fillRect(214+c*48+8,166+r*30,14,10);}
  x.fillStyle='#ff4d97';x.beginPath();x.moveTo(256,138);x.bezierCurveTo(226,112,226,86,248,88);x.bezierCurveTo(254,88,256,94,256,98);x.bezierCurveTo(256,94,258,88,264,88);x.bezierCurveTo(286,86,286,112,256,138);x.fill();
});
const wall=new THREE.Mesh(new THREE.BoxGeometry(3.6,2.25,.1),[0,0,0,0,new THREE.MeshStandardMaterial({map:wallTex,roughness:.7}),0].map(m=>m||new THREE.MeshStandardMaterial({color:0xd9709f,roughness:.8})));
wall.position.set(0,.02,-2.2);stageG.add(wall);
const ledge=new THREE.Mesh(new THREE.BoxGeometry(3.9,.09,.5),new THREE.MeshStandardMaterial({color:0xf4c3d9,roughness:.5}));ledge.position.set(0,1.2,-2.05);stageG.add(ledge);
const ledgeTrim=new THREE.Mesh(new THREE.BoxGeometry(3.9,.025,.02),new THREE.MeshBasicMaterial({color:0x7fe0dc}));ledgeTrim.position.set(0,1.16,-1.79);stageG.add(ledgeTrim);
// the crown: a curved banner with flowers and neon lines
const crownTex=ctxTex(1024,300,(x,w,h)=>{
  const g=x.createLinearGradient(0,0,0,h);g.addColorStop(0,'#f8b9d4');g.addColorStop(1,'#ea78ab');x.fillStyle=g;x.fillRect(0,0,w,h);
  x.strokeStyle='rgba(170,30,90,.45)';x.lineWidth=4;[200,420,604,824].forEach(xx=>{x.beginPath();x.moveTo(xx,0);x.lineTo(xx+(xx<512?-30:30),h);x.stroke();});
  flower(x,150,160,92,'#fbd5e6','#c9457f');flower(x,874,160,92,'#fbd5e6','#c9457f');
  x.shadowColor='#ff2d8a';x.shadowBlur=18;x.strokeStyle='#ff5fa8';x.lineWidth=7;x.lineCap='round';
  for(let k=0;k<3;k++){x.beginPath();for(let xx=300;xx<=724;xx+=6){const u=(xx-512)/212,y=120+k*38+Math.sin(u*5+k)*18*(1-Math.abs(u))+Math.abs(u)*20;xx===300?x.moveTo(xx,y):x.lineTo(xx,y);}x.stroke();}
  x.lineWidth=9;x.beginPath();x.moveTo(512,40);x.lineTo(512,190);x.stroke();x.beginPath();x.ellipse(512,210,14,24,0,0,Math.PI*2);x.stroke();
  x.shadowBlur=0;x.fillStyle='rgba(60,10,30,.25)';x.fillRect(0,h-16,w,16);
});
const crown=new THREE.Mesh(new THREE.CylinderGeometry(3.2,3.2,1.1,48,1,true,-.52,1.04),new THREE.MeshStandardMaterial({map:crownTex,side:THREE.DoubleSide,roughness:.55,emissive:0x3a0018}));
crown.position.set(0,1.85,-5.15);stageG.add(crown);
const crownFrame=new THREE.Mesh(new THREE.CylinderGeometry(3.25,3.25,.07,48,1,true,-.54,1.08),new THREE.MeshStandardMaterial({color:0x3a2a33,side:THREE.DoubleSide}));
crownFrame.position.set(0,1.28,-5.15);stageG.add(crownFrame);
// curled wing shells, left and right
const wingTex=ctxTex(512,440,(x,w,h)=>{
  x.fillStyle='#f19bc3';x.fillRect(0,0,w,h);
  x.fillStyle='#d8347f';
  x.beginPath();x.moveTo(40,60);x.lineTo(210,40);x.lineTo(230,400);x.lineTo(70,410);x.closePath();x.fill();
  x.beginPath();x.moveTo(260,50);x.lineTo(470,70);x.lineTo(450,400);x.lineTo(280,390);x.closePath();x.fill();
  x.fillStyle='#f6b8d4';
  x.beginPath();x.moveTo(70,90);x.lineTo(190,76);x.lineTo(205,370);x.lineTo(95,378);x.closePath();x.fill();
  x.beginPath();x.moveTo(290,86);x.lineTo(440,100);x.lineTo(424,370);x.lineTo(305,360);x.closePath();x.fill();
  x.fillStyle='#8fe6e2';x.fillRect(125,130,16,150);x.fillRect(355,140,16,140);
  x.strokeStyle='#7a1a47';x.lineWidth=6;x.strokeRect(3,3,w-6,h-6);
});
[-1,1].forEach(sd=>{
  const geo=new THREE.PlaneGeometry(1.9,1.55,20,12);const p=geo.attributes.position;
  for(let i=0;i<p.count;i++){const x=p.getX(i),y=p.getY(i);p.setZ(i,-x*x*.28+Math.max(0,y)*Math.max(0,y)*.55);}
  geo.computeVertexNormals();
  const m=new THREE.Mesh(geo,new THREE.MeshStandardMaterial({map:wingTex,side:THREE.DoubleSide,roughness:.6}));
  m.position.set(sd*2.45,1.55,-1.75);m.rotation.set(-.12,-sd*.62,sd*.14);stageG.add(m);
  const lip=new THREE.Mesh(new THREE.BoxGeometry(1.9,.05,.18),new THREE.MeshStandardMaterial({color:0x3a2a33}));lip.position.set(0,-.8,0);m.add(lip);
});
// chandelier
const chand=new THREE.Group();chand.position.set(-.35,.95,-1.6);stageG.add(chand);
const tealMetal=new THREE.MeshStandardMaterial({color:0x7fd6d6,metalness:.6,roughness:.3});
chand.add(new THREE.Mesh(new THREE.TorusGeometry(.2,.012,8,32),tealMetal));chand.children[0].rotation.x=Math.PI/2;
const chain=new THREE.Mesh(new THREE.CylinderGeometry(.006,.006,.3,6),tealMetal);chain.position.y=.15;chand.add(chain);
for(let k=0;k<6;k++){const a=k/6*Math.PI*2;const cnd=new THREE.Mesh(new THREE.ConeGeometry(.018,.07,6),new THREE.MeshBasicMaterial({color:0xfff0f6}));cnd.position.set(Math.cos(a)*.2,.04,Math.sin(a)*.2);chand.add(cnd);}
// hanging teal ribbon ladder, like a mobile
const ladder=new THREE.Group();ladder.position.set(.75,.8,-1.7);stageG.add(ladder);
for(let k=0;k<7;k++){const rung=new THREE.Mesh(new THREE.BoxGeometry(.18,.018,.02),new THREE.MeshStandardMaterial({color:0xd3eef0}));rung.position.set(Math.sin(k*.6)*.1,-k*.07,0);rung.rotation.z=Math.sin(k*.7)*.3;ladder.add(rung);}
// a lounge chair and vanity on the stage floor
const floorPink=new THREE.Mesh(new THREE.BoxGeometry(5.2,.08,1.7),new THREE.MeshStandardMaterial({color:0xefb2cf,roughness:.8}));floorPink.position.set(0,-1.2,-1.35);stageG.add(floorPink);
const chairMat=new THREE.MeshStandardMaterial({color:0xf6d3e3,roughness:.5});
const seat=new THREE.Mesh(new THREE.BoxGeometry(.55,.08,.26),chairMat);seat.position.set(.9,-.98,-1.45);seat.rotation.z=-.08;stageG.add(seat);
const backrest=new THREE.Mesh(new THREE.BoxGeometry(.08,.3,.26),chairMat);backrest.position.set(.63,-.84,-1.45);backrest.rotation.z=.35;stageG.add(backrest);
const vanity=new THREE.Mesh(new THREE.BoxGeometry(.4,.28,.2),new THREE.MeshStandardMaterial({color:0xf8c9dc}));vanity.position.set(-.85,-1.02,-1.55);stageG.add(vanity);
const mirrorHeart=new THREE.Mesh(new THREE.CircleGeometry(.11,24),new THREE.MeshBasicMaterial({color:0xff4d97}));mirrorHeart.position.set(-.85,-.72,-1.6);stageG.add(mirrorHeart);
// gothic arches, left and right
function archShape(w,h){
  const s=new THREE.Shape();s.moveTo(-w/2-.12,0);s.lineTo(-w/2-.12,h+.7);s.lineTo(w/2+.12,h+.7);s.lineTo(w/2+.12,0);s.lineTo(-w/2-.12,0);
  const hole=new THREE.Path();hole.moveTo(-w/2,0);hole.lineTo(-w/2,h);hole.quadraticCurveTo(-w/2,h+.32,0,h+.5);hole.quadraticCurveTo(w/2,h+.32,w/2,h);hole.lineTo(w/2,0);hole.lineTo(-w/2,0);
  s.holes.push(hole);return s;
}
const archGeo=new THREE.ExtrudeGeometry(archShape(.46,.9),{depth:.12,bevelEnabled:false});
const archMat=new THREE.MeshStandardMaterial({color:0xf0a3c4,roughness:.55});
const archGlow=new THREE.MeshBasicMaterial({color:0xff3f8e});
[-1,1].forEach(sd=>{for(let k=0;k<3;k++){
  const a=new THREE.Mesh(archGeo,archMat);a.position.set(sd*(1.55+k*.72),-1.2,-1.1+k*.35);a.rotation.y=-sd*.45;stageG.add(a);
  const glow=new THREE.Mesh(new THREE.PlaneGeometry(.46,.9),archGlow);glow.position.set(0,.45,.02);glow.material.transparent=true;glow.material.opacity=.35;a.add(glow);
}});
// kidney pool
function kidney(sx,sz){
  const s=new THREE.Shape();
  s.moveTo(-1.6*sx,0);
  s.bezierCurveTo(-1.6*sx,.75*sz,-.4*sx,.8*sz,0,.45*sz);
  s.bezierCurveTo(.45*sx,.8*sz,1.7*sx,.8*sz,1.7*sx,0);
  s.bezierCurveTo(1.7*sx,-.8*sz,-1.6*sx,-.85*sz,-1.6*sx,0);
  return s;
}
const rimShape=kidney(1.12,1.18);rimShape.holes.push(kidney(1,1));
const rim=new THREE.Mesh(new THREE.ExtrudeGeometry(rimShape,{depth:.14,bevelEnabled:false}),new THREE.MeshStandardMaterial({color:0x3fc6c8,roughness:.35}));
rim.rotation.x=-Math.PI/2;rim.position.set(0,-1.28,.35);stageG.add(rim);
const water=new THREE.Mesh(new THREE.ShapeGeometry(kidney(1,1),24),new THREE.ShaderMaterial({
  uniforms:{uTime:{value:0}},
  vertexShader:'varying vec2 vP;void main(){vP=position.xy;gl_Position=projectionMatrix*modelViewMatrix*vec4(position,1.);}',
  fragmentShader:NOISE+`uniform float uTime;varying vec2 vP;void main(){
    float n=snoise(vec3(vP*2.2,uTime*.25))*.5+.5;float n2=snoise(vec3(vP*6.,uTime*.4));
    vec3 c=mix(vec3(.45,.82,.84),vec3(.93,.55,.74),smoothstep(.35,.8,n));
    c+=smoothstep(.55,.9,n2)*.25;
    gl_FragColor=vec4(c,1.);}`
}));
water.rotation.x=-Math.PI/2;water.position.set(0,-1.18,.35);stageG.add(water);
// teal grass
const GR=520,grass=new THREE.InstancedMesh(new THREE.ConeGeometry(.018,.26,3),new THREE.MeshStandardMaterial({roughness:.8}),GR);
const grassBase=[],gd=new THREE.Object3D(),gcol=new THREE.Color();
for(let i=0;i<GR;i++){
  const x=(Math.random()-.5)*5.4,z=1.25+Math.random()*.9;grassBase.push([x,z,Math.random()*6,.7+Math.random()*.6]);
  gcol.setHSL(.49+Math.random()*.03,.45,.45+Math.random()*.2);if(Math.random()<.18)gcol.set(0xf0a3c4);grass.setColorAt(i,gcol);
}
stageG.add(grass);
// the eye, floating over the water
const eye=new THREE.Group();eye.position.set(0,.1,.45);eye.scale.setScalar(.4);stageG.add(eye);
const cells=[];
for(let r=.72;r<2.35;r+=.115){const n=Math.floor(Math.PI*2*r/.13);for(let k=0;k<n;k++){const a=k/n*Math.PI*2+r*3;cells.push([Math.cos(a)*r,Math.sin(a)*r,r]);}}
const iris=new THREE.InstancedMesh(new THREE.BoxGeometry(.075,.075,.075),new THREE.MeshStandardMaterial({roughness:.35,metalness:.25}),cells.length);
const dm=new THREE.Object3D(),col=new THREE.Color(),cA=new THREE.Color(0xff3f8e),cB=new THREE.Color(0xf0a3c4),cC=new THREE.Color(0x3fc6c8);
cells.forEach((c,i)=>{const t=(c[2]-.72)/1.63;col.copy(t<.55?cA:cB).lerp(t<.55?cB:cC,t<.55?t/.55:(t-.55)/.45);iris.setColorAt(i,col);});
eye.add(iris);
const pupil=new THREE.Mesh(new THREE.SphereGeometry(.6,40,30),new THREE.MeshStandardMaterial({color:0x0a0508,roughness:.1,metalness:.8}));pupil.scale.z=.35;eye.add(pupil);
const ringM=new THREE.Mesh(new THREE.RingGeometry(.62,.67,64),new THREE.MeshBasicMaterial({color:0xf1e6d8,side:THREE.DoubleSide}));eye.add(ringM);
const scanRing=new THREE.Mesh(new THREE.RingGeometry(1,1.03,96),new THREE.MeshBasicMaterial({color:0xff3f8e,transparent:true,opacity:.6,side:THREE.DoubleSide}));eye.add(scanRing);
// flower petals drifting, like the banners in the set
function flowerTex(){const c=document.createElement('canvas');c.width=c.height=128;const x=c.getContext('2d');x.translate(64,64);
  for(let k=0;k<5;k++){x.save();x.rotate(k/5*Math.PI*2);x.fillStyle='#f6bfd6';x.beginPath();x.ellipse(0,-30,17,30,0,0,Math.PI*2);x.fill();x.strokeStyle='#d9427e';x.lineWidth=2;x.beginPath();x.moveTo(0,-8);x.lineTo(0,-44);x.stroke();x.restore();}
  x.fillStyle='#d9427e';x.beginPath();x.arc(0,0,7,0,Math.PI*2);x.fill();const t=new THREE.CanvasTexture(c);t.encoding=THREE.sRGBEncoding;return t;}
const fMat=new THREE.MeshBasicMaterial({map:flowerTex(),transparent:true,side:THREE.DoubleSide,depthWrite:false});
const flowers=[];
for(let i=0;i<9;i++){const m=new THREE.Mesh(new THREE.PlaneGeometry(.38,.38),fMat);m.userData={x:(Math.random()-.5)*5,y:Math.random()*3.4-1,z:Math.random()*1.4-.4,s:.2+Math.random()*.35,ph:Math.random()*6};flowers.push(m);stageG.add(m);}
const pinkTop=new THREE.PointLight(0xff3f8e,1.5,9);pinkTop.position.set(0,2.4,2);g5.add(pinkTop);
const tealLow=new THREE.PointLight(0x3fc6c8,1.4,7);tealLow.position.set(0,-1,2);g5.add(tealLow);

/* ---------- 6: ink landscape (shan shui) ---------- */
const g6=stage(6);
const inkLayers=[];
[
  {seed:1.3,base:.62,amp:.2,col:[.23,.16,.2],rim:[.55,.40,.47],alpha:.5,z:-5,y:1.1,sp:.25},
  {seed:4.1,base:.52,amp:.25,col:[.15,.10,.13],rim:[.79,.54,.63],alpha:.72,z:-3.6,y:.1,sp:.45},
  {seed:7.7,base:.40,amp:.24,col:[.08,.05,.07],rim:[1.,.5,.68],alpha:.92,z:-2.2,y:-.9,sp:.7}
].forEach(L=>{
  const m=new THREE.Mesh(new THREE.PlaneGeometry(22,7),new THREE.ShaderMaterial({
    transparent:true,depthWrite:false,
    uniforms:{uTime:{value:0},uSeed:{value:L.seed},uBase:{value:L.base},uAmp:{value:L.amp},uCol:{value:new THREE.Vector3(...L.col)},uRim:{value:new THREE.Vector3(...L.rim)},uAlpha:{value:L.alpha},uSp:{value:L.sp}},
    vertexShader:'varying vec2 vUv;void main(){vUv=uv;gl_Position=projectionMatrix*modelViewMatrix*vec4(position,1.);}',
    fragmentShader:NOISE+`uniform float uTime,uSeed,uBase,uAmp,uAlpha,uSp;uniform vec3 uCol,uRim;varying vec2 vUv;
    float fbm(float x){float s=0.,a=.5,fq=1.;for(int i=0;i<5;i++){s+=a*snoise(vec3(x*fq,uSeed*fq,0.));fq*=2.1;a*=.5;}return s;}
    void main(){
      float x=vUv.x*3.2+uTime*.012*uSp;
      float h=uBase+uAmp*fbm(x)+uAmp*.5*max(0.,snoise(vec3(x*.6,uSeed+3.,0.)));
      float y=vUv.y;
      float inside=smoothstep(h+.003,h-.003,y);
      float mist=smoothstep(h-.5,h-.08,y);
      float wash=.72+.28*(snoise(vec3(vUv*vec2(26.,5.),uSeed))*.5+.5);
      float edge=smoothstep(h-.05,h,y)*inside;
      vec3 c=mix(uCol,uRim,edge*.85);
      float fadeX=smoothstep(0.,.18,vUv.x)*smoothstep(1.,.82,vUv.x);
      gl_FragColor=vec4(c,inside*mist*wash*uAlpha*fadeX);
    }`
  }));
  m.position.set(0,L.y,L.z);g6.add(m);inkLayers.push(m);
});
const ensoU={uDraw:{value:0},uFade:{value:1}};
const enso=new THREE.Mesh(new THREE.PlaneGeometry(3.4,3.4),new THREE.ShaderMaterial({
  transparent:true,depthWrite:false,uniforms:ensoU,
  vertexShader:'varying vec2 vUv;void main(){vUv=uv;gl_Position=projectionMatrix*modelViewMatrix*vec4(position,1.);}',
  fragmentShader:NOISE+`uniform float uDraw,uFade;varying vec2 vUv;
  void main(){
    vec2 p=(vUv-.5)*2.;float r=length(p);float a=atan(p.y,p.x);
    float prog=fract((a-1.75)/6.2831853);
    float taper=smoothstep(0.,.05,prog)*(1.-smoothstep(.72,.97,prog)*.75);
    float th=.06*(.3+.7*taper)+.012*snoise(vec3(a*2.5,1.,0.));
    float rr=.74+.025*sin(a*2.+.8);
    float ring=1.-smoothstep(th*.7,th,abs(r-rr));
    float streak=smoothstep(-.35,.45,snoise(vec3((r-rr)*80.,a*1.6,3.)));
    float dry=mix(1.,streak,smoothstep(.4,.95,prog));
    float vis=step(prog,uDraw);
    float bleed=(1.-smoothstep(0.,th*3.5,abs(r-rr)))*.1;
    float al=(ring*dry+bleed)*vis*uFade*(.85+.15*snoise(vec3(p*28.,5.)));
    gl_FragColor=vec4(vec3(.96,.9,.86),al);
  }`
}));
enso.position.set(0,.55,-1.4);g6.add(enso);
function sealTex(){const c=document.createElement('canvas');c.width=c.height=160;const x=c.getContext('2d');
  x.fillStyle='#c8102e';x.fillRect(8,8,144,144);
  x.strokeStyle='#f5e9dc';x.lineWidth=5;x.strokeRect(20,20,120,120);
  x.fillStyle='#f5e9dc';x.font='italic 600 64px Spectral, Georgia, serif';x.textAlign='center';x.textBaseline='middle';x.fillText('AN',80,84);
  const id=x.getImageData(0,0,160,160);for(let i=0;i<id.data.length;i+=4){if(Math.random()<.07)id.data[i+3]=0;}x.putImageData(id,0,0);
  const t=new THREE.CanvasTexture(c);t.encoding=THREE.sRGBEncoding;return t;}
const seal=new THREE.Mesh(new THREE.PlaneGeometry(.5,.5),new THREE.MeshBasicMaterial({map:sealTex(),transparent:true}));
seal.position.set(1.45,-.55,-1.3);seal.rotation.z=.05;g6.add(seal);
const petalsN=90,petalPos=new Float32Array(petalsN*3),petalSeed=[];
for(let i=0;i<petalsN;i++){petalPos[i*3]=(Math.random()-.5)*12;petalPos[i*3+1]=(Math.random()-.5)*7;petalPos[i*3+2]=Math.random()*3-2;petalSeed.push(Math.random()*6);}
const petalGeo=new THREE.BufferGeometry();petalGeo.setAttribute('position',new THREE.BufferAttribute(petalPos,3));
const petals=new THREE.Points(petalGeo,new THREE.PointsMaterial({color:0xff7fae,size:.06,transparent:true,opacity:.85}));g6.add(petals);

/* dust */
{
  const n=700,pos=new Float32Array(n*3);
  for(let i=0;i<n;i++){pos[i*3]=(Math.random()-.5)*18;pos[i*3+1]=(Math.random()-.5)*9;pos[i*3+2]=(Math.random()-.5)*8;}
  const g=new THREE.BufferGeometry();g.setAttribute('position',new THREE.BufferAttribute(pos,3));
  scene.add(new THREE.Points(g,new THREE.PointsMaterial({color:0xf1e6d8,size:.03,transparent:true,opacity:.5})));
}

/* ---------- layout: each scene lives inside its own clear window on the page ---------- */
const targets=[document.getElementById('reel-0'),...document.querySelectorAll('.win'),document.getElementById('credits')];
const FOVH=2*9*Math.tan(THREE.MathUtils.degToRad(20));
// [height, width] each scene needs in world units at scale 1
const dims=[null,[5.6,5.6],[4.3,5.4],[5.2,5.8],[2.45,3.15],[4.9,7.2],null];
const rects=[];
function resize(){const w=innerWidth,h=innerHeight;R.setSize(w,h,false);cam.aspect=w/h;cam.updateProjectionMatrix();}
addEventListener('resize',resize);resize();
function place(){
  const vh=innerHeight,vw=innerWidth,upp=FOVH/vh;
  for(let i=0;i<7;i++){
    const r=targets[i].getBoundingClientRect();rects[i]=r;
    const g=groups[i];
    const vis=r.height>0&&r.bottom>-60&&r.top<vh+60;
    g.visible=vis;if(!vis)continue;
    let cx=r.left+r.width/2,cy=r.top+r.height/2,s;
    if(i===0){cx=vw/2;cy=r.top+Math.min(r.height,vh)/2;s=vw<820?.8:1;}
    else if(i===6){cx=vw/2;s=1;}
    else s=Math.min(r.height*upp/dims[i][0],r.width*upp/dims[i][1]);
    g.position.set((cx-vw/2)*upp,-(cy-vh/2)*upp,0);g.scale.setScalar(s);
  }
}
function inRect(r,x,y){return !!r&&x>=r.left&&x<=r.right&&y>=r.top&&y<=r.bottom;}

/* ---------- pointer ---------- */
const mouse=new THREE.Vector2(0,0),ray=new THREE.Raycaster();let pointerIn=false,pressed=false,px=-1,py=-1;
function setPointer(e){px=e.clientX;py=e.clientY;mouse.x=px/innerWidth*2-1;mouse.y=-(py/innerHeight)*2+1;pointerIn=true;}
addEventListener('pointermove',setPointer,{passive:true});
addEventListener('pointerdown',e=>{setPointer(e);pressed=true;},{passive:true});
['pointerup','pointercancel','blur'].forEach(ev=>addEventListener(ev,()=>{pressed=false;}));
function pick(){
  ray.setFromCamera(mouse,cam);
  if(groups[0].visible){
    const h=ray.intersectObject(fleshProxy)[0];
    if(h){inv.copy(flesh.matrixWorld).invert();tmpV.copy(h.point).applyMatrix4(inv).normalize().multiplyScalar(RAD);fleshU.uPoke.value.lerp(tmpV,.55);woundTarget=pressed?1.35:.6;}
    else woundTarget=0;
  }
  if(groups[2].visible){
    const h=ray.intersectObjects(exObjs)[0];
    exObjs.forEach(o=>o.userData.hover=0);
    if(h){h.object.userData.hover=1;showExhibit(h.object.userData.i);}
  }
  if(groups[3].visible){
    const h=ray.intersectObjects(nodes)[0];
    if(hovNode&&(!h||h.object!==hovNode))hovNode.scale.setScalar(1);
    if(h){hovNode=h.object;hovNode.scale.setScalar(2.4);nodeOut.textContent='> '+hovNode.userData.label;}
  }
}

/* ---------- loop ---------- */
const clock=new THREE.Clock();let camY=0,running=true,termClock=0;
document.addEventListener('visibilitychange',()=>{running=!document.hidden;if(running){clock.getDelta();requestAnimationFrame(tick);}});
const ease=x=>x<.5?2*x*x:1-Math.pow(-2*x+2,2)/2;
function tick(){
  if(!running)return;
  const dt=Math.min(clock.getDelta(),.05),t=clock.elapsedTime*(reduce?.3:1);
  place();
  if(pointerIn)pick();

  if(groups[0].visible){
    fleshU.uTime.value=t;
    fleshU.uWound.value+=(woundTarget-fleshU.uWound.value)*Math.min(1,dt*(woundTarget>fleshU.uWound.value?14:5));
    flesh.rotation.y=t*.06+mouse.x*.25;flesh.rotation.x=mouse.y*.18;
  }
  if(groups[1].visible){
    const want=(pressed&&inRect(rects[1],px,py))?1:0;lift+=(want-lift)*Math.min(1,dt*5);
    knotRig.position.y=lift*1.35;knotRig.scale.setScalar(1+lift*.22);
    knot.rotation.set(t*.25,t*(.35+lift*.8),0);shell.rotation.copy(knot.rotation);core.rotation.copy(knot.rotation);
    shell.scale.setScalar(1+lift*.14);shell.material.opacity=lift*.9;core.material.opacity=lift;
    knot.material.transparent=true;knot.material.opacity=1-lift*.55;
    grid.material.opacity=1;
    props.forEach(p=>{const a=t*.6+p.userData.a;p.position.set(Math.cos(a)*2.4,Math.sin(a*1.3)*.6+lift*1.1,Math.sin(a)*2.4);p.rotation.set(t,t*.7,0);});
  }
  if(groups[2].visible){exObjs.forEach(o=>{const u=o.userData;o.rotation.y+=dt*(.6+u.hover*3);o.rotation.x=Math.sin(t+u.i)*.3;o.position.y=u.base+Math.sin(t*1.4+u.i)*.08+u.hover*.12;const s=1+u.hover*.3;o.scale.lerp(tmpV.set(s,s,s),.15);});pinkL.intensity=2+Math.sin(t*3)*.4;}
  if(groups[3].visible){
    graph.rotation.y=t*.1;
    pulses.forEach(p=>{p.userData.t+=dt*.7;if(p.userData.t>1){p.userData.t=0;p.userData.e=edges[Math.floor(Math.random()*edges.length)];}const e=p.userData.e;p.position.lerpVectors(nodes[e[0]].position,nodes[e[1]].position,p.userData.t);});
    stepTerm(dt*(reduce?.5:1));
    if(!reduce&&Math.random()<dt*.35)term.glitch=.18;
    if(term.glitch>0){term.glitch-=dt;monitor.position.x=(Math.random()-.5)*.06;redL.intensity=3;}else{monitor.position.x=0;redL.intensity=1.4+Math.sin(t*9)*.15;}
    termClock+=dt;if(termClock>1/24){termClock=0;drawTerm(t);}
    monitor.rotation.y=-.28+mouse.x*.08;led.visible=Math.floor(t*1.5)%2===0;
  }
  if(groups[4].visible){
    book.rotation.y=.12+mouse.x*.18;book.rotation.x=-.42-mouse.y*.08;
    flipT+=dt*(reduce?.5:1);
    const dur=1.5;
    if(flipT>=0){
      const p=Math.min(flipT/dur,1);layFlip(Math.PI*ease(p));
      if(p>=1){spread=(spread+2)%pagesData.length;setSpread(spread);layFlip(0);flipT=-2.6;}
    }
    ribbon.rotation.z=Math.sin(t*.8)*.05;
  }
  if(groups[5].visible){
    water.material.uniforms.uTime.value=t;
    eye.rotation.y+=((mouse.x*.55)-eye.rotation.y)*.08;eye.rotation.x+=((-mouse.y*.45)-eye.rotation.x)*.08;
    eye.position.y=.05+Math.sin(t*1.1)*.08;
    const sr=.7+((t*.55)%1)*1.75;scanRing.scale.setScalar(sr);scanRing.material.opacity=.7*(1-(sr-.7)/1.75);
    for(let i=0;i<cells.length;i++){const c=cells[i];const z=Math.sin(c[2]*5-t*2.2)*.09+Math.max(0,.25-Math.abs(c[2]-sr))*1.2;dm.position.set(c[0],c[1],z);dm.rotation.set(0,0,Math.atan2(c[1],c[0]));dm.scale.setScalar(1+Math.max(0,.2-Math.abs(c[2]-sr))*4);dm.updateMatrix();iris.setMatrixAt(i,dm.matrix);}
    iris.instanceMatrix.needsUpdate=true;
    for(let i=0;i<GR;i++){const b=grassBase[i];gd.position.set(b[0],-1.12,b[1]);gd.rotation.set(0,0,Math.sin(t*1.3+b[2]+b[0]*.8)*.14);gd.scale.set(1,b[3],1);gd.updateMatrix();grass.setMatrixAt(i,gd.matrix);}
    grass.instanceMatrix.needsUpdate=true;
    flowers.forEach(m=>{const u=m.userData;m.position.set(u.x+Math.sin(t*.3+u.ph)*.4,u.y+Math.sin(t*.5+u.ph)*.25,u.z);m.rotation.set(Math.sin(t*.4+u.ph)*.6,t*u.s,t*u.s*.7);});
    stageG.rotation.y=mouse.x*.1;
  }
  if(groups[6].visible){
    inkLayers.forEach(m=>m.material.uniforms.uTime.value=t);
    const cyc=t%9;
    ensoU.uDraw.value=cyc<3.6?1-Math.pow(1-cyc/3.6,3):1;
    ensoU.uFade.value=cyc<7.4?1:1-(cyc-7.4)/1.6;
    const pp=petalGeo.attributes.position;
    for(let i=0;i<petalsN;i++){let x=pp.getX(i)+dt*.18,y=pp.getY(i)-dt*(.12+.05*Math.sin(t+petalSeed[i]));if(y<-3.6){y=3.6;x=(Math.random()-.5)*12;}if(x>6)x=-6;pp.setXY(i,x+Math.sin(t*1.3+petalSeed[i])*.002,y);}
    pp.needsUpdate=true;
    enso.rotation.z=Math.sin(t*.1)*.03;
  }
  R.render(scene,cam);
  requestAnimationFrame(tick);
}
requestAnimationFrame(tick);
})();
</script>

</body>
</html>
