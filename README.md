<html lang="en">
<head>
  <script>
    if (!window.location.search.includes('v=')) {
      const version = Date.now();
      const url = window.location.origin + window.location.pathname + '?v=' + version;
      window.location.replace(url);
    }
  </script>

  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Alborz Nazari — Cybersecurity Engineer</title>

  <style>
    :root {
      --bg: #05030a;
      --glass-bg: rgba(10, 5, 20, 0.82);
      --accent: #e056fd;
      --accent-soft: #9b5cff;
      --accent-strong: #ff2e9f;
      --text-main: #f5f3ff;
      --text-muted: #b3a8d9;
      --border-glass: rgba(255, 255, 255, 0.08);
      --shadow-strong: 0 30px 80px rgba(0, 0, 0, 0.85);
      --shadow-soft: 0 18px 40px rgba(0, 0, 0, 0.6);
      --radius-lg: 22px;
      --radius-md: 14px;
      --blur-glass: 22px;
      --transition-fast: 0.18s ease-out;
      --transition-med: 0.28s ease-out;
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "SF Pro Text",
        "Segoe UI", sans-serif;
      color: var(--text-main);
      background: radial-gradient(circle at 10% 0%, #2b0b3f 0, transparent 55%),
                  radial-gradient(circle at 90% 10%, #4b0f5f 0, transparent 55%),
                  radial-gradient(circle at 50% 100%, #ff2e9f33 0, transparent 60%),
                  var(--bg);
      overflow-x: hidden;
    }

    /* Animated glow background */
    .bg-orbit {
      position: fixed;
      inset: -40vh -40vw;
      pointer-events: none;
      z-index: -2;
      background:
        radial-gradient(circle at 20% 20%, #ff2e9f22 0, transparent 55%),
        radial-gradient(circle at 80% 30%, #9b5cff33 0, transparent 55%),
        radial-gradient(circle at 50% 80%, #ff2e9f22 0, transparent 60%);
      filter: blur(4px);
      animation: bgFloat 26s ease-in-out infinite alternate;
      opacity: 0.9;
    }

    @keyframes bgFloat {
      0% {
        transform: translate3d(0, 0, 0) scale(1);
      }
      50% {
        transform: translate3d(-2%, 1%, 0) scale(1.03);
      }
      100% {
        transform: translate3d(2%, -1%, 0) scale(1.05);
      }
    }

    .scanline {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: -1;
      background-image: linear-gradient(
        to bottom,
        rgba(255, 255, 255, 0.04) 1px,
        transparent 1px
      );
      background-size: 100% 2px;
      mix-blend-mode: soft-light;
      opacity: 0.35;
      animation: scan 8s linear infinite;
    }

    @keyframes scan {
      0% {
        transform: translateY(-10px);
      }
      100% {
        transform: translateY(10px);
      }
    }

    .page {
      max-width: 1080px;
      margin: 40px auto 80px;
      padding: 0 20px;
    }

    .card-main {
      background: linear-gradient(
          135deg,
          rgba(255, 255, 255, 0.06),
          rgba(10, 5, 20, 0.9)
        );
      border-radius: 28px;
      border: 1px solid rgba(255, 255, 255, 0.12);
      box-shadow: var(--shadow-strong);
      backdrop-filter: blur(26px);
      padding: 32px 26px 34px;
      position: relative;
      overflow: hidden;
    }

    .card-main::before {
      content: "";
      position: absolute;
      inset: -40%;
      background: radial-gradient(
        circle at 0% 0%,
        rgba(255, 46, 159, 0.18),
        transparent 55%
      );
      opacity: 0.7;
      pointer-events: none;
    }

    .card-main::after {
      content: "";
      position: absolute;
      inset: -40%;
      background: radial-gradient(
        circle at 100% 100%,
        rgba(155, 92, 255, 0.22),
        transparent 55%
      );
      opacity: 0.7;
      pointer-events: none;
    }

    .card-main-inner {
      position: relative;
      z-index: 1;
    }

    .header {
      text-align: center;
      margin-bottom: 26px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 4px 12px;
      border-radius: 999px;
      border: 1px solid rgba(255, 255, 255, 0.18);
      background: radial-gradient(
        circle at 0 0,
        rgba(255, 46, 159, 0.3),
        transparent 60%
      );
      font-size: 0.78rem;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 14px;
    }

    .eyebrow-dot {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: var(--accent-strong);
      box-shadow: 0 0 12px rgba(255, 46, 159, 0.9);
    }

    h1 {
      margin: 0 0 6px;
      font-size: clamp(2.1rem, 3vw, 2.6rem);
      letter-spacing: 0.03em;
    }

    .subtitle {
      margin: 0;
      font-size: 0.98rem;
      color: var(--text-muted);
    }

    .badge-row {
      margin-top: 20px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
    }

    .badge-row img {
      height: 32px;
      border-radius: 999px;
      box-shadow: 0 10px 26px rgba(0, 0, 0, 0.6);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast),
        filter var(--transition-fast);
    }

    .badge-row img:hover {
      transform: translateY(-2px) scale(1.02);
      filter: brightness(1.08);
      box-shadow: 0 16px 40px rgba(0, 0, 0, 0.8);
    }

    .grid {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 1.1fr);
      gap: 22px;
      margin-top: 26px;
    }

    @media (max-width: 840px) {
      .grid {
        grid-template-columns: minmax(0, 1fr);
      }
    }

    .panel {
      background: var(--glass-bg);
      border-radius: var(--radius-lg);
      border: 1px solid var(--border-glass);
      box-shadow: var(--shadow-soft);
      padding: 18px 18px 20px;
      position: relative;
      overflow: hidden;
    }

    .panel::before {
      content: "";
      position: absolute;
      inset: -40%;
      background: radial-gradient(
        circle at 0 0,
        rgba(255, 46, 159, 0.12),
        transparent 60%
      );
      opacity: 0.7;
      pointer-events: none;
    }

    .panel-inner {
      position: relative;
      z-index: 1;
    }

    .panel-title {
      font-size: 0.9rem;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 10px;
    }

    .panel pre {
      margin: 0;
      background: rgba(5, 3, 12, 0.9);
      border-radius: var(--radius-md);
      border: 1px solid rgba(255, 255, 255, 0.06);
      padding: 14px 14px 16px;
      font-family: "JetBrains Mono", ui-monospace, SFMono-Regular, Menlo, Monaco,
        Consolas, "Liberation Mono", "Courier New", monospace;
      font-size: 0.78rem;
      color: var(--text-main);
      max-height: 260px;
      overflow: auto;
    }

    .section {
      margin-top: 26px;
    }

    .section-title {
      font-size: 0.9rem;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 10px;
    }

    .ascii-block {
      background: rgba(5, 3, 12, 0.9);
      border-radius: var(--radius-md);
      border: 1px solid rgba(255, 255, 255, 0.06);
      padding: 14px 14px 16px;
      font-family: "JetBrains Mono", ui-monospace, SFMono-Regular, Menlo, Monaco,
        Consolas, "Liberation Mono", "Courier New", monospace;
      font-size: 0.78rem;
      color: var(--text-main);
      overflow-x: auto;
      white-space: pre;
    }

    .badge-group {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin: 8px 0 14px;
    }

    .badge-group img {
      height: 30px;
      border-radius: 999px;
      box-shadow: 0 10px 26px rgba(0, 0, 0, 0.6);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast),
        filter var(--transition-fast);
    }

    .badge-group img:hover {
      transform: translateY(-1px) scale(1.02);
      filter: brightness(1.08);
      box-shadow: 0 16px 40px rgba(0, 0, 0, 0.8);
    }

    .table-wrap {
      margin-top: 10px;
      border-radius: var(--radius-md);
      overflow: hidden;
      border: 1px solid rgba(255, 255, 255, 0.08);
      background: rgba(5, 3, 12, 0.96);
    }

    table {
      width: 100%;
      border-collapse: collapse;
      font-size: 0.82rem;
    }

    th, td {
      padding: 10px 12px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.06);
      text-align: left;
      color: var(--text-main);
    }

    th {
      background: linear-gradient(
        135deg,
        rgba(155, 92, 255, 0.22),
        rgba(255, 46, 159, 0.18)
      );
      font-weight: 600;
    }

    tr:last-child td {
      border-bottom: none;
    }

    .footer {
      margin-top: 26px;
      text-align: center;
      font-size: 0.8rem;
      color: var(--text-muted);
    }

    .footer strong {
      color: var(--accent-soft);
      font-weight: 500;
    }

    .footer-badges {
      margin-top: 10px;
      display: flex;
      justify-content: center;
      gap: 10px;
      flex-wrap: wrap;
    }

    .footer-badges img {
      height: 30px;
      border-radius: 999px;
      box-shadow: 0 10px 26px rgba(0, 0, 0, 0.6);
    }

    /* =============================
       PROJECTS UI SECTION
    ============================== */

    .projects-panel {
      background: linear-gradient(135deg, #ffffff, #f4f1ff);
      border-radius: 22px;
      padding: 24px;
      box-shadow: 0 25px 70px rgba(0,0,0,0.5);
    }

    .projects-grid {
      display: grid;
      gap: 18px;
    }

    .project-card {
      background: #ffffff;
      border-radius: 16px;
      padding: 18px;
      border: 1px solid rgba(0,0,0,0.08);
      transition: all 0.25s ease;
    }

    .project-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 35px rgba(0,0,0,0.18);
    }

    .project-title {
      font-weight: 700;
      font-size: 1.05rem;
      color: #000;
      margin-bottom: 8px;
    }

    .project-desc {
      font-size: 0.92rem;
      color: #222;
      margin-bottom: 12px;
      line-height: 1.4;
    }

    .project-link a {
      display: inline-block;
      font-size: 0.82rem;
      font-weight: 600;
      padding: 6px 14px;
      border-radius: 999px;
      background: linear-gradient(135deg, #9b5cff, #ff2e9f);
      color: #fff;
      text-decoration: none;
    }

    .project-link a:hover { opacity: 0.85; }

    .working-list {
      margin-top: 22px;
      background: #ffffff;
      border-radius: 16px;
      padding: 16px;
      border: 1px solid rgba(0,0,0,0.08);
    }

    .working-list strong {
      color: #000;
      display: block;
      margin-bottom: 10px;
    }

    .working-list ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }

    .working-list li {
      padding: 8px 0;
      border-bottom: 1px solid rgba(0,0,0,0.06);
      font-size: 0.9rem;
      color: #111;
    }

    .working-list li:last-child { border-bottom: none; }

    /* Entrance animation */
    .card-main {
      opacity: 0;
      transform: translateY(18px) scale(0.99);
      animation: fadeInUp 0.7s var(--transition-med) forwards;
    }

    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }
  </style>
</head>

<body>
  <div class="bg-orbit"></div>
  <div class="scanline"></div>

  <main class="page">
    <section class="card-main">
      <div class="card-main-inner">

        <!-- HEADER -->
        <header class="header">
          <div class="eyebrow">
            <span class="eyebrow-dot"></span>
            <span>ALBORZ NAZARI · CYBERSECURITY ENGINEER</span>
          </div>

          <h1>Software Engineer → Cybersecurity Engineer</h1>
          <p class="subtitle">
            Linux · Web App Security · Digital Forensics · 3D/VFX · Technical Writing
          </p>

          <div class="badge-row">
            <a href="https://github.com/AlborzNazari">
              <img src="https://img.shields.io/badge/GitHub-AlborzNazari-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
            </a>
            <a href="https://linkedin.com/in/AlborzNazari">
              <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
            </a>
            <img src="https://komarev.com/ghpvc/?username=AlborzNazari&style=for-the-badge&color=00ff41&label=PROFILE+VIEWS" alt="Profile Views" />
          </div>
        </header>

        <!-- TOP GRID -->
        <div class="grid">
          <section class="panel">
            <div class="panel-inner">
              <div class="panel-title">whoami</div>
              <pre>
name        : Alborz Nazari
role        : Software Engineer → Cybersecurity Engineer
location    : España 
status      : Building. Learning. Breaking things (ethically).

foundation  :
  - Linux systems & engineering fundamentals
  - Cybersecurity concepts (offensive + defensive)
  - Technical problem-solving & systems thinking

unique_edge :
  - 3D/VFX production → visual explainers for complex security topics
  - Technical writing that makes hard things understandable
  - Engineering mindset applied to security challenges

currently   :
  - Developing hands-on cybersecurity projects on GitHub
  - Expanding into web application security & digital forensics
  - Building offensive/defensive security tooling

open_to     : Cybersecurity engineering roles & collaborations
              </pre>
            </div>
          </section>

          <section class="panel">
            <div class="panel-inner">
              <div class="panel-title">Current Objectives</div>
              <div class="ascii-block">
╔══════════════════════════════════════════════════════════════════╗
║                                                                  ║
║   🕸️  Mastering  →  Web Application Security (OWASP Top 10)     ║
║   🔬  Practicing →  Digital Forensics & Incident Response        ║
║   🛠️  Building   →  Offensive / Defensive Security Tools         ║
║   🎥  Creating   →  3D/VFX Visual Explainers for Security        ║
║   📝  Writing    →  Clear Technical Security Documentation       ║
║   🏁  Targeting  →  CTF Competitions & Real-World Labs           ║
║                                                                  ║
╚══════════════════════════════════════════════════════════════════╝
              </div>
            </div>
          </section>
        </div>

        <!-- TECH STACK -->
        <section class="section">
          <div class="section-title">Tech Stack & Toolkit</div>

          <div class="panel" style="margin-bottom: 14px;">
            <div class="panel-inner">
              <strong>Security &amp; Recon</strong>
              <div class="badge-group">
                <img src="https://img.shields.io/badge/Burp_Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white" alt="Burp Suite" />
                <img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" alt="Wireshark" />
                <img src="https://img.shields.io/badge/Nmap-00549E?style=for-the-badge&logo=linux&logoColor=white" alt="Nmap" />
                <img src="https://img.shields.io/badge/Metasploit-2596CD?style=for-the-badge&logo=metasploit&logoColor=white" alt="Metasploit" />
                <img src="https://img.shields.io/badge/OWASP_ZAP-00549E?style=for-the-badge&logo=owasp&logoColor=white" alt="OWASP ZAP" />
              </div>

              <strong>Systems &amp; Infrastructure</strong>
              <div class="badge-group">
                <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux" />
                <img src="https://img.shields.io/badge/Kali_Linux-268BEE?style=for-the-badge&logo=kalilinux&logoColor=white" alt="Kali Linux" />
                <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
                <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />
                <img src="https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white" alt="Bash" />
              </div>

              <strong>Languages</strong>
              <div class="badge-group">
                <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
                <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" alt="C" />
                <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++" />
                <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
              </div>

              <strong>3D / VFX</strong>
              <div class="badge-group">
                <img src="https://img.shields.io/badge/Blender-F5792A?style=for-the-badge&logo=blender&logoColor=white" alt="Blender" />
                <img src="https://img.shields.io/badge/After_Effects-9999FF?style=for-the-badge&logo=adobeaftereffects&logoColor=white" alt="After Effects" />
                <img src="https://img.shields.io/badge/DaVinci_Resolve-233A51?style=for-the-badge&logo=davinciresolve&logoColor=white" alt="DaVinci Resolve" />
              </div>
            </div>
          </div>
        </section>

        <!-- PROJECTS -->
        <section class="section">
          <div class="section-title">Projects I'm Working On</div>

          <div class="projects-panel">

            <div class="projects-grid">

              <div class="project-card">
                <div class="project-title">🔐 Secure Apportionment System</div>
                <div class="project-desc">
                  A secure apportionment system demonstrating the Huntington-Hill method with AES-256 encryption.
                </div>
                <div class="project-link">
                  <a href="https://github.com/AlborzNazari/Secure-Apportionment-System">View Repository</a>
                </div>
              </div>

              <div class="project-card">
                <div class="project-title">🕵️ Open Intelligence Lab</div>
                <div class="project-desc">
                  Ethical OSINT research platform for threat modeling and explainable analytics.
                </div>
                <div class="project-link">
                  <a href="https://github.com/AlborzNazari/open-intelligence-lab">View Repository</a>
                </div>
              </div>

              <div class="project-card">
                <div class="project-title">🛡️ ThreatBoard OSINT (MITRE)</div>
                <div class="project-desc">
                  Maps OSINT findings to MITRE ATT&amp;CK techniques on a visual threat board.
                </div>
                <div class="project-link">
                  <a href="https://github.com/AlborzNazari/ThreatBoard_OSINT_MITRE">View Repository</a>
                </div>
              </div>

            </div>

            <div class="working-list">
              <strong>Currently Building:</strong>
              <ul>
                <li>🔐 Web App Scanner — Python, Burp API</li>
                <li>🎥 Security VFX Series — Blender, After Effects</li>
                <li>🛡️ Defensive Toolkit — Bash, Python</li>
                <li>📝 CTF Writeups — Markdown</li>
              </ul>
            </div>

          </div>
        </section>

        <!-- ACTIVITY -->
        <section class="section">
          <div class="section-title">Activity</div>
          <div class="panel">
            <div class="panel-inner">
              <div class="ascii-block">
Contributions this year ████████████████████░░░░  in progress
Web App Security        ████████████░░░░░░░░░░░░  learning
Digital Forensics       ████████░░░░░░░░░░░░░░░░  learning
Tool Development        ██████░░░░░░░░░░░░░░░░░░  building
3D / VFX Work           █████████████████░░░░░░░  experienced
Technical Writing       ███████████████░░░░░░░░░  experienced
              </div>
            </div>
          </div>
        </section>

        <!-- DIFFERENTIATOR -->
        <section class="section">
          <div class="section-title">What Makes Me Different</div>
          <div class="panel">
            <div class="panel-inner">
              <div class="ascii-block">
Most engineers:  write code → ship it
       Alborz:  write code → secure it → explain it visually

The intersection of:
  [Engineering] + [Cybersecurity] + [3D/VFX] + [Technical Writing]

= Someone who can build secure systems AND communicate
  exactly why they're secure (or why others aren't).
              </div>
            </div>
          </div>
        </section>

        <!-- PHILOSOPHY -->
        <section class="section">
          <div class="section-title">Philosophy</div>
          <div class="panel">
            <div class="panel-inner">
              <blockquote style="margin: 0; color: var(--text-muted); font-style: italic;">
                "Security isn't a feature — it's a foundation.<br />
                Build it in, or rebuild everything later."
              </blockquote>
            </div>
          </div>
        </section>

        <!-- CONTACT -->
        <section class="section">
          <div class="section-title">Reach Out</div>
          <div class="panel">
            <div class="panel-inner">
              <div class="table-wrap">
                <table>
                  <tr>
                    <th>Platform</th>
                    <th>Link</th>
                  </tr>
                  <tr>
                    <td>🐙 GitHub</td>
                    <td><a href="https://github.com/AlborzNazari">github.com/AlborzNazari</a></td>
                  </tr>
                  <tr>
                    <td>💼 LinkedIn</td>
                    <td><a href="https://linkedin.com/in/AlborzNazari">linkedin.com/in/AlborzNazari</a></td>
                  </tr>
                </table>
              </div>

              <div class="footer-badges">
                <img src="https://img.shields.io/badge/Status-Open_for_Collaborations-00ff41?style=for-the-badge" alt="Open for Collaborations" />
                <img src="https://img.shields.io/badge/Seeking-Cybersecurity_Engineering_Roles-FF6B35?style=for-the-badge" alt="Seeking Roles" />
              </div>
            </div>
          </div>
        </section>

        <!-- FOOTER -->
        <footer class="footer">
          [ <strong>Alborz Nazari</strong> · GitHub Profile · Updated 2026 ]<br />
          If you're building in security or need someone who can explain it visually — let's connect.
        </footer>

      </div>
    </section>
  </main>
</body>
</html>
