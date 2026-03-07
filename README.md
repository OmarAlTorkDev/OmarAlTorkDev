<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>OMAR_AL-TURK :: README</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap" rel="stylesheet"/>
<style>
  * { margin:0; padding:0; box-sizing:border-box; }

  body {
    background: #000;
    color: #00FF41;
    font-family: 'Share Tech Mono', monospace;
    padding: 20px 16px;
    overflow-x: hidden;
  }

  /* scanlines */
  body::after {
    content:'';
    position:fixed;
    inset:0;
    background: repeating-linear-gradient(0deg, transparent, transparent 3px, rgba(0,255,65,0.012) 3px, rgba(0,255,65,0.012) 4px);
    pointer-events:none;
    z-index:999;
  }

  .wrap {
    max-width: 900px;
    margin: 0 auto;
    border: 1px solid #00FF41;
    box-shadow: 0 0 40px rgba(0,255,65,0.1), 0 0 80px rgba(255,0,0,0.05);
    background: #000;
    position: relative;
  }

  .titlebar {
    background: #00FF41;
    color: #000;
    font-size: 12px;
    padding: 5px 16px;
    letter-spacing: 2px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .titlebar span { color: #FF0000; }

  .content { padding: 36px 36px; }

  /* HEADER */
  .header { text-align:center; padding-bottom:28px; border-bottom: 1px dashed #1a3a1a; margin-bottom:32px; }

  .ascii {
    font-size: 7.5px;
    line-height: 1.25;
    color: #00FF41;
    text-shadow: 0 0 6px #00FF41;
    white-space: pre;
    overflow-x: auto;
    margin-bottom: 20px;
    display: inline-block;
  }

  .typing { font-size:14px; margin:5px 0; }
  .typing.green { color:#00FF41; }
  .typing.red { color:#FF0000; }
  .typing::before { content:'> '; opacity:0.5; }

  .badges-row { display:flex; justify-content:center; flex-wrap:wrap; gap:8px; margin:14px 0; }

  .sbadge {
    font-size:11px; padding:4px 12px; letter-spacing:1.5px;
    border:1px solid;
  }
  .sbadge.g { border-color:#00FF41; color:#00FF41; }
  .sbadge.r { border-color:#FF0000; color:#FF0000; }

  .links { display:flex; justify-content:center; flex-wrap:wrap; gap:8px; margin-top:14px; }
  .lbtn { font-size:12px; font-weight:700; padding:7px 16px; text-decoration:none; letter-spacing:1px; transition:all .2s; }
  .lbtn.g { background:#00FF41; color:#000; }
  .lbtn.r { background:#FF0000; color:#fff; }
  .lbtn:hover { opacity:0.8; }

  /* SECTIONS */
  .section { margin-bottom:36px; }

  .cmd {
    font-size:15px; color:#00FF41; font-weight:700;
    margin-bottom:14px; text-shadow:0 0 8px #00FF41;
    letter-spacing:1px;
  }
  .cmd::before { content:'$ '; color:#FF0000; }

  .terminal {
    background:#050505;
    border:1px solid #1a1a1a;
    border-left:3px solid #00FF41;
    padding:16px 20px;
    font-size:13px;
    line-height:1.8;
    color:#00FF41;
    white-space:pre-wrap;
    text-shadow:0 0 3px rgba(0,255,65,0.3);
    margin-bottom:14px;
    border-radius:2px;
  }

  .terminal .red { color:#FF0000; }
  .terminal .dim { color:rgba(0,255,65,0.4); }

  /* BADGES */
  .blabel { font-size:10px; color:rgba(0,255,65,0.45); letter-spacing:2px; margin-bottom:8px; margin-top:16px; }
  .blabel::before { content:'// '; color:#FF0000; }

  .badge-wrap { display:flex; flex-wrap:wrap; gap:6px; margin-bottom:4px; }

  .chip {
    font-size:11px; font-weight:700; padding:5px 12px;
    letter-spacing:0.5px; cursor:default;
  }
  .chip.g { background:#00FF41; color:#000; }
  .chip.r { background:#FF0000; color:#fff; }

  /* PROJECTS TABLE */
  table { width:100%; border-collapse:collapse; font-size:13px; margin-top:14px; }
  th { background:#00FF41; color:#000; padding:9px 14px; text-align:left; font-size:11px; letter-spacing:1px; }
  td { border:1px solid #1a1a1a; padding:9px 14px; color:#00FF41; vertical-align:top; }
  tr:nth-child(even) td { background:rgba(0,255,65,0.02); }
  tr:hover td { background:rgba(255,0,0,0.04); }
  td a { color:#FF0000; text-decoration:none; font-weight:700; }
  td a:hover { text-shadow:0 0 6px #FF0000; }
  td code { color:rgba(0,255,65,0.6); font-size:11px; }

  /* STATS */
  .stats-grid { display:grid; grid-template-columns:1fr 1fr; gap:10px; margin-bottom:10px; }
  .stats-grid img, .streak { width:100%; }

  hr { border:none; border-top:1px dashed #1a1a1a; margin:28px 0; }

  /* FOOTER */
  .footer { text-align:center; border-top:1px solid #FF0000; padding-top:20px; margin-top:32px; }
  .footer .terminal { border-left-color:#FF0000; color:rgba(0,255,65,0.6); font-size:12px; }

  @keyframes blink { 0%,100%{opacity:1}50%{opacity:0} }
  .cur::after { content:'█'; animation:blink 1s infinite; color:#FF0000; }

  @media(max-width:600px){
    .ascii{font-size:4.5px;}
    .stats-grid{grid-template-columns:1fr;}
    .content{padding:20px 16px;}
  }
</style>
</head>
<body>
<div class="wrap">

  <div class="titlebar">
    <span>⬤ ⬤ ⬤</span>
    OMAR_AL-TURK :: /root/profile/README.md
    <span>[CLASSIFIED]</span>
  </div>

  <div class="content">

    <!-- HEADER -->
    <div class="header">
      <div class="ascii"> ██████╗ ███╗   ███╗ █████╗ ██████╗      █████╗ ██╗
██╔═══██╗████╗ ████║██╔══██╗██╔══██╗    ██╔══██╗██║
██║   ██║██╔████╔██║███████║██████╔╝    ███████║██║
██║   ██║██║╚██╔╝██║██╔══██║██╔══██╗    ██╔══██║██║
╚██████╔╝██║ ╚═╝ ██║██║  ██║██║  ██║    ██║  ██║███████╗
 ╚═════╝ ╚═╝     ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝  ╚═╝╚══════╝</div>

      <div class="typing green">[SYSTEM] Initializing profile... OK <span class="cur"></span></div>
      <div class="typing green">[ACCESS] Full-Stack &amp; AI Developer... GRANTED</div>
      <div class="typing red">[ALERT]  Open to Internships... BROADCASTING</div>
      <div class="typing green">[STATUS] Competitive Programmer... ACTIVE</div>
      <div class="typing red">[WARN]   Do not underestimate this dev</div>

      <div class="badges-row">
        <span class="sbadge r">ROOT@JORDAN</span>
        <span class="sbadge g">STATUS: ONLINE</span>
        <span class="sbadge r">THREAT_LEVEL: DEV</span>
      </div>

      <div class="links">
        <a class="lbtn g" href="https://github.com/OmarAlTorkDev">[GITHUB]</a>
        <a class="lbtn r" href="mailto:omaraltourk553@gmail.com">[ENCRYPTED_MAIL]</a>
        <a class="lbtn g" href="https://www.instagram.com/i.ixwy">[INSTAGRAM]</a>
        <a class="lbtn r" href="https://t.me/X_D_Y_2006">[SECURE_CHANNEL]</a>
      </div>
    </div>

    <!-- WHOAMI -->
    <div class="section">
      <div class="cmd">whoami</div>
      <div class="terminal">╔══════════════════════════════════════════════════════════╗
║              [ IDENTITY DECRYPTED ]                      ║
╠══════════════════════════════════════════════════════════╣
║  <span class="red">[*]</span> Handle   :  Omar Yousef Dawod Al-Turk               ║
║  <span class="red">[*]</span> Role     :  Software Engineering Student            ║
║  <span class="red">[*]</span> Focus    :  Full-Stack  |  AI/ML  |  Comp. Prog.    ║
║  <span class="red">[*]</span> Shell    :  bash  |  zsh  |  python3                ║
║  <span class="red">[*]</span> Speaks   :  Arabic  |  English  |  Code             ║
║  <span class="red">[*]</span> Location :  Jordan 🇯🇴                               ║
║  <span class="red">[*]</span> Status   :  OPEN TO INTERNSHIPS & COLLABS           ║
╚══════════════════════════════════════════════════════════╝

<span class="red">[+]</span> Authentication successful.
<span class="dim">[!] "Every great dev got there by solving problems
     they were unqualified to solve — until they did."</span></div>
    </div>

    <hr/>

    <!-- TECH STACK -->
    <div class="section">
      <div class="cmd">cat /etc/tech_stack</div>
      <div class="terminal"><span class="dim">[SCANNING INSTALLED PACKAGES...]</span></div>

      <div class="blabel">CORE LANGUAGES</div>
      <div class="badge-wrap">
        <span class="chip g">[Python]</span><span class="chip r">[C++]</span><span class="chip g">[Java]</span><span class="chip r">[JavaScript]</span><span class="chip g">[TypeScript]</span><span class="chip r">[C#]</span><span class="chip g">[Go]</span><span class="chip r">[Rust]</span><span class="chip g">[Kotlin]</span><span class="chip r">[Swift]</span><span class="chip g">[Dart]</span><span class="chip r">[PHP]</span><span class="chip g">[R]</span>
      </div>

      <div class="blabel">WEB & MOBILE</div>
      <div class="badge-wrap">
        <span class="chip r">[HTML5]</span><span class="chip g">[CSS3]</span><span class="chip r">[React]</span><span class="chip g">[Next.js]</span><span class="chip r">[Vue.js]</span><span class="chip g">[Angular]</span><span class="chip r">[Node.js]</span><span class="chip g">[Express]</span><span class="chip r">[Flutter]</span><span class="chip g">[React Native]</span><span class="chip r">[GraphQL]</span>
      </div>

      <div class="blabel">DATABASES</div>
      <div class="badge-wrap">
        <span class="chip g">[PostgreSQL]</span><span class="chip r">[MySQL]</span><span class="chip g">[MongoDB]</span><span class="chip r">[Redis]</span><span class="chip g">[SQLite]</span><span class="chip r">[Firebase]</span>
      </div>

      <div class="blabel">AI / ML & DATA</div>
      <div class="badge-wrap">
        <span class="chip g">[TensorFlow]</span><span class="chip r">[PyTorch]</span><span class="chip g">[OpenCV]</span><span class="chip r">[Scikit-learn]</span><span class="chip g">[NumPy]</span><span class="chip r">[Pandas]</span><span class="chip g">[Matplotlib]</span>
      </div>

      <div class="blabel">DEVOPS & TOOLS</div>
      <div class="badge-wrap">
        <span class="chip r">[Git]</span><span class="chip g">[GitHub]</span><span class="chip r">[GitLab]</span><span class="chip g">[Docker]</span><span class="chip r">[Kubernetes]</span><span class="chip g">[Linux]</span><span class="chip r">[Bash]</span><span class="chip g">[Postman]</span><span class="chip r">[Vercel]</span>
      </div>

      <div class="blabel">EXPLOITS & CONCEPTS</div>
      <div class="badge-wrap">
        <span class="chip g">[OOP]</span><span class="chip r">[DSA]</span><span class="chip g">[REST API]</span><span class="chip r">[GraphQL]</span><span class="chip g">[TDD]</span><span class="chip r">[Agile]</span><span class="chip g">[CI/CD]</span>
      </div>
    </div>

    <hr/>

    <!-- PROJECTS -->
    <div class="section">
      <div class="cmd">ls -la ./projects/</div>
      <div class="terminal"><span class="red">[*]</span> Enumerating targets...

drwxr-xr-x  projects/
├── <span class="red">[ACTIVE]</span>  store-manager/    → Python  | OOP        | JSON
├── <span class="red">[ACTIVE]</span>  ai-image-bot/     → Python  | TensorFlow | OpenCV
├── <span class="red">[ACTIVE]</span>  cp-solver/        → C++     | Python     | Algorithms
└── <span class="red">[ACTIVE]</span>  task-manager/     → React   | Node.js    | PostgreSQL</div>

      <table>
        <tr><th>[TARGET]</th><th>[PAYLOAD]</th><th>[TOOLS]</th><th>[EXPLOIT]</th></tr>
        <tr>
          <td>🛒 <strong>store-manager</strong></td>
          <td>OOP inventory + JSON persistence + sales reports</td>
          <td><code>Python</code> <code>OOP</code> <code>JSON</code></td>
          <td><a href="#">→ ACCESS</a></td>
        </tr>
        <tr>
          <td>🤖 <strong>ai-image-bot</strong></td>
          <td>Real-time object detection via deep learning</td>
          <td><code>Python</code> <code>TensorFlow</code> <code>OpenCV</code></td>
          <td><a href="#">→ ACCESS</a></td>
        </tr>
        <tr>
          <td>⚡ <strong>cp-solver</strong></td>
          <td>Problem analyzer + DP optimizer + tracker</td>
          <td><code>C++</code> <code>Python</code> <code>Algorithms</code></td>
          <td><a href="#">→ ACCESS</a></td>
        </tr>
        <tr>
          <td>📋 <strong>task-manager</strong></td>
          <td>Full-stack + JWT auth + PostgreSQL backend</td>
          <td><code>React</code> <code>Node.js</code> <code>PostgreSQL</code></td>
          <td><a href="#">→ ACCESS</a></td>
        </tr>
      </table>
    </div>

    <hr/>

    <!-- CERTS -->
    <div class="section">
      <div class="cmd">cat /etc/credentials/certs.log</div>
      <div class="terminal"><span class="red">[*]</span> Verifying credentials...

╔══════════════════════════════════════════════════════════════════╗
║                  [ CERTIFICATIONS — VERIFIED ]                   ║
╠══════════╦═══════════════════════════════╦════════════╦══════════╣
║  [ID]    ║  [CERTIFICATE]                ║  [ISSUER]  ║  [STAT]  ║
╠══════════╬═══════════════════════════════╬════════════╬══════════╣
║ 1204501  ║  Java Programming  (80 hrs)   ║  Al-Azimah ║  <span class="red">✓ PASS</span>  ║
╠══════════╬═══════════════════════════════╬════════════╬══════════╣
║ IEEE-25  ║  Student Membership  2025     ║  IEEE      ║  <span class="red">✓ ACTV</span>  ║
╠══════════╬═══════════════════════════════╬════════════╬══════════╣
║ INT-1229 ║  Introduction to IT           ║  SYNCC     ║  <span class="red">✓ PASS</span>  ║
╚══════════╩═══════════════════════════════╩════════════╩══════════╝

<span class="red">[+]</span> All credentials verified. Access level: <span class="red">TRUSTED</span></div>
    </div>

    <hr/>

    <!-- STATS -->
    <div class="section">
      <div class="cmd">./stats --verbose</div>
      <div class="stats-grid">
        <img src="https://github-readme-stats.vercel.app/api?username=OmarAlTorkDev&show_icons=true&theme=chartreuse-dark&hide_border=true&count_private=true&bg_color=000000&title_color=00FF41&icon_color=FF0000&text_color=00FF41"/>
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=OmarAlTorkDev&layout=compact&theme=chartreuse-dark&hide_border=true&bg_color=000000&title_color=00FF41&text_color=00FF41"/>
      </div>
      <img class="streak" src="https://github-readme-streak-stats.herokuapp.com/?user=OmarAlTorkDev&theme=chartreuse-dark&hide_border=true&background=000000&stroke=00FF41&ring=FF0000&fire=FF0000&currStreakLabel=00FF41&sideLabels=00FF41&dates=00FF41"/>
    </div>

    <hr/>

    <!-- PHILOSOPHY -->
    <div class="section">
      <div class="cmd">cat rules.txt</div>
      <div class="terminal"><span class="dim">[CORE DIRECTIVES LOADED]</span>

  <span class="red">[01]</span> STRUCTURE_FIRST  →  Architecture beats clever tricks
  <span class="red">[02]</span> CLEAN_CODE       →  Readable code beats writable code
  <span class="red">[03]</span> COLLABORATE      →  No great system is built alone
  <span class="red">[04]</span> KEEP_LEARNING    →  Every bug is intel. Use it.</div>
    </div>

    <hr/>

    <!-- QUOTE -->
    <div class="section">
      <div class="cmd">cat /dev/soul</div>
      <div class="terminal" style="direction:rtl; text-align:right;">لَقَدْ عُدْنَا غُرَبَاءَ كَمَا كُنَّا

  في نِهايةْ هذه الرِّحْلة الغَريبة جِدّاً
  تْخَرَّجْنا بَعْضَ الدُّروسْ
  بَعْضَ الجُروحْ
  وَالكَثيرْ مِنَ الجِلْدِ السّميكْ

  فَ شُكراً لاسْتِماعِكُمْ
  وَ شُكْراً لِكُلّْ ما حَصَلْ ✨</div>
    </div>

    <hr/>

    <!-- CONNECT -->
    <div class="section">
      <div class="cmd">./connect --broadcast</div>
      <div class="terminal"><span class="red">[*]</span> Broadcasting identity...

  <span class="red">[+]</span> GitHub    →  github.com/OmarAlTorkDev         [PORT: OPEN]
  <span class="red">[+]</span> Gmail     →  omaraltourk553@gmail.com          [PORT: OPEN]
  <span class="red">[+]</span> Instagram →  instagram.com/i.ixwy              [PORT: OPEN]
  <span class="red">[+]</span> Telegram  →  t.me/X_D_Y_2006                  [PORT: OPEN]

  <span class="red">[!]</span> SEEKING: Internships | Open-Source | Collabs | Projects</div>

      <div class="links">
        <a class="lbtn g" href="https://github.com/OmarAlTorkDev">[GITHUB]</a>
        <a class="lbtn r" href="mailto:omaraltourk553@gmail.com">[ENCRYPTED_MAIL]</a>
        <a class="lbtn g" href="https://www.instagram.com/i.ixwy">[INSTAGRAM]</a>
        <a class="lbtn r" href="https://t.me/X_D_Y_2006">[SECURE_CHANNEL]</a>
      </div>
    </div>

    <!-- FOOTER -->
    <div class="footer">
      <div class="terminal" style="border-left-color:#FF0000; color:rgba(0,255,65,0.5);">> Connection terminated.
> Session log saved to /var/log/omar_al-turk.log
> root@jordan:~# exit
> © 2026 🇯🇴 — All rights reserved. All wrongs reversed. <span class="cur"></span></div>
    </div>

  </div>
</div>
</body>
</html>
