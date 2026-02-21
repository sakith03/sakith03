<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sakith Abeywickrama – Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=IBM+Plex+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050810;
    --surface: #0b1120;
    --surface2: #0f1a2e;
    --border: #1a2a45;
    --cyan: #00d4ff;
    --blue: #0066ff;
    --violet: #6c3bff;
    --green: #00ffaa;
    --orange: #ff6b2b;
    --text: #e8f0ff;
    --muted: #5a7a9e;
    --grid: rgba(0, 180, 255, 0.04);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'IBM Plex Mono', monospace;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(var(--grid) 1px, transparent 1px),
      linear-gradient(90deg, var(--grid) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  /* Ambient orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(120px);
    pointer-events: none;
    z-index: 0;
  }
  .orb1 { width: 600px; height: 600px; background: rgba(0,102,255,0.12); top: -200px; right: -100px; animation: drift1 12s ease-in-out infinite alternate; }
  .orb2 { width: 500px; height: 500px; background: rgba(0,212,255,0.08); bottom: 10%; left: -150px; animation: drift2 15s ease-in-out infinite alternate; }
  .orb3 { width: 350px; height: 350px; background: rgba(108,59,255,0.1); top: 40%; right: 20%; animation: drift3 10s ease-in-out infinite alternate; }

  @keyframes drift1 { from { transform: translate(0,0); } to { transform: translate(-60px, 80px); } }
  @keyframes drift2 { from { transform: translate(0,0); } to { transform: translate(80px,-60px); } }
  @keyframes drift3 { from { transform: translate(0,0); } to { transform: translate(-40px,40px); } }

  .container {
    position: relative;
    z-index: 1;
    max-width: 920px;
    margin: 0 auto;
    padding: 64px 32px;
  }

  /* ── HEADER ── */
  .header {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: start;
    gap: 32px;
    margin-bottom: 80px;
    animation: fadeUp 0.8s ease both;
  }

  .header-left {}

  .status-pill {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(0,255,170,0.08);
    border: 1px solid rgba(0,255,170,0.2);
    color: var(--green);
    font-size: 11px;
    font-family: 'IBM Plex Mono', monospace;
    padding: 5px 12px;
    border-radius: 20px;
    margin-bottom: 20px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }
  .status-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--green);
    animation: pulse-dot 2s infinite;
  }
  @keyframes pulse-dot {
    0%,100% { opacity: 1; box-shadow: 0 0 0 0 rgba(0,255,170,0.4); }
    50% { opacity: 0.7; box-shadow: 0 0 0 6px rgba(0,255,170,0); }
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: clamp(2.4rem, 5vw, 3.8rem);
    line-height: 1;
    letter-spacing: -0.02em;
    color: #fff;
    margin-bottom: 6px;
  }
  h1 .accent { 
    background: linear-gradient(135deg, var(--cyan), var(--blue));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .tagline {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    font-weight: 600;
    color: var(--muted);
    letter-spacing: 0.05em;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .header-meta {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
    font-size: 12px;
    color: var(--muted);
  }
  .meta-item {
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .meta-item svg { width:14px; height:14px; opacity:0.6; }

  .header-badge-col {
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding-top: 8px;
  }
  .badge-chip {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 8px 14px;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-align: center;
    transition: border-color 0.2s, color 0.2s;
    white-space: nowrap;
  }
  .badge-chip:hover { border-color: var(--cyan); color: var(--cyan); }

  /* ── SECTION HEADER ── */
  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 28px;
  }
  .section-label::before {
    content: '';
    display: block;
    width: 24px; height: 1px;
    background: var(--cyan);
  }

  section {
    margin-bottom: 72px;
    animation: fadeUp 0.8s ease both;
  }

  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }
  .about-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 22px;
    display: flex;
    align-items: flex-start;
    gap: 14px;
    transition: border-color 0.2s, background 0.2s;
  }
  .about-card:hover {
    border-color: rgba(0,212,255,0.3);
    background: var(--surface2);
  }
  .about-icon {
    font-size: 20px;
    line-height: 1;
    flex-shrink: 0;
    margin-top: 2px;
  }
  .about-card p {
    font-size: 13px;
    line-height: 1.6;
    color: #8aaed0;
  }
  .about-card strong {
    display: block;
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 13px;
    color: var(--text);
    margin-bottom: 3px;
  }

  /* ── ICON STRIP ── */
  .icon-strip {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 28px;
    padding: 20px 24px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
  }
  .icon-pill {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 7px;
    padding: 12px 14px;
    border-radius: 10px;
    background: rgba(255,255,255,0.03);
    border: 1px solid transparent;
    transition: all 0.2s ease;
    cursor: default;
    min-width: 62px;
  }
  .icon-pill:hover {
    background: rgba(0,212,255,0.07);
    border-color: rgba(0,212,255,0.22);
    transform: translateY(-3px);
  }
  .icon-pill img {
    width: 32px;
    height: 32px;
    object-fit: contain;
  }
  .icon-pill span {
    font-size: 9.5px;
    color: var(--muted);
    letter-spacing: 0.06em;
    text-align: center;
    line-height: 1.2;
    white-space: nowrap;
  }
  .icon-pill:hover span { color: var(--cyan); }

  /* ── SKILLS ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }
  .skill-group {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 22px;
    transition: border-color 0.2s;
  }
  .skill-group:hover { border-color: rgba(0,212,255,0.25); }
  .skill-group-title {
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--cyan);
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .skill-group-title span { font-size: 14px; }
  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 7px;
  }
  .tag {
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    color: #8aaed0;
    font-size: 11px;
    padding: 5px 11px 5px 8px;
    border-radius: 6px;
    letter-spacing: 0.04em;
    transition: all 0.2s;
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }
  .tag:hover { background: rgba(0,212,255,0.08); border-color: rgba(0,212,255,0.3); color: var(--cyan); }
  .tag:hover img { filter: brightness(1.4) saturate(1.2); }
  .tag img {
    width: 14px;
    height: 14px;
    object-fit: contain;
    flex-shrink: 0;
    transition: filter 0.2s;
  }

  /* Span 2 columns */
  .skill-group.wide { grid-column: span 2; }
  .skill-group.wide .skill-tags { flex-direction: row; }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
  }
  .project-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,212,255,0.04) 0%, transparent 60%);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .project-card:hover { border-color: rgba(0,212,255,0.35); transform: translateY(-3px); }
  .project-card:hover::before { opacity: 1; }

  .project-card.featured {
    grid-column: span 2;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 24px;
    align-items: start;
  }
  .project-card.featured::before {
    background: linear-gradient(135deg, rgba(108,59,255,0.06) 0%, transparent 60%);
  }
  .project-card.featured:hover { border-color: rgba(108,59,255,0.4); }

  .project-eyebrow {
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .project-eyebrow .dot { width:4px;height:4px;border-radius:50%;background:var(--violet); }
  .project-title {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 1.2rem;
    color: #fff;
    margin-bottom: 10px;
  }
  .project-title .emoji { margin-right: 8px; }
  .project-desc {
    font-size: 12.5px;
    line-height: 1.7;
    color: #6a8caf;
    margin-bottom: 18px;
  }
  .project-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 7px;
  }
  .stack-tag {
    background: rgba(0,102,255,0.1);
    border: 1px solid rgba(0,102,255,0.25);
    color: #6ea8ff;
    font-size: 10.5px;
    padding: 4px 9px 4px 7px;
    border-radius: 5px;
    letter-spacing: 0.05em;
    display: inline-flex;
    align-items: center;
    gap: 5px;
  }
  .stack-tag img {
    width: 13px; height: 13px;
    object-fit: contain;
    flex-shrink: 0;
  }
  .project-highlight-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 7px;
  }
  .project-highlight-list li {
    font-size: 12px;
    color: #5a7a9e;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .project-highlight-list li::before {
    content: '▸';
    color: var(--cyan);
    font-size: 10px;
    flex-shrink: 0;
  }

  /* ── ACHIEVEMENTS ── */
  .achievements-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }
  .achievement-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 22px 20px;
    text-align: center;
    transition: border-color 0.2s, transform 0.2s;
  }
  .achievement-card:hover { border-color: rgba(255,193,7,0.3); transform: translateY(-2px); }
  .ach-icon { font-size: 26px; margin-bottom: 10px; }
  .ach-title {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 13px;
    color: var(--text);
    margin-bottom: 4px;
  }
  .ach-sub { font-size: 11px; color: var(--muted); }

  /* ── FOCUS ── */
  .focus-list {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 14px;
  }
  .focus-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-left: 3px solid var(--cyan);
    border-radius: 0 10px 10px 0;
    padding: 16px 18px;
    font-family: 'Syne', sans-serif;
    font-weight: 600;
    font-size: 13px;
    color: var(--text);
    transition: background 0.2s;
  }
  .focus-item:nth-child(2) { border-left-color: var(--violet); }
  .focus-item:nth-child(3) { border-left-color: var(--blue); }
  .focus-item:nth-child(4) { border-left-color: var(--green); }
  .focus-item:hover { background: var(--surface2); }

  /* ── STATS BAR ── */
  .stats-bar {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 28px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 72px;
  }
  .stat-item { text-align: center; }
  .stat-value {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1.6rem;
    color: #fff;
    letter-spacing: -0.02em;
  }
  .stat-label { font-size: 10px; color: var(--muted); letter-spacing: 0.1em; text-transform: uppercase; margin-top: 2px; }
  .stat-divider { width: 1px; height: 40px; background: var(--border); }

  /* ── FOOTER ── */
  .footer {
    border-top: 1px solid var(--border);
    padding-top: 32px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 11px;
    color: var(--muted);
  }
  .footer-brand {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 14px;
    color: var(--text);
  }
  .views-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(0,212,255,0.07);
    border: 1px solid rgba(0,212,255,0.15);
    padding: 5px 12px;
    border-radius: 20px;
    color: var(--cyan);
    font-size: 11px;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }
  section:nth-child(1) { animation-delay: 0.1s; }
  section:nth-child(2) { animation-delay: 0.2s; }
  section:nth-child(3) { animation-delay: 0.3s; }
  section:nth-child(4) { animation-delay: 0.4s; }

  /* scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }

  @media (max-width: 700px) {
    .header { grid-template-columns: 1fr; }
    .about-grid, .skills-grid, .projects-grid, .achievements-row, .focus-list { grid-template-columns: 1fr; }
    .project-card.featured { grid-column: span 1; grid-template-columns: 1fr; }
    .skill-group.wide { grid-column: span 1; }
    .stats-bar { flex-wrap: wrap; gap: 20px; justify-content: center; }
  }
</style>
</head>
<body>
<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div class="header-left">
      <div class="status-pill">
        <span class="status-dot"></span>
        Available for collaboration
      </div>
      <h1>Sakith<br><span class="accent">Abeywickrama</span></h1>
      <p class="tagline">Computer Science Undergraduate · Full Stack Developer</p>
      <div class="header-meta">
        <span class="meta-item">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
          Maharagama, Sri Lanka 🇱🇰
        </span>
        <span class="meta-item">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
          Dean's List – SLIIT
        </span>
      </div>
    </div>
    <div class="header-badge-col">
      <div class="badge-chip">Spring Boot</div>
      <div class="badge-chip">ASP.NET Core</div>
      <div class="badge-chip">React · Next.js</div>
      <div class="badge-chip">Azure · AWS</div>
      <div class="badge-chip">OpenMP / HPC</div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-bar">
    <div class="stat-item">
      <div class="stat-value">6+</div>
      <div class="stat-label">Languages</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-item">
      <div class="stat-value">2</div>
      <div class="stat-label">Cloud Platforms</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-item">
      <div class="stat-value">4+</div>
      <div class="stat-label">Featured Projects</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-item">
      <div class="stat-value">Top 20</div>
      <div class="stat-label">IESL StartupSpark</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-item">
      <div class="stat-value">CI/CD</div>
      <div class="stat-label">Production Deploy</div>
    </div>
  </div>

  <!-- ABOUT -->
  <section>
    <div class="section-label">About Me</div>
    <div class="about-grid">
      <div class="about-card">
        <div class="about-icon">🔐</div>
        <div>
          <strong>Secure Backend Architecture</strong>
          <p>Building scalable authentication systems and hardened REST APIs with clean architecture principles.</p>
        </div>
      </div>
      <div class="about-card">
        <div class="about-icon">🧵</div>
        <div>
          <strong>Parallel Computing</strong>
          <p>OpenMP optimization, atomic sections, race condition resolution, and thread scalability benchmarking.</p>
        </div>
      </div>
      <div class="about-card">
        <div class="about-icon">☁️</div>
        <div>
          <strong>Cloud Deployment</strong>
          <p>Shipping real-world applications to Azure Web Apps and AWS EC2 with automated CI/CD pipelines.</p>
        </div>
      </div>
      <div class="about-card">
        <div class="about-icon">⚙️</div>
        <div>
          <strong>DevOps Enthusiast</strong>
          <p>Docker containers, GitHub Actions workflows, n8n automation — bringing engineering rigor to operations.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section>
    <div class="section-label">Technical Skills</div>

    <!-- ICON STRIP -->
    <div class="icon-strip">
      <!-- Languages -->
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg"><span>Java</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg"><span>C#</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg"><span>C</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg"><span>Python</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg"><span>JavaScript</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg"><span>TypeScript</span></div>
      <!-- Divider -->
      <div style="width:1px;background:var(--border);margin:4px 4px;border-radius:2px;"></div>
      <!-- Backend -->
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dotnetcore/dotnetcore-original.svg"><span>ASP.NET</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg"><span>Spring</span></div>
      <!-- Divider -->
      <div style="width:1px;background:var(--border);margin:4px 4px;border-radius:2px;"></div>
      <!-- Frontend -->
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg"><span>React</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original-wordmark.svg" style="filter:invert(0.7)"><span>Next.js</span></div>
      <!-- Divider -->
      <div style="width:1px;background:var(--border);margin:4px 4px;border-radius:2px;"></div>
      <!-- Databases -->
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg"><span>MySQL</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg"><span>PostgreSQL</span></div>
      <!-- Divider -->
      <div style="width:1px;background:var(--border);margin:4px 4px;border-radius:2px;"></div>
      <!-- Cloud / DevOps -->
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg"><span>Azure</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-original.svg" style="filter:brightness(0) invert(0.65)"><span>AWS</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg"><span>Docker</span></div>
      <div class="icon-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/githubactions/githubactions-original.svg"><span>Actions</span></div>
      <div class="icon-pill"><img src="https://cdn.simpleicons.org/n8n/FF6D5A"><span>n8n</span></div>
    </div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-title"><span>💻</span> Languages</div>
        <div class="skill-tags">
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="">Java</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg" alt="">C#</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="">C</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="">Python</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="">JavaScript</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" alt="">TypeScript</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title"><span>⚙️</span> Backend</div>
        <div class="skill-tags">
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dotnetcore/dotnetcore-original.svg" alt="">ASP.NET Core</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg" alt="">Spring Boot</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/fastapi/fastapi-original.svg" alt="">REST APIs</span>
          <span class="tag">🔐 Auth &amp; AuthZ</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title"><span>🎨</span> Frontend</div>
        <div class="skill-tags">
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="">React</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" alt="" style="filter:invert(1) brightness(0.7)">Next.js</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" alt="">TypeScript</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/axios/axios-plain.svg" alt="">Axios</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title"><span>🗄</span> Databases</div>
        <div class="skill-tags">
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="">MySQL</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" alt="">PostgreSQL</span>
          <span class="tag">📐 Data Modeling</span>
          <span class="tag">⚡ Query Optimization</span>
        </div>
      </div>
      <div class="skill-group wide">
        <div class="skill-group-title"><span>☁️</span> Cloud · DevOps · HPC</div>
        <div class="skill-tags">
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg" alt="">Azure Web Apps</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-plain-wordmark.svg" alt="" style="filter:brightness(0) invert(0.6)">AWS EC2</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" alt="">Docker</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/githubactions/githubactions-original.svg" alt="">GitHub Actions</span>
          <span class="tag">🔄 CI/CD Pipelines</span>
          <span class="tag"><img src="https://cdn.simpleicons.org/n8n/FF6D5A" alt="">n8n Automation</span>
          <span class="tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="">OpenMP</span>
          <span class="tag">⚛️ Atomic / Critical</span>
          <span class="tag">📊 Perf Benchmarking</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section>
    <div class="section-label">Featured Projects</div>
    <div class="projects-grid">

      <!-- Vocalyx (featured) -->
      <div class="project-card featured">
        <div>
          <div class="project-eyebrow"><span class="dot"></span> AI · Voice · Cloud</div>
          <div class="project-title"><span class="emoji">🎙️</span>Vocalyx</div>
          <p class="project-desc">AI-powered communication platform enabling intelligent voice-driven interaction and smart workflow automation. Built with secure auth, scalable API design, and clean React frontend integration.</p>
          <div class="project-stack">
            <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg">Spring Boot</span>
            <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg">React</span>
            <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg">MySQL</span>
            <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg">Azure</span>
            <span class="stack-tag"><img src="https://cdn.simpleicons.org/n8n/FF6D5A">n8n</span>
          </div>
        </div>
        <ul class="project-highlight-list">
          <li>Secure authentication system</li>
          <li>Scalable API design</li>
          <li>AI integration layer</li>
          <li>Cloud deployment ready</li>
          <li>n8n workflow automation</li>
        </ul>
      </div>

      <!-- IFAS -->
      <div class="project-card">
        <div class="project-eyebrow"><span class="dot" style="background:var(--green)"></span> Sustainability · FinTech</div>
        <div class="project-title"><span class="emoji">🌱</span>IFAS</div>
        <p class="project-desc">Intelligent Feasibility & Sustainability Assessment System. Evaluates new business ideas across operational, financial, and sustainability dimensions.</p>
        <div class="project-stack">
          <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dotnetcore/dotnetcore-original.svg">ASP.NET Core</span>
          <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" style="filter:invert(1) brightness(0.7)">Next.js</span>
          <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg">PostgreSQL</span>
          <span class="stack-tag">🔄 CI/CD</span>
        </div>
      </div>

      <!-- AlertEYE -->
      <div class="project-card">
        <div class="project-eyebrow"><span class="dot" style="background:var(--orange)"></span> Safety · Mobile · CV</div>
        <div class="project-title"><span class="emoji">👓</span>AlertEYE</div>
        <p class="project-desc">Driver drowsiness detection prototype with real-time fatigue monitoring, Android reward integration. Presented at Idea Spark Exhibition.</p>
        <div class="project-stack">
          <span class="stack-tag">👁️ Computer Vision</span>
          <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/android/android-original.svg">Android</span>
          <span class="stack-tag">🛡️ Safety Systems</span>
        </div>
      </div>

      <!-- Parallel Pi -->
      <div class="project-card">
        <div class="project-eyebrow"><span class="dot" style="background:var(--cyan)"></span> HPC · Systems</div>
        <div class="project-title"><span class="emoji">🧵</span>Parallel π Estimation</div>
        <p class="project-desc">Fixed race conditions using atomic and critical sections. Benchmarked thread scalability on AWS EC2 (1 Core / 2 vCPU) with performance analysis.</p>
        <div class="project-stack">
          <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg">C</span>
          <span class="stack-tag">🧵 OpenMP</span>
          <span class="stack-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-plain-wordmark.svg" style="filter:brightness(0) invert(0.6)">AWS EC2</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ACHIEVEMENTS -->
  <section>
    <div class="section-label">Achievements</div>
    <div class="achievements-row">
      <div class="achievement-card">
        <div class="ach-icon">🎓</div>
        <div class="ach-title">Dean's List</div>
        <div class="ach-sub">SLIIT</div>
      </div>
      <div class="achievement-card">
        <div class="ach-icon">🚀</div>
        <div class="ach-title">Top 20 Finalist</div>
        <div class="ach-sub">IESL Moratuwa StartupSpark</div>
      </div>
      <div class="achievement-card">
        <div class="ach-icon">💡</div>
        <div class="ach-title">Hackathon Finalist</div>
        <div class="ach-sub">MSCLub Minihackathon</div>
      </div>
    </div>
  </section>

  <!-- CURRENT FOCUS -->
  <section>
    <div class="section-label">Current Focus</div>
    <div class="focus-list">
      <div class="focus-item">Scalable Authentication Architectures</div>
      <div class="focus-item">Advanced Backend System Design</div>
      <div class="focus-item">High Performance Computing</div>
      <div class="focus-item">Cloud-Native Applications</div>
    </div>
  </section>

  <!-- FOOTER -->
  <div class="footer">
    <span class="footer-brand">sakith03</span>
    <span style="color: var(--muted); font-size:11px;">Building real-world systems · Sri Lanka</span>
    <span class="views-badge">
      <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/><circle cx="12" cy="12" r="3"/></svg>
      Profile Views
    </span>
  </div>

</div>
</body>
</html>
