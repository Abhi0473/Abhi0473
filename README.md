
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abhilash N | SOC Analyst</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0a0e1a;
    --bg-deep:#060911;
    --surface:#131b2c;
    --surface-2:#1a2438;
    --border:#253249;
    --text:#e6edf3;
    --muted:#8b96a5;
    --blue:#3ea6ff;
    --blue-dim:#1c5d8c;
    --amber:#f0b429;
    --green:#4ade80;
    --mono:'JetBrains Mono',monospace;
    --display:'Space Grotesk',sans-serif;
    --body:'Inter',sans-serif;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    font-family:var(--body);
    background:var(--bg);
    color:var(--text);
    line-height:1.65;
  }
  a{text-decoration:none;color:inherit;}
  ::selection{background:var(--blue-dim);color:#fff;}

  .reveal{opacity:0;transform:translateY(24px);transition:opacity .6s ease, transform .6s ease;}
  .reveal.visible{opacity:1;transform:translateY(0);}
  @media (prefers-reduced-motion: reduce){
    .reveal{opacity:1;transform:none;transition:none;}
    *{animation:none !important;}
  }

  /* HEADER */
  header{
    position:sticky;top:0;z-index:200;
    background:rgba(10,14,26,0.85);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--border);
    padding:16px 6%;
    display:flex;justify-content:space-between;align-items:center;
  }
  .logo{font-family:var(--mono);font-size:1rem;font-weight:700;color:var(--text);display:flex;align-items:center;gap:10px;}
  .logo .dot{width:9px;height:9px;border-radius:50%;background:var(--green);box-shadow:0 0 8px var(--green);animation:pulse 2s infinite;}
  @keyframes pulse{0%,100%{opacity:1;}50%{opacity:.4;}}
  nav ul{display:flex;gap:26px;list-style:none;}
  nav a{font-family:var(--mono);font-size:0.8rem;color:var(--muted);transition:color .2s;text-transform:uppercase;letter-spacing:1px;position:relative;padding-bottom:4px;}
  nav a.active, nav a:hover{color:var(--blue);}
  nav a.active::after{content:'';position:absolute;bottom:-4px;left:0;width:100%;height:2px;background:var(--blue);box-shadow:0 0 6px var(--blue);}
  .nav-toggle{display:none;background:none;border:none;color:var(--text);font-size:1.5rem;cursor:pointer;}

  /* HERO */
  .hero{
    position:relative;
    padding:100px 6% 60px;
    max-width:1200px;margin:0 auto;
    display:grid;grid-template-columns:1.1fr 0.9fr;gap:50px;align-items:center;
  }
  .hero-text{position:relative;z-index:1;}
  .hero-text .eyebrow{
    font-family:var(--mono);color:var(--green);font-size:0.85rem;letter-spacing:2px;
    margin-bottom:18px;display:flex;align-items:center;gap:10px;
  }
  .eyebrow::before{content:'';width:8px;height:8px;background:var(--green);border-radius:50%;box-shadow:0 0 8px var(--green);}
  .hero-text h1{
    font-family:var(--display);font-size:3.4rem;font-weight:700;line-height:1.1;margin-bottom:14px;
    color:var(--text);
  }
  .hero-text h1 span{
    background:linear-gradient(135deg,var(--blue),#7cc7ff);
    -webkit-background-clip:text;background-clip:text;color:transparent;
  }
  .hero-text .role{font-family:var(--mono);color:var(--muted);font-size:1.05rem;margin-bottom:22px;}
  .hero-text p{color:var(--muted);max-width:520px;margin-bottom:30px;}
  .hero-buttons{display:flex;gap:14px;flex-wrap:wrap;}
  .btn{
    padding:13px 28px;border-radius:6px;font-weight:600;font-size:0.92rem;
    font-family:var(--body);transition:all .2s;
    display:inline-flex;align-items:center;gap:8px;cursor:pointer;border:none;
  }
  .btn-primary{background:var(--blue);color:#06121f;border:1px solid var(--blue);}
  .btn-primary:hover{box-shadow:0 0 24px rgba(62,166,255,0.5);transform:translateY(-2px);}
  .btn-outline{border:1px solid var(--border);color:var(--text);background:transparent;}
  .btn-outline:hover{border-color:var(--blue);color:var(--blue);}

  /* TERMINAL */
  .terminal{
    position:relative;z-index:1;
    background:var(--bg-deep);border:1px solid var(--border);border-radius:10px;
    overflow:hidden;box-shadow:0 20px 60px rgba(0,0,0,0.5);
  }
  .terminal-bar{
    background:var(--surface-2);padding:10px 16px;display:flex;align-items:center;gap:8px;
    border-bottom:1px solid var(--border);
  }
  .terminal-bar .tdot{width:11px;height:11px;border-radius:50%;}
  .tdot.red{background:#ff5f56;}.tdot.yellow{background:#ffbd2e;}.tdot.green{background:#27c93f;}
  .terminal-bar span{font-family:var(--mono);font-size:0.75rem;color:var(--muted);margin-left:8px;}
  .terminal-body{
    font-family:var(--mono);font-size:0.82rem;padding:22px;min-height:280px;color:#c8d3e0;
  }
  .terminal-body .line{margin-bottom:9px;opacity:0;animation:fadein .4s forwards;white-space:pre-wrap;}
  .terminal-body .prompt{color:var(--green);}
  .terminal-body .info{color:var(--blue);}
  .terminal-body .warn{color:var(--amber);}
  .terminal-body .ok{color:var(--green);}
  .cursor{display:inline-block;width:8px;height:14px;background:var(--blue);animation:blink 1s infinite;vertical-align:middle;margin-left:4px;}
  @keyframes blink{0%,50%{opacity:1;}51%,100%{opacity:0;}}
  @keyframes fadein{to{opacity:1;}}

  /* STATS STRIP */
  .stats-strip{
    max-width:1200px;margin:0 auto;padding:0 6% 60px;
    display:grid;grid-template-columns:repeat(4,1fr);gap:18px;
  }
  .stat-box{
    background:var(--surface);border:1px solid var(--border);border-radius:10px;
    padding:24px 20px;text-align:center;transition:border-color .2s;
  }
  .stat-box:hover{border-color:var(--blue);}
  .stat-box .num{font-family:var(--display);font-size:2.2rem;font-weight:700;color:var(--blue);margin-bottom:6px;}
  .stat-box .lbl{font-family:var(--mono);font-size:0.75rem;color:var(--muted);text-transform:uppercase;letter-spacing:1.5px;}

  /* SECTIONS */
  section{padding:70px 6%;max-width:1200px;margin:0 auto;}
  .section-head{margin-bottom:44px;}
  .section-tag{font-family:var(--mono);color:var(--blue);font-size:0.8rem;letter-spacing:3px;text-transform:uppercase;margin-bottom:10px;}
  .section-title{font-family:var(--display);font-size:2.2rem;font-weight:700;color:var(--text);}
  .section-sub{color:var(--muted);margin-top:10px;max-width:600px;font-size:0.96rem;}

  /* ABOUT */
  .about-grid{display:grid;grid-template-columns:1.2fr 1fr;gap:50px;align-items:start;}
  .about-grid p{color:var(--muted);margin-bottom:16px;}
  .about-grid strong{color:var(--text);}
  .info-card{
    background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:26px;
  }
  .info-card h3{font-family:var(--mono);color:var(--blue);margin-bottom:16px;font-size:0.85rem;letter-spacing:2px;text-transform:uppercase;}
  .info-list{list-style:none;}
  .info-list li{display:flex;justify-content:space-between;padding:10px 0;border-bottom:1px solid var(--border);font-size:0.9rem;}
  .info-list li:last-child{border-bottom:none;}
  .info-list .label{color:var(--muted);font-family:var(--mono);font-size:0.78rem;}
  .info-list .value{color:var(--text);font-weight:500;text-align:right;}

  /* SKILLS - PROFICIENCY BARS */
  .skills-cols{display:grid;grid-template-columns:repeat(auto-fit,minmax(320px,1fr));gap:32px;}
  .skill-group h3{font-family:var(--display);color:var(--text);margin-bottom:20px;font-size:1.05rem;display:flex;align-items:center;gap:10px;}
  .skill-row{margin-bottom:16px;}
  .skill-row .skill-name{display:flex;justify-content:space-between;font-size:0.88rem;margin-bottom:6px;font-family:var(--mono);}
  .skill-row .skill-name span:last-child{color:var(--muted);}
  .skill-bar-track{height:6px;background:var(--surface-2);border-radius:3px;overflow:hidden;}
  .skill-bar-fill{height:100%;border-radius:3px;background:linear-gradient(90deg,var(--blue),#7cc7ff);width:0%;transition:width 1.2s ease;}

  /* LEARNING */
  .learning-banner{
    background:var(--surface);border:1px solid var(--amber);border-radius:8px;
    padding:26px 28px;margin-top:40px;position:relative;overflow:hidden;
  }
  .learning-banner::before{content:'';position:absolute;top:0;left:0;width:3px;height:100%;background:var(--amber);}
  .learning-banner h3{font-family:var(--display);color:var(--amber);margin-bottom:12px;font-size:1.05rem;}
  .tag-list{display:flex;flex-wrap:wrap;gap:8px;}
  .tag{
    background:var(--surface-2);color:#c8d3e0;padding:6px 12px;border-radius:4px;
    font-size:0.78rem;font-family:var(--mono);border:1px solid var(--border);
  }
  .learning-banner .tag{border-color:var(--amber);color:var(--amber);}

  /* PROJECTS - EXPANDABLE */
  .project-card{
    background:var(--surface);border:1px solid var(--border);border-left:3px solid var(--green);
    border-radius:8px;padding:28px 30px;margin-bottom:20px;transition:border-color .2s;cursor:pointer;
  }
  .project-card:hover{border-left-color:var(--blue);}
  .project-card .pid{font-family:var(--mono);color:var(--muted);font-size:0.75rem;letter-spacing:2px;margin-bottom:8px;}
  .project-card h3{font-family:var(--display);color:var(--text);font-size:1.25rem;margin-bottom:6px;display:flex;justify-content:space-between;align-items:center;}
  .project-card h3 .expand-icon{font-family:var(--mono);color:var(--blue);font-size:1rem;transition:transform .3s;}
  .project-card.open h3 .expand-icon{transform:rotate(45deg);}
  .project-meta{color:var(--muted);font-size:0.85rem;margin-bottom:0;font-family:var(--mono);}
  .project-tags{display:flex;flex-wrap:wrap;gap:8px;margin:14px 0;}
  .project-details{
    max-height:0;overflow:hidden;transition:max-height .4s ease;
  }
  .project-card.open .project-details{max-height:600px;}
  .project-details-inner{padding-top:16px;}
  .project-card ul{margin-left:20px;margin-bottom:16px;}
  .project-card ul li{margin-bottom:7px;font-size:0.94rem;color:#c8d3e0;}
  .impact-badge{
    display:inline-flex;align-items:center;gap:8px;background:rgba(74,222,128,0.1);color:var(--green);
    padding:8px 16px;border-radius:6px;font-weight:600;font-size:0.85rem;margin-top:6px;
    border:1px solid rgba(74,222,128,0.3);font-family:var(--mono);
  }
  .project-links a{
    color:var(--blue);font-weight:600;font-size:0.88rem;margin-right:20px;font-family:var(--mono);
  }
  .project-links a:hover{text-decoration:underline;}
  .click-hint{font-family:var(--mono);font-size:0.72rem;color:var(--muted);margin-top:4px;}

  /* CERTS */
  .cert-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(290px,1fr));gap:18px;}
  .cert-card{
    background:var(--surface);border:1px solid var(--border);border-radius:8px;
    padding:22px;display:flex;gap:16px;align-items:flex-start;transition:border-color .2s;
  }
  .cert-card:hover{border-color:var(--blue);}
  .cert-icon{
    width:44px;height:44px;border-radius:8px;background:var(--surface-2);color:var(--blue);
    display:flex;align-items:center;justify-content:center;font-weight:700;flex-shrink:0;font-size:1.2rem;
    border:1px solid var(--border);
  }
  .cert-card h4{font-family:var(--display);font-size:0.98rem;color:var(--text);margin-bottom:4px;}
  .cert-card p{font-size:0.85rem;color:var(--muted);font-family:var(--mono);}
  .status-badge{
    display:inline-block;font-size:0.7rem;font-weight:700;padding:3px 10px;border-radius:4px;margin-top:8px;
    font-family:var(--mono);letter-spacing:1px;text-transform:uppercase;
  }
  .status-done{background:rgba(74,222,128,0.1);color:var(--green);border:1px solid rgba(74,222,128,0.3);}
  .status-progress{background:rgba(240,180,41,0.1);color:var(--amber);border:1px solid rgba(240,180,41,0.3);}

  /* EXPERIENCE */
  .exp-card{
    background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:30px;
    border-left:3px solid var(--blue);
  }
  .exp-card .pid{font-family:var(--mono);color:var(--muted);font-size:0.75rem;letter-spacing:2px;margin-bottom:8px;}
  .exp-card h3{font-family:var(--display);color:var(--text);font-size:1.2rem;}
  .exp-meta{color:var(--muted);font-size:0.88rem;margin:6px 0 16px;font-family:var(--mono);}
  .exp-card ul{margin-left:20px;}
  .exp-card ul li{margin-bottom:7px;font-size:0.94rem;color:#c8d3e0;}

  /* EDUCATION */
  .edu-card{
    background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:24px;
    margin-bottom:14px;display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;align-items:center;
  }
  .edu-card h3{font-family:var(--display);color:var(--text);font-size:1.05rem;}
  .edu-card p{color:var(--muted);font-size:0.88rem;font-family:var(--mono);margin-top:4px;}
  .edu-card .cgpa{font-family:var(--mono);font-weight:700;color:var(--green);font-size:1.1rem;}

  /* CONTACT */
  .contact-section{text-align:center;}
  .contact-links{display:flex;justify-content:center;gap:14px;flex-wrap:wrap;margin-top:30px;}
  .contact-links a{
    background:var(--surface);border:1px solid var(--border);
    padding:13px 24px;border-radius:6px;font-weight:600;font-size:0.9rem;
    transition:all .2s;font-family:var(--mono);
  }
  .contact-links a:hover{border-color:var(--blue);color:var(--blue);transform:translateY(-2px);box-shadow:0 0 20px rgba(62,166,255,0.2);}

  footer{
    text-align:center;padding:30px;color:var(--muted);font-size:0.82rem;
    border-top:1px solid var(--border);font-family:var(--mono);
  }

  @media(max-width:900px){
    .hero{grid-template-columns:1fr;}
    .about-grid{grid-template-columns:1fr;}
    .stats-strip{grid-template-columns:repeat(2,1fr);}
  }
  @media(max-width:768px){
    nav ul{
      position:absolute;top:60px;right:0;background:var(--bg-deep);
      flex-direction:column;width:100%;padding:24px 6%;gap:20px;
      display:none;border-bottom:1px solid var(--border);
    }
    nav ul.active{display:flex;}
    .nav-toggle{display:block;}
    .hero-text h1{font-size:2.2rem;}
    section{padding:50px 6%;}
    .stats-strip{grid-template-columns:repeat(2,1fr);padding-bottom:40px;}
  }
</style>
</head>
<body>

<header>
  <div class="logo"><span class="dot"></span>abhilash@soc:~$</div>
  <button class="nav-toggle" onclick="document.getElementById('navlinks').classList.toggle('active')">☰</button>
  <nav>
    <ul id="navlinks">
      <li><a href="#about" class="navlink">about</a></li>
      <li><a href="#skills" class="navlink">skills</a></li>
      <li><a href="#projects" class="navlink">projects</a></li>
      <li><a href="#certs" class="navlink">certs</a></li>
      <li><a href="#experience" class="navlink">experience</a></li>
      <li><a href="#education" class="navlink">education</a></li>
      <li><a href="#contact" class="navlink">contact</a></li>
    </ul>
  </nav>
</header>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-text">
    <div class="eyebrow">STATUS: OPEN TO OPPORTUNITIES</div>
    <h1>Abhilash N<br>SOC <span>Analyst</span></h1>
    <div class="role">// Threat Detection · Incident Response · Network Defense</div>
    <p>Final-year BCA student specializing in security monitoring, log analysis, and ML-driven threat detection. Built a SOC alert prioritization framework processing 2.83M+ network records, cutting analyst alert fatigue by ~30%.</p>
    <div class="hero-buttons">
      <a href="#projects" class="btn btn-primary">View Projects →</a>
      <a href="#contact" class="btn btn-outline">Get in Touch</a>
    </div>
  </div>

  <div class="terminal">
    <div class="terminal-bar">
      <div class="tdot red"></div><div class="tdot yellow"></div><div class="tdot green"></div>
      <span>siem-console — analyst-feed</span>
    </div>
    <div class="terminal-body" id="termBody"></div>
  </div>
</section>

<!-- STATS STRIP -->
<div class="stats-strip">
  <div class="stat-box reveal">
    <div class="num" data-target="3">0</div>
    <div class="lbl">Security Projects</div>
  </div>
  <div class="stat-box reveal">
    <div class="num" data-target="4">0</div>
    <div class="lbl">Certifications</div>
  </div>
  <div class="stat-box reveal">
    <div class="num" data-target="45">0</div>
    <div class="lbl">TryHackMe Hours</div>
  </div>
  <div class="stat-box reveal">
    <div class="num" data-target="8.76" data-decimal="true">0</div>
    <div class="lbl">CGPA (BCA)</div>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="section-head reveal">
    <div class="section-tag">01 // About</div>
    <h2 class="section-title">Who I Am</h2>
  </div>
  <div class="about-grid">
    <div class="reveal">
      <p>I'm an <strong>ambitious BCA student</strong> with a solid foundation in Python, web development, and cybersecurity fundamentals, pursuing an entry-level role as a SOC Analyst where I can apply skills in security monitoring, log analysis, and incident response.</p>
      <p>My recent work combines <strong>machine learning with security operations</strong> — including a framework that processed 2.83M+ network flow records to help SOC teams prioritize real threats over noise, mapped directly to the MITRE ATT&CK framework.</p>
      <p>I actively practice on <strong>TryHackMe</strong>, study attacker techniques, and document my learning through structured notes — while expanding into SIEM platforms and red team methodology to become a well-rounded defender.</p>
    </div>
    <div class="info-card reveal">
      <h3>// Profile</h3>
      <ul class="info-list">
        <li><span class="label">LOCATION</span><span class="value">India</span></li>
        <li><span class="label">EMAIL</span><span class="value">abhi0473u@gmail.com</span></li>
        <li><span class="label">PHONE</span><span class="value">+91-6361886147</span></li>
        <li><span class="label">LINKEDIN</span><span class="value">abhilash-n-379067312</span></li>
        <li><span class="label">GITHUB</span><span class="value">Abhi0473</span></li>
        <li><span class="label">TRYHACKME</span><span class="value">abhi0473u</span></li>
        <li><span class="label">STATUS</span><span class="value" style="color:var(--green)">Available</span></li>
      </ul>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-head reveal">
    <div class="section-tag">02 // Skills</div>
    <h2 class="section-title">Technical Arsenal</h2>
    <p class="section-sub">Tools and concepts relevant to SOC operations, security analysis, and development</p>
  </div>

  <div class="skills-cols reveal">
    <div class="skill-group">
      <h3>🛡️ SOC & Security</h3>
      <div class="skill-row"><div class="skill-name"><span>Threat Detection & MITRE ATT&CK</span><span>Intermediate</span></div><div class="skill-bar-track"><div class="skill-bar-fill" data-width="70"></div></div></div>
      <div class="skill-row"><div class="skill-name"><span>Log Analysis & Incident Response</span><span>Intermediate</span></div><div class="skill-bar-track"><div class="skill-bar-fill" data-width="65"></div></div></div>
      <div class="skill-row"><div class="skill-name"><span>Linux & Network Hardening (UFW)</span><span>Strong</span></div><div class="skill-bar-track"><div class="skill-bar-fill" data-width="80"></div></div></div>
      <div class="skill-row"><div class="skill-name"><span>Packet Analysis (Wireshark/Scapy)</span><span>Intermediate</span></div><div class="skill-bar-track"><div class="skill-bar-fill" data-width="65"></div></div></div>
    </div>
    <div class="skill-group">
      <h3>💻 Programming & ML</h3>
      <div class="skill-row"><div class="skill-name"><span>Python</span><span>Strong</span></div><div class="skill-bar-track"><div class="skill-bar-fill" data-width="85"></div></div></div>
      <div class="skill-row"><div class="skill-name"><span>Scikit-learn / XGBoost / SMOTE</span><span>Strong</span></div><div class="skill-bar-track"><div class="skill-bar-fill" data-width="80"></div></div></div>
      <div class="skill-row"><div class="skill-name"><span>Pandas / NumPy / Data Preprocessing</span><span>Strong</span></div><div class="skill-bar-track"><div class="skill-bar-fill" data-width="82"></div></div></div>
      <div class="skill-row"><div class="skill-name"><span>SQL (MySQL/SQLite/MongoDB)</span><span>Intermediate</span></div><div class="skill-bar-track"><div class="skill-bar-fill" data-width="68"></div></div></div>
    </div>
  </div>

  <div class="learning-banner reveal">
    <h3>⚡ Currently Building Expertise In</h3>
    <div class="tag-list">
      <span class="tag">SIEM (Splunk/ELK/QRadar)</span>
      <span class="tag">CEH (In Progress)</span>
      <span class="tag">CRTP</span>
      <span class="tag">CRTO</span>
      <span class="tag">BloodHound</span>
      <span class="tag">Mimikatz</span>
      <span class="tag">Cobalt Strike</span>
      <span class="tag">Red Team Tactics</span>
      <span class="tag">SSL/TLS & Hashing</span>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-head reveal">
    <div class="section-tag">03 // Projects</div>
    <h2 class="section-title">Case Files</h2>
    <p class="section-sub">Security & ML-focused projects with measurable impact — click a case to expand details</p>
  </div>

  <div class="project-card reveal" onclick="this.classList.toggle('open')">
    <div class="pid">CASE-001 // ML SECURITY</div>
    <h3>AI-Driven SOC Alert Prioritization Framework <span class="expand-icon">+</span></h3>
    <div class="project-meta">Python · Machine Learning · Cybersecurity · 2026</div>
    <div class="click-hint">click to view details</div>
    <div class="project-details">
      <div class="project-details-inner">
        <div class="project-tags">
          <span class="tag">Scikit-learn</span><span class="tag">SMOTE</span><span class="tag">Scapy</span>
          <span class="tag">Streamlit</span><span class="tag">MITRE ATT&CK</span>
        </div>
        <ul>
          <li>Designed a multi-layered security infrastructure to ingest and sanitize the 2.83M record CIC-IDS 2017 dataset, processing large-scale network flow logs dynamically.</li>
          <li>Resolved severe data class imbalances across rare attack vectors using SMOTE scaling via Scikit-learn.</li>
          <li>Optimized analyst workflows, reducing alert fatigue by approximately 30% and improving incident response efficiency.</li>
          <li>Deployed a multi-threaded live network sniffer via Scapy alongside an interactive Streamlit dashboard mapped to MITRE ATT&CK.</li>
        </ul>
        <span class="impact-badge">📉 -30% ALERT FATIGUE</span>
        <div class="project-links" style="margin-top:16px;">
          <a href="https://github.com/Abhi0473" target="_blank">→ github</a>
        </div>
      </div>
    </div>
  </div>

  <div class="project-card reveal" onclick="this.classList.toggle('open')">
    <div class="pid">CASE-002 // NETWORK HARDENING</div>
    <h3>Linux Firewall Configuration using UFW <span class="expand-icon">+</span></h3>
    <div class="project-meta">Linux · Networking · Security · 2025</div>
    <div class="click-hint">click to view details</div>
    <div class="project-details">
      <div class="project-details-inner">
        <div class="project-tags">
          <span class="tag">Linux</span><span class="tag">UFW</span><span class="tag">SSH/HTTP Hardening</span><span class="tag">Documentation</span>
        </div>
        <ul>
          <li>Architected a hardened network perimeter security configuration using Linux administration and UFW utilities.</li>
          <li>Implemented strict allow/deny rules for SSH and HTTP services to minimize server attack surfaces.</li>
          <li>Tested firewall configurations using Linux networking tools and validated against standard security benchmarks.</li>
          <li>Documented reusable firewall setup procedures to establish security best practices.</li>
        </ul>
        <div class="project-links" style="margin-top:16px;">
          <a href="https://github.com/Abhi0473" target="_blank">→ github</a>
        </div>
      </div>
    </div>
  </div>

  <div class="project-card reveal" onclick="this.classList.toggle('open')">
    <div class="pid">CASE-003 // HANDS-ON LABS</div>
    <h3>TryHackMe — Cyber Security 101 <span class="expand-icon">+</span></h3>
    <div class="project-meta">Hands-on Labs · 45+ Hours</div>
    <div class="click-hint">click to view details</div>
    <div class="project-details">
      <div class="project-details-inner">
        <div class="project-tags">
          <span class="tag">Recon</span><span class="tag">Linux Fundamentals</span><span class="tag">Web Exploitation</span><span class="tag">Networking</span>
        </div>
        <ul>
          <li>Completed 45+ hours of hands-on security labs covering networking, Linux fundamentals, web exploitation, and security tooling.</li>
          <li>Practiced real-world attack and defense scenarios in a sandboxed environment to build SOC-relevant skills.</li>
        </ul>
        <div class="project-links" style="margin-top:16px;">
          <a href="https://tryhackme.com/p/abhi0473u" target="_blank">→ tryhackme profile</a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CERTS -->
<section id="certs">
  <div class="section-head reveal">
    <div class="section-tag">04 // Certifications</div>
    <h2 class="section-title">Training & Certifications</h2>
  </div>
  <div class="cert-grid reveal">
    <div class="cert-card">
      <div class="cert-icon">🔐</div>
      <div>
        <h4>Ethical Hacking & Web Penetration</h4>
        <p>Comprehensive Training</p>
        <span class="status-badge status-done">Completed</span>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-icon">🌑</div>
      <div>
        <h4>Dark Web, Anonymity & Crypto</h4>
        <p>EC-Council</p>
        <span class="status-badge status-done">Completed</span>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-icon">🎯</div>
      <div>
        <h4>Cyber Security 101</h4>
        <p>TryHackMe · 45+ hrs</p>
        <span class="status-badge status-done">Completed</span>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-icon">📊</div>
      <div>
        <h4>Applied Data Science: ML & DL</h4>
        <p>Aqmenz Automation Pvt. Ltd.</p>
        <span class="status-badge status-done">Completed</span>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-icon">🛡️</div>
      <div>
        <h4>Certified Ethical Hacker (CEH)</h4>
        <p>EC-Council</p>
        <span class="status-badge status-progress">In Progress</span>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-icon">⚔️</div>
      <div>
        <h4>CRTP & CRTO</h4>
        <p>Red Team Certifications</p>
        <span class="status-badge status-progress">Planned</span>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-head reveal">
    <div class="section-tag">05 // Experience</div>
    <h2 class="section-title">Work History</h2>
  </div>
  <div class="exp-card reveal">
    <div class="pid">2026.04 — 2026.05</div>
    <h3>Machine Learning Intern</h3>
    <div class="exp-meta">Aqmenz Automation Pvt. Ltd., Bengaluru, India</div>
    <ul>
      <li>Engineered end-to-end ML pipelines using Python to automate complex data preprocessing workflows.</li>
      <li>Architected and evaluated ML models utilizing Python, Scikit-learn, Pandas, NumPy, and OpenCV.</li>
      <li>Applied data visualization and performance evaluation techniques to improve model prediction accuracy.</li>
      <li>Collaborated on AI-based automation solutions, gaining hands-on experience in real-world ML workflows.</li>
    </ul>
  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="section-head reveal">
    <div class="section-tag">06 // Education</div>
    <h2 class="section-title">Academic Background</h2>
  </div>
  <div class="edu-card reveal">
    <div>
      <h3>Bachelor of Computer Applications (BCA)</h3>
      <p>National Degree College, Bagepalli · 2023 – 2026</p>
    </div>
    <div class="cgpa">CGPA 8.76</div>
  </div>
  <div class="edu-card reveal">
    <div>
      <h3>Pre-University Course</h3>
      <p>The National PU College · 2021 – 2023</p>
    </div>
    <div class="cgpa">71%</div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" class="contact-section">
  <div class="section-head reveal" style="text-align:center;">
    <div class="section-tag">07 // Contact</div>
    <h2 class="section-title">Let's Connect</h2>
    <p class="section-sub" style="margin:10px auto 0;">Open to SOC Analyst internships, entry-level roles & cybersecurity opportunities</p>
  </div>
  <div class="contact-links reveal">
    <a href="mailto:abhi0473u@gmail.com">email</a>
    <a href="https://www.linkedin.com/in/abhilash-n-379067312" target="_blank">linkedin</a>
    <a href="https://github.com/Abhi0473" target="_blank">github</a>
    <a href="https://tryhackme.com/p/abhi0473u" target="_blank">tryhackme</a>
    <a href="tel:+916361886147">+91-6361886147</a>
  </div>
</section>

<footer>
  © 2026 Abhilash N — root@soc-portfolio:~$ <span style="color:var(--green)">_</span>
</footer>

<script>
  // Terminal typing animation
  const lines = [
    {text:'[BOOT] Initializing analyst profile...', cls:'prompt'},
    {text:'[INFO] Name: Abhilash N', cls:'info'},
    {text:'[INFO] Role: SOC Analyst (Entry-Level / Intern)', cls:'info'},
    {text:'[SCAN] Skills loaded: Python, Linux, SIEM concepts,', cls:'ok'},
    {text:'        MITRE ATT&CK, Threat Detection', cls:'ok'},
    {text:'[ALERT] Project: AI Alert Prioritization System', cls:'warn'},
    {text:'        → Alert fatigue reduced by 30%', cls:'warn'},
    {text:'[CERT] CEH: in_progress | CRTP/CRTO: queued', cls:'info'},
    {text:'[STATUS] Availability: OPEN_TO_WORK', cls:'ok'},
    {text:'[READY] Awaiting incoming connection request...', cls:'prompt'},
  ];
  const term = document.getElementById('termBody');
  let lineIndex = 0;
  function addLine(){
    if(lineIndex >= lines.length){
      const cursorLine = document.createElement('div');
      cursorLine.className = 'line';
      cursorLine.style.opacity = 1;
      cursorLine.innerHTML = '<span class="prompt">analyst@soc:~$</span> <span class="cursor"></span>';
      term.appendChild(cursorLine);
      return;
    }
    const div = document.createElement('div');
    div.className = 'line ' + lines[lineIndex].cls;
    div.textContent = lines[lineIndex].text;
    term.appendChild(div);
    lineIndex++;
    setTimeout(addLine, 380);
  }
  addLine();

  // Scroll reveal + skill bar fill
  const observer = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{
      if(e.isIntersecting){
        e.target.classList.add('visible');
        // animate skill bars within this element
        e.target.querySelectorAll('.skill-bar-fill').forEach(bar=>{
          bar.style.width = bar.getAttribute('data-width') + '%';
        });
        // set stat values directly (no count-up animation)
        e.target.querySelectorAll('.num').forEach(num=>{
          if(num.dataset.animated) return;
          num.dataset.animated = 'true';
          const target = parseFloat(num.getAttribute('data-target'));
          const isDecimal = num.getAttribute('data-decimal') === 'true';
          num.textContent = isDecimal ? target.toFixed(2) : Math.floor(target);
        });
      }
    });
  }, {threshold:0.15});
  document.querySelectorAll('.reveal').forEach(el=>observer.observe(el));

  // Active nav link highlighting
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.navlink');
  const navObserver = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting){
        navLinks.forEach(link=>{
          link.classList.toggle('active', link.getAttribute('href') === '#'+entry.target.id);
        });
      }
    });
  }, {threshold:0.4, rootMargin:'-80px 0px -50% 0px'});
  sections.forEach(s=>navObserver.observe(s));

  // Mobile nav close on link click
  navLinks.forEach(a=>{
    a.addEventListener('click', ()=>document.getElementById('navlinks').classList.remove('active'));
  });
</script>

</body>
</html>
