<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Лабораторная работа №3 — CI/CD</title>
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
            max-width: 1100px;
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

        .sourcecraft-link {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            margin: 16px 0 8px;
            padding: 8px 20px;
            background: rgba(92, 30, 31, 0.08);
            border-radius: 40px;
            text-decoration: none;
            color: #5C1E1F;
            font-weight: 500;
            font-size: 0.9rem;
            transition: all 0.2s ease;
        }

        .sourcecraft-link:hover {
            background: rgba(92, 30, 31, 0.15);
            transform: translateY(-1px);
        }

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

        .code-block {
            background: #1E1E1E;
            border-radius: 18px;
            padding: 24px;
            margin: 16px 0 8px;
            overflow-x: auto;
        }

        .code-block pre {
            margin: 0;
            font-family: 'JetBrains Mono', 'Fira Code', monospace;
            font-size: 0.78rem;
            line-height: 1.55;
            color: #e2ddc9;
            white-space: pre-wrap;
            word-break: break-word;
        }

        .code-title {
            margin: 24px 0 12px 0;
            font-weight: 600;
            color: #5C1E1F;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .code-title:first-of-type {
            margin-top: 0;
        }

        .task-list {
            list-style: none;
            padding: 0;
        }

        .task-list li {
            padding: 10px 0;
            display: flex;
            align-items: flex-start;
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
            flex-shrink: 0;
        }

        .result-list {
            list-style: none;
            padding: 0;
            margin-top: 16px;
        }

        .result-list li {
            padding: 8px 0;
            display: flex;
            align-items: flex-start;
            gap: 12px;
        }

        .result-list li::before {
            content: '✓';
            color: #5C1E1F;
            font-weight: 600;
        }

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
            .code-block pre {
                font-size: 0.68rem;
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
    <a href="../index.md" class="back-link">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M19 12H5M12 19l-7-7 7-7"/>
        </svg>
        Назад к портфолио
    </a>

    <div class="lab-header animate-on-scroll">
        <div class="lab-number">Лабораторная работа №3</div>
        <h1 class="lab-title">CI/CD для статического сайта в SourceCraft и GitHub Actions</h1>
        <a href="https://sourcecraft.dev/mailparamonova/portfolio" class="sourcecraft-link" target="_blank" rel="noopener noreferrer">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/>
                <path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/>
            </svg>
            Сайт на SourceCraft
        </a>
    </div>

    <div class="card animate-on-scroll">
        <h2 class="card-title">Цель работы</h2>
        <p style="color: #2C2C2C; font-size: 1.05rem; line-height: 1.6;">
            Настроить автоматическое развертывание (CI/CD) статического сайта, созданного с помощью MkDocs, на двух платформах: GitHub Pages и SourceCraft Sites. Научиться работать с несколькими удаленными репозиториями и настраивать автоматическую сборку при каждом push.
        </p>
    </div>

    <div class="card animate-on-scroll">
        <h2 class="card-title">Задание</h2>
        <ul class="task-list">
            <li>Авторизоваться на SourceCraft через аккаунт Яндекс</li>
            <li>Создать публичную организацию и публичный репозиторий</li>
            <li>Создать персональный токен доступа (PAT) с правами Maintainer</li>
            <li>Добавить удаленный репозиторий SourceCraft в локальный проект</li>
            <li>Настроить CI/CD для автоматической сборки MkDocs сайта на SourceCraft Sites</li>
            <li>Настроить GitHub Actions для автоматической сборки и публикации на GitHub Pages</li>
            <li>Настроить два удаленных репозитория: origin (GitHub) и sourcecraft (SourceCraft)</li>
            <li>Продемонстрировать работающие сайты на обеих платформах</li>
        </ul>
    </div>

    <div class="card animate-on-scroll">
        <h2 class="card-title">Код реализации</h2>
        
        <div class="code-title">⚙️ GitHub Actions (deploy-mkdocs.yml)</div>
        <div class="code-block">
            <pre>name: Deploy MkDocs to GitHub Pages

on:
  push:
    branches: [ main ]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}

    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.x'

      - name: Install MkDocs and plugins
        run: |
          python -m pip install --upgrade pip
          pip install \
            mkdocs \
            mkdocs-material \
            pymdown-extensions \
            mkdocs-git-revision-date-localized-plugin \
            mkdocs-minify-plugin

      - name: Build MkDocs site
        working-directory: ./source
        run: mkdocs build -d ../docs --clean

      - name: Setup GitHub Pages
        uses: actions/configure-pages@v5

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: './docs'

      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4</pre>
        </div>

        <div class="code-title">🚀 SourceCraft CI (.sourcecraft/ci.yaml)</div>
        <div class="code-block">
            <pre>on:
  push:
    branches: [ main ]

workflows:
  - name: Build MkDocs site for SourceCraft
    steps:
      - uses: actions/checkout@v4

      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.x'

      - name: Install dependencies
        run: pip install mkdocs mkdocs-material pymdown-extensions

      - name: Build site
        working-directory: ./source
        run: mkdocs build -d ../docs</pre>
        </div>

        <div class="code-title">🌐 SourceCraft Sites (.sourcecraft/sites.yaml)</div>
        <div class="code-block">
            <pre>site:
  root: "docs"
  ref: "main"</pre>
        </div>

        <div class="code-title">🔧 Добавление удаленного репозитория SourceCraft</div>
        <div class="code-block">
            <pre>git remote add sourcecraft https://alexandraparamonova9:TOKEN@git.sourcecraft.dev/alexandraparamonova9/portfolio.git
git remote -v
git push sourcecraft main</pre>
        </div>

        <p style="margin-top: 16px; color: #677178; font-size: 0.9rem;">
            💡 Конфигурационные файлы обеспечивают автоматическую сборку и деплой на обеих платформах.
        </p>
    </div>

    <div class="card animate-on-scroll">
        <h2 class="card-title">Вывод</h2>
        <p style="color: #2C2C2C; font-size: 1.05rem; line-height: 1.6;">
            В ходе выполнения лабораторной работы были настроены два независимых CI/CD пайплайна для автоматического развертывания статического сайта на MkDocs.
        </p>

        <div class="code-title" style="margin-top: 20px;">✅ Результаты:</div>
        <ul class="result-list">
            <li><strong>GitHub Pages:</strong> сайт автоматически пересобирается и публикуется при каждом push в ветку main с помощью GitHub Actions</li>
            <li><strong>SourceCraft Sites:</strong> настроен автоматический деплой через конфигурационные файлы .sourcecraft/ci.yaml и .sourcecraft/sites.yaml</li>
            <li><strong>Два удаленных репозитория:</strong> локальный проект связан одновременно с GitHub (origin) и SourceCraft (sourcecraft)</li>
        </ul>

        <div class="code-title" style="margin-top: 20px;">🔧 Настройки, выполненные в репозиториях:</div>
        <ul class="result-list">
            <li><strong>GitHub:</strong> в настройках репозитория включена опция GitHub Pages с веткой gh-pages</li>
            <li><strong>SourceCraft:</strong> создана публичная организация и публичный репозиторий, сгенерирован персональный токен доступа (PAT) с правами Maintainer</li>
            <li><strong>Локально:</strong> добавлен удаленный репозиторий sourcecraft командой git remote add</li>
        </ul>

        <p style="margin-top: 20px; color: #2C2C2C; font-size: 1rem; line-height: 1.6;">
            В результате код, загруженный в любой из репозиториев, автоматически запускает сборку сайта, делая его доступным по соответствующим ссылкам. Это позволяет поддерживать сайт в актуальном состоянии без ручных операций.
        </p>
    </div>
</main>

<footer class="footer">
    <div class="container">
        Alexandra Paramonova • P3122 • Лабораторная работа №3
    </div>
</footer>

<button class="to-top" id="toTopBtn" aria-label="Наверх">
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <path d="M18 15l-6-6-6 6"/>
    </svg>
</button>

<script>
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