<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Juan Diego Martínez Cerpa | Full Stack Developer</title>
    <style>
        /* ================= VARIABLES & RESET ================= */
        :root {
            --bg-color: #0b0c10;
            --glass-bg: rgba(255, 255, 255, 0.03);
            --glass-border: rgba(255, 255, 255, 0.05);
            --accent-1: #00e5ff; /* Cyan */
            --accent-2: #b000ff; /* Purple */
            --text-main: #ffffff;
            --text-muted: #8a8d98;
            --font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: var(--font-family);
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            overflow-x: hidden;
            position: relative;
        }

        /* ================= BACKGROUND ANIMATED BLOBS ================= */
        .blob {
            position: absolute;
            filter: blur(80px);
            z-index: -1;
            opacity: 0.5;
            animation: float 10s infinite ease-in-out alternate;
        }
        .blob-1 {
            top: -10%; left: -10%; width: 500px; height: 500px;
            background: radial-gradient(circle, var(--accent-2), transparent 70%);
        }
        .blob-2 {
            top: 40%; right: -10%; width: 400px; height: 400px;
            background: radial-gradient(circle, var(--accent-1), transparent 70%);
            animation-delay: -5s;
        }

        @keyframes float {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(50px, 50px) scale(1.1); }
        }

        /* ================= NAVIGATION ================= */
        nav {
            position: fixed;
            top: 0; width: 100%;
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(11, 12, 16, 0.7);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid var(--glass-border);
            z-index: 1000;
            transition: 0.3s ease;
        }
        .logo { font-size: 1.5rem; font-weight: bold; letter-spacing: 1px; }
        .logo span { color: var(--accent-1); }
        .nav-links a {
            color: var(--text-main);
            text-decoration: none;
            margin-left: 30px;
            font-weight: 500;
            transition: 0.3s;
        }
        .nav-links a:hover { color: var(--accent-1); text-shadow: 0 0 10px var(--accent-1); }

        /* ================= HERO SECTION ================= */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
        }
        .hero h1 {
            font-size: 4rem;
            margin-bottom: 10px;
            background: linear-gradient(90deg, var(--accent-1), var(--accent-2));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero h2 {
            font-size: 2rem;
            font-weight: 400;
            color: var(--text-muted);
            margin-bottom: 30px;
        }
        .typewriter {
            border-right: 3px solid var(--accent-1);
            white-space: nowrap;
            overflow: hidden;
            animation: blink 0.75s step-end infinite;
        }
        @keyframes blink { 50% { border-color: transparent; } }

        .btn-glow {
            padding: 15px 40px;
            font-size: 1.2rem;
            font-weight: bold;
            color: #fff;
            background: transparent;
            border: 2px solid var(--accent-1);
            border-radius: 50px;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: 0.4s;
            text-decoration: none;
        }
        .btn-glow:hover {
            background: var(--accent-1);
            box-shadow: 0 0 20px var(--accent-1), 0 0 40px var(--accent-1);
            color: #000;
        }

        /* ================= SECTIONS LAYOUT ================= */
        section {
            padding: 100px 10%;
        }
        .section-title {
            font-size: 2.5rem;
            margin-bottom: 50px;
            text-align: center;
        }
        .section-title span { color: var(--accent-2); }

        /* ================= SKILLS SECTION ================= */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        .skill-card {
            background: var(--glass-bg);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            backdrop-filter: blur(10px);
            transition: transform 0.3s;
        }
        .skill-card:hover { transform: translateY(-10px); }
        .skill-name { font-size: 1.2rem; margin-bottom: 15px; font-weight: bold; }
        
        .progress-bar {
            width: 100%;
            height: 10px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--accent-1), var(--accent-2));
            width: 0; /* Will be animated via JS */
            border-radius: 10px;
            transition: width 1.5s cubic-bezier(0.1, 0.5, 0.1, 1);
        }
        .skill-percent {
            margin-top: 10px;
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--accent-1);
        }

        /* ================= PROJECTS SECTION (3D TILT) ================= */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }
        .project-card {
            background: var(--glass-bg);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 20px;
            backdrop-filter: blur(10px);
            transform-style: preserve-3d;
            transform: perspective(1000px);
        }
        .project-img {
            width: 100%;
            height: 200px;
            background: #1e1e24;
            border-radius: 15px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            transform: translateZ(30px); /* 3D pop effect */
        }
        .project-info { transform: translateZ(20px); }
        .project-info h3 { margin-bottom: 10px; color: var(--accent-1); }
        .project-info p { color: var(--text-muted); font-size: 0.9rem; margin-bottom: 15px; }
        .tag {
            background: rgba(255,255,255,0.1);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-right: 5px;
            display: inline-block;
        }

        /* ================= SCROLL REVEAL ANIMATIONS ================= */
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease-out;
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* ================= RESPONSIVE ================= */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            nav { padding: 20px; flex-direction: column; gap: 15px; }
            .nav-links { display: flex; gap: 15px; flex-wrap: wrap; justify-content: center; }
            .nav-links a { margin: 0; }
        }
    </style>
</head>
<body>

    <!-- Animated Background -->
    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>

    <!-- Navigation -->
    <nav>
        <div class="logo">Juan<span>Diego</span></div>
        <div class="nav-links">
            <a href="#about">Sobre Mí</a>
            <a href="#skills">Habilidades</a>
            <a href="#projects">Proyectos</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <h1>Juan Diego Martínez</h1>
        <h2><span class="typewriter" id="typewriter-text"></span></h2>
        <p class="reveal" style="max-width: 600px; color: var(--text-muted); margin-bottom: 40px;">
            Especialista en bases de datos relacionales, consumo y creación de APIs RESTful con arquitecturas escalables de alto rendimiento.
        </p>
        <a href="#projects" class="btn-glow reveal" style="transition-delay: 0.2s;">Ver Mis Proyectos</a>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <h2 class="section-title reveal">Mi Stack <span>Tecnológico</span></h2>
        <div class="skills-grid">
            <!-- HTML/CSS -->
            <div class="skill-card reveal">
                <div class="skill-name">HTML5 & CSS3</div>
                <div class="progress-bar">
                    <div class="progress-fill" data-target="100"></div>
                </div>
                <div class="skill-percent counter" data-target="100">0%</div>
            </div>
            <!-- PHP -->
            <div class="skill-card reveal">
                <div class="skill-name">PHP</div>
                <div class="progress-bar">
                    <div class="progress-fill" data-target="100"></div>
                </div>
                <div class="skill-percent counter" data-target="100">0%</div>
            </div>
            <!-- MySQL -->
            <div class="skill-card reveal">
                <div class="skill-name">MySQL</div>
                <div class="progress-bar">
                    <div class="progress-fill" data-target="100"></div>
                </div>
                <div class="skill-percent counter" data-target="100">0%</div>
            </div>
            <!-- Node.js & APIs -->
            <div class="skill-card reveal">
                <div class="skill-name">Node.js & JSON APIs</div>
                <div class="progress-bar">
                    <div class="progress-fill" data-target="90"></div>
                </div>
                <div class="skill-percent counter" data-target="90">0%</div>
            </div>
            <!-- Python -->
            <div class="skill-card reveal">
                <div class="skill-name">Python</div>
                <div class="progress-bar">
                    <div class="progress-fill" data-target="86"></div>
                </div>
                <div class="skill-percent counter" data-target="86">0%</div>
            </div>
            <!-- JavaScript -->
            <div class="skill-card reveal">
                <div class="skill-name">JavaScript</div>
                <div class="progress-bar">
                    <div class="progress-fill" data-target="80"></div>
                </div>
                <div class="skill-percent counter" data-target="80">0%</div>
            </div>
            <!-- React -->
            <div class="skill-card reveal">
                <div class="skill-name">React</div>
                <div class="progress-bar">
                    <div class="progress-fill" data-target="80"></div>
                </div>
                <div class="skill-percent counter" data-target="80">0%</div>
            </div>
            <!-- Ruby -->
            <div class="skill-card reveal">
                <div class="skill-name">Ruby</div>
                <div class="progress-bar">
                    <div class="progress-fill" data-target="70"></div>
                </div>
                <div class="skill-percent counter" data-target="70">0%</div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <h2 class="section-title reveal">Proyectos <span>Destacados</span></h2>
        <div class="projects-grid">
            
            <!-- Project 1 -->
            <div class="project-card reveal">
                <div class="project-img">🛒</div>
                <div class="project-info">
                    <h3>E-Commerce API RESTful</h3>
                    <p>API completa para gestión de tiendas online. Procesamiento seguro de JSON, autenticación de usuarios y consultas optimizadas.</p>
                    <div>
                        <span class="tag">Node.js</span>
                        <span class="tag">MySQL</span>
                        <span class="tag">JSON</span>
                    </div>
                </div>
            </div>

            <!-- Project 2 -->
            <div class="project-card reveal" style="transition-delay: 0.1s;">
                <div class="project-img">📊</div>
                <div class="project-info">
                    <h3>Dashboard Corporativo</h3>
                    <p>Sistema de gestión empresarial con reportes en tiempo real. Backend robusto e interfaz asíncrona altamente responsiva.</p>
                    <div>
                        <span class="tag">PHP</span>
                        <span class="tag">React</span>
                        <span class="tag">CSS3</span>
                    </div>
                </div>
            </div>

            <!-- Project 3 -->
            <div class="project-card reveal" style="transition-delay: 0.2s;">
                <div class="project-img">🤖</div>
                <div class="project-info">
                    <h3>Automatización de Datos</h3>
                    <p>Scripts de scraping y procesamiento de grandes volúmenes de datos con almacenamiento estructurado en bases de datos relacionales.</p>
                    <div>
                        <span class="tag">Python</span>
                        <span class="tag">MySQL</span>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <script>
        // ================= 1. TYPEWRITER EFFECT =================
        const texts = ["Desarrollador Full Stack", "Creador de APIs RESTful", "Experto en Bases de Datos"];
        let count = 0;
        let index = 0;
        let currentText = "";
        let letter = "";
        let isDeleting = false;

        (function type() {
            if (count === texts.length) { count = 0; }
            currentText = texts[count];

            if (isDeleting) {
                letter = currentText.slice(0, --index);
            } else {
                letter = currentText.slice(0, ++index);
            }

            document.getElementById('typewriter-text').textContent = letter;

            let typeSpeed = isDeleting ? 50 : 100;

            if (!isDeleting && letter.length === currentText.length) {
                typeSpeed = 2000; // Pause at end
                isDeleting = true;
            } else if (isDeleting && letter.length === 0) {
                isDeleting = false;
                count++;
                typeSpeed = 500; // Pause before next word
            }
            setTimeout(type, typeSpeed);
        }());

        // ================= 2. SCROLL REVEAL & SKILLS ANIMATION =================
        const reveals = document.querySelectorAll(".reveal");
        const progressFills = document.querySelectorAll(".progress-fill");
        const counters = document.querySelectorAll(".counter");
        let animatedSkills = false;

        function reveal() {
            let windowHeight = window.innerHeight;
            
            // Generic reveal elements
            reveals.forEach(element => {
                let elementTop = element.getBoundingClientRect().top;
                let elementVisible = 100;
                if (elementTop < windowHeight - elementVisible) {
                    element.classList.add("active");
                }
            });

            // Skills specific animation
            const skillsSection = document.getElementById("skills");
            let skillsTop = skillsSection.getBoundingClientRect().top;
            
            if (skillsTop < windowHeight - 100 && !animatedSkills) {
                animatedSkills = true;
                
                // Animate bars
                progressFills.forEach(fill => {
                    fill.style.width = fill.getAttribute("data-target") + "%";
                });

                // Animate numbers
                counters.forEach(counter => {
                    const target = +counter.getAttribute('data-target');
                    const duration = 1500; // 1.5 seconds
                    const increment = target / (duration / 16); // 60fps
                    let current = 0;

                    const updateCounter = () => {
                        current += increment;
                        if (current < target) {
                            counter.innerText = Math.ceil(current) + "%";
                            requestAnimationFrame(updateCounter);
                        } else {
                            counter.innerText = target + "%";
                        }
                    };
                    updateCounter();
                });
            }
        }
        window.addEventListener("scroll", reveal);
        reveal(); // Trigger on load

        // ================= 3. VANILLA 3D TILT EFFECT ON CARDS =================
        const cards = document.querySelectorAll('.project-card');

        cards.forEach(card => {
            card.addEventListener('mousemove', e => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left; // X relative to card
                const y = e.clientY - rect.top;  // Y relative to card
                
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                
                // Calculate rotation (max 15 degrees)
                const rotateX = ((y - centerY) / centerY) * -15;
                const rotateY = ((x - centerX) / centerX) * 15;

                card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale3d(1.02, 1.02, 1.02)`;
                card.style.transition = 'none';
            });

            card.addEventListener('mouseleave', () => {
                card.style.transform = `perspective(1000px) rotateX(0deg) rotateY(0deg) scale3d(1, 1, 1)`;
                card.style.transition = 'transform 0.5s ease';
            });
            
            card.addEventListener('mouseenter', () => {
                card.style.transition = 'none';
            });
        });
    </script>
</body>
</html>
