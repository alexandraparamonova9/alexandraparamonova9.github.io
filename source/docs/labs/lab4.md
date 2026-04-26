---
title: Лабораторная работа №4 — Классификация с применением Scikit-Learn
---

<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>Лабораторная работа №4</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400;1,500&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{--b:#512021;--c:#f3e9da;--o:#5d6b4d;--b2:#3a1617;--ease:cubic-bezier(0.23,1,0.32,1);}
body{background:var(--c);font-family:'DM Sans',system-ui,sans-serif;color:#1c1410;margin:0;padding:0;}
nav{position:fixed;top:0;left:0;right:0;padding:1.3rem 3rem;background:rgba(243,233,218,0.95);backdrop-filter:blur(20px);z-index:1000;display:flex;justify-content:space-between;align-items:center;}
.logo{font-family:'Playfair Display',serif;font-size:1.4rem;color:var(--b);text-decoration:none;}
.full-section{min-height:100vh;padding:170px 8% 100px;display:flex;align-items:center;}
h1{font-family:'Playfair Display',serif;font-size:clamp(2.8rem,7vw,5rem);color:var(--b);line-height:1.1;margin-bottom:1rem;}
h2{font-family:'Playfair Display',serif;font-size:2.3rem;color:var(--b);margin:2.5rem 0 1.5rem;}
h3{font-size:1.55rem;color:var(--o);margin:2.2rem 0 1.2rem;}
.content-box{background:white;padding:2.4rem 2.8rem;border-radius:28px;box-shadow:0 10px 40px rgba(81,32,33,0.08);margin:2rem 0;border:1px solid rgba(81,32,33,0.08);}
.back-btn{position:fixed;bottom:40px;left:50%;transform:translateX(-50%);background:var(--b);color:white;padding:14px 34px;border-radius:50px;text-decoration:none;font-weight:500;z-index:100;box-shadow:0 10px 30px rgba(81,32,33,0.3);}
</style>
</head>
<body>

<nav>
  <a href="../index.html" class="logo">← Главная</a>
</nav>

<section class="full-section">
  <div style="max-width:960px">
    <h1>Лабораторная работа №4</h1>
    <h2>Классификация с применением Scikit-Learn</h2>
    
    <h3>🎯 Цель работы</h3>
    <div class="content-box">
      Освоить применение алгоритмов машинного обучения для решения задачи классификации на примере предсказания дефолта по кредиту. Изучить предобработку данных, обучение моделей и оценку их качества с помощью библиотеки Scikit-Learn.
    </div>
  </div>
</section>

<section class="full-section" style="background:#f9f4eb">
  <div style="max-width:960px">
    <h3>📝 Задание</h3>
    <div class="content-box">
      1. Сделать копию борда преподавателя<br>
      2. Заполнить все пропуски (TODO) в ноутбуке<br>
      3. Провести исследовательский анализ данных<br>
      4. Выполнить предобработку данных (заполнение пропусков, кодирование)<br>
      5. Обучить модели классификации (Logistic Regression, Random Forest и др.)<br>
      6. Оценить качество моделей с помощью метрик ROC-AUC, F1-score и др.
    </div>
  </div>
</section>

<section class="full-section">
  <div style="max-width:960px">
    <h3>💻 Самостоятельная работа</h3>
    <div class="content-box">
      Исследованы дополнительные модели классификации:<br>
      • KNeighborsClassifier<br>
      • Support Vector Machine (SVM)<br>
      • RandomForestClassifier<br>
      • XGBoost Classifier<br><br>
      <strong>Лучшая модель:</strong> XGBoost с наивысшим значением ROC-AUC.<br>
      Также изучены современные подходы к классификации (градиентный бустинг) и описан способ интеграции обученной модели в веб-сервис на FastAPI.
    </div>
  </div>
</section>

<section class="full-section" style="background:#f0e9df">
  <div style="max-width:960px">
    <h3>🔗 Ссылка на выполненный ноутбук</h3>
    <div class="content-box">
      <a href="https://colab.research.google.com/drive/1OPMfk9i1ROD3h0M0zcsWm4u4hEmMiS0z#scrollTo=CFPdG8_dK7gC" target="_blank" style="color:#7b1fa2;font-weight:bold;font-size:1.1rem;">
        → Открыть Google Colab (Лабораторная работа №4)
      </a>
    </div>
  </div>
</section>

<section class="full-section">
  <div style="max-width:960px">
    <h3>📌 Вывод</h3>
    <div class="content-box">
      В ходе выполнения лабораторной работы была решена задача бинарной классификации с помощью библиотеки Scikit-Learn. Проведена полная предобработка данных, обучено несколько моделей, выбрана лучшая. Получены практические навыки работы с алгоритмами машинного обучения и оценки их качества.
    </div>
  </div>
</section>

<a href="../index.html" class="back-btn">← На главную</a>

</body>
</html>