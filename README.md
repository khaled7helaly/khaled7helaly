<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Khaled Mahmoud Helaly — GitHub Profile</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Space Grotesk', sans-serif;
    background: #0a0a0f;
    color: #e8e4ff;
    min-height: 100vh;
    overflow-x: hidden;
  }

  .bg-grid {
    position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 0;
    background-image:
      linear-gradient(rgba(139,92,246,0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(139,92,246,0.05) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .orb {
    position: fixed; border-radius: 50%; filter: blur(80px); pointer-events: none; z-index: 0;
  }
  .orb-1 { width: 400px; height: 400px; background: rgba(139,92,246,0.15); top: -100px; right: -100px; animation: float1 8s ease-in-out infinite; }
  .orb-2 { width: 300px; height: 300px; background: rgba(56,189,248,0.1); bottom: 100px; left: -80px; animation: float2 10s ease-in-out infinite; }
  .orb-3 { width: 200px; height: 200px; background: rgba(244,114,182,0.08); top: 50%; left: 40%; animation: float3 7s ease-in-out infinite; }

  @keyframes float1 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(-30px,30px)} }
  @keyframes float2 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(20px,-20px)} }
  @keyframes float3 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(-15px,25px)} }

  .wrapper {
    position: relative; z-index: 1;
    max-width: 760px; margin: 0 auto; padding: 40px 24px;
  }

  .hero {
    text-align: center; padding: 60px 0 50px;
    opacity: 0; animation: fadeUp 0.8s ease forwards 0.1s;
  }

  .avatar-ring {
    width: 100px; height: 100px; margin: 0 auto 24px;
    border-radius: 50%;
    background: linear-gradient(135deg, #8b5cf6, #38bdf8, #f472b6);
    padding: 3px;
    animation: spinRing 4s linear infinite;
  }
  @keyframes spinRing { from{filter:hue-rotate(0deg)} to{filter:hue-rotate(360deg)} }

  .avatar-inner {
    width: 100%; height: 100%; border-radius: 50%;
    background: #0f0f1a;
    display: flex; align-items: center; justify-content: center;
    font-size: 36px; font-weight: 700; color: #8b5cf6;
    font-family: 'JetBrains Mono', monospace;
  }

  .hero h1 {
    font-size: 32px; font-weight: 700; letter-spacing: -0.5px;
    background: linear-gradient(135deg, #e8e4ff, #8b5cf6, #38bdf8);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 6px;
  }

  .hero .role {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px; color: #8b5cf6;
    background: rgba(139,92,246,0.1); border: 1px solid rgba(139,92,246,0.3);
    display: inline-block; padding: 4px 14px; border-radius: 20px;
    margin-bottom: 20px;
  }

  .typed-line {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px; color: #94a3b8;
    min-height: 22px;
  }

  .cursor { animation: blink 1s step-end infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  .socials { display: flex; gap: 10px; justify-content: center; margin-top: 20px; flex-wrap: wrap; }
  .social-btn {
    display: flex; align-items: center; gap: 6px;
    padding: 7px 16px; border-radius: 8px;
    font-size: 12px; font-weight: 500; text-decoration: none;
    border: 1px solid rgba(255,255,255,0.1);
    background: rgba(255,255,255,0.04);
    color: #cbd5e1; cursor: pointer;
    transition: all 0.2s;
  }
  .social-btn:hover { background: rgba(139,92,246,0.15); border-color: rgba(139,92,246,0.5); color: #e8e4ff; transform: translateY(-2px); }

  .code-block {
    background: rgba(15,15,26,0.8); border: 1px solid rgba(139,92,246,0.2);
    border-radius: 14px; padding: 24px 28px; margin: 32px 0;
    opacity: 0; animation: fadeUp 0.8s ease forwards 0.3s;
    position: relative; overflow: hidden;
  }
  .code-block::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px;
    background: linear-gradient(90deg, transparent, rgba(139,92,246,0.6), transparent);
  }
  .code-dots { display: flex; gap: 6px; margin-bottom: 16px; }
  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #ff5f56; } .dot-y { background: #ffbd2e; } .dot-g { background: #27c93f; }

  .code-content {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px; line-height: 1.8;
  }
  .kw { color: #c084fc; } .fn { color: #38bdf8; } .str { color: #86efac; }
  .key { color: #e8e4ff; } .val { color: #fbbf24; } .cm { color: #475569; }
  .bracket { color: #94a3b8; }

  .section { margin: 36px 0; opacity: 0; }
  .section.visible { animation: fadeUp 0.7s ease forwards; }

  .section-label {
    font-size: 11px; font-weight: 600; letter-spacing: 2px; text-transform: uppercase;
    color: #8b5cf6; margin-bottom: 16px;
    display: flex; align-items: center; gap: 8px;
  }
  .section-label::after { content: ''; flex: 1; height: 1px; background: linear-gradient(90deg, rgba(139,92,246,0.3), transparent); }

  .tech-grid { display: flex; flex-wrap: wrap; gap: 8px; }
  .tech-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px; padding: 5px 12px; border-radius: 6px;
    border: 1px solid; transition: all 0.2s; cursor: default;
  }
  .tech-tag:hover { transform: translateY(-2px) scale(1.05); }

  .tag-js { color: #fbbf24; border-color: rgba(251,191,36,0.3); background: rgba(251,191,36,0.05); }
  .tag-js:hover { background: rgba(251,191,36,0.12); border-color: rgba(251,191,36,0.5); }
  .tag-ts { color: #38bdf8; border-color: rgba(56,189,248,0.3); background: rgba(56,189,248,0.05); }
  .tag-ts:hover { background: rgba(56,189,248,0.12); border-color: rgba(56,189,248,0.5); }
  .tag-react { color: #67e8f9; border-color: rgba(103,232,249,0.3); background: rgba(103,232,249,0.05); }
  .tag-react:hover { background: rgba(103,232,249,0.12); border-color: rgba(103,232,249,0.5); }
  .tag-node { color: #86efac; border-color: rgba(134,239,172,0.3); background: rgba(134,239,172,0.05); }
  .tag-node:hover { background: rgba(134,239,172,0.12); border-color: rgba(134,239,172,0.5); }
  .tag-mongo { color: #4ade80; border-color: rgba(74,222,128,0.3); background: rgba(74,222,128,0.05); }
  .tag-mongo:hover { background: rgba(74,222,128,0.12); border-color: rgba(74,222,128,0.5); }
  .tag-tail { color: #22d3ee; border-color: rgba(34,211,238,0.3); background: rgba(34,211,238,0.05); }
  .tag-tail:hover { background: rgba(34,211,238,0.12); border-color: rgba(34,211,238,0.5); }
  .tag-docker { color: #60a5fa; border-color: rgba(96,165,250,0.3); background: rgba(96,165,250,0.05); }
  .tag-docker:hover { background: rgba(96,165,250,0.12); border-color: rgba(96,165,250,0.5); }
  .tag-git { color: #f97316; border-color: rgba(249,115,22,0.3); background: rgba(249,115,22,0.05); }
  .tag-git:hover { background: rgba(249,115,22,0.12); border-color: rgba(249,115,22,0.5); }
  .tag-figma { color: #f472b6; border-color: rgba(244,114,182,0.3); background: rgba(244,114,182,0.05); }
  .tag-figma:hover { background: rgba(244,114,182,0.12); border-color: rgba(244,114,182,0.5); }

  .stats-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 12px; }
  .stat-card {
    background: rgba(15,15,26,0.6); border: 1px solid rgba(255,255,255,0.07);
    border-radius: 12px; padding: 18px;
    transition: all 0.3s; cursor: pointer; position: relative; overflow: hidden;
  }
  .stat-card::before {
    content: ''; position: absolute; inset: 0; border-radius: 12px;
    background: linear-gradient(135deg, rgba(139,92,246,0.05), transparent);
    opacity: 0; transition: opacity 0.3s;
  }
  .stat-card:hover { border-color: rgba(139,92,246,0.3); transform: translateY(-3px); }
  .stat-card:hover::before { opacity: 1; }
  .stat-icon { font-size: 20px; margin-bottom: 8px; }
  .stat-num { font-size: 28px; font-weight: 700; color: #8b5cf6; font-family: 'JetBrains Mono', monospace; }
  .stat-label { font-size: 12px; color: #64748b; margin-top: 2px; }

  .doing-list { display: flex; flex-direction: column; gap: 8px; }
  .doing-item {
    display: flex; align-items: center; gap: 10px;
    padding: 10px 14px; border-radius: 8px;
    background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.05);
    font-size: 13px; color: #94a3b8;
    transition: all 0.2s;
  }
  .doing-item:hover { background: rgba(139,92,246,0.05); border-color: rgba(139,92,246,0.2); color: #e8e4ff; }
  .doing-dot { width: 6px; height: 6px; border-radius: 50%; background: #8b5cf6; animation: pulse 2s ease-in-out infinite; flex-shrink: 0; }
  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.5;transform:scale(0.8)} }

  .quote-box {
    border-left: 2px solid #8b5cf6; padding: 16px 20px;
    background: rgba(139,92,246,0.05); border-radius: 0 10px 10px 0;
    font-style: italic; font-size: 14px; color: #94a3b8;
    margin: 32px 0;
    opacity: 0; animation: fadeUp 0.8s ease forwards 0.6s;
  }
  .quote-box span { color: #8b5cf6; font-weight: 500; }

  .footer {
    text-align: center; padding: 30px 0 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px; color: #334155;
    opacity: 0; animation: fadeUp 0.8s ease forwards 0.8s;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: rgba(139,92,246,0.4); border-radius: 2px; }
</style>
</head>
<body>

<div class="bg-grid"></div>
<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="wrapper">

  <div class="hero">
    <div class="avatar-ring">
      <div class="avatar-inner">KH</div>
    </div>
    <h1>Khaled Mahmoud Helaly</h1>
    <div class="role">Full Stack Developer · CS Student</div>
    <div class="typed-line">
      <span id="typed"></span><span class="cursor">|</span>
    </div>
    <div class="socials">
      <a class="social-btn" href="https://www.linkedin.com/in/khaledhelaly7/" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a class="social-btn" href="https://github.com/khaled7helaly/" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
        GitHub
      </a>
      <a class="social-btn" href="mailto:helalykhaled3@gmail.com">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        Gmail
      </a>
    </div>
  </div>

  <div class="code-block">
    <div class="code-dots"><div class="dot dot-r"></div><div class="dot dot-y"></div><div class="dot dot-g"></div></div>
    <div class="code-content">
      <span class="kw">const</span> <span class="fn">khaled</span> <span class="bracket">=</span> <span class="bracket">{</span><br>
      &nbsp;&nbsp;<span class="key">name</span><span class="bracket">:</span>       <span class="str">"Khaled Mahmoud"</span><span class="bracket">,</span><br>
      &nbsp;&nbsp;<span class="key">location</span><span class="bracket">:</span>   <span class="str">"Alexandria, Egypt 🇪🇬"</span><span class="bracket">,</span><br>
      &nbsp;&nbsp;<span class="key">university</span><span class="bracket">:</span> <span class="str">"Suez University — CS Final Year"</span><span class="bracket">,</span><br>
      &nbsp;&nbsp;<span class="key">role</span><span class="bracket">:</span>       <span class="bracket">[</span><span class="str">"Full Stack Dev"</span><span class="bracket">,</span> <span class="str">"DevOps Explorer"</span><span class="bracket">]</span><span class="bracket">,</span><br>
      &nbsp;&nbsp;<span class="key">passion</span><span class="bracket">:</span>    <span class="str">"Turning ideas into real products 💡"</span><span class="bracket">,</span><br>
      &nbsp;&nbsp;<span class="key">available</span><span class="bracket">:</span>  <span class="val">true</span> <span class="cm">// open to opportunities</span><br>
      <span class="bracket">};</span>
    </div>
  </div>

  <div class="section" id="s1">
    <div class="section-label">Tech Stack</div>
    <div class="tech-grid">
      <span class="tech-tag tag-js">JavaScript</span>
      <span class="tech-tag tag-ts">TypeScript</span>
      <span class="tech-tag tag-react">React</span>
      <span class="tech-tag tag-node">Node.js</span>
      <span class="tech-tag tag-node">Express.js</span>
      <span class="tech-tag tag-mongo">MongoDB</span>
      <span class="tech-tag tag-tail">Tailwind CSS</span>
      <span class="tech-tag tag-docker">Docker</span>
      <span class="tech-tag tag-git">Git</span>
      <span class="tech-tag tag-figma">Figma</span>
    </div>
  </div>

  <div class="section" id="s2">
    <div class="section-label">GitHub Stats</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-icon">⭐</div>
        <div class="stat-num" id="stars">0</div>
        <div class="stat-label">Stars Earned</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon">🔥</div>
        <div class="stat-num" id="streak">0</div>
        <div class="stat-label">Day Streak</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon">📦</div>
        <div class="stat-num" id="repos">0</div>
        <div class="stat-label">Repositories</div>
      </div>
    </div>
  </div>

  <div class="section" id="s3">
    <div class="section-label">Currently Working On</div>
    <div class="doing-list">
      <div class="doing-item"><div class="doing-dot"></div>Building full-stack apps with Node.js + React</div>
      <div class="doing-item"><div class="doing-dot" style="animation-delay:0.3s"></div>Learning Docker & containerization</div>
      <div class="doing-item"><div class="doing-dot" style="animation-delay:0.6s"></div>Improving UI/UX design skills with Figma</div>
      <div class="doing-item"><div class="doing-dot" style="animation-delay:0.9s"></div>Mastering Advanced JavaScript concepts</div>
    </div>
  </div>

  <div class="quote-box">
    "First, solve the problem. Then, write the code." — <span>John Johnson</span>
  </div>

  <div class="footer">
    &lt;/&gt; built with passion · Alexandria, Egypt · 2025
  </div>

</div>

<script>
  const lines = [
    "Hey there! I'm Khaled 👋",
    "Full Stack Developer 🚀",
    "Node.js + React Enthusiast ⚡",
    "DevOps Explorer 🐳",
    "Always learning, always building 🔥"
  ];
  let lineIdx = 0, charIdx = 0, deleting = false;
  const el = document.getElementById('typed');

  function type() {
    const line = lines[lineIdx];
    if (!deleting) {
      el.textContent = line.slice(0, ++charIdx);
      if (charIdx === line.length) { deleting = true; setTimeout(type, 2000); return; }
    } else {
      el.textContent = line.slice(0, --charIdx);
      if (charIdx === 0) { deleting = false; lineIdx = (lineIdx + 1) % lines.length; setTimeout(type, 300); return; }
    }
    setTimeout(type, deleting ? 40 : 70);
  }
  setTimeout(type, 1000);

  function countUp(id, target, duration) {
    const el = document.getElementById(id);
    let start = 0, step = target / (duration / 16);
    const run = () => {
      start = Math.min(start + step, target);
      el.textContent = Math.round(start);
      if (start < target) requestAnimationFrame(run);
    };
    run();
  }

  const sections = document.querySelectorAll('.section');
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        if (e.target.id === 's2') {
          setTimeout(() => { countUp('stars', 47, 1200); countUp('streak', 23, 1000); countUp('repos', 18, 900); }, 200);
        }
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.15 });

  sections.forEach((s, i) => {
    s.style.animationDelay = (0.4 + i * 0.15) + 's';
    observer.observe(s);
  });
</script>
</body>
</html>
