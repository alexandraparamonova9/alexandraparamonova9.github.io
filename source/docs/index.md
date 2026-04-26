<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Александра Парамонова — Портфолио</title>
    
    <!-- Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&family=Cormorant+Garamond:wght@400;500;600&display=swap" rel="stylesheet">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #f3e9da;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            color: #1a1a1a;
            line-height: 1.5;
            overflow-x: hidden;
        }

        /* Smooth scroll behavior */
        html {
            scroll-behavior: smooth;
        }

        /* Custom cursor (optional premium touch) */
        .cursor-dot {
            width: 6px;
            height: 6px;
            background: #512021;
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 10000;
            transition: transform 0.15s ease;
            opacity: 0;
        }

        .cursor-dot.active {
            opacity: 0.6;
        }

        @media (max-width: 768px) {
            .cursor-dot { display: none; }
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            padding: 1.5rem 2rem;
            backdrop-filter: blur(20px);
            background: rgba(243, 233, 218, 0.85);
            z-index: 1000;
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            border-bottom: 1px solid rgba(81, 32, 33, 0.08);
        }

        .navbar.hidden {
            transform: translateY(-100%);
        }

        .navbar.scrolled {
            padding: 1rem 2rem;
            background: rgba(243, 233, 218, 0.95);
            border-bottom-color: rgba(81, 32, 33, 0.15);
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.25rem;
            font-weight: 500;
            letter-spacing: -0.02em;
            color: #512021;
            text-decoration: none;
            transition: opacity 0.3s ease;
        }

        .logo:hover {
            opacity: 0.7;
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: #2a2a2a;
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: -0.01em;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 1px;
            background: #5d6b4d;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: #512021;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            cursor: pointer;
            padding: 0.5rem;
        }

        .mobile-menu-btn span {
            display: block;
            width: 24px;
            height: 2px;
            background: #512021;
            margin: 5px 0;
            transition: 0.3s;
        }

        /* Sections */
        section {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }

        section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 6rem 1.5rem;
            position: relative;
        }

        .hero-content {
            max-width: 900px;
            margin: 0 auto;
        }

        .hero-subtitle {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            color: #5d6b4d;
            margin-bottom: 1.5rem;
            font-weight: 500;
        }

        .hero-title {
            font-size: clamp(3rem, 8vw, 5.5rem);
            font-weight: 600;
            letter-spacing: -0.03em;
            color: #512021;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            font-family: 'Cormorant Garamond', serif;
        }

        .hero-description {
            font-size: clamp(1rem, 4vw, 1.2rem);
            color: #4a4a4a;
            max-width: 600px;
            margin: 0 auto 2rem;
            line-height: 1.6;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            display: inline-block;
            padding: 0.9rem 2rem;
            border-radius: 100px;
            text-decoration: none;
            font-weight: 500;
            font-size: 0.9rem;
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            cursor: pointer;
            border: none;
            font-family: 'Inter', sans-serif;
        }

        .btn-primary {
            background: #512021;
            color: #f3e9da;
        }

        .btn-primary:hover {
            background: #3a1718;
            transform: scale(1.02);
        }

        .btn-secondary {
            background: transparent;
            color: #512021;
            border: 1px solid #512021;
        }

        .btn-secondary:hover {
            background: #512021;
            color: #f3e9da;
            transform: scale(1.02);
        }

        /* Labs Grid */
        .labs-grid {
            max-width: 1200px;
            margin: 0 auto;
            padding: 6rem 1.5rem;
        }

        .section-title {
            font-size: clamp(2rem, 5vw, 2.8rem);
            font-weight: 500;
            color: #512021;
            margin-bottom: 3rem;
            text-align: center;
            font-family: 'Cormorant Garamond', serif;
            letter-spacing: -0.02em;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 2rem;
        }

        .lab-card {
            background: white;
            border-radius: 24px;
            padding: 2rem;
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            cursor: pointer;
            border: 1px solid rgba(81, 32, 33, 0.08);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.02);
        }

        .lab-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(81, 32, 33, 0.08);
            border-color: rgba(93, 107, 77, 0.2);
        }

        .lab-number {
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            color: #5d6b4d;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .lab-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: #512021;
            margin-bottom: 1rem;
            line-height: 1.3;
        }

        .lab-description {
            color: #666;
            font-size: 0.9rem;
            line-height: 1.5;
            margin-bottom: 1.5rem;
        }

        .lab-status {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.8rem;
            font-weight: 500;
        }

        .status-complete {
            color: #5d6b4d;
        }

        .status-progress {
            color: #cd7a32;
        }

        /* Progress Section */
        .progress-section {
            background: #fff8f0;
            border-radius: 32px;
            padding: 3rem;
            margin: 4rem 0;
        }

        .progress-item {
            margin-bottom: 1.5rem;
        }

        .progress-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
        }

        .progress-bar-bg {
            background: rgba(81, 32, 33, 0.1);
            border-radius: 100px;
            height: 6px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            border-radius: 100px;
            transition: width 1s ease;
            width: 0;
        }

        .progress-fill.complete {
            background: #5d6b4d;
        }

        .progress-fill.progress {
            background: #cd7a32;
        }

        .progress-fill.pending {
            background: #512021;
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 4rem 1.5rem;
            border-top: 1px solid rgba(81, 32, 33, 0.1);
            color: #888;
            font-size: 0.8rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .navbar {
                padding: 1rem;
            }
            
            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 70%;
                height: 100vh;
                background: #f3e9da;
                flex-direction: column;
                justify-content: center;
                gap: 2rem;
                transition: right 0.4s ease;
                box-shadow: -10px 0 30px rgba(0, 0, 0, 0.05);
            }
            
            .nav-links.active {
                right: 0;
            }
            
            .mobile-menu-btn {
                display: block;
                z-index: 1001;
            }
            
            .mobile-menu-btn.active span:nth-child(1) {
                transform: rotate(45deg) translate(5px, 5px);
            }
            
            .mobile-menu-btn.active span:nth-child(2) {
                opacity: 0;
            }
            
            .mobile-menu-btn.active span:nth-child(3) {
                transform: rotate(-45deg) translate(7px, -7px);
            }
            
            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .btn {
                width: 200px;
                text-align: center;
            }
            
            .progress-section {
                padding: 1.5rem;
            }
        }

        /* Loading animation */
        .loading {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #f3e9da;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.5s ease;
        }

        .loading.hide {
            opacity: 0;
            pointer-events: none;
        }

        .loader {
            width: 40px;
            height: 40px;
            border: 2px solid rgba(81, 32, 33, 0.1);
            border-top-color: #512021;
            border-radius: 50%;
            animation: spin 0.8s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>

<div class="loading">
    <div class="loader"></div>
</div>

<!-- Custom cursor -->
<div class="cursor-dot"></div>

<!-- Navigation -->
<nav class="navbar" id="navbar">
    <div class="nav-container">
        <a href="#" class="logo">AP</a>
        <div class="nav-links" id="navLinks">
            <a href="#home">Главная</a>
            <a href="#labs">Работы</a>
            <a href="#" onclick="navigateTo('https://alexandraparamonova9.github.io/about/'); return false;">Обо мне</a>
        </div>
        <button class="mobile-menu-btn" id="mobileMenuBtn">
            <span></span>
            <span></span>
            <span></span>
        </button>
    </div>
</nav>

<main>
    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <div class="hero-subtitle">Портфолио</div>
            <h1 class="hero-title">Александра<br>Парамонова</h1>
            <p class="hero-description">студентка группы P3122 · Нейротехнологии и программирование</p>
            <div class="hero-buttons">
                <button class="btn btn-primary" onclick="navigateTo('https://alexandraparamonova9.github.io/about/')">Обо мне</button>
                <button class="btn btn-secondary" id="labsBtn">Лабораторные работы</button>
            </div>
        </div>
    </section>

    <!-- Labs Grid Section -->
    <div class="labs-grid" id="labs">
        <h2 class="section-title">Лабораторные работы</h2>
        <div class="grid" id="labsGrid"></div>

        <!-- Progress Section -->
        <div class="progress-section">
            <h3 style="font-size: 1.8rem; color: #512021; margin-bottom: 2rem; text-align: center;">Прогресс выполнения</h3>
            <div id="progressList"></div>
        </div>
    </div>
</main>

<footer class="footer">
    <p>© 2026 Александра Парамонова</p>
</footer>

<script>
    // Navigation helper
    function navigateTo(url) {
        window.location.href = url;
    }

    // Labs data
    const labs = [
        { number: 1, title: "Создание и развертывание статического сайта на базе MkDocs", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab1/" },
        { number: 2, title: "Основы NumPy: массивы и векторные операции", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab2/" },
        { number: 3, title: "CI/CD для статического сайта в SourceCraft и GitHub Actions", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab3/" },
        { number: 4, title: "Классификация с применением Scikit-Learn", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab4/" },
        { number: 5, title: "Регрессия с применением Scikit-Learn", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab5/" },
        { number: 6, title: "Лабораторная работа №6", status: "progress", percent: 40 },
        { number: 7, title: "Лабораторная работа №7", status: "progress", percent: 20 },
        { number: 8, title: "Лабораторная работа №8", status: "pending", percent: 0 }
    ];

    const labDescriptions = {
        1: "Освоение MkDocs и развертывание на GitHub Pages",
        2: "Массивы, векторные операции, статистический анализ данных",
        3: "Автоматическое развертывание на двух платформах",
        4: "Бинарная классификация, предсказание дефолта по кредиту",
        5: "Регрессионный анализ, предсказание стоимости недвижимости"
    };

    // Render labs grid
    function renderLabs() {
        const grid = document.getElementById('labsGrid');
        grid.innerHTML = labs.map(lab => `
            <div class="lab-card" onclick="${lab.url ? `navigateTo('${lab.url}')` : 'alert(\"Работа в процессе\")'}">
                <div class="lab-number">Лабораторная работа №${lab.number}</div>
                <h3 class="lab-title">${lab.title}</h3>
                <p class="lab-description">${labDescriptions[lab.number] || 'В процессе выполнения'}</p>
                <div class="lab-status ${lab.status === 'complete' ? 'status-complete' : lab.status === 'progress' ? 'status-progress' : ''}">
                    ${lab.status === 'complete' ? '✓ Выполнено' : lab.status === 'progress' ? '⟳ В процессе' : '○ Не начато'}
                </div>
            </div>
        `).join('');
    }

    // Render progress bars
    function renderProgress() {
        const container = document.getElementById('progressList');
        container.innerHTML = labs.map(lab => `
            <div class="progress-item">
                <div class="progress-header">
                    <span>Лабораторная работа №${lab.number}</span>
                    <span style="color: ${lab.percent === 100 ? '#5d6b4d' : lab.percent > 0 ? '#cd7a32' : '#512021'}">${lab.percent}%</span>
                </div>
                <div class="progress-bar-bg">
                    <div class="progress-fill ${lab.percent === 100 ? 'complete' : lab.percent > 0 ? 'progress' : 'pending'}" 
                         style="width: ${lab.percent}%"></div>
                </div>
            </div>
        `).join('');
    }

    // Intersection Observer for reveal animations
    const observerOptions = {
        threshold: 0.1,
        rootMargin: '0px 0px -50px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, observerOptions);

    // Observe all sections
    document.querySelectorAll('section, .labs-grid, .progress-section').forEach(el => {
        observer.observe(el);
    });

    // Navbar scroll behavior
    const navbar = document.getElementById('navbar');
    let lastScroll = 0;

    window.addEventListener('scroll', () => {
        const currentScroll = window.pageYOffset;
        
        if (currentScroll > 100) {
            navbar.classList.add('scrolled');
        } else {
            navbar.classList.remove('scrolled');
        }
        
        if (currentScroll > lastScroll && currentScroll > 100) {
            navbar.classList.add('hidden');
        } else {
            navbar.classList.remove('hidden');
        }
        
        lastScroll = currentScroll;
    });

    // Mobile menu
    const mobileBtn = document.getElementById('mobileMenuBtn');
    const navLinks = document.getElementById('navLinks');

    mobileBtn.addEventListener('click', () => {
        mobileBtn.classList.toggle('active');
        navLinks.classList.toggle('active');
    });

    // Close mobile menu on link click
    navLinks.querySelectorAll('a').forEach(link => {
        link.addEventListener('click', () => {
            mobileBtn.classList.remove('active');
            navLinks.classList.remove('active');
        });
    });

    // Labs button handler
    document.getElementById('labsBtn').addEventListener('click', () => {
        document.getElementById('labs').scrollIntoView({ behavior: 'smooth' });
    });

    // Custom cursor
    const cursor = document.querySelector('.cursor-dot');
    
    if (cursor) {
        document.addEventListener('mousemove', (e) => {
            cursor.style.left = e.clientX - 3 + 'px';
            cursor.style.top = e.clientY - 3 + 'px';
            cursor.classList.add('active');
        });
        
        document.addEventListener('mouseleave', () => {
            cursor.classList.remove('active');
        });
    }

    // Hide loading screen
    window.addEventListener('load', () => {
        setTimeout(() => {
            document.querySelector('.loading').classList.add('hide');
        }, 500);
    });

    // Initialize
    renderLabs();
    renderProgress();
</script>

</body>
</html>