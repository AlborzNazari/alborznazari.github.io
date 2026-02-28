<!DOCTYPE html>
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
    }

    * { box-sizing: border-box; }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color: var(--text-main);
      background: radial-gradient(circle at 10% 0%, #2b0b3f 0, transparent 55%),
                  radial-gradient(circle at 90% 10%, #4b0f5f 0, transparent 55%),
                  var(--bg);
      overflow-x: hidden;
    }

    .page { max-width: 1080px; margin: 40px auto; padding: 0 20px; }

    .card-main {
      background: linear-gradient(135deg, rgba(255,255,255,0.06), rgba(10,5,20,0.9));
      border-radius: 28px;
      border: 1px solid rgba(255,255,255,0.12);
      box-shadow: var(--shadow-strong);
      backdrop-filter: blur(26px);
      padding: 32px;
    }

    .section { margin-top: 40px; }

    .section-title {
      font-size: 0.9rem;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 18px;
    }

    /* =============================
       NEW PROJECTS UI SECTION
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

  </style>
</head>

<body>
  <main class="page">
    <section class="card-main">

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
                Maps OSINT findings to MITRE ATT&CK techniques on a visual threat board.
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

    </section>
  </main>
</body>
</html>
