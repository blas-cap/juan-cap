<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Juan Diego Martínez Cerpa | Full Stack Developer</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="bg-mesh"></div>

    <nav id="navbar">
        <div class="container nav-content">
            <div class="logo">JDMC.</div>
            <ul class="nav-links">
                <li><a href="#home">Inicio</a></li>
                <li><a href="#about">Sobre Mí</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Proyectos</a></li>
                <li><a href="#contact">Contacto</a></li>
            </ul>
        </div>
    </nav>

    <header id="home" class="hero container">
        <div class="hero-content reveal">
            <span class="greeting">Hola, mundo. Soy</span>
            <h1><span id="typing-name" class="typing-text"></span></h1>
            <h2>Desarrollador Full Stack</h2>
            <p class="hero-desc">
                Construyendo arquitecturas escalables, APIs RESTful y experiencias web inmersivas.
            </p>
            <a href="#projects" class="btn-glow">Ver mis proyectos</a>
        </div>
    </header>

    <section id="about" class="container">
        <h2 class="section-title reveal">Sobre Mí</h2>
        <div class="about-grid">
            <div class="about-text glass reveal">
                <div class="about-inner-padding">
                    <p>Soy un especialista en el diseño y desarrollo de soluciones web completas, enfocado en el <span class="highlight">código limpio y la eficiencia</span>.</p>
                    <p>Con profunda experiencia en bases de datos relacionales, consumo y creación de APIs RESTful con JSON, mi objetivo es construir arquitecturas verdaderamente escalables y seguras desde el servidor hasta el navegador del cliente.</p>
                </div>
            </div>
            <div class="about-stats reveal">
                <div class="stat-box glass">
                    <div class="stat-number">100%</div>
                    <div class="stat-label">Enfoque Técnico</div>
                </div>
                <div class="stat-box glass">
                    <div class="stat-number">Full</div>
                    <div class="stat-label">Stack</div>
                </div>
            </div>
        </div>
    </section>

    <section id="skills" class="container">
        <h2 class="section-title reveal">Habilidades Técnicas</h2>
        <div class="skills-grid">
            <div class="skill-item glass reveal" data-percent="100">
                <div class="skill-info"><span>HTML/CSS</span> <span class="counter">0%</span></div>
                <div class="skill-bar-bg"><div class="skill-bar-fill"></div></div>
            </div>
            <div class="skill-item glass reveal" data-percent="100">
                <div class="skill-info"><span>PHP</span> <span class="counter">0%</span></div>
                <div class="skill-bar-bg"><div class="skill-bar-fill"></div></div>
            </div>
            <div class="skill-item glass reveal" data-percent="100">
                <div class="skill-info"><span>MySQL</span> <span class="counter">0%</span></div>
                <div class="skill-bar-bg"><div class="skill-bar-fill"></div></div>
            </div>
            <div class="skill-item glass reveal" data-percent="90">
                <div class="skill-info"><span>Node.js</span> <span class="counter">0%</span></div>
                <div class="skill-bar-bg"><div class="skill-bar-fill"></div></div>
            </div>
            <div class="skill-item glass reveal" data-percent="86">
                <div class="skill-info"><span>Python</span> <span class="counter">0%</span></div>
                <div class="skill-bar-bg"><div class="skill-bar-fill"></div></div>
            </div>
            <div class="skill-item glass reveal" data-percent="80">
                <div class="skill-info"><span>JavaScript</span> <span class="counter">0%</span></div>
                <div class="skill-bar-bg"><div class="skill-bar-fill"></div></div>
            </div>
            <div class="skill-item glass reveal" data-percent="80">
                <div class="skill-info"><span>React</span> <span class="counter">0%</span></div>
                <div class="skill-bar-bg"><div class="skill-bar-fill"></div></div>
            </div>
            <div class="skill-item glass reveal" data-percent="70">
                <div class="skill-info"><span>Ruby</span> <span class="counter">0%</span></div>
                <div class="skill-bar-bg"><div class="skill-bar-fill"></div></div>
            </div>
        </div>
    </section>

    <section id="projects" class="container">
        <h2 class="section-title reveal">Proyectos Destacados</h2>
        <div class="projects-grid">
            
            <div class="project-card glass reveal">
                <span class="project-type">Backend / API</span>
                <h3 class="project-title">API RESTful E-commerce</h3>
                <p class="project-desc">Arquitectura escalable para procesamiento de pagos, gestión de inventario en tiempo real e interacciones JSON de alto rendimiento.</p>
                <div class="project-tech">
                    <span class="tech-tag">Node.js</span>
                    <span class="tech-tag">MySQL</span>
                    <span class="tech-tag">REST API</span>
                </div>
            </div>

            <div class="project-card glass reveal delay-1">
                <span class="project-type">Full Stack</span>
                <h3 class="project-title">Dashboard de Gestión</h3>
                <p class="project-desc">Panel de control neo-brutalista para visualización de datos de empresas B2B. Interfaz fluida y consumo asíncrono de múltiples endpoints.</p>
                <div class="project-tech">
                    <span class="tech-tag">React</span>
                    <span class="tech-tag">PHP</span>
                    <span class="tech-tag">Python</span>
                </div>
            </div>

            <div class="project-card glass reveal delay-2">
                <span class="project-type">Arquitectura</span>
                <h3 class="project-title">Core de Microservicios</h3>
                <p class="project-desc">Sistema distribuido para alta concurrencia, balanceo de carga y aislamiento de bases de datos relacionales.</p>
                <div class="project-tech">
                    <span class="tech-tag">Docker</span>
                    <span class="tech-tag">MySQL</span>
                    <span class="tech-tag">Ruby</span>
                </div>
            </div>

        </div>
    </section>

    <footer id="contact" class="container">
        <div class="footer-content reveal glass">
            <h2>¿Listo para construir algo extraordinario?</h2>
            <p class="footer-desc">
                Actualmente abierto a nuevas oportunidades como Desarrollador Full Stack. Si buscas código robusto y un diseño impecable, hablemos.
            </p>
            <div class="social-links">
                <a href
