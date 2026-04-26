---
title: Лабораторная работа №4
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
  
  .model-list {
    list-style: none;
    padding: 0;
    margin: 0.5rem 0 0 0;
  }
  
  .model-list li {
    padding: 0.5rem 0;
    padding-left: 1.5rem;
    position: relative;
    color: #cbd5e1;
  }
  
  .model-list li::before {
    content: "🤖";
    position: absolute;
    left: 0;
  }
  
  .best-model {
    background: rgba(34, 197, 94, 0.1);
    border-left: 3px solid #22c55e;
    padding: 0.8rem 1rem;
    border-radius: 12px;
    margin: 0.5rem 0;
  }
  
  .best-model strong {
    color: #22c55e;
  }
  
  .goal-text, .conclusion-text {
    color: #cbd5e1;
    line-height: 1.6;
    font-size: 1rem;
  }
  
  .colab-link {
    display: inline-block;
    padding: 0.8rem 1.5rem;
    background: linear-gradient(135deg, rgba(0, 198, 255, 0.1), rgba(124, 58, 237, 0.1));
    border: 1px solid rgba(0, 198, 255, 0.4);
    border-radius: 16px;
    color: #00c6ff;
    text-decoration: none;
    font-weight: 600;
    transition: all 0.3s ease;
    margin-bottom: 0.5rem;
  }
  
  .colab-link:hover {
    background: rgba(0, 198, 255, 0.2);
    transform: translateY(-2px);
    box-shadow: 0 5px 20px rgba(0, 198, 255, 0.2);
  }
  
  hr {
    border: none;
    height: 1px;
    background: linear-gradient(90deg, transparent, #00c6ff, #7c3aed, #ff00cc, transparent);
    margin: 2rem 0;
  }
  
  .badge {
    display: inline-block;
    padding: 0.25rem 0.75rem;
    background: rgba(0, 198, 255, 0.15);
    border-radius: 20px;
    font-size: 0.8rem;
    color: #00c6ff;
    margin-right: 0.5rem;
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
  }
</style>

<div class="lab-container">

<!-- ЗАГОЛОВОК -->
<div class="lab-title">
  <h1>✦ Лабораторная работа №4 ✦</h1>
  <h2>Классификация с применением Scikit-Learn</h2>
</div>

<hr>

<!-- ЦЕЛЬ РАБОТЫ -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">🎯</span> Цель работы
  </h3>
  <div class="goal-text">
    Освоить применение алгоритмов машинного обучения для решения задачи классификации на примере предсказания дефолта по кредиту. Изучить предобработку данных, обучение моделей и оценку их качества с помощью библиотеки Scikit-Learn.
  </div>
</div>

<!-- ЗАДАНИЕ -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">📝</span> Задание
  </h3>
  <ul class="task-list">
    <li>Сделать копию борда преподавателя</li>
    <li>Заполнить все пропуски (TODO) в ноутбуке</li>
    <li>Провести исследовательский анализ данных</li>
    <li>Выполнить предобработку данных (заполнение пропусков, кодирование)</li>
    <li>Обучить модели классификации (Logistic Regression, Random Forest и др.)</li>
    <li>Оценить качество моделей с помощью метрик ROC-AUC, F1-score и др.</li>
  </ul>
</div>

<!-- САМОСТОЯТЕЛЬНАЯ РАБОТА -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">🔬</span> Самостоятельная работа
  </h3>
  <div class="goal-text">
    Исследованы дополнительные модели классификации:
  </div>
  <ul class="model-list">
    <li>KNeighborsClassifier</li>
    <li>Support Vector Machine (SVM)</li>
    <li>RandomForestClassifier</li>
    <li>XGBoost Classifier</li>
  </ul>
  
  <div class="best-model" style="margin-top: 1rem;">
    <strong>🏆 Лучшая модель:</strong> XGBoost с наивысшим значением ROC-AUC.
  </div>
  
  <div class="goal-text" style="margin-top: 1rem;">
    Также изучены современные подходы к классификации (градиентный бустинг) и описан способ интеграции обученной модели в веб-сервис на FastAPI.
  </div>
</div>

<!-- ССЫЛКА НА НОУТБУК -->
<div class="content-card" style="text-align: center;">
  <h3 class="section-title" style="justify-content: center;">
    <span class="section-icon">🔗</span> Ссылка на выполненный ноутбук
  </h3>
  
  <a href="https://colab.research.google.com/drive/1OPMfk9i1ROD3h0M0zcsWm4u4hEmMiS0z#scrollTo=CFPdG8_dK7gC" target="_blank" class="colab-link">
    📓 → Открыть Google Colab (Лабораторная работа №4)
  </a>
</div>

<!-- ВЫВОД -->
<div class="content-card">
  <h3 class="section-title">
    <span class="section-icon">📌</span> Вывод
  </h3>
  <div class="conclusion-text">
    В ходе выполнения лабораторной работы была решена задача бинарной классификации с помощью библиотеки Scikit-Learn. Проведена полная предобработка данных, обучено несколько моделей, выбрана лучшая. Получены практические навыки работы с алгоритмами машинного обучения и оценки их качества.
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