<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jother043 — José Miguel Gutiérrez</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Cabinet+Grotesk:wght@400;500;700;800&display=swap" rel="stylesheet">
<style>
:root {
  --bg:       #0d1117;
  --bg1:      #161b22;
  --bg2:      #1c2128;
  --border:   #30363d;
  --border2:  #3d4450;
  --green:    #3fb950;
  --green-d:  #238636;
  --cyan:     #58a6ff;
  --amber:    #e3b341;
  --purple:   #bc8cff;
  --red:      #f85149;
  --text:     #e6edf3;
  --text2:    #8b949e;
  --text3:    #484f58;
  --mono:     'DM Mono', monospace;
  --sans:     'Cabinet Grotesk', sans-serif;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--sans);
  font-size: 15px;
  line-height: 1.6;
  overflow-x: hidden;
}

/* ── GRID BG ── */
body::before {
  content: '';
  position: fixed; inset: 0;
  background-image:
    linear-gradient(rgba(48,54,61,0.35) 1px, transparent 1px),
    linear-gradient(90deg, rgba(48,54,61,0.35) 1px, transparent 1px);
  background-size: 48px 48px;
  pointer-events: none; z-index: 0;
}

/* ── LAYOUT ── */
.page { position: relative; z-index: 1; max-width: 860px; margin: 0 auto; padding: 0 1.5rem; }

/* ── HERO ── */
.hero {
  padding: 5rem 0 3rem;
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 2rem;
  align-items: start;
  border-bottom: 1px solid var(--border);
}
@media(max-width:600px){ .hero { grid-template-columns: 1fr; } .avatar-wrap { display: none; } }

.hero-left {}

.status-pill {
  display: inline-flex; align-items: center; gap: 7px;
  font-family: var(--mono); font-size: 11px; letter-spacing: 0.1em;
  color: var(--green);
  border: 1px solid rgba(63,185,80,0.3);
  background: rgba(63,185,80,0.07);
  padding: 5px 12px; border-radius: 20px;
  margin-bottom: 1.5rem;
  animation: fadeIn 0.5s ease both;
}
.status-dot {
  width: 6px; height: 6px; border-radius: 50%; background: var(--green);
  animation: blink 2s ease-in-out infinite;
}
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.4} }

.hero-name {
  font-size: clamp(2.4rem, 5vw, 4rem);
  font-weight: 800;
  letter-spacing: -0.03em;
  line-height: 1.05;
  margin-bottom: 0.3rem;
  animation: fadeIn 0.5s 0.08s ease both;
}
.hero-handle {
  font-family: var(--mono); font-size: 1rem;
  color: var(--text3); margin-bottom: 1.2rem;
  animation: fadeIn 0.5s 0.14s ease both;
}
.hero-handle span { color: var(--cyan); }

.hero-bio {
  font-size: 1rem; color: var(--text2);
  max-width: 500px; line-height: 1.75;
  margin-bottom: 1.75rem;
  font-weight: 400;
  animation: fadeIn 0.5s 0.2s ease both;
}
.hero-bio strong { color: var(--text); font-weight: 700; }

.hero-meta {
  display: flex; flex-wrap: wrap; gap: 16px;
  margin-bottom: 1.75rem;
  animation: fadeIn 0.5s 0.26s ease both;
}
.meta-item {
  display: flex; align-items: center; gap: 6px;
  font-family: var(--mono); font-size: 12px; color: var(--text2);
}
.meta-item svg { opacity: 0.5; flex-shrink: 0; }

.hero-links {
  display: flex; gap: 10px; flex-wrap: wrap;
  animation: fadeIn 0.5s 0.32s ease both;
}
.link-btn {
  display: inline-flex; align-items: center; gap: 7px;
  font-family: var(--mono); font-size: 12px; letter-spacing: 0.05em;
  padding: 7px 14px; border-radius: 6px;
  text-decoration: none; transition: all 0.17s;
  border: 1px solid var(--border2); color: var(--text2);
  background: transparent;
}
.link-btn:hover { border-color: var(--text2); color: var(--text); transform: translateY(-1px); }
.link-btn.primary { background: var(--green-d); border-color: var(--green-d); color: #fff; }
.link-btn.primary:hover { background: #196c2e; }

/* Avatar */
.avatar-wrap {
  position: relative;
  animation: fadeIn 0.5s 0.1s ease both;
}
.avatar-ring {
  width: 130px; height: 130px; border-radius: 50%;
  border: 2px solid var(--border2);
  padding: 4px;
  background: var(--bg1);
  position: relative;
}
.avatar-inner {
  width: 100%; height: 100%; border-radius: 50%;
  background: linear-gradient(135deg, var(--bg2) 0%, #2d3748 100%);
  display: flex; align-items: center; justify-content: center;
  font-size: 3rem;
  overflow: hidden;
}
.avatar-inner img { width: 100%; height: 100%; object-fit: cover; border-radius: 50%; }
.level-badge-hero {
  position: absolute; bottom: 4px; right: 4px;
  font-family: var(--mono); font-size: 10px;
  background: var(--amber); color: #000;
  padding: 2px 7px; border-radius: 10px; font-weight: 500;
  border: 2px solid var(--bg);
}

/* ── SECTIONS ── */
.section { padding: 3rem 0; border-bottom: 1px solid var(--border); }
.section:last-child { border-bottom: none; }

.sec-label {
  font-family: var(--mono); font-size: 10px; letter-spacing: 0.14em;
  color: var(--text3); margin-bottom: 0.4rem;
  display: flex; align-items: center; gap: 6px;
}
.sec-label::before { content: '//'; color: var(--border2); }
h2.sec-title {
  font-size: 1.4rem; font-weight: 800;
  letter-spacing: -0.02em; margin-bottom: 1.5rem; color: var(--text);
}

/* ── SKILL GROUPS ── */
.skills-wrap { display: flex; flex-direction: column; gap: 1.25rem; }
.skill-group { }
.skill-group-label {
  font-family: var(--mono); font-size: 10px; letter-spacing: 0.1em;
  color: var(--text3); margin-bottom: 0.6rem;
}
.skill-pills { display: flex; flex-wrap: wrap; gap: 8px; }
.skill-pill {
  display: flex; align-items: center; gap: 6px;
  font-family: var(--mono); font-size: 12px;
  padding: 5px 12px; border-radius: 5px;
  background: var(--bg1); border: 1px solid var(--border);
  color: var(--text2); transition: border-color 0.17s, color 0.17s;
}
.skill-pill:hover { border-color: var(--border2); color: var(--text); }
.skill-pill .dot { width: 7px; height: 7px; border-radius: 50%; flex-shrink: 0; }
.dot-green  { background: var(--green); }
.dot-cyan   { background: var(--cyan); }
.dot-amber  { background: var(--amber); }
.dot-purple { background: var(--purple); }
.dot-red    { background: var(--red); }
.dot-gray   { background: var(--text3); }

/* ── EXPERIENCE TIMELINE ── */
.timeline { display: flex; flex-direction: column; gap: 0; }
.tl-item {
  display: grid; grid-template-columns: 110px 1fr;
  gap: 1.25rem; padding-bottom: 2rem;
}
.tl-item:last-child { padding-bottom: 0; }
.tl-left { text-align: right; padding-top: 3px; }
.tl-date { font-family: var(--mono); font-size: 11px; color: var(--text3); line-height: 1.6; }
.tl-right { position: relative; padding-left: 1.5rem; }
.tl-line { position: absolute; left: 0; top: 10px; bottom: -2rem; width: 1px; background: var(--border); }
.tl-item:last-child .tl-line { display: none; }
.tl-dot { position: absolute; left: -4px; top: 5px; width: 9px; height: 9px; border-radius: 50%; background: var(--bg); border: 2px solid var(--green); }
.tl-role { font-size: 0.93rem; font-weight: 700; color: var(--text); margin-bottom: 2px; }
.tl-company { font-family: var(--mono); font-size: 11px; color: var(--cyan); margin-bottom: 0.5rem; }
.tl-desc { font-size: 0.83rem; color: var(--text2); line-height: 1.7; }
.tl-tags { display: flex; flex-wrap: wrap; gap: 5px; margin-top: 0.5rem; }
.tl-tag {
  font-family: var(--mono); font-size: 10px; color: var(--text3);
  padding: 2px 7px; background: var(--bg2); border: 1px solid var(--border); border-radius: 3px;
}
@media(max-width:500px){
  .tl-item { grid-template-columns: 1fr; }
  .tl-left { text-align: left; }
}

/* ── PROJECTS ── */
.projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px,1fr)); gap: 10px; }
.proj-card {
  background: var(--bg1); border: 1px solid var(--border);
  border-radius: 8px; padding: 1.1rem;
  transition: border-color 0.2s, transform 0.2s;
  text-decoration: none; display: block;
}
.proj-card:hover { border-color: var(--border2); transform: translateY(-2px); }
.proj-card.featured { border-color: rgba(63,185,80,0.35); }
.proj-card.featured::before {
  content: '';
  display: block; height: 2px; margin: -1.1rem -1.1rem 1rem;
  background: linear-gradient(90deg, var(--green), var(--cyan));
  border-radius: 8px 8px 0 0;
}
.proj-top { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 0.6rem; }
.proj-icon { font-size: 1.3rem; }
.proj-star { font-family: var(--mono); font-size: 10px; color: var(--amber); display: flex; align-items: center; gap: 4px; }
.proj-name { font-size: 0.9rem; font-weight: 700; color: var(--text); margin-bottom: 0.35rem; }
.proj-desc { font-size: 0.8rem; color: var(--text2); line-height: 1.6; margin-bottom: 0.75rem; }
.proj-tags { display: flex; flex-wrap: wrap; gap: 5px; }
.proj-tag { font-family: var(--mono); font-size: 10px; color: var(--text3); padding: 2px 7px; background: var(--bg2); border: 1px solid var(--border); border-radius: 3px; }

/* ── EDUCATION ── */
.edu-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px,1fr)); gap: 10px; }
.edu-card {
  background: var(--bg1); border: 1px solid var(--border);
  border-radius: 8px; padding: 1.1rem;
  transition: border-color 0.18s;
}
.edu-card:hover { border-color: var(--border2); }
.edu-icon { font-size: 1.4rem; margin-bottom: 0.6rem; }
.edu-title { font-size: 0.9rem; font-weight: 700; color: var(--text); margin-bottom: 3px; }
.edu-center { font-family: var(--mono); font-size: 11px; color: var(--cyan); margin-bottom: 3px; }
.edu-year { font-family: var(--mono); font-size: 10px; color: var(--text3); }
.edu-note { font-size: 0.8rem; color: var(--text2); margin-top: 0.4rem; }

/* ── CERT ── */
.cert-row {
  margin-top: 10px;
  display: flex; align-items: center; gap: 12px;
  background: var(--bg1); border: 1px solid var(--border);
  border-radius: 8px; padding: 1rem 1.25rem;
}
.cert-badge-box {
  font-family: var(--mono); font-size: 11px;
  color: var(--green); background: rgba(63,185,80,0.08);
  border: 1px solid rgba(63,185,80,0.3);
  padding: 5px 10px; border-radius: 5px; white-space: nowrap; flex-shrink: 0;
}
.cert-title { font-size: 0.9rem; font-weight: 700; color: var(--text); }
.cert-sub { font-family: var(--mono); font-size: 10px; color: var(--text3); margin-top: 2px; }

/* ── STATS ── */
.stats-strip {
  display: grid; grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
  gap: 1px; background: var(--border); border-radius: 8px; overflow: hidden;
  margin-bottom: 1.5rem;
}
.stat-box { background: var(--bg1); padding: 1.1rem; text-align: center; }
.stat-num { font-size: 1.5rem; font-weight: 800; color: var(--green); letter-spacing: -0.03em; }
.stat-lbl { font-family: var(--mono); font-size: 10px; color: var(--text3); letter-spacing: 0.08em; margin-top: 3px; }

/* ── CONTACT ── */
.contact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px,1fr)); gap: 10px; }
.contact-item {
  display: flex; align-items: center; gap: 12px;
  padding: 0.85rem 1rem;
  background: var(--bg1); border: 1px solid var(--border);
  border-radius: 8px; text-decoration: none;
  color: var(--text); transition: border-color 0.17s, color 0.17s;
}
.contact-item:hover { border-color: var(--border2); color: var(--green); }
.contact-icon { font-family: var(--mono); font-size: 11px; color: var(--text3); min-width: 28px; }
.contact-lbl { font-family: var(--mono); font-size: 9px; color: var(--text3); letter-spacing: 0.1em; margin-bottom: 2px; }
.contact-val { font-size: 0.85rem; color: var(--text); }

/* ── FOOTER ── */
footer {
  padding: 2rem 0 3rem;
  font-family: var(--mono); font-size: 11px; color: var(--text3);
  display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 8px;
}
footer a { color: var(--text2); text-decoration: none; }
footer a:hover { color: var(--text); }

/* ── ANIM ── */
@keyframes fadeIn { from{ opacity:0; transform:translateY(-10px); } to{ opacity:1; transform:none; } }
.reveal { opacity:0; transform:translateY(14px); transition: opacity 0.55s ease, transform 0.55s ease; }
.reveal.in { opacity:1; transform:none; }
.d1{transition-delay:.07s} .d2{transition-delay:.14s} .d3{transition-delay:.21s}
</style>
</head>
<body>
<div class="page">

  <!-- ══ HERO ══ -->
  <div class="hero">
    <div class="hero-left">
      <div class="status-pill"><div class="status-dot"></div>Disponible · Open to work</div>

      <h1 class="hero-name">José Miguel<br>Gutiérrez</h1>
      <div class="hero-handle">@<span>Jother043</span> · github.com/Jother043</div>

      <p class="hero-bio">
        Desarrollador <strong>backend y DevOps</strong> con base en Sevilla.
        Especializado en <strong>Java, Spring Boot y Python</strong>.
        Apasionado por las APIs REST, la automatización de procesos y el código limpio que escala.
      </p>

      <div class="hero-meta">
        <div class="meta-item">
          <svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
          Jother043
        </div>
        <div class="meta-item">
          <svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0a8 8 0 1 1 0 16A8 8 0 0 1 8 0ZM1.5 8a6.5 6.5 0 1 0 13 0 6.5 6.5 0 0 0-13 0Zm7-3.25v2.992l2.028.812a.75.75 0 0 1-.557 1.392l-2.5-1A.751.751 0 0 1 7 8.25v-3.5a.75.75 0 0 1 1.5 0Z"/></svg>
          Disponible
        </div>
        <div class="meta-item">
          <svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 1a2 2 0 0 1 2 2v4H6V3a2 2 0 0 1 2-2zm3 6V3a3 3 0 0 0-6 0v4a2 2 0 0 0-2 2v5a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2V9a2 2 0 0 0-2-2z"/></svg>
          Sevilla, España
        </div>
        <div class="meta-item">
          <svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M0 1.75C0 .784.784 0 1.75 0h12.5C15.216 0 16 .784 16 1.75v9.5A1.75 1.75 0 0 1 14.25 13H8.06l-2.573 2.573A1.458 1.458 0 0 1 3 14.543V13H1.75A1.75 1.75 0 0 1 0 11.25Zm1.75-.25a.25.25 0 0 0-.25.25v9.5c0 .138.112.25.25.25h2a.75.75 0 0 1 .75.75v2.19l2.72-2.72a.749.749 0 0 1 .53-.22h6.5a.25.25 0 0 0 .25-.25v-9.5a.25.25 0 0 0-.25-.25Z"/></svg>
          Inglés C1 (EF SET)
        </div>
      </div>

      <div class="hero-links">
        <a href="https://www.linkedin.com/in/jose-miguel-gutierrez-hernandez-392261185/" target="_blank" class="link-btn primary">LinkedIn ↗</a>
        <a href="https://github.com/Jother043" target="_blank" class="link-btn">GitHub</a>
        <a href="mailto:tu@email.com" class="link-btn">Email</a>
      </div>
    </div>

    <div class="avatar-wrap">
      <div class="avatar-ring">
        <div class="avatar-inner">
          <!-- Puedes reemplazar esto con: <img src="https://github.com/Jother043.png" alt="Avatar"> -->
          🧑‍💻
        </div>
      </div>
      <div class="level-badge-hero">DevOps Dev</div>
    </div>
  </div>

  <!-- ══ SOBRE MÍ ══ -->
  <div class="section">
    <div class="sec-label reveal">sobre mí</div>
    <h2 class="sec-title reveal d1">Un poco de contexto</h2>

    <div class="stats-strip reveal d2">
      <div class="stat-box"><div class="stat-num">4+</div><div class="stat-lbl">AÑOS EXP.</div></div>
      <div class="stat-box"><div class="stat-num">20+</div><div class="stat-lbl">REPOS</div></div>
      <div class="stat-box"><div class="stat-num">DAM</div><div class="stat-lbl">GRADO SUP.</div></div>
      <div class="stat-box"><div class="stat-num">C1</div><div class="stat-lbl">INGLÉS</div></div>
      <div class="stat-box"><div class="stat-num">5</div><div class="stat-lbl">EMPRESAS</div></div>
    </div>

    <p class="reveal d3" style="font-size:0.93rem;color:var(--text2);line-height:1.8;max-width:680px;">
      Empecé en sistemas microinformáticos y acabé enamorándome del backend. Hoy trabajo como
      <strong style="color:var(--text)">DevOps Developer en Ampliqure</strong> (Sevilla), donde mezclo automatización,
      integración continua y desarrollo de software. Tengo el Grado Superior en <strong style="color:var(--text)">DAM</strong>
      por el IES Padre José Miravett y certificación de inglés <strong style="color:var(--text)">C1</strong>.
      Mi stack principal es Java + Spring Boot, pero me defiendo bien con Python, SQL y todo lo que gira alrededor del ciclo de vida de una app.
    </p>
  </div>

  <!-- ══ SKILLS ══ -->
  <div class="section">
    <div class="sec-label reveal">habilidades</div>
    <h2 class="sec-title reveal d1">Stack técnico</h2>

    <div class="skills-wrap reveal d2">
      <div class="skill-group">
        <div class="skill-group-label">LENGUAJES</div>
        <div class="skill-pills">
          <div class="skill-pill"><div class="dot dot-amber"></div>Java</div>
          <div class="skill-pill"><div class="dot dot-green"></div>Python</div>
          <div class="skill-pill"><div class="dot dot-cyan"></div>SQL</div>
          <div class="skill-pill"><div class="dot dot-purple"></div>Visual Basic .NET</div>
          <div class="skill-pill"><div class="dot dot-amber"></div>JavaScript</div>
          <div class="skill-pill"><div class="dot dot-gray"></div>Bash / Shell</div>
        </div>
      </div>

      <div class="skill-group">
        <div class="skill-group-label">FRAMEWORKS & LIBRERÍAS</div>
        <div class="skill-pills">
          <div class="skill-pill"><div class="dot dot-amber"></div>Spring Boot</div>
          <div class="skill-pill"><div class="dot dot-amber"></div>Hibernate / JPA</div>
          <div class="skill-pill"><div class="dot dot-amber"></div>Spring MVC</div>
          <div class="skill-pill"><div class="dot dot-cyan"></div>Swagger / OpenAPI</div>
          <div class="skill-pill"><div class="dot dot-cyan"></div>Maven</div>
          <div class="skill-pill"><div class="dot dot-purple"></div>JavaFX</div>
          <div class="skill-pill"><div class="dot dot-purple"></div>Android SDK</div>
          <div class="skill-pill"><div class="dot dot-green"></div>Jetpack Compose</div>
        </div>
      </div>

      <div class="skill-group">
        <div class="skill-group-label">BASES DE DATOS</div>
        <div class="skill-pills">
          <div class="skill-pill"><div class="dot dot-cyan"></div>PostgreSQL</div>
          <div class="skill-pill"><div class="dot dot-cyan"></div>MySQL</div>
          <div class="skill-pill"><div class="dot dot-cyan"></div>SQL Server</div>
          <div class="skill-pill"><div class="dot dot-amber"></div>Oracle / PLSQL</div>
          <div class="skill-pill"><div class="dot dot-green"></div>MongoDB</div>
          <div class="skill-pill"><div class="dot dot-gray"></div>SQLite</div>
        </div>
      </div>

      <div class="skill-group">
        <div class="skill-group-label">DEVOPS & HERRAMIENTAS</div>
        <div class="skill-pills">
          <div class="skill-pill"><div class="dot dot-green"></div>Git / GitHub</div>
          <div class="skill-pill"><div class="dot dot-green"></div>CI / CD</div>
          <div class="skill-pill"><div class="dot dot-amber"></div>Docker</div>
          <div class="skill-pill"><div class="dot dot-cyan"></div>Linux / TTY</div>
          <div class="skill-pill"><div class="dot dot-purple"></div>Automatización</div>
          <div class="skill-pill"><div class="dot dot-gray"></div>Redes LAN / WAN</div>
        </div>
      </div>
    </div>
  </div>

  <!-- ══ EXPERIENCIA ══ -->
  <div class="section">
    <div class="sec-label reveal">trayectoria</div>
    <h2 class="sec-title reveal d1">Experiencia profesional</h2>

    <div class="timeline reveal d2">

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">2025<br>Presente</div></div>
        <div class="tl-right">
          <div class="tl-line"></div><div class="tl-dot"></div>
          <div class="tl-role">DevOps Developer</div>
          <div class="tl-company">Ampliqure · Sevilla / Remoto</div>
          <div class="tl-desc">Automatización de procesos y desarrollo de software en entorno DevOps. Integración y despliegue continuo de aplicaciones en producción.</div>
          <div class="tl-tags"><span class="tl-tag">DevOps</span><span class="tl-tag">CI/CD</span><span class="tl-tag">Automatización</span><span class="tl-tag">Python</span></div>
        </div>
      </div>

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">jun 2024<br>ago 2024</div></div>
        <div class="tl-right">
          <div class="tl-line"></div><div class="tl-dot"></div>
          <div class="tl-role">Backend Developer Junior (prácticas)</div>
          <div class="tl-company">Sillsoft · Sevilla</div>
          <div class="tl-desc">Desarrollo de APIs REST con Spring Boot e Hibernate. Integración con SQL Server y documentación con Swagger/OpenAPI.</div>
          <div class="tl-tags"><span class="tl-tag">Java</span><span class="tl-tag">Spring Boot</span><span class="tl-tag">Hibernate</span><span class="tl-tag">Swagger</span><span class="tl-tag">SQL Server</span></div>
        </div>
      </div>

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">sep 2023<br>actualidad</div></div>
        <div class="tl-right">
          <div class="tl-line"></div><div class="tl-dot"></div>
          <div class="tl-role">Cajero y Responsable de Sección</div>
          <div class="tl-company">Lidl · Sevilla</div>
          <div class="tl-desc">Gestión de equipo, administración de sistemas SQL Server internos y resolución de incidencias técnicas en tienda.</div>
          <div class="tl-tags"><span class="tl-tag">SQL Server</span><span class="tl-tag">Liderazgo</span><span class="tl-tag">Trabajo en equipo</span></div>
        </div>
      </div>

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">feb 2022<br>mar 2022</div></div>
        <div class="tl-right">
          <div class="tl-line"></div><div class="tl-dot"></div>
          <div class="tl-role">Técnico Informático (prácticas)</div>
          <div class="tl-company">Takkar 2000 · Sevilla</div>
          <div class="tl-desc">Programación en VB.NET y Java. Mantenimiento de software e incidencias técnicas.</div>
          <div class="tl-tags"><span class="tl-tag">VB.NET</span><span class="tl-tag">Java</span><span class="tl-tag">Soporte IT</span></div>
        </div>
      </div>

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">mar 2021<br>jun 2021</div></div>
        <div class="tl-right">
          <div class="tl-dot"></div>
          <div class="tl-role">Especialista Informático (prácticas)</div>
          <div class="tl-company">Wika · Dos Hermanas, Sevilla</div>
          <div class="tl-desc">Instalación de TTY en equipos de clientes y soporte técnico en entorno industrial.</div>
          <div class="tl-tags"><span class="tl-tag">Linux</span><span class="tl-tag">Hardware</span><span class="tl-tag">Redes</span></div>
        </div>
      </div>

    </div>
  </div>

  <!-- ══ PROYECTOS ══ -->
  <div class="section">
    <div class="sec-label reveal">proyectos</div>
    <h2 class="sec-title reveal d1">Repositorios destacados</h2>

    <div class="projects-grid reveal d2">

      <a href="https://github.com/Jother043/Proyecto-Springboot-IPA-con-Swagger" target="_blank" class="proj-card featured">
        <div class="proj-top">
          <div class="proj-icon">⚡</div>
          <div class="proj-star">★ Destacado</div>
        </div>
        <div class="proj-name">Spring Boot API + Swagger</div>
        <div class="proj-desc">API REST completa con arquitectura por capas, documentada con Swagger/OpenAPI y persistencia con JPA.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Spring Boot</span><span class="proj-tag">Swagger</span><span class="proj-tag">JPA</span></div>
      </a>

      <a href="https://github.com/Jother043/Hibernate-y-JPA-usando-consultas-JPQL" target="_blank" class="proj-card featured">
        <div class="proj-top">
          <div class="proj-icon">🗄️</div>
          <div class="proj-star">★ Destacado</div>
        </div>
        <div class="proj-name">Hibernate & JPA con JPQL</div>
        <div class="proj-desc">Persistencia avanzada, consultas JPQL, mapeo de entidades y gestión de relaciones entre tablas.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Hibernate</span><span class="proj-tag">JPA</span><span class="proj-tag">JPQL</span></div>
      </a>

      <a href="https://github.com/Jother043/FoodCode" target="_blank" class="proj-card featured">
        <div class="proj-top">
          <div class="proj-icon">🍽️</div>
          <div class="proj-star">★ Destacado</div>
        </div>
        <div class="proj-name">FoodCode</div>
        <div class="proj-desc">App Android de gestión de recetas con cálculo nutricional. Desarrollada en colaboración con el instituto.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Android</span><span class="proj-tag">SQLite</span></div>
      </a>

      <a href="https://github.com/Jother043/GasoilGPS" target="_blank" class="proj-card">
        <div class="proj-top">
          <div class="proj-icon">⛽</div>
        </div>
        <div class="proj-name">GasoilGPS</div>
        <div class="proj-desc">App Android con GPS, precios de carburante en tiempo real y sistema de logros por KM recorridos.</div>
        <div class="proj-tags"><span class="proj-tag">Kotlin</span><span class="proj-tag">Compose</span><span class="proj-tag">Hilt</span><span class="proj-tag">Room</span></div>
      </a>

      <a href="https://github.com/Jother043/EuroGas" target="_blank" class="proj-card">
        <div class="proj-top">
          <div class="proj-icon">🌍</div>
        </div>
        <div class="proj-name">EuroGas</div>
        <div class="proj-desc">Consulta y seguimiento de precios de combustibles en Europa con integración de API REST.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">API REST</span></div>
      </a>

      <a href="https://github.com/Jother043/HomeOfTheDragons" target="_blank" class="proj-card">
        <div class="proj-top">
          <div class="proj-icon">🐉</div>
        </div>
        <div class="proj-name">Home of The Dragons</div>
        <div class="proj-desc">Videojuego desarrollado en Java con mecánicas propias, POO aplicada a lógica de juego.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">JavaFX</span><span class="proj-tag">POO</span></div>
      </a>

    </div>

    <p style="margin-top:1rem;font-family:var(--mono);font-size:11px;color:var(--text3)">
      → Más repositorios en
      <a href="https://github.com/Jother043?tab=repositories" target="_blank" style="color:var(--cyan);text-decoration:none">github.com/Jother043</a>
    </p>
  </div>

  <!-- ══ EDUCACIÓN ══ -->
  <div class="section">
    <div class="sec-label reveal">formación</div>
    <h2 class="sec-title reveal d1">Educación y certificaciones</h2>

    <div class="edu-grid reveal d2">
      <div class="edu-card">
        <div class="edu-icon">🎓</div>
        <div class="edu-title">Grado Superior — DAM</div>
        <div class="edu-center">IES Padre José Miravett · Sevilla</div>
        <div class="edu-year">sep 2022 – jun 2024</div>
        <div class="edu-note">Desarrollo de Aplicaciones Multiplataforma. MVM, PLSQL, Java multiplataforma.</div>
      </div>
      <div class="edu-card">
        <div class="edu-icon">💻</div>
        <div class="edu-title">Grado Medio — SMR</div>
        <div class="edu-center">IES Padre José Miravett · Sevilla</div>
        <div class="edu-year">2019 – 2021</div>
        <div class="edu-note">Sistemas Microinformáticos y Redes. Linux, LAN/WAN, administración de sistemas.</div>
      </div>
    </div>

    <div class="cert-row reveal d3">
      <div class="cert-badge-box">C1 ADVANCED</div>
      <div>
        <div class="cert-title">EF SET English Certificate 61/100</div>
        <div class="cert-sub">EF SET · Expedición: septiembre 2025</div>
      </div>
    </div>
  </div>

  <!-- ══ CONTACTO ══ -->
  <div class="section">
    <div class="sec-label reveal">contacto</div>
    <h2 class="sec-title reveal d1">¿Hablamos?</h2>
    <p class="reveal d2" style="font-size:0.9rem;color:var(--text2);margin-bottom:1.25rem;">
      Abierto a nuevas oportunidades, proyectos freelance o cualquier idea técnica interesante.
    </p>

    <div class="contact-grid reveal d3">
      <a href="https://www.linkedin.com/in/jose-miguel-gutierrez-hernandez-392261185/" target="_blank" class="contact-item">
        <div class="contact-icon">IN</div>
        <div><div class="contact-lbl">LINKEDIN</div><div class="contact-val">jose-miguel-gutierrez-hernandez</div></div>
      </a>
      <a href="https://github.com/Jother043" target="_blank" class="contact-item">
        <div class="contact-icon">GH</div>
        <div><div class="contact-lbl">GITHUB</div><div class="contact-val">github.com/Jother043</div></div>
      </a>
      <a href="mailto:tu@email.com" class="contact-item">
        <div class="contact-icon">@</div>
        <div><div class="contact-lbl">EMAIL</div><div class="contact-val">tu@email.com</div></div>
      </a>
      <div class="contact-item" style="cursor:default;pointer-events:none">
        <div class="contact-icon">📍</div>
        <div><div class="contact-lbl">UBICACIÓN</div><div class="contact-val">Sevilla, Andalucía 🇪🇸</div></div>
      </div>
    </div>
  </div>

  <!-- ══ FOOTER ══ -->
  <footer>
    <span>© 2025 · José Miguel Gutiérrez Hernández</span>
    <span>
      <a href="https://github.com/Jother043" target="_blank">github.com/Jother043</a>
      · Sevilla, España
    </span>
  </footer>

</div>

<script>
const obs = new IntersectionObserver(
  entries => entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('in') }),
  { threshold: 0.07 }
);
document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
</script>
</body>
</html>
