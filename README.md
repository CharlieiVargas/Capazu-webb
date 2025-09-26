<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CTP Ing. Carlos Pascua Zúñiga</title>
  <style>
    * {margin:0; padding:0; box-sizing:border-box;}
    body {
      font-family: 'Segoe UI', sans-serif;
      line-height:1.6;
      background:#f8fafc;
      color:#334155;
    }

    /* HEADER */
    .header {
      background:#1e293b;
      color:white;
      padding:1.5rem;
      text-align:center;
    }
    .header h1 {font-size:1.6rem;}
    .header p {font-size:1rem; opacity:.9;}

    /* NAV MOBILE */
    .nav-container {
      background:#fff;
      border-bottom:2px solid #1e293b;
      position:sticky; top:0; z-index:100;
    }
    .nav {
      display:none;
      flex-direction:column;
      gap:.5rem;
      padding:1rem;
    }
    .nav-button {
      padding:.8rem;
      border:none;
      border-radius:8px;
      background:#e2e8f0;
      font-weight:600;
      cursor:pointer;
      transition:.3s;
    }
    .nav-button:hover {background:#cbd5e1;}
    .nav-button.active {background:#1e293b; color:white;}

    /* Botón hamburguesa */
    .menu-toggle {
      display:flex;
      justify-content:space-between;
      align-items:center;
      padding:1rem;
      cursor:pointer;
      background:#f1f5f9;
    }
    .menu-toggle span {font-size:1.4rem; font-weight:bold;}

    /* SECCIONES */
    .container {padding:1rem;}
    .section {
      display:none;
      background:#fff;
      padding:1.5rem;
      border-radius:12px;
      margin:1rem 0;
      box-shadow:0 4px 12px rgba(0,0,0,0.1);
    }
    .section.active {display:block;}
    .section-title {
      font-size:1.4rem;
      margin-bottom:1rem;
      text-align:center;
    }
    .intro-text {text-align:center; font-size:1rem; margin-bottom:1rem;}
    .highlight-box, .important-note {
      padding:1rem; border-radius:10px; margin:1rem 0;
      background:#e0f2fe;
    }
    .important-note {background:#fde68a; color:#92400e;}

    /* Cards simples */
    .card {
      background:#f1f5f9;
      padding:1rem;
      border-radius:10px;
      margin-bottom:1rem;
    }
    .card h3 {margin-bottom:.5rem; font-size:1.1rem;}
    .card p {font-size:.95rem;}

    @media(min-width:768px){
      .nav{display:flex; flex-direction:row; justify-content:center;}
      .menu-toggle{display:none;}
      .card{margin:1rem;}
      .grid{display:grid; grid-template-columns:repeat(2,1fr); gap:1rem;}
    }
  </style>
</head>
<body>
  <header class="header">
    <h1>CTP Ing. Carlos Pascua Zúñiga</h1>
    <p>Excelencia académica y formación técnica</p>
  </header>

  <!-- Menú -->
  <div class="nav-container">
    <div class="menu-toggle" onclick="toggleMenu()">
      <span>☰ Menú</span>
    </div>
    <div class="nav" id="navMenu">
      <button class="nav-button active" onclick="showSection('presentacion')">🏠 Inicio</button>
      <button class="nav-button" onclick="showSection('mision')">🎯 Misión</button>
      <button class="nav-button" onclick="showSection('especialidades')">📚 Especialidades</button>
      <button class="nav-button" onclick="showSection('contacto')">📞 Contacto</button>
    </div>
  </div>

  <div class="container">
    <!-- Presentación -->
    <section id="presentacion" class="section active">
      <h2 class="section-title">Nuestra Institución</h2>
      <p class="intro-text">El Colegio Técnico Profesional Ingeniero Carlos Pascua Zúñiga combina formación académica con preparación técnica especializada.</p>
      <div class="highlight-box">
        <h3>🌟 ¿Por qué elegir educación técnica?</h3>
        <p>Certificaciones reconocidas, acceso laboral y base sólida para estudios universitarios.</p>
      </div>
    </section>

    <!-- Misión -->
    <section id="mision" class="section">
      <h2 class="section-title">Misión</h2>
      <p>Formar profesionales integrales con valores, preparados para el desarrollo de Costa Rica.</p>
    </section>

    <!-- Especialidades -->
    <section id="especialidades" class="section">
      <h2 class="section-title">Especialidades</h2>
      <div class="grid">
        <div class="card"><h3>💻 Desarrollo Web</h3><p>HTML, CSS, JS, BD, backend y frontend.</p></div>
        <div class="card"><h3>🏦 Banca y Finanzas</h3><p>Operaciones bancarias y productos financieros.</p></div>
      </div>
    </section>

    <!-- Contacto -->
    <section id="contacto" class="section">
      <h2 class="section-title">Contacto</h2>
      <p>📞 Teléfono: 1234-5678</p>
      <p>📧 Email: ejemplo@ctp.ac.cr</p>
    </section>
  </div>

  <script>
    function toggleMenu(){
      document.getElementById("navMenu").classList.toggle("show");
      let nav = document.getElementById("navMenu");
      nav.style.display = (nav.style.display === "flex") ? "none" : "flex";
    }

    function showSection(id){
      document.querySelectorAll('.section').forEach(sec=>sec.classList.remove('active'));
      document.getElementById(id).classList.add('active');
      document.querySelectorAll('.nav-button').forEach(btn=>btn.classList.remove('active'));
      event.target.classList.add('active');
      if(window.innerWidth < 768){ // cerrar menú en móvil
        document.getElementById("navMenu").style.display="none";
      }
    }
  </script>
</body>
</html>

