# Parvathavarthini-PORTFOLIO-
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>S. Parvathavarthini | Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=Outfit:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg: #04040a;
  --surface: #090915;
  --card: #0f0f1e;
  --border: rgba(140,100,255,0.15);
  --glow: rgba(140,100,255,0.25);
  --accent: #9d6fff;
  --accent2: #ff6eb4;
  --teal: #00e5c3;
  --gold: #ffd166;
  --text: #f0f0ff;
  --muted: #8080aa;
}

*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}

body {
  font-family:'Outfit',sans-serif;
  background:var(--bg);
  color:var(--text);
  min-height:100vh;
  overflow-x:hidden;
}

/* ── Animated background ── */
body::before {
  content:'';
  position:fixed;inset:0;
  background:
    radial-gradient(ellipse 80% 60% at 20% 10%, rgba(157,111,255,0.07) 0%, transparent 60%),
    radial-gradient(ellipse 60% 80% at 80% 80%, rgba(255,110,180,0.05) 0%, transparent 60%),
    radial-gradient(ellipse 50% 50% at 50% 50%, rgba(0,229,195,0.03) 0%, transparent 60%);
  pointer-events:none;z-index:0;
  animation:bgPulse 12s ease-in-out infinite alternate;
}
@keyframes bgPulse {
  from{opacity:.6} to{opacity:1}
}

/* Grid overlay */
body::after {
  content:'';
  position:fixed;inset:0;
  background-image:
    linear-gradient(rgba(140,100,255,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(140,100,255,0.03) 1px, transparent 1px);
  background-size:48px 48px;
  pointer-events:none;z-index:0;
}

/* ── Nav ── */
nav {
  position:sticky;top:0;z-index:100;
  backdrop-filter:blur(24px) saturate(180%);
  background:rgba(4,4,10,0.65);
  border-bottom:1px solid var(--border);
}
.nav-inner {
  max-width:1120px;margin:0 auto;
  display:flex;align-items:center;justify-content:space-between;
  padding:16px 28px;
}
.nav-logo {
  font-family:'Cormorant Garamond',serif;
  font-size:1.4rem;font-style:italic;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
  letter-spacing:0.02em;
}
.nav-links {
  display:flex;gap:32px;list-style:none;
}
.nav-links a {
  color:var(--muted);text-decoration:none;
  font-size:.8rem;letter-spacing:.1em;text-transform:uppercase;
  font-weight:500;transition:color .2s;
}
.nav-links a:hover{color:var(--accent)}

/* ── Hero ── */
.hero {
  position:relative;z-index:1;
  min-height:100vh;display:flex;align-items:center;
  padding:80px 28px 60px;
}
.hero-inner {
  max-width:1120px;margin:0 auto;
  display:grid;grid-template-columns:1fr 380px;
  gap:72px;align-items:center;width:100%;
}

/* Text side */
.hero-eyebrow {
  display:inline-flex;align-items:center;gap:10px;
  font-family:'JetBrains Mono',monospace;font-size:.72rem;
  color:var(--teal);letter-spacing:.2em;text-transform:uppercase;
  margin-bottom:22px;
  opacity:0;animation:fadeUp .8s .2s forwards;
}
.hero-eyebrow::before {
  content:'';display:block;width:32px;height:1px;
  background:var(--teal);
}

h1.hero-name {
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(3rem,6vw,5.5rem);
  font-weight:600;line-height:1.05;
  margin-bottom:12px;
  opacity:0;animation:fadeUp .8s .4s forwards;
}
.name-grad {
  background:linear-gradient(125deg,var(--accent) 0%,var(--accent2) 60%,var(--gold) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
}

.hero-title {
  font-family:'JetBrains Mono',monospace;
  font-size:.88rem;color:var(--muted);
  margin-bottom:28px;letter-spacing:.04em;
  opacity:0;animation:fadeUp .8s .6s forwards;
}

.hero-desc {
  font-size:1.05rem;color:#9898cc;line-height:1.8;
  max-width:500px;margin-bottom:44px;
  opacity:0;animation:fadeUp .8s .8s forwards;
}

.hero-btns {
  display:flex;gap:16px;flex-wrap:wrap;
  opacity:0;animation:fadeUp .8s 1s forwards;
}
.btn-main {
  padding:14px 32px;border-radius:100px;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  color:#fff;font-weight:600;font-size:.9rem;text-decoration:none;
  transition:transform .2s,box-shadow .2s;
  box-shadow:0 0 32px rgba(157,111,255,0.3);
}
.btn-main:hover{transform:translateY(-3px);box-shadow:0 8px 40px rgba(157,111,255,0.5)}
.btn-ghost {
  padding:14px 32px;border-radius:100px;
  border:1px solid var(--border);
  color:var(--text);font-size:.9rem;text-decoration:none;
  transition:border-color .2s,transform .2s;
}
.btn-ghost:hover{border-color:var(--accent);transform:translateY(-3px)}

/* Photo side */
.hero-photo {
  position:relative;
  opacity:0;animation:fadeIn .9s .6s forwards;
}
.photo-ring {
  position:relative;width:340px;height:340px;margin:0 auto;
}
.photo-ring::before {
  content:'';position:absolute;inset:-4px;border-radius:50%;
  background:conic-gradient(var(--accent),var(--accent2),var(--teal),var(--gold),var(--accent));
  animation:spin 6s linear infinite;z-index:0;
}
.photo-ring::after {
  content:'';position:absolute;inset:0;border-radius:50%;
  background:var(--bg);margin:3px;z-index:1;
}
@keyframes spin{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}

.photo-img {
  position:absolute;inset:8px;border-radius:50%;
  overflow:hidden;z-index:2;
  border:3px solid rgba(157,111,255,0.3);
}
.photo-img img {
  width:100%;height:100%;object-fit:cover;object-position:center top;
  filter:grayscale(20%) contrast(1.05);
}

/* Floating badges */
.badge {
  position:absolute;z-index:10;
  background:rgba(9,9,21,0.85);backdrop-filter:blur(16px);
  border:1px solid var(--border);border-radius:12px;
  padding:10px 16px;font-size:.78rem;font-weight:500;
  display:flex;align-items:center;gap:8px;
  box-shadow:0 8px 32px rgba(0,0,0,0.4);
  animation:badgeFloat 3s ease-in-out infinite;
}
.badge-dot {width:8px;height:8px;border-radius:50%;flex-shrink:0}
.badge-1{top:10px;right:-20px;animation-delay:0s}
.badge-2{bottom:50px;left:-30px;animation-delay:1s}
.badge-3{bottom:-10px;right:10px;animation-delay:2s}
@keyframes badgeFloat {
  0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)}
}

/* ── Stats strip ── */
.stats {
  position:relative;z-index:1;
  background:var(--surface);
  border-top:1px solid var(--border);
  border-bottom:1px solid var(--border);
}
.stats-inner {
  max-width:1120px;margin:0 auto;
  display:grid;grid-template-columns:repeat(4,1fr);
}
.stat-item {
  padding:36px 28px;text-align:center;
  border-right:1px solid var(--border);
  transition:background .2s;
}
.stat-item:last-child{border-right:none}
.stat-item:hover{background:rgba(157,111,255,0.05)}
.stat-num {
  font-family:'Cormorant Garamond',serif;
  font-size:2.8rem;font-weight:600;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;display:block;
  margin-bottom:6px;
}
.stat-lbl {
  font-size:.75rem;color:var(--muted);
  letter-spacing:.12em;text-transform:uppercase;
  font-family:'JetBrains Mono',monospace;
}

/* ── Sections ── */
section{position:relative;z-index:1;padding:100px 28px}
.container{max-width:1120px;margin:0 auto}

.sec-eyebrow {
  font-family:'JetBrains Mono',monospace;
  font-size:.72rem;letter-spacing:.2em;text-transform:uppercase;
  color:var(--teal);margin-bottom:16px;
}
.sec-title {
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(2.2rem,4vw,3.2rem);font-weight:600;
  margin-bottom:16px;line-height:1.15;
}
.sec-sub {
  color:var(--muted);font-size:1rem;line-height:1.75;
  max-width:520px;margin-bottom:60px;
}

/* ── Skills ── */
#skills{background:var(--surface)}
.skills-wrap {
  display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:20px;
}
.skill-card {
  background:var(--card);border:1px solid var(--border);
  border-radius:20px;padding:28px;
  position:relative;overflow:hidden;
  transition:transform .3s,border-color .3s,box-shadow .3s;
}
.skill-card::before {
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--accent),transparent);
  transform:scaleX(0);transform-origin:left;transition:transform .4s;
}
.skill-card:hover{
  transform:translateY(-6px);
  border-color:rgba(157,111,255,.4);
  box-shadow:0 20px 60px rgba(157,111,255,0.12);
}
.skill-card:hover::before{transform:scaleX(1)}
.skill-icon-wrap {
  width:52px;height:52px;border-radius:14px;
  display:flex;align-items:center;justify-content:center;
  font-size:1.5rem;margin-bottom:18px;
}
.skill-card h3{font-size:1.05rem;font-weight:600;margin-bottom:14px}
.skill-tags{display:flex;flex-wrap:wrap;gap:8px}
.stag {
  font-size:.7rem;font-family:'JetBrains Mono',monospace;
  padding:5px 12px;border-radius:100px;
  border:1px solid var(--border);color:var(--muted);
  transition:color .2s,border-color .2s;
}
.skill-card:hover .stag{color:var(--accent);border-color:rgba(157,111,255,.35)}

/* ── Certifications ── */
.cert-grid {
  display:grid;grid-template-columns:repeat(auto-fit,minmax(330px,1fr));
  gap:24px;
}
.cert-card {
  background:var(--card);border-radius:24px;padding:32px;
  border:1px solid var(--border);
  position:relative;overflow:hidden;
  transition:transform .3s,box-shadow .3s;
  display:flex;flex-direction:column;gap:14px;
}
.cert-card:hover{transform:translateY(-6px);box-shadow:0 24px 80px rgba(0,0,0,0.4)}
.cert-badge {
  width:54px;height:54px;border-radius:16px;
  display:flex;align-items:center;justify-content:center;font-size:1.7rem;
}
.cert-org {
  font-family:'JetBrains Mono',monospace;font-size:.68rem;
  color:var(--muted);letter-spacing:.12em;text-transform:uppercase;
}
.cert-card h3{font-size:1.1rem;font-weight:600;line-height:1.45}
.cert-card p{font-size:.88rem;color:var(--muted);line-height:1.65;flex:1}
.cert-link {
  display:inline-flex;align-items:center;gap:8px;
  font-family:'JetBrains Mono',monospace;font-size:.78rem;
  color:var(--accent);text-decoration:none;font-weight:500;
  margin-top:4px;transition:gap .2s;
}
.cert-link:hover{gap:14px}
.cert-glow{
  position:absolute;bottom:-40px;right:-40px;
  width:140px;height:140px;border-radius:50%;
  filter:blur(60px);opacity:.25;pointer-events:none;
}

/* ── Timeline / Experience ── */
#internships{background:var(--surface)}
.timeline{display:flex;flex-direction:column;gap:28px}
.tl-item {
  display:grid;grid-template-columns:60px 1fr;
  gap:24px;align-items:start;
}
.tl-dot-wrap {
  display:flex;flex-direction:column;align-items:center;gap:0;
  padding-top:6px;
}
.tl-dot {
  width:44px;height:44px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-size:1.2rem;flex-shrink:0;
  border:1px solid var(--border);
  position:relative;z-index:1;
}
.tl-line {
  width:1px;flex:1;min-height:28px;
  background:linear-gradient(to bottom,var(--border),transparent);
  margin-top:4px;
}
.tl-item:last-child .tl-line{display:none}
.tl-body {
  background:var(--card);border:1px solid var(--border);
  border-radius:18px;padding:24px;
  transition:border-color .3s;
}
.tl-body:hover{border-color:rgba(157,111,255,.4)}
.tl-top {
  display:flex;justify-content:space-between;
  align-items:flex-start;gap:12px;flex-wrap:wrap;margin-bottom:10px;
}
.tl-co {
  font-family:'JetBrains Mono',monospace;font-size:.7rem;
  color:var(--teal);letter-spacing:.1em;text-transform:uppercase;
  margin-bottom:4px;
}
.tl-role{font-weight:600;font-size:1.05rem}
.tl-date {
  font-family:'JetBrains Mono',monospace;font-size:.7rem;
  color:var(--muted);background:rgba(140,100,255,.1);
  padding:4px 14px;border-radius:100px;white-space:nowrap;
}
.tl-desc{font-size:.9rem;color:#9898cc;line-height:1.68;margin-top:8px}
.tl-link {
  display:inline-flex;align-items:center;gap:6px;
  font-family:'JetBrains Mono',monospace;font-size:.78rem;
  color:var(--accent);text-decoration:none;margin-top:12px;
  transition:gap .2s;
}
.tl-link:hover{gap:10px}

/* ── Contact ── */
.contact-card {
  background:linear-gradient(135deg,rgba(157,111,255,.1),rgba(255,110,180,.06));
  border:1px solid rgba(157,111,255,.25);
  border-radius:28px;padding:64px;text-align:center;
  position:relative;overflow:hidden;
}
.contact-card::before {
  content:'';position:absolute;top:-100px;left:50%;transform:translateX(-50%);
  width:400px;height:400px;border-radius:50%;
  background:radial-gradient(circle,rgba(157,111,255,.12),transparent 60%);
  pointer-events:none;
  animation:cGlow 6s ease-in-out infinite;
}
@keyframes cGlow{0%,100%{opacity:.6}50%{opacity:1}}
.contact-card h2 {
  font-family:'Cormorant Garamond',serif;
  font-size:2.6rem;font-weight:600;margin-bottom:16px;
  position:relative;
}
.contact-card p{color:var(--muted);margin-bottom:40px;position:relative}
.contact-btns{display:flex;justify-content:center;gap:16px;flex-wrap:wrap;position:relative}

/* ── Footer ── */
footer {
  border-top:1px solid var(--border);
  padding:32px 28px;text-align:center;
  color:var(--muted);font-size:.8rem;
  font-family:'JetBrains Mono',monospace;
  position:relative;z-index:1;
}

/* ── Animations ── */
@keyframes fadeUp{from{opacity:0;transform:translateY(32px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0;transform:scale(.92)}to{opacity:1;transform:scale(1)}}

.reveal{opacity:0;transform:translateY(40px);transition:opacity .7s ease,transform .7s ease}
.reveal.visible{opacity:1;transform:translateY(0)}

/* ── Responsive ── */
@media(max-width:800px){
  .hero-inner{grid-template-columns:1fr;text-align:center}
  .hero-inner>*:first-child{order:2}
  .hero-photo{order:1;display:flex;justify-content:center}
  .photo-ring{width:240px;height:240px}
  .hero-btns{justify-content:center}
  .hero-desc{margin-inline:auto}
  .stats-inner{grid-template-columns:repeat(2,1fr)}
  .stat-item:nth-child(2){border-right:none}
  .stat-item:nth-child(3){border-top:1px solid var(--border)}
  .nav-links{display:none}
  .contact-card{padding:40px 24px}
  .badge-1,.badge-2,.badge-3{display:none}
  .tl-item{grid-template-columns:1fr}
  .tl-dot-wrap{display:none}
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-inner">
    <div class="nav-logo">SP</div>
    <ul class="nav-links">
      <li><a href="#skills">Skills</a></li>
      <li><a href="#certifications">Certifications</a></li>
      <li><a href="#internships">Experience</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-inner">
    <div>
      <div class="hero-eyebrow">Open to Opportunities</div>
      <h1 class="hero-name">S. <span class="name-grad">Parvatha&shy;varthini</span></h1>
      <p class="hero-title">Full Stack Developer &nbsp;·&nbsp; AI Enthusiast &nbsp;·&nbsp; Data Visualization</p>
      <p class="hero-desc">
        Computer Science student building at the intersection of full-stack development and artificial intelligence. Certified in AI, Data Visualization, and experienced through multiple industry internships.
      </p>
      <div class="hero-btns">
        <a href="https://www.linkedin.com/in/parvathavarthini-s-a4580b347" target="_blank" class="btn-main">Connect on LinkedIn ↗</a>
        <a href="#certifications" class="btn-ghost">View Certifications</a>
      </div>
    </div>

    <div class="hero-photo">
      <div class="photo-ring">
        <div class="photo-img">
          <img src="data:image/webp;base64,PHOTO_PLACEHOLDER" alt="S. Parvathavarthini"/>
        </div>
      </div>

      <!-- Floating badges -->
      <div class="badge badge-1">
        <span class="badge-dot" style="background:var(--teal)"></span>
        <span>AI Certified</span>
      </div>
      <div class="badge badge-2">
        <span class="badge-dot" style="background:var(--accent)"></span>
        <span>Full Stack Dev</span>
      </div>
      <div class="badge badge-3">
        <span class="badge-dot" style="background:var(--gold)"></span>
        <span>Power BI</span>
      </div>
    </div>
  </div>
</section>

<!-- STATS -->
<div class="stats reveal">
  <div class="stats-inner">
    <div class="stat-item"><span class="stat-num">3+</span><span class="stat-lbl">Internships</span></div>
    <div class="stat-item"><span class="stat-num">3</span><span class="stat-lbl">Certifications</span></div>
    <div class="stat-item"><span class="stat-num">10+</span><span class="stat-lbl">Technologies</span></div>
    <div class="stat-item"><span class="stat-num">2</span><span class="stat-lbl">AI Tracks</span></div>
  </div>
</div>

<!-- SKILLS -->
<section id="skills">
<div class="container">
  <div class="sec-eyebrow">What I Bring</div>
  <h2 class="sec-title">Skills &amp; Expertise</h2>
  <p class="sec-sub">A versatile skill set across front-end, back-end, AI, and data — built through courses, certifications, and real internships.</p>

  <div class="skills-wrap reveal">
    <div class="skill-card">
      <div class="skill-icon-wrap" style="background:rgba(157,111,255,.15)">🌐</div>
      <h3>Full Stack Development</h3>
      <div class="skill-tags">
        <span class="stag">HTML</span><span class="stag">CSS</span><span class="stag">JavaScript</span>
        <span class="stag">React JS</span><span class="stag">MySQL</span><span class="stag">Git</span><span class="stag">GitHub</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-icon-wrap" style="background:rgba(255,110,180,.15)">🤖</div>
      <h3>Prompt Engineering</h3>
      <div class="skill-tags">
        <span class="stag">AI Prompting</span><span class="stag">LLM Interaction</span>
        <span class="stag">Generative AI</span><span class="stag">ChatGPT</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-icon-wrap" style="background:rgba(0,229,195,.15)">📊</div>
      <h3>Data Visualization</h3>
      <div class="skill-tags">
        <span class="stag">Power BI</span><span class="stag">Data Analysis</span>
        <span class="stag">Dashboards</span><span class="stag">Business Intelligence</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-icon-wrap" style="background:rgba(255,209,102,.15)">🧠</div>
      <h3>Artificial Intelligence</h3>
      <div class="skill-tags">
        <span class="stag">ML Basics</span><span class="stag">Python</span>
        <span class="stag">AI Concepts</span><span class="stag">Data Analysis</span>
      </div>
    </div>
  </div>
</div>
</section>

<!-- CERTIFICATIONS -->
<section id="certifications">
<div class="container">
  <div class="sec-eyebrow">Credentials</div>
  <h2 class="sec-title">Certifications</h2>
  <p class="sec-sub">Verified credentials from globally recognized platforms in AI, data visualization, and full-stack development.</p>

  <div class="cert-grid reveal">
    <div class="cert-card" style="background:linear-gradient(145deg,var(--card),rgba(0,229,195,.04));border-color:rgba(0,229,195,.2)">
      <div class="cert-badge" style="background:rgba(0,229,195,.15)">📈</div>
      <div class="cert-org">Tata / Forage</div>
      <h3>Data Visualisation: Empowering Business with Effective Insights</h3>
      <p>Job simulation covering Power BI dashboards and business storytelling through data — real-world analytics experience with Tata Consultancy Services.</p>
      <a href="https://www.theforage.com/completion-certificates/ifobHAoMjQs9s6bKS/MyXvBcppsW2FkNYCX_ifobHAoMjQs9s6bKS_69f4105f8eadc1fc3f26233a_1777808016370_completion_certificate.pdf" target="_blank" class="cert-link">View Certificate →</a>
      <div class="cert-glow" style="background:var(--teal)"></div>
    </div>

    <div class="cert-card" style="background:linear-gradient(145deg,var(--card),rgba(157,111,255,.05));border-color:rgba(157,111,255,.25)">
      <div class="cert-badge" style="background:rgba(157,111,255,.15)">🤖</div>
      <div class="cert-org">Infosys Springboard</div>
      <h3>Artificial Intelligence — Virtual Internship (AI Track 7.0)</h3>
      <p>Comprehensive AI track covering ML fundamentals, Python for AI, Data Analysis, and core AI concepts through structured modules and project submissions.</p>
      <a href="https://drive.google.com/file/d/1EwzKskdgv4R4JIFnp5m4MEb1P0hkBrMu/view?usp=drivesdk" target="_blank" class="cert-link">View Certificate →</a>
      <div class="cert-glow" style="background:var(--accent)"></div>
    </div>

    <div class="cert-card" style="background:linear-gradient(145deg,var(--card),rgba(255,110,180,.04));border-color:rgba(255,110,180,.2)">
      <div class="cert-badge" style="background:rgba(255,110,180,.15)">💻</div>
      <div class="cert-org">Certification</div>
      <h3>Full Stack Development</h3>
      <p>Certified in full-stack web development spanning HTML, CSS, JavaScript, React JS, MySQL, and version control with Git &amp; GitHub.</p>
      <a href="https://drive.google.com/file/d/1SlstnFX6r3jwXE_ypa_m7296YrceessI/view?usp=drivesdk" target="_blank" class="cert-link">View Certificate →</a>
      <div class="cert-glow" style="background:var(--accent2)"></div>
    </div>
  </div>
</div>
</section>

<!-- EXPERIENCE -->
<section id="internships">
<div class="container">
  <div class="sec-eyebrow">Experience</div>
  <h2 class="sec-title">Internships</h2>
  <p class="sec-sub">Hands-on experience with leading industry platforms in AI and software development.</p>

  <div class="timeline reveal">
    <div class="tl-item">
      <div class="tl-dot-wrap">
        <div class="tl-dot" style="background:rgba(157,111,255,.15)">🚀</div>
        <div class="tl-line"></div>
      </div>
      <div class="tl-body">
        <div class="tl-top">
          <div>
            <div class="tl-co">Infosys Springboard</div>
            <div class="tl-role">Virtual Intern — AI Track (7.0)</div>
          </div>
          <span class="tl-date">2025–2026</span>
        </div>
        <p class="tl-desc">Participated in Infosys Springboard 7.0 Virtual Internship on the AI track. Covered Machine Learning basics, Python programming, Data Analysis, and core AI concepts through structured modules and project submissions.</p>
        <a href="https://drive.google.com/file/d/1yPPreO_uFIiENOj26clT6anSKXueJ7Ex/view?usp=drivesdk" target="_blank" class="tl-link">View Certificate →</a>
      </div>
    </div>

    <div class="tl-item">
      <div class="tl-dot-wrap">
        <div class="tl-dot" style="background:rgba(0,229,195,.15)">💼</div>
        <div class="tl-line"></div>
      </div>
      <div class="tl-body">
        <div class="tl-top">
          <div>
            <div class="tl-co">Scode Software Solutions</div>
            <div class="tl-role">Software Development Intern</div>
          </div>
          <span class="tl-date">2025</span>
        </div>
        <p class="tl-desc">Gained practical software development experience working on real-world projects in a professional environment at Scode Software Solutions.</p>
      </div>
    </div>

    <div class="tl-item">
      <div class="tl-dot-wrap">
        <div class="tl-dot" style="background:rgba(255,209,102,.15)">📊</div>
        <div class="tl-line"></div>
      </div>
      <div class="tl-body">
        <div class="tl-top">
          <div>
            <div class="tl-co">Tata / Forage</div>
            <div class="tl-role">Data Visualisation Virtual Intern</div>
          </div>
          <span class="tl-date">2025</span>
        </div>
        <p class="tl-desc">Completed Tata's Data Visualisation job simulation on Forage — developed business insight dashboards using Power BI and learned how data storytelling drives enterprise decision-making.</p>
        <a href="https://www.theforage.com/completion-certificates/ifobHAoMjQs9s6bKS/MyXvBcppsW2FkNYCX_ifobHAoMjQs9s6bKS_69f4105f8eadc1fc3f26233a_1777808016370_completion_certificate.pdf" target="_blank" class="tl-link">View Certificate →</a>
      </div>
    </div>
  </div>
</div>
</section>

<!-- CONTACT -->
<section id="contact">
<div class="container reveal">
  <div class="contact-card">
    <h2>Let's Connect ✦</h2>
    <p>Open to internships, collaborations, and exciting opportunities in AI, Full Stack Development &amp; Data.</p>
    <div class="contact-btns">
      <a href="https://www.linkedin.com/in/parvathavarthini-s-a4580b347" target="_blank" class="btn-main">LinkedIn Profile ↗</a>
    </div>
  </div>
</div>
</section>

<footer>
  ✦ S. Parvathavarthini &nbsp;·&nbsp; Full Stack Developer &amp; AI Enthusiast &nbsp;·&nbsp; 2025
</footer>

<script>
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('visible') });
}, {threshold:.1});
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
