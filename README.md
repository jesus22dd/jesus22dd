<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>jesus22dd — Developer Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Inter:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg-deep: #0a0c0f;
    --bg-card: #111417;
    --bg-card-hover: #161a20;
    --accent: #00e5ff;
    --accent-dim: rgba(0, 229, 255, 0.15);
    --accent-glow: rgba(0, 229, 255, 0.4);
    --text-primary: #e8eaed;
    --text-secondary: #7a8a9e;
    --border: rgba(0, 229, 255, 0.12);
    --font-display: 'Orbitron', sans-serif;
    --font-mono: 'Share Tech Mono', monospace;
    --font-body: 'Inter', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg-deep);
    color: var(--text-primary);
    font-family: var(--font-body);
    min-height: 100vh;
    overflow-x: hidden;
    position: relative;
  }

  /* ─── BACKGROUND GRID ─── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 50px 50px;
    pointer-events: none;
    z-index: 0;
  }

  /* ─── FLOATING ORBS ─── */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
    opacity: 0.35;
    animation: orbFloat 8s ease-in-out infinite alternate;
  }
  .orb-1 { width: 400px; height: 400px; background: #00e5ff; top: -100px; left: -100px; animation-delay: 0s; }
  .orb-2 { width: 300px; height: 300px; background: #0066cc; bottom: -80px; right: -80px; animation-delay: 2s; }
  .orb-3 { width: 200px; height: 200px; background: #00e5ff; top: 50%; left: 60%; animation-delay: 4s; opacity: 0.15; }

  @keyframes orbFloat {
    0% { transform: translate(0, 0) scale(1); }
    100% { transform: translate(30px, -40px) scale(1.1); }
  }

  /* ─── MAIN LAYOUT ─── */
  .container {
    position: relative; z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 24px 80px;
  }

  /* ─── HERO ─── */
  .hero {
    text-align: center;
    padding: 60px 0 50px;
  }
  .hero-avatar {
    width: 110px; height: 110px;
    border-radius: 50%;
    border: 2px solid var(--accent);
    box-shadow: 0 0 24px var(--accent-glow), inset 0 0 20px rgba(0,229,255,0.08);
    margin: 0 auto 28px;
    background: var(--bg-card);
    display: flex; align-items: center; justify-content: center;
    font-size: 42px;
    animation: avatarPulse 3s ease-in-out infinite;
  }
  @keyframes avatarPulse {
    0%, 100% { box-shadow: 0 0 24px var(--accent-glow), inset 0 0 20px rgba(0,229,255,0.08); }
    50% { box-shadow: 0 0 40px var(--accent-glow), inset 0 0 30px rgba(0,229,255,0.15); }
  }
  .hero h1 {
    font-family: var(--font-display);
    font-size: clamp(1.8rem, 5vw, 2.8rem);
    font-weight: 900;
    letter-spacing: 2px;
    color: var(--accent);
    text-shadow: 0 0 20px var(--accent-glow);
    opacity: 0; transform: translateY(20px);
    animation: fadeUp 0.8s 0.2s forwards;
  }
  .hero .tagline {
    font-family: var(--font-mono);
    font-size: 0.95rem;
    color: var(--text-secondary);
    margin-top: 10px;
    opacity: 0; transform: translateY(12px);
    animation: fadeUp 0.8s 0.45s forwards;
  }
  .hero .tagline span { color: var(--accent); }

  /* ─── BADGES ROW ─── */
  .badges {
    display: flex; flex-wrap: wrap; gap: 10px;
    justify-content: center;
    margin-top: 24px;
    opacity: 0;
    animation: fadeUp 0.8s 0.65s forwards;
  }
  .badge {
    font-family: var(--font-mono);
    font-size: 0.78rem;
    color: var(--accent);
    background: var(--accent-dim);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 6px 14px;
    letter-spacing: 0.5px;
    transition: background 0.3s, box-shadow 0.3s;
  }
  .badge:hover {
    background: rgba(0,229,255,0.25);
    box-shadow: 0 0 12px var(--accent-glow);
  }

  /* ─── SECTION TITLE ─── */
  .section-title {
    font-family: var(--font-display);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--text-secondary);
    margin-bottom: 18px;
    display: flex; align-items: center; gap: 12px;
  }
  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }
  .section-title .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 6px var(--accent-glow);
  }

  /* ─── ABOUT CARD ─── */
  .about-card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 30px 32px;
    margin-bottom: 40px;
    position: relative;
    overflow: hidden;
    opacity: 0; transform: translateY(24px);
    animation: fadeUp 0.7s 0.3s forwards;
    transition: border-color 0.3s;
  }
  .about-card:hover { border-color: var(--accent-glow); }
  .about-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
  }
  .about-card p {
    font-size: 0.95rem;
    line-height: 1.8;
    color: var(--text-secondary);
    font-weight: 300;
  }
  .about-card p .highlight { color: var(--text-primary); font-weight: 500; }

  /* ─── TECH GRID ─── */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 14px;
    margin-bottom: 40px;
  }
  .tech-card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 18px;
    display: flex; align-items: center; gap: 14px;
    opacity: 0; transform: translateY(18px);
    transition: background 0.3s, border-color 0.3s, transform 0.3s, box-shadow 0.3s;
    cursor: default;
  }
  .tech-card.visible { animation: fadeUp 0.5s forwards; }
  .tech-card:hover {
    background: var(--bg-card-hover);
    border-color: var(--accent-glow);
    transform: translateY(-3px);
    box-shadow: 0 8px 30px rgba(0,0,0,0.3), 0 0 12px var(--accent-dim);
  }
  .tech-icon {
    width: 38px; height: 38px;
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }
  .tech-card .tech-info { min-width: 0; }
  .tech-card .tech-name {
    font-family: var(--font-mono);
    font-size: 0.82rem;
    color: var(--text-primary);
    font-weight: 500;
  }
  .tech-card .tech-label {
    font-size: 0.68rem;
    color: var(--text-secondary);
    margin-top: 2px;
    text-transform: uppercase;
    letter-spacing: 0.8px;
  }

  /* Tech icon colors */
  .icon-dotnet { background: rgba(99,102,241,0.2); color: #818cf8; }
  .icon-nextjs { background: rgba(255,255,255,0.08); color: #fff; }
  .icon-php { background: rgba(139,99,217,0.2); color: #b388ff; }
  .icon-supabase { background: rgba(0,229,255,0.15); color: #00e5ff; }
  .icon-sql { background: rgba(255,167,38,0.15); color: #ffb74d; }
  .icon-winforms { background: rgba(99,102,241,0.2); color: #818cf8; }
  .icon-mysql { background: rgba(255,167,38,0.15); color: #ffb74d; }
  .icon-pg { background: rgba(68,149,203,0.2); color: #5ba3d9; }

  /* ─── INTEREST STRIP ─── */
  .interest-strip {
    background: linear-gradient(135deg, rgba(0,229,255,0.07), rgba(0,102,204,0.07));
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 22px 28px;
    margin-bottom: 40px;
    display: flex; align-items: center; gap: 18px;
    opacity: 0; transform: translateY(18px);
    transition: border-color 0.3s;
  }
  .interest-strip.visible { animation: fadeUp 0.6s forwards; }
  .interest-strip:hover { border-color: var(--accent-glow); }
  .interest-strip .icon-wrap {
    font-size: 1.6rem;
    flex-shrink: 0;
  }
  .interest-strip .text-wrap .label {
    font-family: var(--font-display);
    font-size: 0.68rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--text-secondary);
    margin-bottom: 4px;
  }
  .interest-strip .text-wrap p {
    font-size: 0.9rem;
    color: var(--text-secondary);
    font-weight: 300;
  }
  .interest-strip .text-wrap p span { color: var(--accent); font-weight: 500; }

  /* ─── CONTACT CARDS ─── */
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 14px;
    margin-bottom: 40px;
  }
  .contact-card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 22px;
    text-decoration: none;
    display: flex; align-items: center; gap: 14px;
    opacity: 0; transform: translateY(18px);
    transition: background 0.3s, border-color 0.3s, transform 0.3s, box-shadow 0.3s;
  }
  .contact-card.visible { animation: fadeUp 0.5s forwards; }
  .contact-card:hover {
    background: var(--bg-card-hover);
    border-color: var(--accent-glow);
    transform: translateY(-3px);
    box-shadow: 0 8px 30px rgba(0,0,0,0.3);
  }
  .contact-card .c-icon {
    width: 40px; height: 40px;
    border-radius: 10px;
    background: var(--accent-dim);
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem;
    color: var(--accent);
    flex-shrink: 0;
  }
  .contact-card .c-info .c-label {
    font-size: 0.67rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--text-secondary);
  }
  .contact-card .c-info .c-value {
    font-family: var(--font-mono);
    font-size: 0.82rem;
    color: var(--text-primary);
    margin-top: 2px;
  }

  /* ─── AVAILABILITY BADGE ─── */
  .availability {
    text-align: center;
    margin-bottom: 36px;
    opacity: 0;
    animation: fadeUp 0.6s 0.5s forwards;
  }
  .avail-badge {
    display: inline-flex; align-items: center; gap: 8px;
    font-family: var(--font-mono);
    font-size: 0.78rem;
    color: #4caf50;
    background: rgba(76,175,80,0.1);
    border: 1px solid rgba(76,175,80,0.25);
    border-radius: 20px;
    padding: 7px 16px;
  }
  .avail-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: #4caf50;
    box-shadow: 0 0 6px rgba(76,175,80,0.6);
    animation: blink 2s ease-in-out infinite;
  }
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  /* ─── FOOTER ─── */
  .footer {
    text-align: center;
    padding-top: 30px;
    border-top: 1px solid var(--border);
  }
  .footer p {
    font-family: var(--font-mono);
    font-size: 0.7rem;
    color: var(--text-secondary);
  }
  .footer p span { color: var(--accent); }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 500px) {
    .container { padding: 40px 16px 60px; }
    .hero { padding: 40px 0 36px; }
    .about-card { padding: 22px 20px; }
    .interest-strip { flex-direction: column; text-align: center; padding: 22px 18px; }
  }
</style>
</head>
<body>

<!-- Floating background orbs -->
<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="container">

  <!-- ─── HERO ─── -->
  <section class="hero">
    <div class="hero-avatar">👨‍💻</div>
    <h1>jesus22dd</h1>
    <p class="tagline">Full-Stack Developer &nbsp;|&nbsp; <span>Building things that work.</span></p>
    <div class="badges">
      <span class="badge">🎓 CS Student</span>
      <span class="badge">⚡ Open to Opportunities</span>
      <span class="badge">🌐 On-site & Remote</span>
    </div>
  </section>

  <!-- ─── AVAILABILITY ─── -->
  <div class="availability">
    <div class="avail-badge">
      <div class="avail-dot"></div>
      Available for internships & junior roles
    </div>
  </div>

  <!-- ─── ABOUT ─── -->
  <div class="section-title"><span class="dot"></span> About</div>
  <div class="about-card">
    <p>
      I'm a <span class="highlight">programming student</span> focused on building full-stack web applications.
      I work across the entire stack — from structured databases and backend APIs down to clean, responsive interfaces.
      I like keeping things <span class="highlight">clean, organized, and scalable</span>.
    </p>
  </div>

  <!-- ─── TECH STACK ─── -->
  <div class="section-title"><span class="dot"></span> Tech Stack</div>
  <div class="tech-grid" id="techGrid">
    <div class="tech-card" data-delay="0">
      <div class="tech-icon icon-dotnet">⬡</div>
      <div class="tech-info">
        <div class="tech-name">ASP.NET Web API</div>
        <div class="tech-label">Backend · C#</div>
      </div>
    </div>
    <div class="tech-card" data-delay="80">
      <div class="tech-icon icon-nextjs">▲</div>
      <div class="tech-info">
        <div class="tech-name">Next.js</div>
        <div class="tech-label">Frontend · React</div>
      </div>
    </div>
    <div class="tech-card" data-delay="160">
      <div class="tech-icon icon-php">◈</div>
      <div class="tech-info">
        <div class="tech-name">PHP</div>
        <div class="tech-label">Backend · Server</div>
      </div>
    </div>
    <div class="tech-card" data-delay="240">
      <div class="tech-icon icon-supabase">◎</div>
      <div class="tech-info">
        <div class="tech-name">Supabase</div>
        <div class="tech-label">Cloud · Database</div>
      </div>
    </div>
    <div class="tech-card" data-delay="320">
      <div class="tech-icon icon-sql">▪</div>
      <div class="tech-info">
        <div class="tech-name">SQL Server</div>
        <div class="tech-label">Relational DB</div>
      </div>
    </div>
    <div class="tech-card" data-delay="400">
      <div class="tech-icon icon-mysql">▪</div>
      <div class="tech-info">
        <div class="tech-name">MySQL</div>
        <div class="tech-label">Relational DB</div>
      </div>
    </div>
    <div class="tech-card" data-delay="480">
      <div class="tech-icon icon-pg">▪</div>
      <div class="tech-info">
        <div class="tech-name">PostgreSQL</div>
        <div class="tech-label">Relational DB</div>
      </div>
    </div>
    <div class="tech-card" data-delay="560">
      <div class="tech-icon icon-winforms">⬡</div>
      <div class="tech-info">
        <div class="tech-name">Windows Forms</div>
        <div class="tech-label">Desktop · .NET</div>
      </div>
    </div>
  </div>

  <!-- ─── INTEREST ─── -->
  <div class="interest-strip" id="interestStrip">
    <div class="icon-wrap">🔌</div>
    <div class="text-wrap">
      <div class="label">Passion</div>
      <p>Particularly interested in designing and building <span>REST APIs</span> — clean endpoints, solid architecture, and reliable data flow.</p>
    </div>
  </div>

  <!-- ─── CONTACT ─── -->
  <div class="section-title"><span class="dot"></span> Contact</div>
  <div class="contact-grid" id="contactGrid">
    <a href="https://linkedin.com/in/your-profile" class="contact-card" data-delay="0" target="_blank">
      <div class="c-icon">in</div>
      <div class="c-info">
        <div class="c-label">LinkedIn</div>
        <div class="c-value">your-profile</div>
      </div>
    </a>
    <a href="mailto:your-email@gmail.com" class="contact-card" data-delay="100">
      <div class="c-icon">✉</div>
      <div class="c-info">
        <div class="c-label">Email</div>
        <div class="c-value">your-email@gmail.com</div>
      </div>
    </a>
    <a href="https://your-portfolio.com" class="contact-card" data-delay="200" target="_blank">
      <div class="c-icon">◎</div>
      <div class="c-info">
        <div class="c-label">Portfolio</div>
        <div class="c-value">your-portfolio.com</div>
      </div>
    </a>
  </div>

  <!-- ─── FOOTER ─── -->
  <div class="footer">
    <p>Built with <span>code & caffeine</span> · jesus22dd <span>©</span> 2025</p>
  </div>

</div>

<script>
  // ─── Staggered reveal on scroll ───
  function revealOnScroll(containerId) {
    const cards = document.querySelectorAll(`#${containerId} [data-delay]`);
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const delay = entry.target.getAttribute('data-delay') || 0;
          setTimeout(() => entry.target.classList.add('visible'), delay);
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.15 });
    cards.forEach(card => observer.observe(card));
  }

  // Single-element reveal
  function revealSingle(id) {
    const el = document.getElementById(id);
    if (!el) return;
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.2 });
    observer.observe(el);
  }

  revealOnScroll('techGrid');
  revealOnScroll('contactGrid');
  revealSingle('interestStrip');
</script>
</body>
</html>
