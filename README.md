<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Portafolio - Angelo Jossepe Perez Correa</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
  <style>
    body { background: #f4f6f9; font-family: 'Segoe UI', sans-serif; }
    .hero { background: #0A3D62; color: white; padding: 60px 20px; text-align: center; }
    .section-title { color: #1B1464; margin: 40px 0 20px; text-align: center; }
    .card { border-radius: 12px; box-shadow: 0 4px 8px rgba(0,0,0,0.05); }
    footer { background: #0A3D62; color: white; text-align: center; padding: 15px; margin-top: 40px; }
  </style>
</head>
<body>
  <!-- Hero -->
  <div class="hero">
    <h1>👋 Hola, soy <b>Angelo Jossepe Perez Correa</b></h1>
    <p>Tecnólogo en Sistemas | Est. Ingeniería de Sistemas</p>
    <p>+2 años de experiencia en soporte técnico, mesa de ayuda e infraestructura TI.</p>
  </div>

  <!-- Experiencia -->
  <div class="container">
    <h2 class="section-title">💼 Experiencia</h2>
    <div class="row">
      <div class="col-md-6">
        <div class="card p-3">
          <h5>Cotecmar / Skillnet – Analista de Mesa de Ayuda</h5>
          <p><i>2022 - 2025 | Cartagena</i></p>
          <ul>
            <li>Soporte a más de 200 usuarios.</li>
            <li>Mantenimiento de equipos y recuperación de datos.</li>
            <li>Administración de Office 365 y software de ingeniería.</li>
          </ul>
        </div>
      </div>
      <div class="col-md-6">
        <div class="card p-3">
          <h5>Universidad Tecnológica de Bolívar – Soporte Técnico</h5>
          <p><i>2018 | Cartagena</i></p>
          <ul>
            <li>Resolución de incidentes de hardware y software.</li>
            <li>Instalación de programas y respaldo de información.</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- Proyectos dinámicos desde GitHub -->
  <div class="container">
    <h2 class="section-title">🚀 Proyectos en GitHub</h2>
    <div id="repos" class="row"></div>
  </div>

  <!-- Habilidades -->
  <div class="container">
    <h2 class="section-title">🛠 Habilidades</h2>
    <ul>
      <li>Soporte técnico (hardware, software, redes)</li>
      <li>Cableado estructurado, diagnóstico de puntos de red</li>
      <li>Office 365, GSuite</li>
      <li>Python, C++, HTML, CSS</li>
    </ul>
  </div>

  <!-- Contacto -->
  <div class="container">
    <h2 class="section-title">📬 Contacto</h2>
    <p>Email: <a href="mailto:anggelo20@hotmail.com">anggelo20@hotmail.com</a></p>
    <p>LinkedIn: <a href="https://linkedin.com/in/angelo-jossepe-pérez-correa">Perfil</a></p>
    <p>GitHub: <a href="https://github.com/angeloperezcorrea">Repositorios</a></p>
  </div>

  <!-- Footer -->
  <footer>
    <p>© 2025 Angelo Jossepe Perez Correa</p>
  </footer>

  <!-- Script para cargar proyectos desde GitHub -->
  <script>
    const username = "angeloperezcorrea"; // tu usuario de GitHub
    fetch(`https://api.github.com/users/${username}/repos?sort=updated`)
      .then(response => response.json())
      .then(repos => {
        const container = document.getElementById("repos");
        repos.slice(0, 6).forEach(repo => { // mostrar 6 proyectos
          const col = document.createElement("div");
          col.className = "col-md-4 mb-3";
          col.innerHTML = `
            <div class="card p-3 h-100">
              <h5>${repo.name}</h5>
              <p>${repo.description || "Sin descripción"}</p>
              <a href="${repo.html_url}" target="_blank" class="btn btn-sm btn-primary">Ver proyecto</a>
            </div>
          `;
          container.appendChild(col);
        });
      });
  </script>
</body>
</html>
