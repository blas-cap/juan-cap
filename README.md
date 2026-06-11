<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Juan Diego Martínez Cerpa | Full Stack Developer</title>
    <style>
        /* ========================================
           VARIABLES & RESET
        ======================================== */
        :root {
            --bg-color: #070709;
            --glass-bg: rgba(255, 255, 255, 0.04);
            --glass-border: rgba(255, 255, 255, 0.08);
            --accent-cyan: #00f0ff;
            --accent-purple: #bd00ff;
            --text-main: #f8f8f8;
            --text-muted: #a0a0b0;
            --font-main: 'Segoe UI', system-ui, -apple-system, sans-serif;
            --transition-smooth: all 0.4s cubic-bezier(0.23, 1, 0.32, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-main);
            background-color: var(--bg-color);
            color: var(--text-main);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated Background Mesh */
        .bg-mesh {
            position: fixed;
            top: 0; left: 0; width: 100vw; height: 100vh;
            z-index: -1;
            background: 
                radial-gradient(circle at 15% 50%, rgba(0, 240, 255, 0.06), transparent 40%),
                radial-gradient(circle at 85% 30%, rgba(189, 0, 255, 0.06), transparent 40%);
            filter: blur(80px);
            animation: pulseBg 10s infinite alternate;
        }

        @keyframes pulseBg {
            0% { transform: scale(1); opacity: 0.8; }
            100% { transform: scale(1.1); opacity: 1; }
        }

        /* ========================================
           UTILITIES (Glassmorphism & Reveal)
        ======================================== */
        .glass {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.3);
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* ========================================
           NAVIGATION
        ======================================== */
        nav {
            position: fixed;
            top: 0; left: 0; width: 100%;
            padding: 1.5rem 0;
            z-index: 1000;
            transition: var(--transition-smooth);
        }

        nav.scrolled {
            padding: 1rem 0;
            background: rgba(7, 7, 9, 0.8);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid var(--glass-border);
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.2rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
            background: linear-gradient(90deg, var(--accent-cyan), var(--accent-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a
