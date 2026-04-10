<h1>Лабораторная работа №3</h1>
<h2>CI/CD для статического сайта в SourceCraft и GitHub Actions</h2>

---

Репозиторий с исходным кодом - https://github.com/alexandraparamonova9/alexandraparamonova9.github.io

<h3>🎯 Цель работы</h3>

<div style="background: #f8f0fa; padding: 25px; border-radius: 15px; margin: 20px 0; border: 1px solid #e1bee7; box-shadow: 0 4px 10px rgba(123, 31, 162, 0.1);">

Настроить автоматическое развертывание (CI/CD) статического сайта, созданного с помощью MkDocs, на двух платформах: GitHub Pages и SourceCraft Sites. Научиться работать с несколькими удаленными репозиториями и настраивать автоматическую сборку при каждом push.

</div>

---

<h3>📝 Задание</h3>

<div style="background: white; padding: 25px; border-radius: 15px; margin: 20px 0; border: 1px solid #e1bee7; box-shadow: 0 4px 10px rgba(123, 31, 162, 0.1);">

1. Авторизоваться на SourceCraft через аккаунт Яндекс<br>
2. Создать публичную организацию и публичный репозиторий<br>
3. Создать персональный токен доступа (PAT) с правами Maintainer<br>
4. Добавить удаленный репозиторий SourceCraft в локальный проект<br>
5. Настроить CI/CD для автоматической сборки MkDocs сайта на SourceCraft Sites<br>
6. Настроить GitHub Actions для автоматической сборки и публикации на GitHub Pages<br>
7. Настроить два удаленных репозитория: origin (GitHub) и sourcecraft (SourceCraft)<br>
8. Продемонстрировать работающие сайты на обеих платформах

</div>

---

<h3>💻 Код реализации</h3>

<div style="background: #f8f0fa; padding: 25px; border-radius: 15px; margin: 20px 0; border: 1px solid #e1bee7; box-shadow: 0 4px 10px rgba(123, 31, 162, 0.1);">

<h4>📁 Структура репозитория</h4>

<pre style="margin: 0; font-family: monospace; background: #2d2d2d; color: #f8f8f2; padding: 15px; border-radius: 10px; overflow-x: auto;">
alexandraparamonova9.github.io/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions
├── .sourcecraft/
│   ├── ci.yaml                 # SourceCraft CI конфигурация
│   └── sites.yaml              # SourceCraft Sites конфигурация
├── docs/                       # Исходные .md файлы
├── mkdocs.yml                  # Конфигурация MkDocs
└── requirements.txt            # Зависимости Python
</pre>

<h4>⚙️ GitHub Actions (deploy.yml)</h4>

<pre style="margin: 0; font-family: monospace; background: #2d2d2d; color: #f8f8f2; padding: 15px; border-radius: 10px; overflow-x: auto;">
name: Deploy MkDocs to GitHub Pages

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.10'
          
      - name: Install dependencies
        run: |
          pip install mkdocs mkdocs-material
        
      - name: Build site
        run: mkdocs build --clean
        
      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./site
          publish_branch: gh-pages
</pre>

<h4>🚀 SourceCraft CI (.sourcecraft/ci.yaml)</h4>

<pre style="margin: 0; font-family: monospace; background: #2d2d2d; color: #f8f8f2; padding: 15px; border-radius: 10px; overflow-x: auto;">
version: 1
jobs:
  - name: build-site
    steps:
      - name: install-python
        uses: script
        script: |
          apt-get update && apt-get install -y python3 python3-pip
      - name: install-mkdocs
        uses: script
        script: |
          pip3 install mkdocs mkdocs-material
      - name: build-docs
        uses: script
        script: |
          mkdocs build --clean -d site
      - name: publish
        uses: site-publish
        with:
          source: site
          target: /
</pre>

<h4>🌐 SourceCraft Sites (.sourcecraft/sites.yaml)</h4>

<pre style="margin: 0; font-family: monospace; background: #2d2d2d; color: #f8f8f2; padding: 15px; border-radius: 10px; overflow-x: auto;">
site:
  root: site
  ref: release
</pre>

<h4>🔧 Добавление удаленного репозитория SourceCraft</h4>

<pre style="margin: 0; font-family: monospace; background: #2d2d2d; color: #f8f8f2; padding: 15px; border-radius: 10px; overflow-x: auto;">
git remote add sourcecraft https://alexandraparamonova9:TOKEN@git.sourcecraft.dev/alexandraparamonova9/portfolio.git
git remote -v
git push sourcecraft main
</pre>

</div>

---

<h3>📌 Вывод</h3>

<div style="background: #f8f0fa; padding: 25px; border-radius: 15px; margin: 20px 0; border: 1px solid #e1bee7; box-shadow: 0 4px 10px rgba(123, 31, 162, 0.1);">

В ходе выполнения лабораторной работы были настроены два независимых CI/CD пайплайна для автоматического развертывания статического сайта на MkDocs.

<h4>✅ Результаты:</h4>

<ul style="margin-top: 10px;">
    <li><strong>GitHub Pages:</strong> сайт автоматически пересобирается и публикуется при каждом push в ветку main с помощью GitHub Actions</li>
    <li><strong>SourceCraft Sites:</strong> настроен автоматический деплой через конфигурационные файлы .sourcecraft/ci.yaml и .sourcecraft/sites.yaml</li>
    <li><strong>Два удаленных репозитория:</strong> локальный проект связан одновременно с GitHub (origin) и SourceCraft (sourcecraft)</li>
</ul>

<h4>🔧 Настройки, выполненные в репозиториях:</h4>

<ul style="margin-top: 10px;">
    <li><strong>GitHub:</strong> в настройках репозитория включена опция GitHub Pages с веткой gh-pages</li>
    <li><strong>SourceCraft:</strong> создана публичная организация и публичный репозиторий, сгенерирован персональный токен доступа (PAT) с правами Maintainer</li>
    <li><strong>Локально:</strong> добавлен удаленный репозиторий sourcecraft командой git remote add</li>
</ul>

<p style="margin-top: 15px;">В результате код, загруженный в любой из репозиториев, автоматически запускает сборку сайта, делая его доступным по соответствующим ссылкам. Это позволяет поддерживать сайт в актуальном состоянии без ручных операций.</p>

</div>