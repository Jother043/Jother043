<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>José Miguel Gutiérrez — Backend Developer</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500&family=Sora:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#08090c;--bg1:#0c0f15;--bg2:#10141e;
  --surface:#161b28;--border:#1e2a3d;--border2:#2a3a55;
  --green:#00d68f;--green-dim:#00a06a;--cyan:#5eb6f7;--amber:#f0a04b;
  --text:#dce8f5;--text2:#8fa8c8;--text3:#4a6080;
  --mono:'JetBrains Mono',monospace;--sans:'Sora',sans-serif;
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--sans);font-size:15px;line-height:1.65;overflow-x:hidden}
::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--border2);border-radius:2px}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:200;display:flex;align-items:center;justify-content:space-between;padding:0 3rem;height:56px;background:rgba(8,9,12,0.92);backdrop-filter:blur(16px);border-bottom:1px solid var(--border)}
.nav-logo{font-family:var(--mono);font-size:12px;color:var(--text2);letter-spacing:0.06em}
.nav-logo strong{color:var(--green);font-weight:500}
.nav-links{display:flex;gap:2rem;list-style:none}
.nav-links a{font-family:var(--mono);font-size:11px;color:var(--text3);text-decoration:none;letter-spacing:0.08em;transition:color 0.2s}
.nav-links a:hover{color:var(--text)}
.nav-cta{font-family:var(--mono);font-size:11px;letter-spacing:0.08em;padding:6px 16px;border:1px solid var(--green-dim);color:var(--green);border-radius:3px;text-decoration:none;transition:all 0.2s}
.nav-cta:hover{background:var(--green);color:var(--bg)}

/* HERO */
#hero{min-height:100vh;display:flex;align-items:center;padding:0 3rem;max-width:1100px;margin:0 auto;position:relative}
.grid-pattern{position:absolute;right:-60px;top:50%;transform:translateY(-50%);width:440px;height:440px;opacity:0.06;background-image:linear-gradient(var(--cyan) 1px,transparent 1px),linear-gradient(90deg,var(--cyan) 1px,transparent 1px);background-size:40px 40px;mask-image:radial-gradient(circle at center,black 30%,transparent 75%);pointer-events:none}
.eyebrow{display:inline-flex;align-items:center;gap:8px;font-family:var(--mono);font-size:11px;letter-spacing:0.12em;color:var(--green);margin-bottom:2rem}
.eyebrow-line{width:32px;height:1px;background:var(--green)}
h1.hero-name{font-size:clamp(2.8rem,5.5vw,4.8rem);font-weight:700;line-height:1.05;letter-spacing:-0.03em;margin-bottom:0.2rem}
h1.hero-name .first{color:var(--text)}
h1.hero-name .last{color:transparent;-webkit-text-stroke:1.5px var(--text2);opacity:0.5}
.hero-title{font-family:var(--mono);font-size:clamp(0.82rem,1.8vw,1rem);color:var(--cyan);margin:1.5rem 0;letter-spacing:0.04em;display:flex;align-items:center;gap:8px}
.hero-title::before{content:'>';color:var(--text3)}
.cursor{display:inline-block;width:2px;height:1em;background:var(--cyan);vertical-align:middle;margin-left:2px;animation:blink 1.1s step-end infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
.hero-desc{font-size:1rem;color:var(--text2);line-height:1.85;max-width:510px;margin-bottom:2.5rem;font-weight:300}
.hero-desc strong{color:var(--text);font-weight:500}
.hero-actions{display:flex;gap:1rem;align-items:center;flex-wrap:wrap}
.btn-main{display:inline-flex;align-items:center;gap:8px;padding:0.7rem 1.6rem;background:var(--green);color:var(--bg);font-family:var(--mono);font-size:12px;letter-spacing:0.06em;font-weight:500;border-radius:3px;text-decoration:none;border:none;cursor:pointer;transition:all 0.2s}
.btn-main:hover{background:#00f0a0;transform:translateY(-1px)}
.btn-ghost{display:inline-flex;align-items:center;gap:8px;padding:0.7rem 1.6rem;background:transparent;color:var(--text2);font-family:var(--mono);font-size:12px;letter-spacing:0.06em;border:1px solid var(--border2);border-radius:3px;text-decoration:none;transition:all 0.2s}
.btn-ghost:hover{color:var(--text);border-color:var(--text3)}
.hero-meta{margin-top:3rem;padding-top:2rem;border-top:1px solid var(--border);display:flex;gap:2.5rem;flex-wrap:wrap}
.meta-item{font-family:var(--mono);font-size:11px}
.meta-label{color:var(--text3);letter-spacing:0.1em;margin-bottom:4px}
.meta-val{color:var(--text);font-size:13px}

/* SECTIONS */
.s{max-width:1100px;margin:0 auto;padding:6rem 3rem}
.s-header{margin-bottom:3.5rem}
.s-eyebrow{font-family:var(--mono);font-size:11px;letter-spacing:0.12em;color:var(--text3);margin-bottom:0.6rem;display:flex;align-items:center;gap:8px}
.s-eyebrow::before{content:'//';color:var(--border2)}
h2.s-title{font-size:1.8rem;font-weight:600;letter-spacing:-0.02em;color:var(--text)}
.divider{border:none;border-top:1px solid var(--border);max-width:1100px;margin:0 auto}

/* STATS */
.stats-row{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:1px;background:var(--border);border-radius:6px;overflow:hidden;margin-bottom:3rem}
.stat-box{background:var(--bg1);padding:1.5rem;display:flex;flex-direction:column;gap:4px}
.stat-num{font-size:2rem;font-weight:700;color:var(--green);letter-spacing:-0.03em}
.stat-label{font-family:var(--mono);font-size:10px;color:var(--text3);letter-spacing:0.08em}
.about-text{font-size:0.95rem;color:var(--text2);line-height:1.85;max-width:700px;font-weight:300}
.about-text strong{color:var(--text);font-weight:500}

/* SKILLS */
.skills-cols{display:grid;grid-template-columns:repeat(auto-fit,minmax(255px,1fr));gap:1.25rem}
.skill-group{background:var(--bg1);border:1px solid var(--border);border-radius:6px;padding:1.5rem}
.skill-group-title{font-family:var(--mono);font-size:10px;letter-spacing:0.1em;color:var(--text3);margin-bottom:1.25rem;display:flex;align-items:center;gap:8px}
.skill-group-title::after{content:'';flex:1;height:1px;background:var(--border)}
.skill-item{display:flex;align-items:center;justify-content:space-between;padding:0.5rem 0;border-bottom:1px solid var(--border)}
.skill-item:last-child{border-bottom:none}
.skill-name-row{display:flex;align-items:center;gap:10px;font-size:0.88rem;color:var(--text)}
.skill-dot{width:6px;height:6px;border-radius:50%;background:var(--green);flex-shrink:0}
.skill-dot.c{background:var(--cyan)}.skill-dot.a{background:var(--amber)}
.skill-lvl{font-family:var(--mono);font-size:9px;color:var(--text3);letter-spacing:0.06em}

/* TIMELINE */
.timeline{display:flex;flex-direction:column;gap:0}
.tl-item{display:grid;grid-template-columns:150px 1fr;gap:2rem;padding-bottom:2.5rem}
.tl-item:last-child{padding-bottom:0}
.tl-left{text-align:right;padding-top:4px}
.tl-date{font-family:var(--mono);font-size:11px;color:var(--text3);letter-spacing:0.06em;line-height:1.6}
.tl-right{position:relative;padding-left:2rem}
.tl-line{position:absolute;left:0;top:12px;bottom:-2.5rem;width:1px;background:var(--border)}
.tl-item:last-child .tl-line{display:none}
.tl-dot{position:absolute;left:-5px;top:6px;width:11px;height:11px;border-radius:50%;background:var(--bg);border:2px solid var(--green)}
.tl-role{font-size:0.95rem;font-weight:600;color:var(--text);margin-bottom:2px}
.tl-company{font-family:var(--mono);font-size:11px;color:var(--cyan);margin-bottom:0.6rem}
.tl-desc{font-size:0.83rem;color:var(--text2);line-height:1.75;font-weight:300}
.tl-tags{display:flex;flex-wrap:wrap;gap:5px;margin-top:0.6rem}
.tl-tag{font-family:var(--mono);font-size:9px;color:var(--text3);padding:2px 7px;background:var(--bg2);border:1px solid var(--border);border-radius:2px}

/* PROJECTS */
.proj-intro{font-size:0.9rem;color:var(--text2);margin-bottom:2rem;font-weight:300;max-width:600px}
.projects-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(285px,1fr));gap:1rem}
.proj-card{background:var(--bg1);border:1px solid var(--border);border-radius:6px;padding:1.4rem;position:relative;overflow:hidden;transition:border-color 0.25s,transform 0.25s}
.proj-card:hover{border-color:var(--border2);transform:translateY(-3px)}
.proj-card.feat{border-color:var(--green-dim)}
.featured-bar{display:none;position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--green),var(--cyan))}
.proj-card.feat .featured-bar{display:block}
.proj-top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:0.85rem}
.proj-num{font-family:var(--mono);font-size:10px;color:var(--text3);letter-spacing:0.08em}
.proj-link{font-family:var(--mono);font-size:10px;letter-spacing:0.06em;color:var(--text3);text-decoration:none;padding:3px 10px;border:1px solid var(--border);border-radius:2px;transition:all 0.15s}
.proj-link:hover{color:var(--green);border-color:var(--green-dim)}
.proj-name{font-size:0.95rem;font-weight:600;color:var(--text);margin-bottom:0.45rem;letter-spacing:-0.01em}
.proj-desc{font-size:0.8rem;color:var(--text2);line-height:1.65;margin-bottom:1rem;font-weight:300}
.proj-tags{display:flex;flex-wrap:wrap;gap:5px}
.proj-tag{font-family:var(--mono);font-size:9px;letter-spacing:0.05em;color:var(--text3);padding:2px 8px;background:var(--bg2);border:1px solid var(--border);border-radius:2px}

/* EDUCATION */
.edu-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.25rem;margin-bottom:1.5rem}
.edu-card{background:var(--bg1);border:1px solid var(--border);border-radius:6px;padding:1.5rem;transition:border-color 0.2s}
.edu-card:hover{border-color:var(--border2)}
.edu-icon{font-size:1.5rem;margin-bottom:0.75rem}
.edu-degree{font-size:0.92rem;font-weight:600;color:var(--text);margin-bottom:4px}
.edu-center{font-family:var(--mono);font-size:11px;color:var(--cyan);margin-bottom:4px}
.edu-year{font-family:var(--mono);font-size:10px;color:var(--text3)}
.edu-note{font-size:0.8rem;color:var(--text2);margin-top:0.5rem;font-weight:300}
.cert-card{background:var(--bg1);border:1px solid var(--border);border-radius:6px;padding:1.25rem 1.5rem;display:flex;align-items:center;gap:1rem}
.cert-badge{font-family:var(--mono);font-size:11px;color:var(--green);background:rgba(0,214,143,0.08);border:1px solid var(--green-dim);border-radius:3px;padding:4px 10px;white-space:nowrap}
.cert-info-title{font-size:0.9rem;font-weight:600;color:var(--text)}
.cert-info-sub{font-family:var(--mono);font-size:10px;color:var(--text3);margin-top:2px}

/* CONTACT */
.contact-wrap{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:start}
.contact-copy{font-size:0.9rem;color:var(--text2);line-height:1.85;font-weight:300;margin-bottom:2rem}
.cl-item{display:flex;align-items:center;gap:1rem;padding:0.9rem 0;border-bottom:1px solid var(--border);text-decoration:none;color:var(--text);transition:color 0.2s}
.cl-item:last-child{border-bottom:none}
.cl-item:hover{color:var(--green)}
.cl-icon{font-family:var(--mono);font-size:10px;color:var(--text3);min-width:30px;letter-spacing:0.06em}
.cl-label{font-family:var(--mono);font-size:9px;color:var(--text3);letter-spacing:0.1em;margin-bottom:2px}
.cl-val{font-size:0.88rem;color:var(--text)}
.form{display:flex;flex-direction:column;gap:10px}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.form-field{display:flex;flex-direction:column;gap:4px}
.form-label{font-family:var(--mono);font-size:9px;letter-spacing:0.1em;color:var(--text3)}
.form input,.form textarea{background:var(--surface);border:1px solid var(--border);border-radius:4px;padding:0.7rem 0.9rem;color:var(--text);font-family:var(--sans);font-size:0.85rem;outline:none;transition:border-color 0.2s;resize:vertical}
.form input:focus,.form textarea:focus{border-color:var(--green-dim)}
.form input::placeholder,.form textarea::placeholder{color:var(--text3)}

/* FOOTER */
.footer-wrap{max-width:1100px;margin:0 auto;padding:0 3rem}
footer{border-top:1px solid var(--border);padding:2rem 0;display:flex;align-items:center;justify-content:space-between;font-family:var(--mono);font-size:11px;color:var(--text3)}
.footer-status{display:flex;align-items:center;gap:8px}
.status-dot{width:6px;height:6px;border-radius:50%;background:var(--green);animation:pulse 2.5s ease-in-out infinite}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:0.4}}

/* RESPONSIVE */
@media(max-width:700px){
  nav{padding:0 1.5rem}.nav-links{display:none}
  #hero{padding:80px 1.5rem 3rem}.hero-left{max-width:100%}
  .s{padding:4rem 1.5rem}
  .tl-item{grid-template-columns:1fr}.tl-left{text-align:left}
  .contact-wrap{grid-template-columns:1fr}
  .footer-wrap{padding:0 1.5rem}
  footer{flex-direction:column;gap:8px;text-align:center}
}

/* ANIMATE */
.fade{opacity:0;transform:translateY(18px);transition:opacity 0.65s ease,transform 0.65s ease}
.fade.in{opacity:1;transform:none}
.fd1{transition-delay:0.1s}.fd2{transition-delay:0.2s}.fd3{transition-delay:0.3s}
</style>
</head>
<body>

<nav>
  <div class="nav-logo"><strong>jmgh</strong>.dev</div>
  <ul class="nav-links">
    <li><a href="#sobre-mi">acerca</a></li>
    <li><a href="#skills">stack</a></li>
    <li><a href="#experiencia">experiencia</a></li>
    <li><a href="#proyectos">proyectos</a></li>
    <li><a href="#educacion">formación</a></li>
  </ul>
  <a href="#contacto" class="nav-cta">contactar</a>
</nav>

<!-- HERO -->
<section id="hero" style="position:relative;z-index:1">
  <div class="grid-pattern"></div>
  <div class="hero-left">
    <div class="eyebrow"><span class="eyebrow-line"></span>Backend Developer · Java & DevOps</div>
    <h1 class="hero-name">
      <span class="first">José Miguel</span><br>
      <span class="last">Gutiérrez</span>
    </h1>
    <div class="hero-title">Automatización · APIs · Desarrollo multiplataforma<span class="cursor"></span></div>
    <p class="hero-desc">
      Desarrollador con experiencia en <strong>Java, Spring Boot y DevOps</strong>. Especializado en APIs REST, persistencia de datos con Hibernate y automatización de procesos. Actualmente como <strong>DevOps Developer en Ampliqure</strong>, Sevilla.
    </p>
    <div class="hero-actions">
      <a href="#proyectos" class="btn-main">Ver proyectos ↓</a>
      <a href="https://www.linkedin.com/in/jose-miguel-gutierrez-hernandez-392261185/" target="_blank" class="btn-ghost">LinkedIn ↗</a>
    </div>
    <div class="hero-meta">
      <div class="meta-item"><div class="meta-label">UBICACIÓN</div><div class="meta-val">Sevilla, Andalucía</div></div>
      <div class="meta-item"><div class="meta-label">ESTADO</div><div class="meta-val" style="color:var(--green)">Disponible</div></div>
      <div class="meta-item"><div class="meta-label">GITHUB</div><div class="meta-val"><a href="https://github.com/Jother043" target="_blank" style="color:var(--cyan);text-decoration:none">Jother043</a></div></div>
      <div class="meta-item"><div class="meta-label">INGLÉS</div><div class="meta-val">C1 Advanced (EF SET)</div></div>
    </div>
  </div>
</section>

<hr class="divider">

<!-- ABOUT -->
<section id="sobre-mi">
  <div class="s">
    <div class="s-header fade">
      <div class="s-eyebrow">acerca de mí</div>
      <h2 class="s-title">Quién soy</h2>
    </div>
    <div class="stats-row fade fd1">
      <div class="stat-box"><div class="stat-num">4+</div><div class="stat-label">AÑOS DE EXPERIENCIA</div></div>
      <div class="stat-box"><div class="stat-num">20+</div><div class="stat-label">REPOS EN GITHUB</div></div>
      <div class="stat-box"><div class="stat-num">C1</div><div class="stat-label">INGLÉS EF SET</div></div>
      <div class="stat-box"><div class="stat-num">DAM</div><div class="stat-label">GRADO SUPERIOR</div></div>
    </div>
    <p class="about-text fade fd2">
      Soy <strong>José Miguel Gutiérrez Hernández</strong>, desarrollador backend afincado en Sevilla. Cuento con experiencia profesional real en empresas como <strong>Ampliqure</strong> (DevOps Developer), <strong>Sillsoft</strong> (Backend Junior en prácticas) y Lidl. Mi formación es en <strong>Desarrollo de Aplicaciones Multiplataforma (DAM)</strong> con especialidad en MVM y PLSQL. Me apasionan las <strong>APIs REST con Spring Boot</strong>, la automatización de procesos y la arquitectura de software limpia. Trabajo bien en equipo, soy metódico y siempre busco aprender y mejorar.
    </p>
  </div>
</section>

<hr class="divider">

<!-- SKILLS -->
<section id="skills">
  <div class="s">
    <div class="s-header fade">
      <div class="s-eyebrow">tecnologías</div>
      <h2 class="s-title">Stack técnico</h2>
    </div>
    <div class="skills-cols fade fd1">
      <div class="skill-group">
        <div class="skill-group-title">LENGUAJES</div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>Java</div><div class="skill-lvl">AVANZADO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>Python</div><div class="skill-lvl">AVANZADO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>SQL</div><div class="skill-lvl">SÓLIDO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>Visual Basic .NET</div><div class="skill-lvl">INTERMEDIO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>JavaScript</div><div class="skill-lvl">BÁSICO</div></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">FRAMEWORKS & LIBS</div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot c"></div>Spring Boot</div><div class="skill-lvl">AVANZADO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot c"></div>Hibernate / JPA</div><div class="skill-lvl">SÓLIDO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot c"></div>Swagger / OpenAPI</div><div class="skill-lvl">SÓLIDO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot c"></div>Maven</div><div class="skill-lvl">SÓLIDO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot c"></div>JavaFX / Android</div><div class="skill-lvl">INTERMEDIO</div></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">BASES DE DATOS</div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot a"></div>SQL Server</div><div class="skill-lvl">SÓLIDO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot a"></div>MySQL</div><div class="skill-lvl">SÓLIDO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot a"></div>Oracle / PLSQL</div><div class="skill-lvl">INTERMEDIO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot a"></div>MongoDB</div><div class="skill-lvl">BÁSICO</div></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">DEVOPS & SISTEMAS</div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>Linux / TTY</div><div class="skill-lvl">SÓLIDO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>Git / GitHub</div><div class="skill-lvl">AVANZADO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>CI/CD Automatización</div><div class="skill-lvl">INTERMEDIO</div></div>
        <div class="skill-item"><div class="skill-name-row"><div class="skill-dot"></div>Redes LAN/WAN</div><div class="skill-lvl">INTERMEDIO</div></div>
      </div>
    </div>
  </div>
</section>

<hr class="divider">

<!-- EXPERIENCIA -->
<section id="experiencia">
  <div class="s">
    <div class="s-header fade">
      <div class="s-eyebrow">trayectoria</div>
      <h2 class="s-title">Experiencia profesional</h2>
    </div>
    <div class="timeline fade fd1">

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">2025<br>Presente</div></div>
        <div class="tl-right">
          <div class="tl-line"></div><div class="tl-dot"></div>
          <div class="tl-role">DevOps Developer</div>
          <div class="tl-company">Ampliqure · Sevilla / Remoto · Jornada completa</div>
          <div class="tl-desc">Perfil técnico integral enfocado en la automatización de procesos y el desarrollo de software orientado a DevOps. Integración y despliegue continuo de aplicaciones en entorno productivo.</div>
          <div class="tl-tags"><span class="tl-tag">DevOps</span><span class="tl-tag">Automatización</span><span class="tl-tag">CI/CD</span><span class="tl-tag">Python</span></div>
        </div>
      </div>

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">sep 2023<br>actualidad</div></div>
        <div class="tl-right">
          <div class="tl-line"></div><div class="tl-dot"></div>
          <div class="tl-role">Cajero y Responsable de Sección</div>
          <div class="tl-company">Lidl · Sevilla · Jornada completa</div>
          <div class="tl-desc">Administración de SQL Server, gestión de equipo y resolución de incidencias operativas. Responsabilidades de supervisión y liderazgo de sección.</div>
          <div class="tl-tags"><span class="tl-tag">SQL Server</span><span class="tl-tag">Trabajo en equipo</span><span class="tl-tag">Gestión</span></div>
        </div>
      </div>

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">jun 2024<br>ago 2024</div></div>
        <div class="tl-right">
          <div class="tl-line"></div><div class="tl-dot"></div>
          <div class="tl-role">Desarrollador Backend Junior (prácticas)</div>
          <div class="tl-company">Sillsoft · Sevilla · Contrato de prácticas</div>
          <div class="tl-desc">Programación Java con Spring Boot e Hibernate. Desarrollo de APIs REST documentadas con Swagger. Trabajo con bases de datos relacionales SQL Server. Participación activa en el ciclo completo de desarrollo de software.</div>
          <div class="tl-tags"><span class="tl-tag">Java</span><span class="tl-tag">Spring Boot</span><span class="tl-tag">Hibernate</span><span class="tl-tag">Swagger</span><span class="tl-tag">SQL Server</span></div>
        </div>
      </div>

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">feb 2022<br>mar 2022</div></div>
        <div class="tl-right">
          <div class="tl-line"></div><div class="tl-dot"></div>
          <div class="tl-role">Técnico Informático / Programador (prácticas)</div>
          <div class="tl-company">Takkar 2000 · Sevilla</div>
          <div class="tl-desc">Programación en Visual Basic .NET y Java. Mantenimiento de incidencias informáticas. Trabajo en equipo con resolución del software Maker.</div>
          <div class="tl-tags"><span class="tl-tag">VB.NET</span><span class="tl-tag">Java</span><span class="tl-tag">Soporte IT</span></div>
        </div>
      </div>

      <div class="tl-item">
        <div class="tl-left"><div class="tl-date">mar 2021<br>jun 2021</div></div>
        <div class="tl-right">
          <div class="tl-dot"></div>
          <div class="tl-role">Especialista Informático (prácticas)</div>
          <div class="tl-company">Wika · Dos Hermanas, Sevilla</div>
          <div class="tl-desc">Instalación de TTY en equipos de clientes. Asistencia técnica y resolución de incidencias en entorno empresarial industrial.</div>
          <div class="tl-tags"><span class="tl-tag">Linux TTY</span><span class="tl-tag">Hardware</span><span class="tl-tag">Soporte técnico</span></div>
        </div>
      </div>

    </div>
  </div>
</section>

<hr class="divider">

<!-- PROYECTOS -->
<section id="proyectos">
  <div class="s">
    <div class="s-header fade">
      <div class="s-eyebrow">trabajo</div>
      <h2 class="s-title">Proyectos en GitHub</h2>
    </div>
    <p class="proj-intro fade">Selección de proyectos públicos en <a href="https://github.com/Jother043" target="_blank" style="color:var(--cyan);text-decoration:none">github.com/Jother043</a> — APIs REST, aplicaciones Android, videojuegos y más.</p>
    <div class="projects-grid fade fd1">

      <div class="proj-card feat">
        <div class="featured-bar"></div>
        <div class="proj-top">
          <div class="proj-num">01 · Destacado</div>
          <a href="https://github.com/Jother043/Proyecto-Springboot-IPA-con-Swagger" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">Spring Boot API + Swagger</div>
        <div class="proj-desc">API REST completa con Spring Boot, documentada con Swagger/OpenAPI. Arquitectura por capas: controladores, servicios y repositorios con JPA.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Spring Boot</span><span class="proj-tag">Swagger</span><span class="proj-tag">JPA</span></div>
      </div>

      <div class="proj-card feat">
        <div class="featured-bar"></div>
        <div class="proj-top">
          <div class="proj-num">02 · Destacado</div>
          <a href="https://github.com/Jother043/Hibernate-y-JPA-usando-consultas-JPQL" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">Hibernate & JPA con JPQL</div>
        <div class="proj-desc">Persistencia avanzada con Hibernate y JPA. Consultas JPQL, mapeo de entidades y gestión de relaciones entre tablas en base de datos relacional.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Hibernate</span><span class="proj-tag">JPA</span><span class="proj-tag">JPQL</span></div>
      </div>

      <div class="proj-card feat">
        <div class="featured-bar"></div>
        <div class="proj-top">
          <div class="proj-num">03 · Destacado</div>
          <a href="https://github.com/Jother043/FoodCode" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">FoodCode</div>
        <div class="proj-desc">App de gestión de recetas y productos con cálculo de valor energético. Desarrollada junto a IES Padre José Miravett, con búsqueda de ingredientes y datos nutricionales.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Android</span><span class="proj-tag">SQLite</span><span class="proj-tag">API</span></div>
      </div>

      <div class="proj-card">
        <div class="proj-top">
          <div class="proj-num">04</div>
          <a href="https://github.com/Jother043/EuroGas" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">EuroGas</div>
        <div class="proj-desc">Aplicación de consulta y seguimiento de precios de combustibles y gas en Europa, con integración de datos en tiempo real.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">API REST</span></div>
      </div>

      <div class="proj-card">
        <div class="proj-top">
          <div class="proj-num">05</div>
          <a href="https://github.com/Jother043/HomeOfTheDragons" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">Home of The Dragons</div>
        <div class="proj-desc">Videojuego desarrollado en Java con mecánicas propias. Proyecto que explora programación orientada a eventos, gráficos y lógica de juego.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">JavaFX</span><span class="proj-tag">Videojuego</span></div>
      </div>

      <div class="proj-card">
        <div class="proj-top">
          <div class="proj-num">06</div>
          <a href="https://github.com/Jother043/ConexionAndroid" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">Conexión Android</div>
        <div class="proj-desc">Integración de servicios y conexión a APIs externas desde aplicación Android nativa. Gestión de peticiones HTTP y respuestas JSON.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Android</span><span class="proj-tag">REST</span></div>
      </div>

      <div class="proj-card">
        <div class="proj-top">
          <div class="proj-num">07</div>
          <a href="https://github.com/Jother043/LectorQR" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">Lector QR</div>
        <div class="proj-desc">App Android para lectura y generación de códigos QR. Integración con cámara del dispositivo y procesamiento de imágenes en tiempo real.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Android</span><span class="proj-tag">ZXing</span></div>
      </div>

      <div class="proj-card">
        <div class="proj-top">
          <div class="proj-num">08</div>
          <a href="https://github.com/Jother043/Primer-proyecto-Hibernate-con-JPA" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">Primer proyecto Hibernate + JPA</div>
        <div class="proj-desc">Introducción práctica a la persistencia con Hibernate y JPA. Configuración de entidades, sesiones y transacciones en base de datos relacional.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Hibernate</span><span class="proj-tag">JPA</span></div>
      </div>

      <div class="proj-card">
        <div class="proj-top">
          <div class="proj-num">09</div>
          <a href="https://github.com/Jother043/Acceso_Datos_XML_JAXB_Marshaller_ACTI" target="_blank" class="proj-link">GitHub ↗</a>
        </div>
        <div class="proj-name">Acceso Datos XML & JAXB</div>
        <div class="proj-desc">Manejo de datos XML con JAXB para marshalling y unmarshalling. Serialización de objetos Java a XML y viceversa en contexto de acceso a datos.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">JAXB</span><span class="proj-tag">XML</span></div>
      </div>

      <div class="proj-card">
        <div class="proj-top">
          <div class="proj-num">+12</div>
          <a href="https://github.com/Jother043?tab=repositories" target="_blank" class="proj-link">Ver todos ↗</a>
        </div>
        <div class="proj-name">Más proyectos disponibles</div>
        <div class="proj-desc">CrudBBDD, BásicaBDD, VideoJuegoBDD, PracticandoJS, Ejercicios_Archivos, Clases-colecciones-2023, repositorioPrácticaGit y más en el perfil de GitHub.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Python</span><span class="proj-tag">SQL</span><span class="proj-tag">Android</span><span class="proj-tag">JavaScript</span></div>
      </div>

    </div>
  </div>
</section>

<hr class="divider">

<!-- EDUCACIÓN -->
<section id="educacion">
  <div class="s">
    <div class="s-header fade">
      <div class="s-eyebrow">formación</div>
      <h2 class="s-title">Educación y certificaciones</h2>
    </div>
    <div class="edu-grid fade fd1">
      <div class="edu-card">
        <div class="edu-icon">🎓</div>
        <div class="edu-degree">Grado Superior — Desarrollo de Aplicaciones Multiplataforma (DAM)</div>
        <div class="edu-center">IES Padre José Miravett · Sevilla</div>
        <div class="edu-year">sep 2022 – jun 2024</div>
        <div class="edu-note">Especialización en Modelo-Vista-Modelo (MVM), PLSQL y desarrollo de aplicaciones multiplataforma con Java.</div>
      </div>
      <div class="edu-card">
        <div class="edu-icon">💻</div>
        <div class="edu-degree">Grado Medio — Sistemas Microinformáticos y Redes</div>
        <div class="edu-center">IES Padre José Miravett · Sevilla</div>
        <div class="edu-year">2019 – 2021</div>
        <div class="edu-note">LAN-WAN, administración de sistemas Linux y Windows, soporte técnico y redes informáticas.</div>
      </div>
    </div>
    <div class="fade fd2">
      <div class="cert-card">
        <div class="cert-badge">C1 ADVANCED</div>
        <div>
          <div class="cert-info-title">EF SET English Certificate 61/100 (C1 Advanced)</div>
          <div class="cert-info-sub">EF SET · Expedición: septiembre 2025</div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="divider">

<!-- CONTACTO -->
<section id="contacto">
  <div class="s">
    <div class="s-header fade">
      <div class="s-eyebrow">contacto</div>
      <h2 class="s-title">Hablemos</h2>
    </div>
    <div class="contact-wrap fade fd1">
      <div>
        <p class="contact-copy">¿Buscas un desarrollador backend con experiencia real en Java, Spring Boot y DevOps? Estoy abierto a nuevas oportunidades, proyectos freelance o simplemente una buena conversación técnica. No dudes en escribirme.</p>
        <div>
          <a href="https://www.linkedin.com/in/jose-miguel-gutierrez-hernandez-392261185/" target="_blank" class="cl-item">
            <div class="cl-icon">IN</div>
            <div><div class="cl-label">LINKEDIN</div><div class="cl-val">jose-miguel-gutierrez-hernandez</div></div>
          </a>
          <a href="https://github.com/Jother043" target="_blank" class="cl-item">
            <div class="cl-icon">GH</div>
            <div><div class="cl-label">GITHUB</div><div class="cl-val">github.com/Jother043</div></div>
          </a>
          <a href="mailto:tu@email.com" class="cl-item">
            <div class="cl-icon">@</div>
            <div><div class="cl-label">EMAIL</div><div class="cl-val">tu@email.com</div></div>
          </a>
          <div class="cl-item" style="cursor:default;pointer-events:none">
            <div class="cl-icon">📍</div>
            <div><div class="cl-label">UBICACIÓN</div><div class="cl-val">Sevilla, Andalucía, España</div></div>
          </div>
        </div>
      </div>
      <div class="form">
        <div class="form-row">
          <div class="form-field"><div class="form-label">NOMBRE</div><input type="text" placeholder="Tu nombre"></div>
          <div class="form-field"><div class="form-label">EMAIL</div><input type="email" placeholder="tu@email.com"></div>
        </div>
        <div class="form-field"><div class="form-label">ASUNTO</div><input type="text" placeholder="¿En qué puedo ayudarte?"></div>
        <div class="form-field"><div class="form-label">MENSAJE</div><textarea rows="5" placeholder="Cuéntame tu proyecto o propuesta..."></textarea></div>
        <button class="btn-main" style="align-self:flex-start">Enviar mensaje →</button>
      </div>
    </div>
  </div>
</section>

<div class="footer-wrap">
  <hr class="divider" style="max-width:none">
  <footer>
    <div>© 2025 · José Miguel Gutiérrez Hernández · Sevilla</div>
    <div class="footer-status">
      <div class="status-dot"></div>
      Disponible para nuevas oportunidades
    </div>
  </footer>
</div>

<script>
const obs = new IntersectionObserver(entries => {
  entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('in') });
}, {threshold:0.07});
document.querySelectorAll('.fade').forEach(el => obs.observe(el));
</script>
</body>
</html>
