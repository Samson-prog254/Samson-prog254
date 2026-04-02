<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes" />
  <title>Samson Chinthenga · Mobile · Backend · Web</title>
  <style>
    :root{
      --bg: #0a0c10;
      --panel: #0d1117;
      --panel2: #0b0f14;
      --border: #21262d;
      --border2: #2d333b;
      --text: #e6edf3;
      --muted: #9aa4af;
      --muted2:#b7c0cb;
      --accent: #fbbf24; /* amber-400 */
      --accent2:#f59e0b; /* amber-500 */
      --good:#22c55e;
      --shadow: 0 16px 48px rgba(0,0,0,.45);
      --radius: 22px;
    }

    * { box-sizing: border-box; }
    body{
      margin:0;
      padding: 28px 14px;
      background: radial-gradient(1200px 600px at 10% -10%, rgba(251,191,36,.16), transparent 55%),
                  radial-gradient(900px 520px at 90% 0%, rgba(34,197,94,.10), transparent 60%),
                  var(--bg);
      color: var(--text);
      font-family: ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", "Noto Sans", Inter, Helvetica, Arial, sans-serif;
      line-height: 1.55;
    }

    a{ color: inherit; }

    .wrap{
      max-width: 1040px;
      margin: 0 auto;
    }

    .card{
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.0)) , var(--panel);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      overflow: hidden;
    }

    /* HERO */
    .hero{
      padding: 22px;
      border-bottom: 1px solid rgba(255,255,255,0.04);
      background:
        radial-gradient(900px 350px at 10% 0%, rgba(251,191,36,.18), transparent 60%),
        radial-gradient(700px 320px at 90% 10%, rgba(34,197,94,.10), transparent 55%),
        linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,0));
    }

    .hero-top{
      display:flex;
      justify-content: space-between;
      align-items:flex-start;
      gap: 14px;
      flex-wrap: wrap;
    }

    .name{
      margin:0;
      font-size: 2.35rem;
      letter-spacing: -0.03em;
      line-height: 1.1;
      background: linear-gradient(135deg, #fde68a, var(--accent), var(--accent2));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      font-weight: 800;
    }

    .headline{
      margin: 10px 0 0 0;
      color: var(--muted2);
      font-size: 1.03rem;
      max-width: 62ch;
    }

    .pill{
      display:inline-flex;
      align-items:center;
      gap: 8px;
      padding: 8px 12px;
      border-radius: 999px;
      border: 1px solid var(--border2);
      background: rgba(255,255,255,0.03);
      font-size: .86rem;
      color: var(--muted2);
      white-space: nowrap;
    }
    .pill.good{
      border-color: rgba(34,197,94,.35);
      background: rgba(34,197,94,.08);
      color: #d9ffe7;
    }

    .actions{
      display:flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 14px;
    }

    .btn{
      display:inline-flex;
      align-items:center;
      gap: 8px;
      padding: 10px 12px;
      border-radius: 12px;
      border: 1px solid var(--border2);
      background: rgba(255,255,255,0.03);
      text-decoration: none;
      font-size: .9rem;
      font-weight: 600;
      transition: transform .15s ease, border-color .15s ease, background .15s ease;
    }
    .btn:hover{
      transform: translateY(-1px);
      border-color: rgba(251,191,36,.55);
      background: rgba(251,191,36,.08);
    }
    .btn.primary{
      border-color: rgba(251,191,36,.55);
      background: rgba(251,191,36,.12);
    }

    /* BADGES */
    .badges{
      display:flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 16px;
    }
    .badge{
      padding: 6px 10px;
      border-radius: 999px;
      border: 1px solid var(--border2);
      background: rgba(255,255,255,0.02);
      font-size: .78rem;
      color: #dbe3ea;
    }
    .badge.accent{
      border-color: rgba(251,191,36,.45);
      background: rgba(251,191,36,.10);
      color: #fff4c2;
    }

    /* BODY GRID */
    .body{
      padding: 18px 22px 22px 22px;
      display:grid;
      grid-template-columns: 1.2fr .8fr;
      gap: 16px;
    }

    .section{
      background: rgba(255,255,255,0.02);
      border: 1px solid rgba(255,255,255,0.06);
      border-radius: 18px;
      padding: 16px;
    }

    h2{
      margin:0 0 10px 0;
      font-size: 1.15rem;
      letter-spacing: -0.01em;
      display:flex;
      align-items:center;
      gap: 8px;
    }

    .muted{ color: var(--muted); }

    /* STATS */
    .stats{
      display:grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 10px;
      margin-top: 10px;
    }
    .stat{
      background: rgba(0,0,0,.18);
      border: 1px solid rgba(255,255,255,0.06);
      border-radius: 16px;
      padding: 12px;
      text-align:left;
    }
    .stat .num{
      font-size: 1.35rem;
      font-weight: 800;
      color: var(--accent);
      margin:0;
      line-height: 1.15;
    }
    .stat .lbl{
      margin-top: 4px;
      font-size: .75rem;
      text-transform: uppercase;
      letter-spacing: .08em;
      color: var(--muted);
    }

    /* SKILLS */
    .split{
      display:grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 10px;
    }
    .kv{
      border: 1px solid rgba(255,255,255,0.06);
      border-radius: 14px;
      padding: 12px;
      background: rgba(0,0,0,.14);
    }
    .kv strong{
      display:block;
      margin-bottom: 4px;
    }
    .kv div{
      color: #cfd7df;
      font-size: .9rem;
    }

    /* PROJECTS */
    .projects{
      display:grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 12px;
      margin-top: 10px;
    }
    .project{
      border: 1px solid rgba(255,255,255,0.06);
      background: rgba(0,0,0,.14);
      border-radius: 18px;
      padding: 14px;
      transition: transform .15s ease, border-color .15s ease;
    }
    .project:hover{
      transform: translateY(-2px);
      border-color: rgba(251,191,36,.45);
    }
    .project h3{
      margin:0;
      font-size: 1.02rem;
      color: #fff4c2;
      letter-spacing: -0.01em;
    }
    .chips{
      display:flex;
      flex-wrap: wrap;
      gap: 6px;
      margin: 10px 0 8px 0;
    }
    .chip{
      font-size: .72rem;
      padding: 4px 8px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,0.07);
      background: rgba(255,255,255,0.02);
      color: #d7dee6;
    }
    .project p{
      margin:0;
      font-size: .9rem;
      color: #c9d1d9;
    }

    /* CONTACT */
    .contact{
      display:grid;
      gap: 10px;
      margin-top: 10px;
    }

    .contact a{
      text-decoration:none;
    }

    .contact .btn{
      justify-content: space-between;
      width: 100%;
    }

    .footer{
      padding: 16px 22px 22px 22px;
      border-top: 1px solid rgba(255,255,255,0.04);
      color: var(--muted);
      text-align:center;
      font-size: .88rem;
    }

    @media (max-width: 860px){
      .body{ grid-template-columns: 1fr; }
      .projects{ grid-template-columns: 1fr; }
      .split{ grid-template-columns: 1fr; }
      .stats{ grid-template-columns: 1fr 1fr; }
    }

    @media (max-width: 520px){
      body{ padding: 18px 10px; }
      .name{ font-size: 1.85rem; }
      .stats{ grid-template-columns: 1fr; }
      .hero{ padding: 18px; }
      .body{ padding: 14px; }
      .section{ padding: 14px; }
    }
  </style>
</head>

<body>
  <div class="wrap">
    <div class="card">

      <!-- HERO -->
      <div class="hero">
        <div class="hero-top">
          <div>
            <h1 class="name">Samson Chinthenga</h1>
            <p class="headline">
              📱 Mobile · ⚙️ Backend · 🌐 Web — cross‑platform engineer building fast, reliable products end‑to‑end.
            </p>

            <div class="actions">
              <a class="btn primary" href="mailto:samsonchinthenga29@gmail.com">✉️ Email me</a>
              <a class="btn" target="_blank" href="https://www.linkedin.com/in/samson-chinthenga-5ab6aa321">🔗 LinkedIn</a>
              <a class="btn" target="_blank" href="https://github.com/samsonchinthenga">🐙 GitHub</a>
            </div>

            <div class="badges">
              <span class="badge accent">Flutter</span>
              <span class="badge accent">React Native</span>
              <span class="badge">Node.js</span>
              <span class="badge">Python</span>
              <span class="badge">Firebase</span>
              <span class="badge">React / Next.js</span>
              <span class="badge">Tailwind</span>
              <span class="badge">MongoDB</span>
              <span class="badge">PostgreSQL</span>
              <span class="badge">Docker</span>
            </div>
          </div>

          <div style="display:flex; flex-direction:column; gap:10px; align-items:flex-end;">
            <span class="pill good">🟢 Available for opportunities</span>
            <span class="pill">🎨 UI/UX friendly · Figma</span>
            <span class="pill">🚀 Ship fast · iterate faster</span>
          </div>
        </div>
      </div>

      <!-- BODY -->
      <div class="body">
        <!-- LEFT COLUMN -->
        <div style="display:grid; gap:16px;">

          <div class="section">
            <h2>About</h2>
            <p style="margin:0;">
              I'm a <strong>cross‑platform mobile engineer</strong> (<strong>Flutter</strong> · <strong>React Native</strong>)
              who also architects <strong>scalable backends</strong> (Node.js, Python, Firebase) and crafts
              <strong>modern web experiences</strong> (React/Next, Tailwind).
              I deliver complete, user‑first solutions — from database design to pixel‑perfect interfaces.
            </p>

            <div class="stats">
              <div class="stat">
                <div class="num">15+</div>
                <div class="lbl">Projects shipped</div>
              </div>
              <div class="stat">
                <div class="num">3+</div>
                <div class="lbl">Years experience</div>
              </div>
              <div class="stat">
                <div class="num">12+</div>
                <div class="lbl">Technologies</div>
              </div>
              <div class="stat">
                <div class="num">100%</div>
                <div class="lbl">User‑focused</div>
              </div>
            </div>
          </div>

          <div class="section">
            <h2>🛠️ Tech arsenal</h2>
            <div class="split">
              <div class="kv">
                <strong>📱 Mobile</strong>
                <div>Flutter · React Native · Dart · Swift basics</div>
              </div>
              <div class="kv">
                <strong>⚙️ Backend</strong>
                <div>Node.js · Express · Python · Firebase · MongoDB · PostgreSQL</div>
              </div>
              <div class="kv">
                <strong>🌐 Web</strong>
                <div>React · Next.js · TypeScript · Tailwind · HTML/CSS</div>
              </div>
              <div class="kv">
                <strong>🧰 DevOps & Tools</strong>
                <div>Git · Docker · GitHub Actions · GCP · Postman · Figma</div>
              </div>
            </div>
          </div>

          <div class="section">
            <h2>📌 Featured projects</h2>
            <p class="muted" style="margin:0 0 10px 0;">
              A few highlights (happy to share demos, links, or case studies on request).
            </p>

            <div class="projects">
              <div class="project">
                <h3>Health Product Delivery</h3>
                <div class="chips">
                  <span class="chip">Flutter</span><span class="chip">Firebase</span><span class="chip">AI recos</span>
                </div>
                <p>AI-powered health delivery with real-time tracking, smart recommendations, and seamless checkout. Served 500+ users in pilot.</p>
              </div>

              <div class="project">
                <h3>AI Chatbot Platform</h3>
                <div class="chips">
                  <span class="chip">React Native</span><span class="chip">Node.js</span><span class="chip">OpenAI</span>
                </div>
                <p>Cross-platform conversational AI with memory, custom personality tuning, and multi-tenant support.</p>
              </div>

              <div class="project">
                <h3>E‑Commerce Platform</h3>
                <div class="chips">
                  <span class="chip">React</span><span class="chip">Node.js</span><span class="chip">MongoDB</span>
                </div>
                <p>Full‑stack marketplace: admin dashboard, Stripe payments, real‑time inventory & order tracking.</p>
              </div>

              <div class="project">
                <h3>TaskFlow (SaaS)</h3>
                <div class="chips">
                  <span class="chip">React Native</span><span class="chip">Node.js</span><span class="chip">PostgreSQL</span>
                </div>
                <p>Team productivity suite with real‑time updates, file attachments, and role‑based access.</p>
              </div>

              <div class="project">
                <h3>Fitness Tracker App</h3>
                <div class="chips">
                  <span class="chip">Flutter</span><span class="chip">Dart</span><span class="chip">Firebase</span>
                </div>
                <p>Workout plans, progress charts, social challenges & health data sync — available on iOS & Android.</p>
              </div>

              <div class="project">
                <h3>Portfolio 2025 (Redesign)</h3>
                <div class="chips">
                  <span class="chip">React</span><span class="chip">Tailwind</span><span class="chip">Framer Motion</span>
                </div>
                <p>Modern interactive portfolio with dark mode, responsive layout, and smooth animations.</p>
              </div>
            </div>
          </div>

          <div class="section">
            <h2>🎨 Design & UI approach</h2>
            <p style="margin:0;">
              I don’t just build — I <strong>redesign with intention</strong>. I collaborate with designers (or create UI myself)
              using <strong>Figma</strong> and modern CSS. Focus areas: clear information hierarchy, micro‑interactions,
              accessibility, and consistent components across mobile + web.
            </p>
          </div>

          <div class="section">
            <h2>🔗 End‑to‑end capabilities</h2>
            <p style="margin:0;">
              I’ve built production apps where I own the <strong>Flutter/React Native frontend</strong>,
              <strong>Node.js/Python backend</strong>, the database (MongoDB/PostgreSQL/Firebase), and deployment (Docker/GCP).
              Real-world experience with auth, push notifications, payments, and WebSockets.
            </p>
          </div>

        </div>

        <!-- RIGHT COLUMN -->
        <div style="display:grid; gap:16px;">
          <div class="section">
            <h2>💡 What I bring</h2>
            <div class="badges" style="margin-top:10px;">
              <span class="badge accent">📱 Cross‑platform mobile</span>
              <span class="badge accent">⚡ REST & GraphQL APIs</span>
              <span class="badge accent">🔥 Real‑time (Firebase/WS)</span>
              <span class="badge accent">🤖 AI‑integrated apps</span>
              <span class="badge accent">🎨 UI/UX collaboration</span>
              <span class="badge accent">🚀 Full‑stack deployment</span>
            </div>
          </div>

          <div class="section">
            <h2>📈 GitHub pulse</h2>
            <p class="muted" style="margin:0 0 10px 0;">Snapshot-style stats (can be replaced with live badges later).</p>

            <div class="stats">
              <div class="stat">
                <div class="num">340+</div>
                <div class="lbl">Commits (2025)</div>
              </div>
              <div class="stat">
                <div class="num">22</div>
                <div class="lbl">Repos contributed</div>
              </div>
              <div class="stat">
                <div class="num">128</div>
                <div class="lbl">Stars earned</div>
              </div>
              <div class="stat">
                <div class="num">48</div>
                <div class="lbl">PRs merged</div>
              </div>
            </div>
          </div>

          <div class="section">
            <h2>📬 Let’s collaborate</h2>
            <div class="contact">
              <a class="btn primary" href="mailto:samsonchinthenga29@gmail.com">
                <span>✉️ samsonchinthenga29@gmail.com</span><span>→</span>
              </a>
              <a class="btn" target="_blank" href="https://www.linkedin.com/in/samson-chinthenga-5ab6aa321">
                <span>🔗 LinkedIn · Samson Chinthenga</span><span>→</span>
              </a>
              <a class="btn" target="_blank" href="https://github.com/samsonchinthenga">
                <span>🐙 GitHub · /samsonchinthenga</span><span>→</span>
              </a>
            </div>

            <p class="muted" style="margin:10px 0 0 0; font-size:.92rem;">
              Open for freelance, contract, or full‑time roles — mobile dev, backend engineer, or full‑stack web.
            </p>
          </div>
        </div>
      </div>

      <!-- FOOTER -->
      <div class="footer">
        <span style="color:var(--accent); font-weight:800;">“</span>
        Turning complex problems into elegant, user-centric solutions — one line of code at a time.
        <span style="color:var(--accent); font-weight:800;">”</span>
        <div style="margin-top:6px; font-size:.78rem;">
          Flutter · React Native · Node · Python · React — full-spectrum dev & redesign specialist
        </div>
      </div>

      <!-- hidden remark (kept) -->
      <div style="height: 0; opacity: 0; position: absolute; pointer-events: none;" aria-hidden="true">
        <!-- This README is optimized for GitHub preview: shows modern dev skills: mobile, backend, web, UI redesign -->
      </div>

    </div>
  </div>
</body>
</html>
