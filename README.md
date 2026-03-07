<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Omar Al-Turk — Software Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;600;700;800&family=Noto+Sans+Arabic:wght@400;600;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080b12;
    --surface: #0e1422;
    --surface2: #141926;
    --border: #1e2740;
    --accent: #4f8eff;
    --accent2: #7c5dfa;
    --accent3: #00e5a0;
    --gold: #f0c060;
    --text: #c9d1e8;
    --muted: #5a6480;
    --white: #edf2ff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Syne', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(79,142,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(79,142,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: center;
    margin-bottom: 80px;
    padding-bottom: 60px;
    border-bottom: 1px solid var(--border);
    position: relative;
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: -1px;
    left: 0;
    width: 120px;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), transparent);
  }

  .hero-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .hero-label::before {
    content: '';
    display: block;
    width: 24px;
    height: 1px;
    background: var(--accent);
  }

  h1 {
    font-size: clamp(36px, 6vw, 64px);
    font-weight: 800;
    line-height: 1.05;
    color: var(--white);
    letter-spacing: -1px;
    margin-bottom: 20px;
  }

  h1 span {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-bio {
    font-size: 15px;
    line-height: 1.7;
    color: var(--muted);
    max-width: 540px;
    margin-bottom: 28px;
  }

  .hero-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    padding: 5px 12px;
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--muted);
    background: var(--surface);
    letter-spacing: 0.5px;
    transition: all 0.2s;
  }

  .tag:hover { border-color: var(--accent); color: var(--accent); }
  .tag.active { border-color: var(--accent2); color: var(--accent2); background: rgba(124,93,250,0.08); }

  .hero-avatar {
    width: 110px;
    height: 110px;
    border-radius: 16px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 48px;
    flex-shrink: 0;
    position: relative;
    box-shadow: 0 0 0 1px var(--border), 0 20px 60px rgba(79,142,255,0.15);
  }

  .hero-avatar::after {
    content: '';
    position: absolute;
    inset: -1px;
    border-radius: 17px;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3));
    z-index: -1;
    opacity: 0.4;
    filter: blur(8px);
  }

  /* ── SECTION HEADER ── */
  .section-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 32px;
  }

  .section-header h2 {
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    font-family: 'Space Mono', monospace;
  }

  .section-header::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── LANGUAGES GRID ── */
  .section { margin-bottom: 72px; }

  .lang-category {
    margin-bottom: 32px;
  }

  .lang-category-title {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .lang-category-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
    opacity: 0.5;
  }

  .langs-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .lang-chip {
    display: flex;
    align-items: center;
    gap: 7px;
    padding: 7px 13px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
    transition: all 0.2s ease;
    cursor: default;
    font-family: 'Space Mono', monospace;
    letter-spacing: 0.3px;
  }

  .lang-chip:hover {
    border-color: var(--accent);
    color: var(--white);
    background: var(--surface2);
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(79,142,255,0.12);
  }

  .lang-chip .dot {
    width: 7px;
    height: 7px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    transition: all 0.25s ease;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s ease;
  }

  .project-card:hover::before { transform: scaleX(1); }
  .project-card:hover {
    border-color: rgba(79,142,255,0.3);
    box-shadow: 0 12px 40px rgba(0,0,0,0.3);
    transform: translateY(-3px);
  }

  .project-icon {
    font-size: 28px;
    margin-bottom: 14px;
  }

  .project-name {
    font-size: 15px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 8px;
  }

  .project-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 14px;
  }

  .project-tech {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tech-badge {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    padding: 3px 8px;
    background: rgba(79,142,255,0.08);
    border: 1px solid rgba(79,142,255,0.2);
    border-radius: 4px;
    color: var(--accent);
    letter-spacing: 0.5px;
  }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 24px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px 16px;
    text-align: center;
    transition: all 0.2s;
  }

  .stat-card:hover {
    border-color: rgba(79,142,255,0.3);
    transform: translateY(-2px);
  }

  .stat-value {
    font-size: 24px;
    font-weight: 800;
    color: var(--white);
    margin-bottom: 4px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .stat-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* ── PHILOSOPHY ── */
  .principles {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .principle {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 20px;
    display: flex;
    align-items: flex-start;
    gap: 12px;
    transition: border-color 0.2s;
  }

  .principle:hover { border-color: rgba(0,229,160,0.3); }

  .principle-icon { font-size: 20px; flex-shrink: 0; margin-top: 1px; }

  .principle-title {
    font-size: 13px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 4px;
  }

  .principle-text {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.5;
  }

  /* ── QUOTE ── */
  .quote-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 36px 40px;
    text-align: center;
    position: relative;
    overflow: hidden;
    margin-bottom: 72px;
  }

  .quote-block::before {
    content: '"';
    position: absolute;
    top: -20px;
    left: 20px;
    font-size: 180px;
    color: rgba(79,142,255,0.05);
    font-family: Georgia, serif;
    line-height: 1;
    pointer-events: none;
  }

  .quote-arabic {
    font-family: 'Noto Sans Arabic', sans-serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--gold);
    direction: rtl;
    margin-bottom: 20px;
    line-height: 1.8;
  }

  .quote-arabic .line {
    display: block;
    font-size: 14px;
    font-weight: 400;
    color: var(--muted);
    margin-top: 6px;
  }

  .quote-divider {
    width: 60px;
    height: 1px;
    background: var(--border);
    margin: 20px auto;
  }

  .quote-credit {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 2px;
  }

  /* ── CONNECT ── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
  }

  .connect-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 14px;
    text-align: center;
    text-decoration: none;
    color: var(--text);
    transition: all 0.2s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
  }

  .connect-card:hover {
    border-color: rgba(79,142,255,0.4);
    transform: translateY(-3px);
    box-shadow: 0 12px 30px rgba(0,0,0,0.3);
    color: var(--white);
  }

  .connect-card .icon { font-size: 22px; }
  .connect-card .label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--muted);
  }
  .connect-card:hover .label { color: var(--accent); }

  /* ── FOOTER ── */
  .footer {
    margin-top: 80px;
    padding-top: 32px;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .footer-text {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.5px;
  }

  .footer-flag { font-size: 18px; }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero { animation: fadeUp 0.6s ease both; }
  .section { animation: fadeUp 0.6s ease both; }
  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 640px) {
    .hero { grid-template-columns: 1fr; }
    .hero-avatar { display: none; }
    .projects-grid { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: repeat(2, 1fr); }
    .connect-grid { grid-template-columns: repeat(2, 1fr); }
    .principles { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <header class="hero">
    <div>
      <div class="hero-label">Software Engineering Student</div>
      <h1>Omar<br/><span>Al-Turk</span></h1>
      <p class="hero-bio">
        Full-Stack & AI Developer based in Jordan. Passionate about turning complex ideas into elegant, purposeful code. Competitive programmer and open-source enthusiast.
      </p>
      <div class="hero-tags">
        <span class="tag active">Full-Stack</span>
        <span class="tag active">AI / ML</span>
        <span class="tag active">Competitive Programming</span>
        <span class="tag">📍 Jordan</span>
        <span class="tag">🟢 Open to internships</span>
      </div>
    </div>
    <div class="hero-avatar">👨‍💻</div>
  </header>

  <!-- LANGUAGES & TECHNOLOGIES -->
  <section class="section">
    <div class="section-header"><h2>// Languages & Tech</h2></div>

    <div class="lang-category">
      <div class="lang-category-title">Core Languages</div>
      <div class="langs-grid">
        <div class="lang-chip"><span class="dot" style="background:#3776AB"></span>Python</div>
        <div class="lang-chip"><span class="dot" style="background:#00599C"></span>C++</div>
        <div class="lang-chip"><span class="dot" style="background:#ED8B00"></span>Java</div>
        <div class="lang-chip"><span class="dot" style="background:#F7DF1E"></span>JavaScript</div>
        <div class="lang-chip"><span class="dot" style="background:#007ACC"></span>TypeScript</div>
        <div class="lang-chip"><span class="dot" style="background:#239120"></span>C#</div>
        <div class="lang-chip"><span class="dot" style="background:#00ADD8"></span>Go</div>
        <div class="lang-chip"><span class="dot" style="background:#CE422B"></span>Rust</div>
        <div class="lang-chip"><span class="dot" style="background:#7F52FF"></span>Kotlin</div>
        <div class="lang-chip"><span class="dot" style="background:#FA7343"></span>Swift</div>
        <div class="lang-chip"><span class="dot" style="background:#0175C2"></span>Dart</div>
        <div class="lang-chip"><span class="dot" style="background:#276DC3"></span>R</div>
        <div class="lang-chip"><span class="dot" style="background:#777BB4"></span>PHP</div>
      </div>
    </div>

    <div class="lang-category">
      <div class="lang-category-title">Web & Mobile</div>
      <div class="langs-grid">
        <div class="lang-chip"><span class="dot" style="background:#E34F26"></span>HTML5</div>
        <div class="lang-chip"><span class="dot" style="background:#1572B6"></span>CSS3</div>
        <div class="lang-chip"><span class="dot" style="background:#61DAFB"></span>React</div>
        <div class="lang-chip"><span class="dot" style="background:#000000"></span>Next.js</div>
        <div class="lang-chip"><span class="dot" style="background:#4FC08D"></span>Vue.js</div>
        <div class="lang-chip"><span class="dot" style="background:#DD0031"></span>Angular</div>
        <div class="lang-chip"><span class="dot" style="background:#339933"></span>Node.js</div>
        <div class="lang-chip"><span class="dot" style="background:#000000"></span>Express</div>
        <div class="lang-chip"><span class="dot" style="background:#02569B"></span>Flutter</div>
        <div class="lang-chip"><span class="dot" style="background:#61DAFB"></span>React Native</div>
        <div class="lang-chip"><span class="dot" style="background:#E10098"></span>GraphQL</div>
      </div>
    </div>

    <div class="lang-category">
      <div class="lang-category-title">Databases</div>
      <div class="langs-grid">
        <div class="lang-chip"><span class="dot" style="background:#316192"></span>PostgreSQL</div>
        <div class="lang-chip"><span class="dot" style="background:#4479A1"></span>MySQL</div>
        <div class="lang-chip"><span class="dot" style="background:#47A248"></span>MongoDB</div>
        <div class="lang-chip"><span class="dot" style="background:#DC382D"></span>Redis</div>
        <div class="lang-chip"><span class="dot" style="background:#003B57"></span>SQLite</div>
        <div class="lang-chip"><span class="dot" style="background:#FFCA28"></span>Firebase</div>
      </div>
    </div>

    <div class="lang-category">
      <div class="lang-category-title">AI / ML & Data Science</div>
      <div class="langs-grid">
        <div class="lang-chip"><span class="dot" style="background:#FF6F00"></span>TensorFlow</div>
        <div class="lang-chip"><span class="dot" style="background:#EE4C2C"></span>PyTorch</div>
        <div class="lang-chip"><span class="dot" style="background:#5C3EE8"></span>OpenCV</div>
        <div class="lang-chip"><span class="dot" style="background:#F7931E"></span>Scikit-learn</div>
        <div class="lang-chip"><span class="dot" style="background:#4DABCF"></span>NumPy</div>
        <div class="lang-chip"><span class="dot" style="background:#150458"></span>Pandas</div>
        <div class="lang-chip"><span class="dot" style="background:#11557C"></span>Matplotlib</div>
      </div>
    </div>

    <div class="lang-category">
      <div class="lang-category-title">DevOps & Tools</div>
      <div class="langs-grid">
        <div class="lang-chip"><span class="dot" style="background:#F05032"></span>Git</div>
        <div class="lang-chip"><span class="dot" style="background:#181717"></span>GitHub</div>
        <div class="lang-chip"><span class="dot" style="background:#FC6D26"></span>GitLab</div>
        <div class="lang-chip"><span class="dot" style="background:#2496ED"></span>Docker</div>
        <div class="lang-chip"><span class="dot" style="background:#326CE5"></span>Kubernetes</div>
        <div class="lang-chip"><span class="dot" style="background:#FCC624"></span>Linux</div>
        <div class="lang-chip"><span class="dot" style="background:#4EAA25"></span>Bash</div>
        <div class="lang-chip"><span class="dot" style="background:#FF6C37"></span>Postman</div>
        <div class="lang-chip"><span class="dot" style="background:#000000"></span>Vercel</div>
      </div>
    </div>

    <div class="lang-category">
      <div class="lang-category-title">Concepts & Methodologies</div>
      <div class="langs-grid">
        <div class="lang-chip"><span class="dot" style="background:#4f8eff"></span>OOP</div>
        <div class="lang-chip"><span class="dot" style="background:#7c5dfa"></span>DSA</div>
        <div class="lang-chip"><span class="dot" style="background:#00e5a0"></span>REST API</div>
        <div class="lang-chip"><span class="dot" style="background:#f0c060"></span>TDD</div>
        <div class="lang-chip"><span class="dot" style="background:#4f8eff"></span>Agile</div>
        <div class="lang-chip"><span class="dot" style="background:#7c5dfa"></span>CI/CD</div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="section">
    <div class="section-header"><h2>// Featured Projects</h2></div>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-icon">🛒</div>
        <div class="project-name">Store Management System</div>
        <div class="project-desc">Console-based inventory management demonstrating solid OOP principles with JSON persistence and sales reporting.</div>
        <div class="project-tech">
          <span class="tech-badge">Python</span>
          <span class="tech-badge">OOP</span>
          <span class="tech-badge">JSON</span>
          <span class="tech-badge">DSA</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">🤖</div>
        <div class="project-name">AI Image Recognition Bot</div>
        <div class="project-desc">Real-time object detection and classification using deep learning with TensorFlow and OpenCV pipeline.</div>
        <div class="project-tech">
          <span class="tech-badge">Python</span>
          <span class="tech-badge">TensorFlow</span>
          <span class="tech-badge">OpenCV</span>
          <span class="tech-badge">NumPy</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">⚡</div>
        <div class="project-name">Competitive Programming Solver</div>
        <div class="project-desc">Automated problem analyzer with dynamic programming optimization, test-case generation, and progress tracking.</div>
        <div class="project-tech">
          <span class="tech-badge">C++</span>
          <span class="tech-badge">Python</span>
          <span class="tech-badge">Algorithms</span>
          <span class="tech-badge">Bash</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">📋</div>
        <div class="project-name">Full-Stack Task Manager</div>
        <div class="project-desc">Modern productivity app with JWT auth, PostgreSQL relational design, and responsive React frontend.</div>
        <div class="project-tech">
          <span class="tech-badge">React</span>
          <span class="tech-badge">Node.js</span>
          <span class="tech-badge">PostgreSQL</span>
          <span class="tech-badge">JWT</span>
        </div>
      </div>

    </div>
  </section>

  <!-- PHILOSOPHY -->
  <section class="section">
    <div class="section-header"><h2>// Philosophy</h2></div>
    <div class="principles">
      <div class="principle">
        <div class="principle-icon">🏗️</div>
        <div>
          <div class="principle-title">Structure First</div>
          <div class="principle-text">Architecture matters more than clever tricks. Design before code.</div>
        </div>
      </div>
      <div class="principle">
        <div class="principle-icon">🧹</div>
        <div>
          <div class="principle-title">Clean Code</div>
          <div class="principle-text">Readable beats writable — your future self will thank you.</div>
        </div>
      </div>
      <div class="principle">
        <div class="principle-icon">🤝</div>
        <div>
          <div class="principle-title">Collaboration</div>
          <div class="principle-text">Great software is built together, never in isolation.</div>
        </div>
      </div>
      <div class="principle">
        <div class="principle-icon">🌱</div>
        <div>
          <div class="principle-title">Continuous Growth</div>
          <div class="principle-text">Every bug is a lesson. Every project is progress.</div>
        </div>
      </div>
    </div>
  </section>

  <!-- STATS -->
  <section class="section">
    <div class="section-header"><h2>// Stats</h2></div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-value">150K+</div>
        <div class="stat-label">Followers</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">2.5K+</div>
        <div class="stat-label">Stars</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">800+</div>
        <div class="stat-label">Forks</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">47+</div>
        <div class="stat-label">Bugs Crushed</div>
      </div>
    </div>
  </section>

  <!-- QUOTE -->
  <div class="quote-block">
    <div class="quote-arabic">
      لَقَدْ عُدْنَا غُرَبَاءَ كَمَا كُنَّا
      <span class="line">في نِهايةْ هذه الرِّحْلة الغَريبة جِدّاً — تْخَرَّجْنا بَعْضَ الدُّروسْ، بَعْضَ الجُروحْ، وَالكَثيرْ مِنَ الجِلْدِ السّميكْ</span>
    </div>
    <div class="quote-divider"></div>
    <div class="quote-credit">فَ شُكراً لاسْتِماعِكُمْ • شُكْراً لِكُلّْ ما حَصَلْ ✨</div>
  </div>

  <!-- CONNECT -->
  <section class="section">
    <div class="section-header"><h2>// Let's Connect</h2></div>
    <div class="connect-grid">
      <a class="connect-card" href="https://github.com/OmarAlTurk">
        <span class="icon">🐙</span>
        <span class="label">GitHub</span>
      </a>
      <a class="connect-card" href="mailto:omaraltourk553@gmail.com">
        <span class="icon">📧</span>
        <span class="label">Email</span>
      </a>
      <a class="connect-card" href="https://www.instagram.com/i.ixwy">
        <span class="icon">📸</span>
        <span class="label">Instagram</span>
      </a>
      <a class="connect-card" href="https://t.me/X_D_Y_2006">
        <span class="icon">✈️</span>
        <span class="label">Telegram</span>
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <div class="footer-text">Made with ❤️ by Omar Yousef Dawod Al-Turk • © 2026</div>
    <div class="footer-flag">🇯🇴</div>
  </footer>

</div>
</body>
</html>
