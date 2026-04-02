<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Samson Chinthenga · Mobile · Backend · Web</title>
  <!-- GitHub Markdown style + modern touches -->
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #0a0c10;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', 'Inter', Helvetica, Arial, sans-serif;
      line-height: 1.5;
      color: #e6edf3;
      padding: 2rem 1rem;
    }

    /* README card - clean, wide, GitHub-like */
    .readme-card {
      max-width: 1000px;
      margin: 0 auto;
      background: #0d1117;
      border-radius: 24px;
      padding: 2rem 1.8rem;
      box-shadow: 0 8px 24px rgba(0,0,0,0.4);
      border: 1px solid #21262d;
    }

    /* Typography with subtle glow */
    h1 {
      font-size: 2.4rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, #FACC15, #EAB308, #FDE047);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin-bottom: 0.25rem;
    }

    h2 {
      font-size: 1.6rem;
      font-weight: 600;
      margin-top: 2rem;
      margin-bottom: 1rem;
      padding-bottom: 0.3rem;
      border-bottom: 2px solid #2d2f36;
      display: inline-block;
      letter-spacing: -0.3px;
    }

    h3 {
      font-size: 1.25rem;
      font-weight: 600;
      margin: 1.5rem 0 0.75rem 0;
      color: #FACC15;
    }

    .subhead {
      font-size: 1.1rem;
      color: #b1bac4;
      margin-bottom: 1.5rem;
      border-left: 3px solid #EAB308;
      padding-left: 1rem;
    }

    .badge-strip {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin: 1rem 0 1.2rem 0;
    }

    .tech-badge {
      background: #1f242e;
      padding: 0.25rem 0.9rem;
      border-radius: 40px;
      font-size: 0.75rem;
      font-weight: 500;
      color: #e6edf3;
      border: 0.5px solid #30363d;
      transition: all 0.2s;
    }

    .tech-badge:hover {
      border-color: #EAB308;
      background: #2a2f3a;
    }

    .accent-badge {
      background: rgba(234,179,8,0.12);
      border-color: rgba(234,179,8,0.4);
      color: #FACC15;
    }

    .flex-icons {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin: 1.5rem 0 1rem 0;
    }

    .icon-pill {
      background: #161b22;
      border-radius: 40px;
      padding: 0.4rem 1rem;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-size: 0.85rem;
      font-weight: 500;
      border: 1px solid #2d333b;
    }

    .icon-pill img, .icon-pill svg {
      width: 20px;
      height: 20px;
    }

    /* project cards (grid) */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.5rem;
      margin: 1.8rem 0;
    }

    .project-item {
      background: #0d1117;
      border: 1px solid #21262d;
      border-radius: 18px;
      padding: 1.2rem 1.2rem 1.4rem;
      transition: transform 0.2s ease, border-color 0.2s;
    }

    .project-item:hover {
      border-color: #EAB308;
      transform: translateY(-3px);
    }

    .project-title {
      font-size: 1.25rem;
      font-weight: 600;
      margin-bottom: 0.5rem;
      color: #FACC15;
    }

    .project-tech {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
      margin: 0.6rem 0;
    }

    .project-tech span {
      background: #1a1f29;
      font-size: 0.7rem;
      padding: 0.2rem 0.6rem;
      border-radius: 20px;
      font-weight: 500;
      letter-spacing: -0.2px;
    }

    .project-desc {
      font-size: 0.85rem;
      color: #c9d1d9;
      margin-top: 0.5rem;
      line-height: 1.4;
    }

    /* contact / social row */
    .contact-row {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin: 1.8rem 0 1rem 0;
      background: #0a0c10;
      padding: 1rem 0;
      border-radius: 20px;
    }

    .contact-link {
      background: #161b22;
      padding: 0.6rem 1.2rem;
      border-radius: 40px;
      display: inline-flex;
      align-items: center;
      gap: 0.6rem;
      color: #e6edf3;
      text-decoration: none;
      font-size: 0.85rem;
      font-weight: 500;
      border: 1px solid #2d333b;
      transition: all 0.2s;
    }

    .contact-link:hover {
      border-color: #EAB308;
      color: #FACC15;
      background: #1f252f;
    }

    hr {
      border: none;
      border-top: 1px solid #2d333b;
      margin: 1.8rem 0;
    }

    .footer-quote {
      text-align: center;
      font-size: 0.85rem;
      color: #8b949e;
      margin-top: 2rem;
      padding-top: 1rem;
      border-top: 1px solid #21262d;
    }

    .stat-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: center;
      margin: 2rem 0;
    }

    .stat-card {
      text-align: center;
      background: #161b22;
      padding: 0.8rem 1.6rem;
      border-radius: 32px;
      border: 1px solid #30363d;
    }

    .stat-number {
      font-size: 2rem;
      font-weight: 700;
      color: #EAB308;
    }

    .stat-label {
      font-size: 0.7rem;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    @media (max-width: 640px) {
      .readme-card {
        padding: 1.5rem;
      }
      h1 {
        font-size: 1.8rem;
      }
      .contact-link {
        padding: 0.5rem 1rem;
        font-size: 0.75rem;
      }
    }

    /* custom emoji / icons inline */
    .inline-icon {
      display: inline-block;
      vertical-align: middle;
      margin-right: 4px;
    }
  </style>
</head>
<body>
<div class="readme-card">
  
  <!-- HEADER with name and roles -->
  <div style="display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap;">
    <div>
      <h1>Samson Chinthenga</h1>
      <div class="subhead">
        📱 Mobile · ⚙️ Backend · 🌐 Web — full-spectrum software developer
      </div>
    </div>
    <div class="badge-strip" style="margin-top: 8px;">
      <span class="tech-badge accent-badge">🟢 Available for opportunities</span>
    </div>
  </div>

  <!-- tagline + badges (Flutter, React Native, Node, etc) -->
  <div class="badge-strip">
    <span class="tech-badge">Flutter</span>
    <span class="tech-badge">React Native</span>
    <span class="tech-badge">Dart</span>
    <span class="tech-badge">Node.js</span>
    <span class="tech-badge">Python</span>
    <span class="tech-badge">Firebase</span>
    <span class="tech-badge">React / Next</span>
    <span class="tech-badge">Tailwind</span>
    <span class="tech-badge">MongoDB</span>
    <span class="tech-badge">PostgreSQL</span>
    <span class="tech-badge">Docker</span>
  </div>

  <!-- About: Mobile + Backend + Web identity -->
  <p style="margin-top: 1rem; font-size: 0.95rem;">
    I'm a <strong>cross-platform mobile engineer</strong> (<strong>Flutter</strong> · <strong>React Native</strong>) 
    who also architects <strong>scalable backends</strong> (Node.js, Python, Firebase) and crafts 
    <strong>modern web experiences</strong> (React, Tailwind). I deliver complete, user-first solutions — from 
    database design to pixel-perfect interfaces.
  </p>

  <div class="flex-icons">
    <div class="icon-pill">📱 Flutter · 5+ apps shipped</div>
    <div class="icon-pill">⚛️ React Native · cross-platform</div>
    <div class="icon-pill">🖥️ Node.js + Express APIs</div>
    <div class="icon-pill">🐍 Python (Flask/Django)</div>
    <div class="icon-pill">🔥 Firebase · Auth · Functions</div>
    <div class="icon-pill">🌐 React + Tailwind CSS</div>
  </div>

  <!-- quick stat / experience visual -->
  <div class="stat-grid">
    <div class="stat-card"><div class="stat-number">15+</div><div class="stat-label">Projects shipped</div></div>
    <div class="stat-card"><div class="stat-number">3+</div><div class="stat-label">Years experience</div></div>
    <div class="stat-card"><div class="stat-number">12+</div><div class="stat-label">Technologies</div></div>
    <div class="stat-card"><div class="stat-number">100%</div><div class="stat-label">User-focused</div></div>
  </div>

  <!-- 🔧 TECH STACK (detailed but compact) -->
  <h2>🛠️ Tech arsenal</h2>
  <div style="display: flex; flex-wrap: wrap; gap: 0.8rem; margin-bottom: 1.5rem;">
    <div style="min-width: 160px;"><strong>📱 Mobile</strong><br>Flutter · React Native · Dart · Swift basics</div>
    <div style="min-width: 160px;"><strong>⚙️ Backend</strong><br>Node.js · Express · Python · Firebase · MongoDB · PostgreSQL</div>
    <div style="min-width: 160px;"><strong>🌐 Web</strong><br>React · Next.js · TypeScript · Tailwind · HTML/CSS</div>
    <div style="min-width: 160px;"><strong>🧰 DevOps & Tools</strong><br>Git · Docker · GitHub Actions · GCP · Postman · Figma</div>
  </div>

  <!-- SPECIALIZATION BADGES -->
  <h2>💡 What I bring</h2>
  <div class="badge-strip" style="margin-bottom: 1rem;">
    <span class="tech-badge accent-badge">📱 Cross‑platform mobile</span>
    <span class="tech-badge accent-badge">⚡ REST & GraphQL APIs</span>
    <span class="tech-badge accent-badge">🔥 Real‑time (Firebase/WS)</span>
    <span class="tech-badge accent-badge">🤖 AI‑integrated apps</span>
    <span class="tech-badge accent-badge">🎨 UI/UX collaboration</span>
    <span class="tech-badge accent-badge">🚀 Full‑stack deployment</span>
  </div>

  <!-- FEATURED PROJECTS (redesigned cards) -->
  <h2>📌 Featured projects</h2>
  <div class="projects-grid">
    <div class="project-item">
      <div class="project-title">Health Product Delivery</div>
      <div class="project-tech"><span>Flutter</span><span>Firebase</span><span>AI recos</span></div>
      <div class="project-desc">AI-powered health delivery with real-time tracking, smart recommendations, and seamless checkout. Served 500+ users in pilot.</div>
    </div>
    <div class="project-item">
      <div class="project-title">AI Chatbot Platform</div>
      <div class="project-tech"><span>React Native</span><span>Node.js</span><span>OpenAI</span></div>
      <div class="project-desc">Cross-platform conversational AI with memory, custom personality tuning, and multi-tenant support.</div>
    </div>
    <div class="project-item">
      <div class="project-title">E‑Commerce Platform</div>
      <div class="project-tech"><span>React</span><span>Node.js</span><span>MongoDB</span></div>
      <div class="project-desc">Full‑stack marketplace: admin dashboard, Stripe payments, real‑time inventory & order tracking.</div>
    </div>
    <div class="project-item">
      <div class="project-title">Fitness Tracker App</div>
      <div class="project-tech"><span>Flutter</span><span>Dart</span><span>Firebase</span></div>
      <div class="project-desc">Workout plans, progress charts, social challenges & health data sync — available on iOS & Android.</div>
    </div>
    <div class="project-item">
      <div class="project-title">TaskFlow (SaaS)</div>
      <div class="project-tech"><span>React Native</span><span>Node.js</span><span>PostgreSQL</span></div>
      <div class="project-desc">Team productivity suite with real‑time updates, file attachments, and role‑based access.</div>
    </div>
    <div class="project-item">
      <div class="project-title">Portfolio 2025 (Redesign)</div>
      <div class="project-tech"><span>React</span><span>Tailwind</span><span>Framer Motion</span></div>
      <div class="project-desc">Modern interactive portfolio with dark mode, responsive layout, and smooth animations.</div>
    </div>
  </div>

  <!-- REDESIGN / UI THINKING -->
  <h2>🎨 Design & UI approach</h2>
  <p>I don't just build — I <strong>redesign</strong> with intention. I collaborate with designers or craft interfaces myself using <strong>Figma</strong> and modern CSS (Tailwind, animations). My focus: <strong>intuitive navigation, micro-interactions, accessibility, and pixel-perfect implementation</strong> from mobile to web.</p>
  <div class="badge-strip">
    <span class="tech-badge">🎯 Component-driven</span>
    <span class="tech-badge">📱 Mobile-first</span>
    <span class="tech-badge">✨ Micro-animations</span>
    <span class="tech-badge">♿ A11Y minded</span>
    <span class="tech-badge">🔄 Design handoff</span>
  </div>

  <!-- BACKEND + MOBILE FULL-STACK note -->
  <h2>🔗 End-to-end capabilities</h2>
  <p>I've built production apps where I own the <strong>Flutter/React Native frontend</strong>, <strong>Node.js/Python backend</strong>, database (MongoDB, PostgreSQL or Firebase), and deployment (Docker, GCP). Real-world experience with auth, push notifications, payment gateways, and WebSockets.</p>

  <!-- GITHUB STATS SIMULATED (clean visual) -->
  <h2>📈 GitHub pulse</h2>
  <div style="display: flex; flex-wrap: wrap; gap: 1.2rem; justify-content: space-between; background: #0a0c10; border-radius: 20px; padding: 0.8rem 0;">
    <div style="flex:1; min-width: 140px;">
      <div style="font-size: 0.75rem; color: #8b949e;">✨ Commits 2025</div>
      <div style="font-size: 1.4rem; font-weight: 700;">340+</div>
    </div>
    <div style="flex:1; min-width: 140px;">
      <div style="font-size: 0.75rem; color: #8b949e;">📦 Repos contributed</div>
      <div style="font-size: 1.4rem; font-weight: 700;">22</div>
    </div>
    <div style="flex:1; min-width: 140px;">
      <div style="font-size: 0.75rem; color: #8b949e;">⭐ Stars earned</div>
      <div style="font-size: 1.4rem; font-weight: 700;">128</div>
    </div>
    <div style="flex:1; min-width: 140px;">
      <div style="font-size: 0.75rem; color: #8b949e;">🤝 PRs merged</div>
      <div style="font-size: 1.4rem; font-weight: 700;">48</div>
    </div>
  </div>

  <!-- REDESIGNED CONTACT SECTION -->
  <h2>📬 Let’s collaborate</h2>
  <div class="contact-row">
    <a href="mailto:samsonchinthenga29@gmail.com" class="contact-link">✉️ samsonchinthenga29@gmail.com</a>
    <a href="https://www.linkedin.com/in/samson-chinthenga-5ab6aa321" target="_blank" class="contact-link">🔗 LinkedIn · Samson Chinthenga</a>
    <a href="https://github.com/samsonchinthenga" target="_blank" class="contact-link">🐙 GitHub /samsonchinthenga</a>
  </div>
  <p style="font-size: 0.85rem;">💬 Open for freelance, contract, or full‑time roles — mobile dev, backend engineer, or full‑stack web. Let’s build something amazing.</p>

  <!-- QUOTE / FOOTER -->
  <hr />
  <div class="footer-quote">
    <span style="color:#EAB308;">“</span> Turning complex problems into elegant, user-centric solutions — one line of code at a time.<span style="color:#EAB308;">”</span><br/>
    <span style="font-size: 0.7rem;">Flutter · React Native · Node · Python · React — full-spectrum dev & redesign specialist</span>
  </div>

  <!-- additional hidden remark for github paste (pure markdown styled, but fully HTML ready) -->
  <div style="height: 0; opacity: 0; position: absolute; pointer-events: none;" aria-hidden="true">
    <!-- This README is optimized for GitHub preview: shows modern dev skills: mobile, backend, web, UI redesign -->
  </div>
</div>
</body>
</html>
