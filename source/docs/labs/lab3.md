---
title: Лабораторная работа №3
hide:
  - navigation
  - toc
---

<style>
  .lab-container {
    max-width: 1000px;
    margin: 0 auto;
  }
  
  .lab-title {
    text-align: center;
    margin-bottom: 2rem;
  }
  
  .lab-title h1 {
    font-size: clamp(2rem, 5vw, 2.8rem);
    font-weight: 700;
    background: linear-gradient(135deg, #00c6ff, #7c3aed, #ff00cc);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    margin-bottom: 0.5rem;
  }
  
  .lab-title h2 {
    font-size: clamp(1.2rem, 4vw, 1.5rem);
    color: #94a3b8;
    font-weight: 400;
  }
  
  .section-icon {
    font-size: 1.8rem;
    margin-right: 0.5rem;
  }
  
  .section-title {
    font-size: 1.5rem;
    font-weight: 600;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    background: linear-gradient(135deg, #ffffff, #00c6ff);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }
  
  .section-title-sub {
    font-size: 1.3rem;
    font-weight: 600;
    margin: 1rem 0 0.5rem 0;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    color: #00c6ff;
  }
  
  .content-card {
    background: rgba(20, 20, 35, 0.6);
    backdrop-filter: blur(12px);
    border: 1px solid rgba(0, 198, 255, 0.2);
    border-radius: 24px;
    padding: 1.8rem;
    margin: 1.5rem 0;
    transition: all 0.3s ease;
  }
  
  .content-card:hover {
    border-color: rgba(0, 198, 255, 0.5);
    transform: translateY(-3px);
    box-shadow: 0 15px 40px rgba(0, 198, 255, 0.1);
  }
  
  .task-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  .task-list li {
    padding: 0.6rem 0;
    padding-left: 1.5rem;
    position: relative;
    color: #cbd5e1;
    border-bottom: 1px solid rgba(0, 198, 255, 0.1);
  }
  
  .task-list li:last-child {
    border-bottom: none;
  }
  
  .task-list li::before {
    content: "✦";
    position: absolute;
    left: 0;
    color: #00c6ff;
  }
  
  .result-list {
    list-style: none;
    padding: 0;
    margin: 0.5rem 0 1rem 0;
  }
  
  .result-list li {
    padding: 0.5rem 0;
    padding-left: 1.5rem;
    position: relative;
    color: #cbd5e1;
  }
  
  .result-list li::before {
    content: "✅";
    position: absolute;
    left: 0;
    color: #22c55e;
  }
  
  .settings-list {
    list-style: none;
    padding: 0;
    margin: 0.5rem 0 0 0;
  }
  
  .settings-list li {
    padding: 0.5rem 0;
    padding-left: 1.5rem;
    position: relative;
    color: #cbd5e1;
  }
  
  .settings-list li::before {
    content: "🔧";
    position: absolute;
    left: 0;
  }
  
  pre {
    background: #0a0a0f !important;
    border: 1px solid rgba(0, 198, 255, 0.3) !important;
    border-radius: 16px !important;
    padding: 1.2rem !important;
    overflow-x: auto;
    font-family: 'Fira Code', 'Courier New', monospace;
    font-size: 0.85rem;
    color: #00c6ff;
  }
  
  code {
    background: rgba(0, 198, 255, 0.1);
    color: #00c6ff;
    padding: 0.2rem 0.4rem;
    border-radius: 8px;
    font-size: 0.9em;
  }
  
  .goal-text, .conclusion-text {
    color: #cbd5e1;
    line-height: 1.6;
    font-size: 1rem;
  }
  
  .source-link {
    display: inline-block;
    padding: 0.5rem 1rem;
    background: rgba(0, 198, 255, 0.1);
    border: 1px solid rgba(0, 198, 255, 0.3);
    border-radius: 12px;
    color: #00c6ff;
    text-decoration: none;
    transition: all 0.3s ease;
    margin-bottom: 1rem;
  }
  
  .source-link:hover {
    background: rgba(0, 198, 255, 0.2);
    transform: translateY(-2px);
  }
  
  hr {
    border: none;
    height: 1px;
    background: linear-gradient(90deg, transparent, #00c6ff, #7c3aed, #ff00cc, transparent);
    margin: 2rem 0;
  }
  
  @media (max-width: 768px) {
    .content-card {
      padding: 1.2rem;
    }
    .section-title {
      font-size: 1.3rem;
    }
    .section-title-sub {
      font-size: 1.1rem;
    }
    pre {
      font-size: 0.7rem;
      padding: 1rem !important;
    }
  }
</style>

<div class="lab-container">

<!-- ЗАГОЛОВОК -->
<div class="lab-title">
  <h1>✦ Лабораторная работа №3 ✦</h1>
  <h2>CI/CD для статического сайта в SourceCraft и GitHub Actions</h2>
</div>

<!-- ССЫЛКА НА РЕЗУЛЬТАТ -->
<div align="center">
  <a href="https://sourcecraft.dev/mailparamonova/portfolio" target="_blank" class="source-link">
    🔗 sourcecraft.dev/mailparamonova/portfolio
  </a>
</div>

<hr>

<!-- ЦЕЛЬ РАБОТЫ -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">🎯</span> Цель работы
  </h3>
  <div class="goal-text">
    Настроить автоматическое развертывание (CI/CD) статического сайта, созданного с помощью MkDocs, на двух платформах: GitHub Pages и SourceCraft Sites. Научиться работать с несколькими удаленными репозиториями и настраивать автоматическую сборку при каждом push.
  </div>
</div>

<!-- ЗАДАНИЕ -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">📝</span> Задание
  </h3>
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

<!-- КОД РЕАЛИЗАЦИИ -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">💻</span> Код реализации
  </h3>
  
  <h4 class="section-title-sub">
    <span>⚙️</span> GitHub Actions (deploy-mkdocs.yml)
  </h4>
  <pre style="margin: 0 0 1.5rem 0; font-family: monospace;">
name: Deploy MkDocs to GitHub Pages

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

  <h4 class="section-title-sub">
    <span>🚀</span> SourceCraft CI (.sourcecraft/ci.yaml)
  </h4>
  <pre style="margin: 0 0 1.5rem 0; font-family: monospace;">
on:
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

  <h4 class="section-title-sub">
    <span>🌐</span> SourceCraft Sites (.sourcecraft/sites.yaml)
  </h4>
  <pre style="margin: 0 0 1.5rem 0; font-family: monospace;">
site:
  root: "docs"
  ref: "main"</pre>

  <h4 class="section-title-sub">
    <span>🔧</span> Добавление удаленного репозитория SourceCraft
  </h4>
  <pre style="margin: 0; font-family: monospace;">
git remote add sourcecraft https://alexandraparamonova9:TOKEN@git.sourcecraft.dev/alexandraparamonova9/portfolio.git
git remote -v
git push sourcecraft main</pre>
</div>

<!-- ВЫВОД -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">📌</span> Вывод
  </h3>
  <div class="conclusion-text">
    В ходе выполнения лабораторной работы были настроены два независимых CI/CD пайплайна для автоматического развертывания статического сайта на MkDocs.
  </div>
  
  <h4 class="section-title-sub" style="margin-top: 1rem;">
    <span>✅</span> Результаты
  </h4>
  <ul class="result-list">
    <li><strong>GitHub Pages:</strong> сайт автоматически пересобирается и публикуется при каждом push в ветку main с помощью GitHub Actions</li>
    <li><strong>SourceCraft Sites:</strong> настроен автоматический деплой через конфигурационные файлы .sourcecraft/ci.yaml и .sourcecraft/sites.yaml</li>
    <li><strong>Два удаленных репозитория:</strong> локальный проект связан одновременно с GitHub (origin) и SourceCraft (sourcecraft)</li>
  </ul>
  
  <h4 class="section-title-sub" style="margin-top: 1rem;">
    <span>🔧</span> Настройки, выполненные в репозиториях
  </h4>
  <ul class="settings-list">
    <li><strong>GitHub:</strong> в настройках репозитория включена опция GitHub Pages с веткой gh-pages</li>
    <li><strong>SourceCraft:</strong> создана публичная организация и публичный репозиторий, сгенерирован персональный токен доступа (PAT) с правами Maintainer</li>
    <li><strong>Локально:</strong> добавлен удаленный репозиторий sourcecraft командой git remote add</li>
  </ul>
  
  <div class="conclusion-text" style="margin-top: 1rem;">
    В результате код, загруженный в любой из репозиториев, автоматически запускает сборку сайта, делая его доступным по соответствующим ссылкам. Это позволяет поддерживать сайт в актуальном состоянии без ручных операций.
  </div>
</div>

<hr>

<!-- ДЕКОРАТИВНАЯ ПОДПИСЬ -->
<div align="center" style="margin-top: 2rem;">
  <p style="color: #475569; font-size: 0.85rem;">
    ✦ ИТМО • Нейротехнологии и программирование • 2026 ✦
  </p>
</div>

</div>