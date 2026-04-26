---
title: Лабораторная работа №1
hide:
  - navigation
  - toc
---

<style>
  .lab-container {
    max-width: 900px;
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
  
  pre {
    background: #0a0a0f !important;
    border: 1px solid rgba(0, 198, 255, 0.3) !important;
    border-radius: 16px !important;
    padding: 1.2rem !important;
    overflow-x: auto;
    font-family: 'Fira Code', 'Courier New', monospace;
    font-size: 0.9rem;
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
    pre {
      font-size: 0.75rem;
      padding: 1rem !important;
    }
  }
</style>

<div class="lab-container">

<!-- ЗАГОЛОВОК -->
<div class="lab-title">
  <h1>✦ Лабораторная работа №1 ✦</h1>
  <h2>Создание и развертывание статического сайта на базе MkDocs</h2>
</div>

<hr>

<!-- ЦЕЛЬ РАБОТЫ -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">🎯</span> Цель работы
  </h3>
  <div class="goal-text">
    Освоить процесс создания статического сайта с использованием генератора документации MkDocs, научиться организовывать структуру документации проекта и развернуть сайт с использованием GitHub Pages.
  </div>
</div>

<!-- ЗАДАНИЕ -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">📝</span> Задание
  </h3>
  <ul class="task-list">
    <li>Создать публичный репозиторий на GitHub</li>
    <li>Настроить GitHub Pages для публикации из каталога <code>/docs</code></li>
    <li>Установить и настроить MkDocs</li>
    <li>Создать структуру сайта с несколькими страницами</li>
    <li>Настроить тему оформления</li>
    <li>Опубликовать сайт на GitHub Pages</li>
  </ul>
</div>

<!-- КОД РЕАЛИЗАЦИИ -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">💻</span> Код реализации
  </h3>
  <pre style="margin: 0; font-family: monospace;">
mkdocs new source
cd source
mkdocs serve
mkdocs build -d ../docs</pre>
</div>

<!-- ВЫВОД -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">📌</span> Вывод
  </h3>
  <div class="conclusion-text">
    В ходе работы был создан статический сайт с помощью MkDocs и опубликован в интернете через GitHub Pages. Были изучены основы работы с Git и структура документации проекта.
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