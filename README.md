<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Robert Noriega — Portafolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,500;0,9..144,600;1,9..144,500&family=Inter:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#051F20;
    --ink-2:#0B2B26;
    --ink-3:#163832;
    --steel:#235347;
    --sage:#8EB69B;
    --sage-soft:#DAF1DE;
    --paper:#F6FAF6;
    --line: rgba(218,241,222,0.14);
    --max: 1180px;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--ink);
    color:var(--sage-soft);
    font-family:'Inter', sans-serif;
    font-size:16px;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  img{max-width:100%; display:block;}
  a{color:inherit;}
  .wrap{max-width:var(--max); margin:0 auto; padding:0 32px;}
  h1,h2,h3{font-family:'Fraunces', serif; font-weight:600; letter-spacing:-0.01em; color:#fff;}
  .eyebrow{
    font-family:'IBM Plex Mono', monospace;
    font-size:12px;
    letter-spacing:0.16em;
    text-transform:uppercase;
    color:var(--sage);
  }
  :focus-visible{outline:2px solid var(--sage); outline-offset:3px;}

  /* ---------- NAV ---------- */
  header{
    position:fixed; top:0; left:0; right:0; z-index:100;
    transition:background .35s ease, border-color .35s ease, backdrop-filter .35s ease;
    border-bottom:1px solid transparent;
  }
  header.scrolled{
    background:rgba(5,31,32,0.82);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--line);
  }
  nav{
    display:flex; align-items:center; justify-content:space-between;
    padding:22px 32px; max-width:var(--max); margin:0 auto;
  }
  .logo{
    font-family:'Fraunces', serif; font-weight:600; font-size:19px; color:#fff;
    display:flex; align-items:center; gap:8px;
  }
  .logo .dot{width:7px; height:7px; border-radius:50%; background:var(--sage); display:inline-block;}
  .nav-links{display:flex; gap:34px; list-style:none; font-size:13.5px;}
  .nav-links a{
    text-decoration:none; color:var(--sage-soft); letter-spacing:0.03em;
    position:relative; padding-bottom:4px; text-transform:uppercase; font-size:12.5px;
    font-family:'IBM Plex Mono', monospace;
  }
  .nav-links a::after{
    content:''; position:absolute; left:0; bottom:0; width:0; height:1px;
    background:var(--sage); transition:width .25s ease;
  }
  .nav-links a:hover::after{width:100%;}
  .nav-toggle{display:none; background:none; border:none; cursor:pointer;}
  .nav-toggle span{display:block; width:22px; height:1.5px; background:#fff; margin:5px 0;}

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    height:100vh;
    min-height:640px;
    display:flex;
    flex-direction:column;
    justify-content:flex-end;
    overflow:hidden;
  }
  .hero-bg{
    position:absolute; inset:0;
    background:
      radial-gradient(ellipse 90% 60% at 30% 15%, rgba(142,182,155,0.20), transparent 60%),
      radial-gradient(ellipse 70% 50% at 80% 85%, rgba(35,83,71,0.55), transparent 65%),
      linear-gradient(190deg, #0B2B26 0%, #051F20 55%, #051F20 100%);
  }
  .hero-bg img{
    position:absolute; inset:0; width:100%; height:100%; object-fit:cover;
    object-position:center 30%;
  }
  .hero-bg .photo-overlay{
    position:absolute; inset:0;
    background:linear-gradient(180deg, rgba(5,31,32,0.55) 0%, rgba(5,31,32,0.35) 40%, rgba(5,31,32,0.92) 100%);
  }
  .hero-bg::after{
    content:'';
    position:absolute; inset:0;
    background-image:
      repeating-linear-gradient(115deg, rgba(255,255,255,0.02) 0px, rgba(255,255,255,0.02) 1px, transparent 1px, transparent 3px);
    mix-blend-mode:overlay;
  }
  .hero-content{
    position:relative; z-index:2;
    padding:0 32px 46px;
    max-width:var(--max); margin:0 auto; width:100%;
  }
  .hero-content .eyebrow{margin-bottom:18px; display:block;}
  .hero-content h1{
    font-size:clamp(40px, 7vw, 84px);
    line-height:0.98;
    max-width:14ch;
    margin-bottom:26px;
  }
  .hero-content h1 em{font-style:italic; color:var(--sage);}
  .hero-content p.lead{
    font-size:16.5px; color:var(--sage-soft); opacity:0.8; max-width:42ch; margin-bottom:34px;
  }
  .btn-row{display:flex; gap:14px; flex-wrap:wrap;}
  .btn{
    display:inline-flex; align-items:center; gap:8px;
    padding:14px 26px; border-radius:2px; font-size:13px; font-weight:500;
    text-decoration:none; transition:transform .2s ease, box-shadow .2s ease, background .2s ease;
    font-family:'IBM Plex Mono', monospace; letter-spacing:0.04em; text-transform:uppercase;
  }
  .btn-primary{background:var(--sage); color:var(--ink);}
  .btn-primary:hover{transform:translateY(-2px); box-shadow:0 10px 24px rgba(142,182,155,0.28);}
  .btn-ghost{border:1px solid rgba(218,241,222,0.35); color:#fff;}
  .btn-ghost:hover{background:rgba(218,241,222,0.1);}

  /* horizontal scroll cards over hero */
  .hero-scroller{
    position:relative; z-index:3;
    margin-top:44px;
    display:flex; gap:16px; overflow-x:auto;
    padding-bottom:6px; scroll-snap-type:x mandatory;
    -ms-overflow-style:none; scrollbar-width:none;
  }
  .hero-scroller::-webkit-scrollbar{display:none;}
  .scroll-card{
    flex:0 0 190px; scroll-snap-align:start;
    aspect-ratio:3/4; border-radius:4px; position:relative; overflow:hidden;
    border:1px solid var(--line); cursor:pointer;
    transition:transform .3s ease, border-color .3s ease;
  }
  .scroll-card:hover{transform:translateY(-6px); border-color:var(--sage);}
  .scroll-card .sc-bg{position:absolute; inset:0;}
  .scroll-card.sc1 .sc-bg{background:linear-gradient(155deg, var(--steel), var(--ink) 80%);}
  .scroll-card.sc2 .sc-bg{background:linear-gradient(155deg, var(--sage), var(--ink) 80%);}
  .scroll-card.sc3 .sc-bg{background:linear-gradient(155deg, var(--ink-3), var(--ink) 80%);}
  .scroll-card.sc4 .sc-bg{background:linear-gradient(155deg, var(--ink-2), var(--ink) 80%);}
  .scroll-card .sc-label{
    position:absolute; left:14px; bottom:14px; z-index:2;
    font-family:'IBM Plex Mono', monospace; font-size:11px; color:#fff;
    text-transform:uppercase; letter-spacing:0.05em;
  }
  .scroll-card .sc-num{
    position:absolute; top:14px; left:14px; z-index:2;
    font-family:'IBM Plex Mono', monospace; font-size:10.5px; color:var(--sage);
  }
  .scroll-card::before{
    content:'▶'; position:absolute; top:50%; left:50%; transform:translate(-50%,-50%);
    width:36px; height:36px; border-radius:50%; z-index:2;
    background:rgba(5,31,32,0.4); border:1px solid rgba(255,255,255,0.35);
    color:#fff; display:flex; align-items:center; justify-content:center; font-size:11px;
  }

  .scroll-hint{
    position:absolute; right:32px; bottom:46px; z-index:3;
    font-family:'IBM Plex Mono', monospace; font-size:11px; color:var(--sage);
    display:flex; align-items:center; gap:8px; letter-spacing:0.05em;
  }
  .scroll-hint .arrow{display:inline-block; animation:nudge 1.6s ease-in-out infinite;}
  @keyframes nudge{0%,100%{transform:translateX(0);} 50%{transform:translateX(5px);}}

  /* ---------- SECTION SHELL ---------- */
  section{padding:120px 0;}
  .section-head{margin-bottom:56px; max-width:600px;}
  .section-head h2{font-size:clamp(30px,3.4vw,44px); margin-top:12px;}
  .bg-2{background:var(--ink-2);}

  /* ---------- SHOWCASE (Discover section) ---------- */
  .showcase-grid{
    display:grid; grid-template-columns:1.5fr 1fr; gap:20px; align-items:stretch;
  }
  .showcase-tile{
    position:relative; border-radius:4px; overflow:hidden; border:1px solid var(--line);
    min-height:420px; display:flex; flex-direction:column; justify-content:flex-end; padding:28px;
    cursor:pointer;
  }
  .showcase-tile.big{background:linear-gradient(165deg, var(--steel) 0%, var(--ink) 78%);}
  .showcase-tile.small{background:linear-gradient(165deg, var(--ink-3) 0%, var(--ink) 78%); min-height:200px;}
  .showcase-col{display:flex; flex-direction:column; gap:20px;}
  .showcase-tile .t-eyebrow{
    font-family:'IBM Plex Mono', monospace; font-size:11px; color:var(--sage);
    text-transform:uppercase; letter-spacing:0.08em; margin-bottom:8px;
  }
  .showcase-tile h3{font-size:24px; color:#fff; max-width:16ch;}
  .play-btn{
    position:absolute; top:24px; right:24px; width:44px; height:44px; border-radius:50%;
    background:rgba(5,31,32,0.5); border:1px solid rgba(255,255,255,0.35);
    display:flex; align-items:center; justify-content:center; color:#fff; font-size:13px;
    backdrop-filter:blur(3px);
  }
  .expand-btn{
    position:absolute; top:20px; right:20px; width:34px; height:34px; border-radius:50%;
    background:rgba(5,31,32,0.5); border:1px solid rgba(255,255,255,0.35);
    display:flex; align-items:center; justify-content:center; color:#fff; font-size:13px;
  }

  /* ---------- ABOUT ---------- */
  .about .wrap{display:grid; grid-template-columns:1fr 1fr; gap:64px; align-items:start;}
  .about p{color:var(--sage-soft); opacity:0.78; max-width:48ch; margin-bottom:18px; font-size:15.5px;}
  .tool-list{list-style:none; display:flex; flex-direction:column; gap:0;}
  .tool-list li{
    display:flex; justify-content:space-between; padding:16px 0;
    border-bottom:1px solid var(--line); font-size:15px; color:#fff;
  }
  .tool-list li span:last-child{color:var(--sage); font-family:'IBM Plex Mono', monospace; font-size:12px;}

  /* ---------- PROJECTS ---------- */
  .projects-grid{display:flex; flex-direction:column; gap:22px;}
  .project-card{
    border:1px solid var(--line); background:var(--ink-2);
    padding:40px; display:grid; grid-template-columns:0.9fr 1.1fr; gap:40px; align-items:center;
    border-radius:4px;
  }
  .project-card .thumb{
    aspect-ratio:4/3; border-radius:3px; overflow:hidden;
    background:linear-gradient(135deg, var(--steel), var(--ink) 120%);
    display:flex; align-items:center; justify-content:center;
    font-family:'IBM Plex Mono', monospace; font-size:12px; color:var(--sage-soft); letter-spacing:0.05em;
    border:1px solid var(--line); opacity:0.9;
  }
  .project-card h3{font-size:26px; margin:8px 0 12px; color:#fff;}
  .project-card p{color:var(--sage-soft); opacity:0.78; font-size:15px; margin-bottom:18px; max-width:50ch;}
  .project-meta{display:flex; gap:22px; margin-bottom:18px; flex-wrap:wrap;}
  .project-meta div{font-size:12.5px; color:var(--sage-soft);}
  .project-meta .k{font-family:'IBM Plex Mono', monospace; color:var(--sage); display:block; margin-bottom:3px; text-transform:uppercase; letter-spacing:0.08em; font-size:10.5px;}
  .project-link{
    font-size:13px; font-weight:500; text-decoration:none; color:var(--sage);
    border-bottom:1px solid var(--sage); padding-bottom:2px;
    font-family:'IBM Plex Mono', monospace; text-transform:uppercase; letter-spacing:0.04em;
  }

  /* ---------- CONTACT ---------- */
  .contact{text-align:center;}
  .contact h2{font-size:clamp(32px,4.5vw,50px); max-width:16ch; margin:16px auto 26px;}
  .contact .btn-row{justify-content:center;}
  .contact-mail{font-size:14px; margin-top:28px; color:var(--sage); font-family:'IBM Plex Mono', monospace;}

  footer{
    border-top:1px solid var(--line); padding:30px 0; font-size:12.5px; color:var(--sage-soft); opacity:0.55;
  }
  footer .wrap{display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px;}

  /* reveal on scroll */
  .reveal{opacity:0; transform:translateY(18px); transition:opacity .7s ease, transform .7s ease;}
  .reveal.in{opacity:1; transform:translateY(0);}

  @media (prefers-reduced-motion: reduce){
    .reveal{opacity:1; transform:none; transition:none;}
    html{scroll-behavior:auto;}
    .scroll-hint .arrow{animation:none;}
  }

  /* ---------- RESPONSIVE ---------- */
  @media (max-width: 900px){
    .showcase-grid{grid-template-columns:1fr;}
    .showcase-tile.big{min-height:320px;}
    .about .wrap{grid-template-columns:1fr;}
    .project-card{grid-template-columns:1fr;}
    .project-card .thumb{order:-1;}
    .scroll-hint{display:none;}
  }
  @media (max-width: 640px){
    .nav-links{
      position:fixed; top:64px; left:0; right:0; background:rgba(5,31,32,0.97);
      flex-direction:column; padding:24px 32px; gap:22px;
      border-bottom:1px solid var(--line);
      transform:translateY(-130%); transition:transform .3s ease;
    }
    .nav-links.open{transform:translateY(0);}
    .nav-toggle{display:block;}
    section{padding:76px 0;}
    .hero{min-height:580px;}
    .project-card{padding:26px;}
    .scroll-card{flex:0 0 150px;}
  }
</style>
</head>
<body>

<header id="siteHeader">
  <nav class="wrap">
    <div class="logo"><span class="dot"></span>Robert Noriega</div>
    <ul class="nav-links" id="navLinks">
      <li><a href="#about">Sobre mí</a></li>
      <li><a href="#showcase">Video</a></li>
      <li><a href="#proyectos">Proyectos</a></li>
      <li><a href="#contacto">Contacto</a></li>
    </ul>
    <button class="nav-toggle" id="navToggle" aria-label="Abrir menú">
      <span></span><span></span><span></span>
    </button>
  </nav>
</header>

<section class="hero">
  <div class="hero-bg">
    <img id="heroPhoto" src="robert-hero.jpg" alt="Robert Noriega" onerror="this.style.display='none'">
    <div class="photo-overlay"></div>
  </div>
  <div class="hero-content">
    <span class="eyebrow">Diseño de Producto · Community Management</span>
    <h1>Diseño objetos.<br>Construyo <em>comunidad.</em></h1>
    <p class="lead">Soy Robert Noriega, diseñador de productos industriales y community manager. Actualmente creo contenido y piezas gráficas para mi universidad y una marca de café local.</p>
    <div class="btn-row">
      <a href="#showcase" class="btn btn-primary">Ver mi trabajo</a>
      <a href="#contacto" class="btn btn-ghost">Hablemos</a>
    </div>

    <div class="hero-scroller" id="heroScroller">
      <div class="scroll-card sc1"><div class="sc-bg"></div><span class="sc-num">01</span><span class="sc-label">Café — Reel</span></div>
      <div class="scroll-card sc2"><div class="sc-bg"></div><span class="sc-num">02</span><span class="sc-label">Universidad — Evento</span></div>
      <div class="scroll-card sc3"><div class="sc-bg"></div><span class="sc-num">03</span><span class="sc-label">Café — Producto</span></div>
      <div class="scroll-card sc4"><div class="sc-bg"></div><span class="sc-num">04</span><span class="sc-label">Universidad — Piezas</span></div>
    </div>
  </div>
  <div class="scroll-hint">Desliza <span class="arrow">→</span></div>
</section>

<section id="showcase">
  <div class="wrap">
    <div class="section-head reveal">
      <p class="eyebrow">Video</p>
      <h2>Descubre mi trabajo de una nueva forma</h2>
    </div>
    <div class="showcase-grid reveal">
      <div class="showcase-tile big">
        <div class="play-btn">▶</div>
        <span class="t-eyebrow">Reel destacado</span>
        <h3>Detrás de cámara — Marca de café</h3>
      </div>
      <div class="showcase-col">
        <div class="showcase-tile small">
          <div class="expand-btn">⤢</div>
          <span class="t-eyebrow">Universidad</span>
          <h3>Cobertura de evento</h3>
        </div>
        <div class="showcase-tile small">
          <div class="expand-btn">⤢</div>
          <span class="t-eyebrow">Café</span>
          <h3>Contenido de producto</h3>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="about bg-2" id="about">
  <div class="wrap">
    <div class="reveal">
      <p class="eyebrow">Sobre mí</p>
      <h2 style="margin-top:10px;">Entre el objeto<br>y la comunidad.</h2>
      <p>Soy diseñador de productos industriales, pero hoy también estoy construyendo mi lado como community manager: grabo con mi celular y diseño en Canva para dar vida a marcas en redes, mientras sigo formándome como diseñador.</p>
      <p>Este portafolio reúne ambos caminos — mi mirada de producto y mi trabajo de contenido — en proyectos reales para mi universidad y una marca de café.</p>
    </div>
    <ul class="tool-list reveal">
      <li><span>Diseño de producto industrial</span><span>En formación</span></li>
      <li><span>Diseño de piezas gráficas</span><span>Canva</span></li>
      <li><span>Grabación y edición</span><span>Celular / CapCut</span></li>
      <li><span>Gestión de redes</span><span>Instagram · TikTok</span></li>
      <li><span>Colaboración actual</span><span>Universidad</span></li>
      <li><span>Colaboración actual</span><span>Marca de café</span></li>
    </ul>
  </div>
</section>

<section id="proyectos">
  <div class="wrap">
    <div class="section-head reveal">
      <p class="eyebrow">Proyectos</p>
      <h2>Trabajos seleccionados</h2>
    </div>
    <div class="projects-grid">

      <article class="project-card reveal">
        <div class="thumb">Imagen del proyecto — reemplazar</div>
        <div>
          <h3>Marca de café — Identidad en redes</h3>
          <p>Piezas gráficas y contenido para redes sociales de una marca de café local: publicaciones de producto, promociones y contenido de comunidad.</p>
          <div class="project-meta">
            <div><span class="k">Cliente</span>Marca de café</div>
            <div><span class="k">Rol</span>Diseño + contenido</div>
            <div><span class="k">Herramientas</span>Canva</div>
          </div>
          <a href="#" class="project-link">Ver proyecto completo →</a>
        </div>
      </article>

      <article class="project-card reveal">
        <div class="thumb">Imagen del proyecto — reemplazar</div>
        <div>
          <h3>Universidad — Piezas y video institucional</h3>
          <p>Publicaciones y video de apoyo para actividades de la universidad: cobertura de eventos, piezas informativas y contenido para redes.</p>
          <div class="project-meta">
            <div><span class="k">Cliente</span>Universidad</div>
            <div><span class="k">Rol</span>Video + diseño</div>
            <div><span class="k">Herramientas</span>Canva · Celular</div>
          </div>
          <a href="#" class="project-link">Ver proyecto completo →</a>
        </div>
      </article>

    </div>
  </div>
</section>

<section class="contact bg-2" id="contacto">
  <div class="wrap reveal">
    <p class="eyebrow">Contacto</p>
    <h2>¿Tienes un proyecto en mente? Conversemos.</h2>
    <div class="btn-row">
      <a href="mailto:tu@email.com" class="btn btn-primary">Escríbeme</a>
      <a href="#" class="btn btn-ghost">Instagram</a>
    </div>
    <p class="contact-mail">tu@email.com</p>
  </div>
</section>

<footer>
  <div class="wrap">
    <span>© 2026 Robert Noriega</span>
    <span>Hecho con celular, Canva y ganas de aprender.</span>
  </div>
</footer>

<script>
  const toggle = document.getElementById('navToggle');
  const links = document.getElementById('navLinks');
  toggle.addEventListener('click', () => links.classList.toggle('open'));
  links.querySelectorAll('a').forEach(a => a.addEventListener('click', () => links.classList.remove('open')));

  const header = document.getElementById('siteHeader');
  window.addEventListener('scroll', () => {
    header.classList.toggle('scrolled', window.scrollY > 60);
  });

  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => { if(e.isIntersecting){ e.target.classList.add('in'); } });
  }, { threshold: 0.15 });
  document.querySelectorAll('.reveal').forEach(el => io.observe(el));
</script>

</body>
</html>
