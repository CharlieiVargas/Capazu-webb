:root {
  --primary: #1e40af;
  --primary-light: #3b82f6;
  --primary-dark: #1e3a8a;
  --secondary: #64748b;
  --background: #f8fafc;
  --surface: #ffffff;
  --text: #1e293b;
  --text-light: #64748b;
  --accent: #10b981;
  --border: #e2e8f0;
  --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
  --shadow-lg: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
}

body {
  font-family: 'Inter', 'Segoe UI', sans-serif;
  background: var(--background);
  color: var(--text);
  line-height: 1.6;
  overflow-x: hidden;
}

/* Header moderno con gradiente dinámico */
header {
  background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary-light) 100%);
  position: relative;
  overflow: hidden;
  padding: 3rem 1rem;
  text-align: center;
  color: white;
}

header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.05'%3E%3Ccircle cx='30' cy='30' r='4'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
  animation: float 20s infinite linear;
}

@keyframes float {
  0% { transform: translateX(0) translateY(0); }
  100% { transform: translateX(-60px) translateY(-60px); }
}

.header-content {
  position: relative;
  z-index: 2;
  max-width: 1200px;
  margin: 0 auto;
}

header h1 {
  font-size: clamp(1.8rem, 5vw, 3rem);
  font-weight: 800;
  margin-bottom: 0.5rem;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

header p {
  font-size: clamp(1rem, 3vw, 1.2rem);
  opacity: 0.95;
  max-width: 600px;
  margin: 0 auto;
  font-weight: 300;
}

/* Navegación móvil amigable */
.nav-container {
  background: rgba(30, 41, 59, 0.95);
  backdrop-filter: blur(10px);
  position: sticky;
  top: 0;
  z-index: 1000;
  padding: 0.5rem 1rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

nav {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  gap: 0.5rem;
  overflow-x: auto;
  padding: 0.5rem 0;
  scrollbar-width: none;
  -ms-overflow-style: none;
}

nav::-webkit-scrollbar {
  display: none;
}

nav button {
  background: linear-gradient(135deg, var(--primary-light), var(--primary));
  border: none;
  color: white;
  padding: 0.8rem 1.2rem;
  border-radius: 12px;
  cursor: pointer;
  font-weight: 600;
  font-size: 0.9rem;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  white-space: nowrap;
  box-shadow: var(--shadow);
  position: relative;
  overflow: hidden;
}

nav button::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s;
}

nav button:hover::before {
  left: 100%;
}

nav button:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-lg);
}

nav button.active {
  background: linear-gradient(135deg, var(--accent), #059669);
  transform: translateY(-2px);
  box-shadow: var(--shadow-lg);
}

/* Contenido principal */
.main-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

section {
  display: none;
  padding: 2rem 0;
  animation: slideIn 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

section.active {
  display: block;
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-header h2 {
  color: var(--primary-dark);
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 800;
  margin-bottom: 1rem;
  position: relative;
  display: inline-block;
}

.section-header h2::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 4px;
  background: linear-gradient(90deg, var(--primary-light), var(--accent));
  border-radius: 2px;
}

/* Cards modernos y responsivos */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.card {
  background: var(--surface);
  border-radius: 20px;
  padding: 2rem;
  box-shadow: var(--shadow);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  border: 1px solid var(--border);
  position: relative;
  overflow: hidden;
}

.card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: linear-gradient(90deg, var(--primary-light), var(--accent));
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: var(--shadow-lg);
}

.card h3 {
  color: var(--primary-dark);
  font-size: 1.3rem;
  font-weight: 700;
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.card p {
  color: var(--text-light);
  line-height: 1.7;
  margin: 0;
}

/* Especialidades con íconos mejorados */
.specialty-card {
  background: var(--surface);
  border-radius: 20px;
  padding: 2rem;
  border-left: 6px solid var(--primary-light);
  box-shadow: var(--shadow);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
}

.specialty-card::before {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  width: 100px;
  height: 100px;
  background: linear-gradient(135deg, var(--primary-light), var(--accent));
  opacity: 0.05;
  border-radius: 0 20px 0 50%;
}

.specialty-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-lg);
  border-left-color: var(--accent);
}

.specialty-card h3 {
  color: var(--primary-dark);
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  gap: 0.8rem;
}

/* Galería moderna */
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.gallery-item {
  position: relative;
  border-radius: 16px;
  overflow: hidden;
  aspect-ratio: 1;
  box-shadow: var(--shadow);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.gallery-item:hover {
  transform: scale(1.05);
  box-shadow: var(--shadow-lg);
}

.gallery img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.gallery-item:hover img {
  transform: scale(1.1);
}

/* Horarios responsivos */
.schedule-tabs {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
  margin-bottom: 2rem;
  justify-content: center;
}

.schedule-tabs button {
  padding: 1rem 1.5rem;
  border: 2px solid var(--border);
  border-radius: 12px;
  background: var(--surface);
  cursor: pointer;
  font-weight: 600;
  color: var(--text);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  font-size: 0.9rem;
}

.schedule-tabs button:hover {
  border-color: var(--primary-light);
  color: var(--primary-light);
}

.schedule-tabs button.active {
  background: var(--primary-light);
  color: white;
  border-color: var(--primary-light);
  box-shadow: var(--shadow);
}

.schedule-content {
  display: none;
  background: var(--surface);
  border-radius: 16px;
  overflow: hidden;
  box-shadow: var(--shadow);
}

.schedule-content.active {
  display: block;
  animation: fadeIn 0.4s ease-in-out;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.table-container {
  overflow-x: auto;
  border-radius: 16px;
}

table {
  width: 100%;
  border-collapse: collapse;
  min-width: 600px;
  font-size: 0.9rem;
}

th, td {
  padding: 1rem;
  text-align: center;
  border-bottom: 1px solid var(--border);
}

th {
  background: var(--primary-dark);
  color: white;
  font-weight: 600;
  position: sticky;
  top: 0;
}

td {
  background: var(--surface);
  transition: background-color 0.2s;
}

tr:hover td {
  background: rgba(59, 130, 246, 0.05);
}

/* Información de contacto moderna */
.contact-info {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.contact-card {
  background: var(--surface);
  padding: 2rem;
  border-radius: 20px;
  text-align: center;
  box-shadow: var(--shadow);
  transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.contact-card:hover {
  transform: translateY(-5px);
}

.contact-icon {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, var(--primary-light), var(--accent));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
  font-size: 1.5rem;
}

/* Footer moderno */
footer {
  background: linear-gradient(135deg, var(--text) 0%, #0f172a 100%);
  color: white;
  padding: 3rem 1rem 1.5rem;
  margin-top: 4rem;
  position: relative;
  overflow: hidden;
}

footer::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--primary-light), var(--accent));
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
}

footer p {
  margin: 0.5rem 0;
  opacity: 0.9;
}

/* Animación de entrada */
.fade-in {
  opacity: 0;
  animation: fadeInUp 0.6s ease-out forwards;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive mejorado */
@media (max-width: 768px) {
  header {
    padding: 2rem 1rem;
  }

  .nav-container {
    padding: 0.5rem;
  }

  nav {
    gap: 0.3rem;
  }

  nav button {
    padding: 0.6rem 1rem;
    font-size: 0.8rem;
  }

  section {
    padding: 1.5rem 0;
  }

  .section-header {
    margin-bottom: 2rem;
  }

  .card-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }

  .card {
    padding: 1.5rem;
  }

  .gallery {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1rem;
  }

  .schedule-tabs {
    gap: 0.5rem;
  }

  .schedule-tabs button {
    padding: 0.8rem 1rem;
    font-size: 0.8rem;
  }

  th, td {
    padding: 0.8rem 0.5rem;
    font-size: 0.8rem;
  }
}

@media (max-width: 480px) {
  .main-container {
    padding: 0 0.5rem;
  }

  header {
    padding: 1.5rem 0.5rem;
  }

  .card {
    padding: 1rem;
  }

  .specialty-card {
    padding: 1rem;
  }

  .contact-card {
    padding: 1.5rem;
  }
}

/* Indicador de carga suave */
.loading {
  opacity: 0.5;
  transition: opacity 0.3s ease;
}

/* Mejoras de accesibilidad */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}

/* Focus states para accesibilidad */
button:focus,
nav button:focus {
  outline: 3px solid var(--accent);
  outline-offset: 2px;
}

/* Scrollbar personalizada */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: var(--background);
}

::-webkit-scrollbar-thumb {
  background: var(--primary-light);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: var(--primary-dark);
}
