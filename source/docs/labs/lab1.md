<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Лабораторная работа №1 — MkDocs | Александра Парамонова</title>
    
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
            line-height: 1.6;
        }

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

        .logo:hover { opacity: 0.7; }

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

        .nav-links a:hover::after { width: 100%; }
        .nav-links a:hover { color: #512021; }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            cursor: pointer;
        }

        .mobile-menu-btn span {
            display: block;
            width: 24px;
            height: 2px;
            background: #512021;
            margin: 5px 0;
            transition: 0.3s;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 8rem 1.5rem 4rem;
        }

        .lab-header {
            margin-bottom: 4rem;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .lab-header.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .lab-number {
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            color: #5d6b4d;
            margin-bottom: 1rem;
        }

        .lab-header h1 {
            font-size: clamp(2.5rem, 6vw, 4rem);
            color: #512021;
            font-family: 'Cormorant Garamond', serif;
            font-weight: 500;
            margin-bottom: 1rem;
            line-height: 1.2;
        }

        .lab-header h2 {
            font-size: 1.4rem;
            font-weight: 400;
            color: #666;
            line-height: 1.4;
        }

        .section {
            background: white;
            border-radius: 32px;
            padding: 2.5rem;
            margin-bottom: 2rem;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
            border: 1px solid rgba(81, 32, 33, 0.05);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.02);
        }

        .section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .section h3 {
            font-size: 1.5rem;
            color: #512021;
            margin-bottom: 1.5rem;
            font-family: 'Cormorant Garamond', serif;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .section p, .section ul, .section ol {
            color: #444;
            line-height: 1.7;
        }

        .section ul, .section ol {
            margin-left: 1.5rem;
            margin-top: 1rem;
        }

        .section li {
            margin-bottom: 0.5rem;
        }

        pre {
            background: #1a1a1a;
            color: #e2e2e2;
            padding: 1.5rem;
            border-radius: 20px;
            overflow-x: auto;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
            line-height: 1.5;
            margin: 1.5rem 0;
        }

        code {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
            background: rgba(81, 32, 33, 0.08);
            padding: 0.2rem 0.4rem;
            border-radius: 8px;
        }

        .footer {
            text-align: center;
            padding: 3rem 1.5rem;
            border-top: 1px solid rgba(81, 32, 33, 0.1);
            color: #888;
            font-size: 0.8rem;
        }

        @media (max-width: 768px) {
            .navbar { padding: 1rem; }
            
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
            
            .nav-links.active { right: 0; }
            .mobile-menu-btn { display: block; }
            
            .mobile-menu-btn.active span:nth-child(1) {
                transform: rotate(45deg) translate(5px, 5px);
            }
            .mobile-menu-btn.active span:nth-child(2) { opacity: 0; }
            .mobile-menu-btn.active span:nth-child(3) {
                transform: rotate(-45deg) translate(7px, -7px);
            }
            
            .container { padding-top: 6rem; }
            .section { padding: 1.5rem; }
        }

        .back-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            color: #5d6b4d;
            text-decoration: none;
            margin-bottom: 2rem;
            transition: gap 0.3s ease;
        }

        .back-link:hover {
            gap: 0.75rem;
            color: #512021;
        }
    </style>
</head>
<body>

<nav class="navbar" id="navbar">
    <div class="nav-container">
        <a href="https://alexandraparamonova9.github.io/" class="logo">AP</a>
        <div class="nav-links" id="navLinks">
            <a href="https://alexandraparamonova9.github.io/">Главная</a>
            <a href="https://alexandraparamonova9.github.io/#labs">Работы</a>
            <a href="https://alexandraparamonova9.github.io/about/">Обо мне</a>
        </div>
        <button class="mobile-menu-btn" id="mobileMenuBtn">
            <span></span>
            <span></span>
            <span></span>
        </button>
    </div>
</nav>

<div class="container">
    <a href="https://alexandraparamonova9.github.io/#labs" class="back-link">← Назад к работам</a>

    <div class="lab-header" id="header">
        <div class="lab-number">Лабораторная работа №1</div>
        <h1>Создание и развертывание<br>статического сайта</h1>
        <h2>на базе MkDocs</h2>
    </div>

    <div class="section" id="goal">
        <h3>🎯 Цель работы</h3>
        <p>Освоить процесс создания статического сайта с использованием генератора документации MkDocs, научиться организовывать структуру документации проекта и развернуть сайт с использованием GitHub Pages.</p>
    </div>

    <div class="section" id="task">
        <h3>📝 Задание</h3>
        <ul>
            <li>Создать публичный репозиторий на GitHub</li>
            <li>Настроить GitHub Pages для публикации из каталога <code>/docs</code></li>
            <li>Установить и настроить MkDocs</li>
            <li>Создать структуру сайта с несколькими страницами</li>
            <li>Настроить тему оформления</li>
            <li>Опубликовать сайт на GitHub Pages</li>
        </ul>
    </div>

    <div class="section" id="code">
        <h3>💻 Код реализации</h3>
        <pre>mkdocs new source
cd source
mkdocs serve
mkdocs build -d ../docs</pre>
    </div>

    <div class="section" id="conclusion">
        <h3>📌 Вывод</h3>
        <p>В ходе работы был создан статический сайт с помощью MkDocs и опубликован в интернете через GitHub Pages. Были изучены основы работы с Git и структура документации проекта.</p>
    </div>
</div>

<footer class="footer">
    <p>© 2026 Александра Парамонова</p>
</footer>

<script>
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

    const mobileBtn = document.getElementById('mobileMenuBtn');
    const navLinks = document.getElementById('navLinks');

    mobileBtn?.addEventListener('click', () => {
        mobileBtn.classList.toggle('active');
        navLinks.classList.toggle('active');
    });

    navLinks?.querySelectorAll('a').forEach(link => {
        link.addEventListener('click', () => {
            mobileBtn?.classList.remove('active');
            navLinks.classList.remove('active');
        });
    });

    const observerOptions = { threshold: 0.1, rootMargin: '0px 0px -50px 0px' };
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, observerOptions);

    document.querySelectorAll('.lab-header, .section').forEach(el => observer.observe(el));
</script>

</body>
</html>