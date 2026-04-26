<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Александра Парамонова — Портфолио</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
    <style>
        /* ---------- RESET & BASE ---------- */
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

        /* Кастомный скроллбар — премиум */
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

        /* Контейнер */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 32px;
        }

        /* Анимации появления */
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

        /* Glassmorphic Navbar */
        .navbar {
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(12px);
            background: rgba(239, 234, 212, 0.75);
            border-bottom: 1px solid rgba(103, 113, 120, 0.15);
            padding: 20px 0;
            transition: all 0.3s ease;
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
            flex-wrap: wrap;
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

        /* Hero секция */
        .hero {
            padding: 80px 0 60px;
            text-align: center;
            animation: fadeUp 0.8s ease-out forwards;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 6vw, 4rem);
            font-weight: 600;
            letter-spacing: -0.02em;
            color: #1E1E1E;
            margin-bottom: 16px;
        }

        .hero h1 span {
            color: #5C1E1F;
            font-weight: 700;
        }

        .hero-sub {
            font-size: 1.2rem;
            color: #677178;
            font-weight: 400;
            letter-spacing: 0.01em;
        }

        /* Карточка welcome */
        .glass-card {
            background: rgba(239, 234, 212, 0.7);
            backdrop-filter: blur(4px);
            border-radius: 28px;
            padding: 48px;
            margin: 40px 0;
            border: 1px solid rgba(103, 113, 120, 0.2);
            box-shadow: 0 15px 35px -12px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .glass-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 25px 40px -16px rgba(0, 0, 0, 0.08);
        }

        .welcome-text {
            font-size: 1.2rem;
            line-height: 1.6;
            color: #2C2C2C;
            text-align: center;
        }

        /* Кнопки */
        .btn-group {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin: 48px 0 32px;
        }

        .btn {
            display: inline-block;
            padding: 12px 32px;
            border-radius: 40px;
            font-weight: 500;
            font-size: 1rem;
            text-decoration: none;
            transition: all 0.25s ease;
            cursor: pointer;
            border: 1px solid transparent;
            background: none;
            font-family: 'Inter', sans-serif;
        }

        .btn-primary {
            background: #5C1E1F;
            color: #EFEAD4;
            border-color: #5C1E1F;
        }

        .btn-primary:hover {
            background: #3f1415;
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(92, 30, 31, 0.2);
        }

        .btn-secondary {
            background: transparent;
            border-color: #677178;
            color: #1E1E1E;
        }

        .btn-secondary:hover {
            background: rgba(103, 113, 120, 0.08);
            border-color: #5C1E1F;
            color: #5C1E1F;
            transform: translateY(-2px);
        }

        /* Прогресс бар */
        .progress-section {
            margin: 60px 0;
        }

        .section-title {
            font-size: clamp(1.8rem, 5vw, 2.2rem);
            font-weight: 600;
            letter-spacing: -0.01em;
            margin: 0 0 40px 0;
            text-align: center;
            color: #1E1E1E;
        }

        .progress-container {
            background: rgba(239, 234, 212, 0.5);
            border-radius: 28px;
            padding: 2rem;
            border: 1px solid rgba(103, 113, 120, 0.15);
        }

        .progress-item {
            margin-bottom: 1.8rem;
        }

        .progress-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .progress-label {
            font-weight: 500;
            font-size: 1rem;
        }

        .progress-label a {
            color: #1E1E1E;
            text-decoration: none;
            transition: color 0.2s;
        }

        .progress-label a:hover {
            color: #5C1E1F;
        }

        .progress-percent {
            font-weight: 600;
        }

        .progress-bar-bg {
            background: rgba(103, 113, 120, 0.2);
            border-radius: 100px;
            height: 6px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            border-radius: 100px;
            width: 0%;
            transition: width 0.8s cubic-bezier(0.2, 0.9, 0.4, 1.1);
        }

        /* Цвета процентов */
        .progress-fill.completed {
            background: linear-gradient(90deg, #5C1E1F, #8a3b3c);
        }
        .progress-fill.in-progress {
            background: linear-gradient(90deg, #677178, #8d979c);
        }
        .progress-fill.not-started {
            background: #c9c4b0;
        }

        /* Лаборатории сетка */
        .labs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 28px;
            margin-top: 30px;
        }

        .lab-card {
            background: #EFEAD4;
            border-radius: 24px;
            padding: 24px;
            border: 1px solid rgba(103, 113, 120, 0.2);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.02);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .lab-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 20px 30px -12px rgba(0, 0, 0, 0.1);
            border-color: rgba(92, 30, 31, 0.3);
        }

        .lab-number {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #5C1E1F;
            font-weight: 600;
            margin-bottom: 12px;
        }

        .lab-title {
            font-size: 1.35rem;
            font-weight: 600;
            margin-bottom: 12px;
            color: #1E1E1E;
        }

        .lab-status {
            display: inline-block;
            font-size: 0.75rem;
            padding: 4px 10px;
            border-radius: 30px;
            background: rgba(103, 113, 120, 0.1);
            color: #677178;
            margin-top: 12px;
        }

        /* футер */
        .footer {
            margin-top: 80px;
            padding: 32px 0;
            border-top: 1px solid rgba(103, 113, 120, 0.2);
            text-align: center;
            color: #677178;
            font-size: 0.85rem;
        }

        /* Адаптив */
        @media (max-width: 768px) {
            .container {
                padding: 0 20px;
            }
            .glass-card {
                padding: 28px;
            }
            .btn-group {
                gap: 12px;
            }
            .btn {
                padding: 10px 24px;
            }
            .nav-container {
                flex-direction: column;
                gap: 12px;
            }
            .nav-links {
                gap: 20px;
            }
        }
    </style>
</head>
<body>

<nav class="navbar">
    <div class="nav-container">
        <a href="index.md" class="nav-logo">Alexandra Paramonova</a>
        <div class="nav-links">
            <button class="nav-link" data-nav="about">About</button>
            <button class="nav-link labs-menu-btn" data-nav="labs">Labs</button>
        </div>
    </div>
</nav>

<main class="container">
    <!-- Hero -->
    <div class="hero animate-on-scroll">
        <h1>✦ <span>Александра Парамонова</span> ✦</h1>
        <div class="hero-sub">студентка группы P3122</div>
    </div>

    <!-- Welcome Card -->
    <div class="glass-card animate-on-scroll">
        <div class="welcome-text">
            ✦ Добро пожаловать в моё портфолио ✦<br>
            Здесь собраны лабораторные работы, выполненные в рамках нашего курса.
        </div>
    </div>

    <!-- Кнопки навигации -->
    <div class="btn-group animate-on-scroll">
        <button class="btn btn-primary" id="aboutBtn">Об авторе →</button>
        <button class="btn btn-secondary" id="labsMenuBtn">Лабораторные работы ↓</button>
    </div>

    <!-- Прогресс выполнения -->
    <div class="progress-section animate-on-scroll" id="progressSection">
        <h2 class="section-title">📊 Прогресс выполнения</h2>
        <div class="progress-container" id="progressContainer">
            <!-- Прогресс-бары будут добавлены js, но сохраняем ваш контент -->
        </div>
    </div>

    <!-- Сетка лабораторий (появится при клике) -->
    <div id="labsGridContainer" style="margin: 40px 0;"></div>

</main>

<footer class="footer">
    <div class="container">
        Alexandra Paramonova • P3122 • портфолио
    </div>
</footer>

<script>
    (function() {
        // Данные из вашего описания
        const labsData = [
            { name: "Лабораторная работа №1", status: "✅ Выполнено", percent: 100, date: "март 2026", link: "lab1.md" },
            { name: "Лабораторная работа №2", status: "✅ Выполнено", percent: 100, date: "март 2026", link: "lab2.md" },
            { name: "Лабораторная работа №3", status: "✅ Выполнено", percent: 100, date: "апрель 2026", link: "lab3.md" },
            { name: "Лабораторная работа №4", status: "✅ Выполнено", percent: 100, date: "апрель 2026", link: "lab4.md" },
            { name: "Лабораторная работа №5", status: "✅ Выполнено", percent: 100, date: "апрель 2026", link: "lab5.md" },
            { name: "Лабораторная работа №6", status: "🕐 В процессе", percent: 40, date: "апрель 2026", link: null },
            { name: "Лабораторная работа №7", status: "🕐 В процессе", percent: 20, date: "апрель 2026", link: null },
            { name: "Лабораторная работа №8", status: "🕐 В процессе", percent: 0, date: "апрель 2026", link: null }
        ];

        function getPercentColor(percent) {
            if (percent === 100) return "completed";
            if (percent > 0) return "in-progress";
            return "not-started";
        }

        function renderProgress() {
            const container = document.getElementById('progressContainer');
            if (!container) return;
            let html = '';
            labsData.forEach(lab => {
                let fillClass = getPercentColor(lab.percent);
                let percentColor = lab.percent === 100 ? "#5C1E1F" : (lab.percent > 0 ? "#677178" : "#aaa");
                let linkHtml = lab.link ? `<a href="${lab.link}" style="color: #1E1E1E; text-decoration: none;">${lab.name}</a>` : `<span style="color: #677178;">${lab.name}</span>`;
                html += `
                    <div class="progress-item">
                        <div class="progress-header">
                            <span class="progress-label">${linkHtml}</span>
                            <span class="progress-percent" style="color: ${percentColor};">${lab.percent}%</span>
                        </div>
                        <div class="progress-bar-bg">
                            <div class="progress-fill ${fillClass}" style="width: ${lab.percent}%;"></div>
                        </div>
                    </div>
                `;
            });
            container.innerHTML = html;
        }

        function renderLabsGrid() {
            const gridContainer = document.getElementById('labsGridContainer');
            if (!gridContainer) return;
            let gridHtml = `<div class="labs-grid">`;
            labsData.forEach((lab, idx) => {
                if (lab.link) {
                    gridHtml += `
                        <div class="lab-card" data-link="${lab.link}">
                            <div class="lab-number">WORK ${idx+1}</div>
                            <div class="lab-title">${lab.name}</div>
                            <div class="lab-status">${lab.status} • ${lab.date}</div>
                        </div>
                    `;
                } else {
                    gridHtml += `
                        <div class="lab-card" style="opacity:0.7;">
                            <div class="lab-number">WORK ${idx+1}</div>
                            <div class="lab-title">${lab.name}</div>
                            <div class="lab-status">${lab.status} • ${lab.date}</div>
                        </div>
                    `;
                }
            });
            gridHtml += `</div>`;
            gridContainer.innerHTML = gridHtml;

            // Клик по карточке с ссылкой
            document.querySelectorAll('.lab-card[data-link]').forEach(card => {
                card.addEventListener('click', (e) => {
                    const link = card.getAttribute('data-link');
                    if (link) window.location.href = link;
                });
            });
        }

        // Навигация
        document.getElementById('aboutBtn')?.addEventListener('click', () => {
            window.location.href = 'about.md';
        });

        document.getElementById('labsMenuBtn')?.addEventListener('click', () => {
            const grid = document.getElementById('labsGridContainer');
            if (grid) {
                if (grid.style.display === 'none' || !grid.innerHTML) {
                    renderLabsGrid();
                    grid.style.display = 'block';
                } else {
                    grid.style.display = grid.style.display === 'none' ? 'block' : 'none';
                }
                if (grid.innerHTML === '') renderLabsGrid();
                grid.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        });

        // Навбар кнопки
        document.querySelector('[data-nav="about"]')?.addEventListener('click', () => {
            window.location.href = 'about.md';
        });
        document.querySelector('[data-nav="labs"]')?.addEventListener('click', () => {
            renderLabsGrid();
            const gridDiv = document.getElementById('labsGridContainer');
            if (gridDiv) {
                gridDiv.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        });

        // Анимация при скролле
        const animatedElements = document.querySelectorAll('.animate-on-scroll');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animated');
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.1, rootMargin: "0px 0px -40px 0px" });

        animatedElements.forEach(el => observer.observe(el));

        // Рендер прогресса сразу
        renderProgress();

        // Скрыть сетку лаб сначала
        const gridDiv = document.getElementById('labsGridContainer');
        if (gridDiv) gridDiv.style.display = 'none';
    })();
</script>

</body>
</html>