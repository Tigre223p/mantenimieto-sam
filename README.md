<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <meta name="description" content="Computadores y Play - Tu sitio de tecnologia, precios, ayuda y mucho mas. Explora computadores, servicios y soluciones tecnologicas."/>
  <meta name="keywords" content="computadores, precios, tecnología, ayuda, tienda online, PC gaming, laptop, servicio técnico"/>
  <meta name="author" content="Computadores y Play"/>
  <meta name="theme-color" content="#1d1fb1"/>
  <meta property="og:title" content="Computadores y Play"/>
  <meta property="og:description" content="Tu sitio de tecnologia, precios, ayuda y mucho mas. Explora todo lo que tenemos para ti."/>
  <meta property="og:type" content="website"/>
  <meta name="twitter:card" content="summary_large_image"/>
  <meta name="twitter:title" content="Computadores y Play"/>
  <meta name="twitter:description" content="Tu sitio de tecnologia, precios, ayuda y mucho mas"/>
  <title>Computadores y Play - Tecnología, Precios y Ayuda</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      overflow-x: hidden;
      color: white;
    }

    
    #fondo-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 80px 20px 40px;
      gap: 20px;
    }

    .hero h1 {
      font-size: 3rem;
      color: rgb(204, 238, 13);
      animation: brillar 15s ease-in-out infinite;
      letter-spacing: 2px;
    }

    .hero p {
      font-size: 1.2rem;
      opacity: 0.85;
      max-width: 500px;
    }

    @keyframes brillar {
      0%   { text-shadow: 0 0 10px rgb(255, 51, 0); }
      50%  { text-shadow: 0 0 40px rgb(148, 127, 33), 0 0 80px rgb(228, 247, 65); }
      100% { text-shadow: 0 0 10px rgb(208, 255, 0); }
    }

    /* ── BOTONES ── */
    button {
      padding: 14px 32px;
      font-size: 1rem;
      color: white;
      background: rgb(29, 31, 177);
      border: none;
      border-radius: 50px;
      cursor: pointer;
      animation: pulso 1.7s ease-in-out infinite;
    }

    @keyframes pulso {
      0%, 100% { transform: scale(1); box-shadow: 0 0 10px rgb(255, 174, 0); }
      50%       { transform: scale(1.1); box-shadow: 0 0 30px rgb(255, 230, 0); }
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      display: flex;
      align-items: center;
      gap: 20px;
      padding: 15px 25px;
      background: rgba(0, 0, 0, 0.45);
      backdrop-filter: blur(8px);
      z-index: 100;
    }

    .nav-logo {
      font-size: 1.1rem;
      font-weight: bold;
      color: rgb(204, 238, 13);
      margin-right: auto;
      letter-spacing: 1px;
    }

    nav a.activo {
      color: yellow;
      border-bottom: 2px solid yellow;
    }

    nav a {
      color: white;
      text-decoration: none;
      font-size: 0.95rem;
      position: relative;
    }

    nav a::after {
      content: '';
      position: absolute;
      bottom: -3px;
      left: 0;
      width: 0;
      height: 2px;
      background: yellow;
      transition: width 0.3s ease;
    }

    nav a:hover::after {
      width: 100%;
    }

    html {
      scroll-behavior: smooth;
    }

    /* ── SECCIONES ── */
    section {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 80px 20px 40px;
    }

    section div.contenido {
      text-align: center;
      color: white;
      max-width: 400px;
    }

    .icono-seccion {
      font-size: 3.5rem;
      margin-bottom: 16px;
      display: block;
    }

    section h2 {
      font-size: 2rem;
      margin-bottom: 10px;
    }

    section p {
      font-size: 1rem;
      margin-bottom: 24px;
      opacity: 0.8;
      line-height: 1.5;
    }

    /* colores de cada seccion */
    #principal   { background: rgba(19, 230, 124, 0.35); }
    #precios     { background: rgba(200, 0, 100, 0.35); }
    #sugerencias { background: rgba(50, 50, 200, 0.35); }
    #ayudas      { background: rgba(200, 150, 0, 0.35); }
    #ajustes     { background: rgba(150, 0, 200, 0.35); }
    #ia          { background: rgba(81, 204, 179, 0.35); }
    #creditos    { background: rgba(100, 100, 100, 0.35); }

    /* ── FOOTER ── */
    footer {
      background: rgba(0, 0, 0, 0.6);
      backdrop-filter: blur(8px);
      text-align: center;
      padding: 30px 20px;
      color: rgba(255, 255, 255, 0.7);
      font-size: 0.9rem;
      line-height: 1.8;
    }

    footer span {
      color: rgb(204, 238, 13);
    }

    /* ── BOTON VOLVER ARRIBA ── */
    #btn-arriba {
      position: fixed;
      bottom: 30px;
      right: 30px;
      width: 48px;
      height: 48px;
      border-radius: 50%;
      background: rgba(29, 31, 177, 0.85);
      color: white;
      font-size: 1.4rem;
      border: none;
      cursor: pointer;
      display: none;
      align-items: center;
      justify-content: center;
      box-shadow: 0 0 15px rgba(255, 200, 0, 0.5);
      animation: none;
      z-index: 200;
      transition: opacity 0.3s;
    }

    #btn-arriba:hover {
      background: rgba(29, 31, 177, 1);
    }

    #btn-arriba.visible {
      display: flex;
    }
  </style>
</head>
<body>

  <!-- canvas del fondo animado -->
  <canvas id="fondo-canvas"></canvas>

  <!-- nav con logo -->
  <nav>
    <a href="#" class="nav-logo">💻 Computadores y Play</a>
    <a href="#principal">principal</a>
    <a href="#precios">precios</a>
    <a href="#sugerencias">sugerencias</a>
    <a href="#ayudas">ayudas</a>
    <a href="#ajustes">ajustes</a>
    <a href="#ia">IA</a>
    <a href="#creditos">creditos</a>
  </nav>

  <!-- hero section -->
  <div class="hero">
    <h1>Computadores y Play</h1>
    <p>Tu sitio de tecnologia, precios, ayuda y mucho mas. Explora todo lo que tenemos para ti.</p>
    <button onclick="window.location.href='proyecto.html'">haz click para conocer mas</button>
  </div>

  <section id="principal">
    <div class="contenido">
      <span class="icono-seccion">🏠</span>
      <h2>Principal</h2>
      <p>todo lo que quieres saber sobre mi proyecto</p>
      <button onclick="window.location.href='mi primer proyecto.html'">haz click</button>
    </div>
  </section>

  <section id="precios">
    <div class="contenido">
      <span class="icono-seccion">💰</span>
      <h2>Precios</h2>
      <p>Consulta nuestros planes y tarifas</p>
      <button onclick="window.location.href='precios.html'">haz click</button>
    </div>
  </section>

  <section id="sugerencias">
    <div class="contenido">
      <span class="icono-seccion">💡</span>
      <h2>Sugerencias</h2>
      <p>Envianos tus ideas y comentarios</p>
      <button onclick="window.location.href='sugerencias.html'">haz click</button>
    </div>
  </section>

  <section id="ayudas">
    <div class="contenido">
      <span class="icono-seccion">🆘</span>
      <h2>Ayudas</h2>
      <p>Encuentra respuestas a tus preguntas</p>
      <button onclick="window.location.href='ayudas.html'">haz click</button>
    </div>
  </section>

  <section id="ajustes">
    <div class="contenido">
      <span class="icono-seccion">⚙️</span>
      <h2>Ajustes</h2>
      <p>Configura tu experiencia</p>
      <button onclick="window.location.href='ajustes.html'">haz click</button>
    </div>
  </section>

  <section id="ia">
    <div class="contenido">
      <span class="icono-seccion">🤖</span>
      <h2>IA</h2>
      <p>Chatea con nuestra inteligencia artificial</p>
      <button onclick="window.location.href='chatbot.html'">haz click</button>
    </div>
  </section>

  <section id="creditos">
    <div class="contenido">
      <span class="icono-seccion">🏆</span>
      <h2>Creditos</h2>
      <p>agradecemos al que hiso este proyecto</p>
      <button onclick="window.location.href='creditos.html'">haz click</button>
    </div>
  </section>

  <!-- footer -->
  <footer>
    <p><span>💻 Computadores y Play</span></p>
    <p>Proyecto personal &mdash; Todos los derechos reservados</p>
    <p>Hecho con dedicacion y codigo</p>
  </footer>

  <!-- boton volver arriba -->
  <button id="btn-arriba" onclick="window.scrollTo({top:0, behavior:'smooth'})">&#8679;</button>

  <script>
    /* ── FONDO ANIMADO CON CANVAS ── */
    const canvas = document.getElementById('fondo-canvas');
    const ctx = canvas.getContext('2d');

    let colorAngle = 0;
    const particulas = [];
    const CANTIDAD = 80;

    function colorHSL(h, s, l) {
      return `hsl(${h}, ${s}%, ${l}%)`;
    }

    function crearParticula() {
      return {
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        radio: Math.random() * 3 + 1,
        velocidadX: (Math.random() - 0.5) * 0.6,
        velocidadY: (Math.random() - 0.5) * 0.6,
        tono: Math.random() * 360,
        opacidad: Math.random() * 0.6 + 0.2
      };
    }

    function iniciarParticulas() {
      particulas.length = 0;
      for (let i = 0; i < CANTIDAD; i++) {
        particulas.push(crearParticula());
      }
    }

    function ajustarCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
      iniciarParticulas();
    }

    function dibujar() {
      colorAngle += 0.3;
      const grad = ctx.createLinearGradient(0, 0, canvas.width, canvas.height);
      grad.addColorStop(0, colorHSL((colorAngle) % 360, 70, 15));
      grad.addColorStop(0.5, colorHSL((colorAngle + 120) % 360, 60, 10));
      grad.addColorStop(1, colorHSL((colorAngle + 240) % 360, 70, 15));
      ctx.fillStyle = grad;
      ctx.fillRect(0, 0, canvas.width, canvas.height);

      particulas.forEach(p => {
        p.x += p.velocidadX;
        p.y += p.velocidadY;
        p.tono = (p.tono + 0.5) % 360;

        if (p.x < 0 || p.x > canvas.width)  p.velocidadX *= -1;
        if (p.y < 0 || p.y > canvas.height) p.velocidadY *= -1;

        const brillo = ctx.createRadialGradient(p.x, p.y, 0, p.x, p.y, p.radio * 6);
        brillo.addColorStop(0, `hsla(${p.tono}, 100%, 70%, ${p.opacidad})`);
        brillo.addColorStop(1, `hsla(${p.tono}, 100%, 70%, 0)`);

        ctx.beginPath();
        ctx.arc(p.x, p.y, p.radio * 6, 0, Math.PI * 2);
        ctx.fillStyle = brillo;
        ctx.fill();

        ctx.beginPath();
        ctx.arc(p.x, p.y, p.radio, 0, Math.PI * 2);
        ctx.fillStyle = `hsla(${p.tono}, 100%, 90%, ${p.opacidad + 0.3})`;
        ctx.fill();
      });

      requestAnimationFrame(dibujar);
    }

    window.addEventListener('resize', ajustarCanvas);
    ajustarCanvas();
    dibujar();

    /* ── BOTON VOLVER ARRIBA ── */
    const btnArriba = document.getElementById('btn-arriba');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 400) {
        btnArriba.classList.add('visible');
      } else {
        btnArriba.classList.remove('visible');
      }
    });

    const secciones = document.querySelectorAll('section');
    const enlaces = document.querySelectorAll('nav a');

    const observer = new IntersectionObserver((entradas) => {
      entradas.forEach(entrada => {
        if (entrada.isIntersecting) {
          enlaces.forEach(a => a.classList.remove('activo'));
          const enlaceActivo = document.querySelector(`nav a[href="#${entrada.target.id}"]`);
          if (enlaceActivo) enlaceActivo.classList.add('activo');
        }
      });
    }, { threshold: 0.5 });

    secciones.forEach(s => observer.observe(s));
 
  </script>
 
</body>
</html>
