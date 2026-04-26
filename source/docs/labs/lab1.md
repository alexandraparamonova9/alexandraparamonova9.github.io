<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Лабораторная работа №1 — MkDocs</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #EFEAD4;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'SF Pro Text', sans-serif;
            color: #1E1E1E;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #e2ddc9;
        }
        ::-webkit-scrollbar-thumb {
            background: #677178;
            border-radius: 8px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #5C1E1F;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 32px;
        }

        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .animate-on-scroll {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s cubic-bezier(0.2, 0.9, 0.4, 1.1), transform 0.6s cubic-bezier(0.2, 0.9, 0.4, 1.1);
        }

        .animate-on-scroll.animated {
            opacity: 1;
            transform: translateY(0);
        }

        /* Navbar */
        .navbar {
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(12px);
            background: rgba(239, 234, 212, 0.75);
            border-bottom: 1px solid rgba(103, 113, 120, 0.15);
            padding: 20px 0;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 32px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 40px;
            flex-wrap: wrap;
        }

        .nav-logo {
            font-weight: 600;
            font-size: 1.25rem;
            letter-spacing: -0.01em;
            color: #5C1E1F;
            text-decoration: none;
            transition: opacity 0.2s;
        }

        .nav-logo:hover {
            opacity: 0.75;
        }

        .nav-links {
            display: flex;
            gap: 32px;
            align-items: center;
        }

        .nav-link {
            background: none;
            border: none;
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
            font-weight: 500;
            color: #1E1E1E;
            cursor: pointer;
            padding: 8px 0;
            transition: color 0.2s;
            position: relative;
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: #5C1E1F;
            transition: width 0.3s ease;
        }

        .nav-link:hover {
            color: #5C1E1F;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        /* Back button */
        .back-link {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            margin: 32px 0 24px;
            color: #677178;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s;
        }

        .back-link:hover {
            color: #5C1E1F;
        }

        /* Header */
        .lab-header {
            margin: 40px 0 32px;
            border-bottom: 1px solid rgba(103, 113, 120, 0.2);
            padding-bottom: 24px;
        }

        .lab-number {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #5C1E1F;
            font-weight: 600;
            margin-bottom: 12px;
        }

        .lab-title {
            font-size: clamp(2rem, 5vw, 2.8rem);
            font-weight: 600;
            letter-spacing: -0.02em;
            color: #1E1E1E;
            margin-bottom: 12px;
        }

        .lab-subtitle {
            font-size: 1.2rem;
            color: #677178;
            font-weight: 400;
        }

        /* Cards */
        .card {
            background: rgba(239, 234, 212, 0.6);
            backdrop-filter: blur(4px);
            border-radius: 24px;
            padding: 32px;
            margin: 28px 0;
            border: 1px solid rgba(103, 113, 120, 0.2);
            box-shadow: 0 8px 20px -8px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08);
        }

        .card-title {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            color: #1E1E1E;
        }

        .card-title::before {
            content: '✦';
            color: #5C1E1F;
            font-size: 1.6rem;
        }

        /* Code block */
        .code-block {
            background: #1E1E1E;
            border-radius: 18px;
            padding: 20px;
            margin: 16px 0 8px;
            overflow-x: auto;
        }

        .code-block pre {
            margin: 0;
            font-family: 'JetBrains Mono', 'Fira Code', monospace;
            font-size: 0.85rem;
            line-height: 1.6;
            color: #e2ddc9;
        }

        .task-list {
            list-style: none;
            padding: 0;
        }

        .task-list li {
            padding: 10px 0;
            display: flex;
            align-items: center;
            gap: 12px;
            border-bottom: 1px solid rgba(103, 113, 120, 0.1);
        }

        .task-list li:last-child {
            border-bottom: none;
        }

        .task-list li::before {
            content: '▹';
            color: #5C1E1F;
            font-size: 1rem;
        }

        /* Footer */
        .footer {
            margin-top: 80px;
            padding: 32px 0;
            border-top: 1px solid rgba(103, 113, 120, 0.2);
            text-align: center;
            color: #677178;
            font-size: 0.85rem;
        }

        .to-top {
            position: fixed;
            bottom: 32px;
            right: 32px;
            width: 48px;
            height: 48px;
            border-radius: 50%;
            background: #5C1E1F;
            color: #EFEAD4;
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            opacity: 0;
            visibility: hidden;
            box-shadow: 0 4px 12px rgba(92, 30, 31, 0.3);
        }

        .to-top.visible {
            opacity: 1;
            visibility: visible;
        }

        .to-top:hover {
            transform: translateY(-4px);
            background: #3f1415;
        }

        @media (max-width: 768px) {
            .container {
                padding: 0 20px;
            }
            .card {
                padding: 24px;
            }
            .nav-container {
                flex-direction: column;
                gap: 12px;
            }
            .to-top {
                bottom: 20px;
                right: 20px;
                width: 42px;
                height: 42px;
            }
        }
    </style>
</head>
<body>

<nav class="navbar">
    <div class="nav-container">
        <a href="../index.md" class="nav-logo">Alexandra Paramonova</a>
        <div class="nav-links">
            <button class="nav-link" onclick="window.location.href='../index.md'">Home</button>
            <button class="nav-link" onclick="window.location.href='../about.md'">About</button>
        </div>
    </div>
</nav>

<main class="container">
    <!-- Back button -->
    <a href="../index.md" class="back-link">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M19 12H5M12 19l-7-7 7-7"/>
        </svg>
        Назад к портфолио
    </a>

    <!-- Header -->
    <div class="lab-header animate-on-scroll">
        <div class="lab-number">Лабораторная работа №1</div>
        <h1 class="lab-title">Создание и развертывание статического сайта на базе MkDocs</h1>
    </div>

    <!-- Цель работы -->
    <div class="card animate-on-scroll">
        <h2 class="card-title">Цель работы</h2>
        <p style="color: #2C2C2C; font-size: 1.05rem; line-height: 1.6;">
            Освоить процесс создания статического сайта с использованием генератора документации MkDocs, научиться организовывать структуру документации проекта и развернуть сайт с использованием GitHub Pages.
        </p>
    </div>

    <!-- Задание -->
    <div class="card animate-on-scroll">
        <h2 class="card-title">Задание</h2>
        <ul class="task-list">
            <li>Создать публичный репозиторий на GitHub</li>
            <li>Настроить GitHub Pages для публикации из каталога <code style="background: rgba(103,113,120,0.15); padding: 2px 8px; border-radius: 8px;">/docs</code></li>
            <li>Установить и настроить MkDocs</li>
            <li>Создать структуру сайта с несколькими страницами</li>
            <li>Настроить тему оформления</li>
            <li>Опубликовать сайт на GitHub Pages</li>
        </ul>
    </div>

    <!-- Код реализации -->
    <div class="card animate-on-scroll">
        <h2 class="card-title">Код реализации</h2>
        <div class="code-block">
            <pre>mkdocs new source
cd source
mkdocs serve
mkdocs build -d ../docs</pre>
        </div>
        <p style="margin-top: 16px; color: #677178; font-size: 0.9rem;">
            💡 Команды для создания нового проекта MkDocs, локального запуска и сборки статического сайта.
        </p>
    </div>

    <!-- Вывод -->
    <div class="card animate-on-scroll">
        <h2 class="card-title">Вывод</h2>
        <p style="color: #2C2C2C; font-size: 1.05rem; line-height: 1.6;">
            В ходе работы был создан статический сайт с помощью MkDocs и опубликован в интернете через GitHub Pages. Были изучены основы работы с Git и структура документации проекта.
        </p>
    </div>
</main>

<footer class="footer">
    <div class="container">
        Alexandra Paramonova • P3122 • Лабораторная работа №1
    </div>
</footer>

<button class="to-top" id="toTopBtn" aria-label="Наверх">
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M18 15l-6-6-6 6"/>
    </svg>
</button>

<script>
    // Анимация при скролле
    const animatedElements = document.querySelectorAll('.animate-on-scroll');
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('animated');
                observer.unobserve(entry.target);
            }
        });
    }, { threshold: 0.1, rootMargin: "0px 0px -30px 0px" });
    animatedElements.forEach(el => observer.observe(el));

    // Кнопка наверх
    const toTopBtn = document.getElementById('toTopBtn');
    window.addEventListener('scroll', () => {
        if (window.scrollY > 300) {
            toTopBtn.classList.add('visible');
        } else {
            toTopBtn.classList.remove('visible');
        }
    });
    toTopBtn.addEventListener('click', () => {
        window.scrollTo({ top: 0, behavior: 'smooth' });
    });
</script>

</body>
</html>