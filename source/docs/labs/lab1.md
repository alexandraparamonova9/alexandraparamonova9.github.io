---
title: Лабораторная работа №1 — Создание и развертывание статического сайта
---

<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>Лабораторная работа №1</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400;1,500&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{
  --b:#512021;
  --c:#f3e9da;
  --o:#5d6b4d;
  --b2:#3a1617;
  --ease:cubic-bezier(0.23,1,0.32,1);
}
body{background:var(--c); font-family:'DM Sans',system-ui,sans-serif; color:#1c1410; margin:0; padding:0;}
nav{position:fixed; top:0; left:0; right:0; padding:1.3rem 3rem; background:rgba(243,233,218,0.95); backdrop-filter:blur(20px); z-index:1000; display:flex; justify-content:space-between; align-items:center;}
.logo{font-family:'Playfair Display',serif; font-size:1.4rem; color:var(--b); text-decoration:none;}
.full-section{min-height:100vh; padding:170px 8% 100px; display:flex; align-items:center;}
h1{font-family:'Playfair Display',serif; font-size:clamp(2.8rem,7vw,5rem); color:var(--b); line-height:1.1; margin-bottom:1rem;}
h2{font-family:'Playfair Display',serif; font-size:2.4rem; color:var(--b); margin:2.5rem 0 1.5rem;}
h3{font-size:1.55rem; color:var(--o); margin:2rem 0 1rem;}
.content-box{background:white; padding:2.2rem 2.8rem; border-radius:28px; box-shadow:0 10px 40px rgba(81,32,33,0.08); margin:1.8rem 0; border:1px solid rgba(81,32,33,0.08);}
.code-block{background:#1c1410; color:#d4c4b0; padding:2rem; border-radius:24px; font-family:'DM Mono',monospace; overflow-x:auto; line-height:1.65; margin:2rem 0;}
.back-btn{position:fixed; bottom:40px; left:50%; transform:translateX(-50%); background:var(--b); color:white; padding:14px 34px; border-radius:50px; text-decoration:none; font-weight:500; z-index:100; box-shadow:0 10px 30px rgba(81,32,33,0.3);}
</style>
</head>
<body>

<nav>
  <a href="../index.html" class="logo">← Главная</a>
</nav>

<section class="full-section">
  <div style="max-width:960px">
    <h1>Лабораторная работа №1</h1>
    <h2>Создание и развертывание статического сайта на базе MkDocs</h2>
    
    <h3>🎯 Цель работы</h3>
    <div class="content-box">
      Освоить процесс создания статического сайта с использованием генератора документации MkDocs, научиться организовывать структуру документации проекта и развернуть сайт с использованием GitHub Pages.
    </div>
  </div>
</section>

<section class="full-section" style="background:#f9f4eb">
  <div style="max-width:960px">
    <h3>📝 Задание</h3>
    <div class="content-box">
      1. Создать публичный репозиторий на GitHub<br>
      2. Настроить GitHub Pages для публикации из каталога <code>/docs</code><br>
      3. Установить и настроить MkDocs<br>
      4. Создать структуру сайта с несколькими страницами<br>
      5. Настроить тему оформления<br>
      6. Опубликовать сайт на GitHub Pages
    </div>
  </div>
</section>

<section class="full-section">
  <div style="max-width:960px">
    <h3>💻 Код реализации</h3>
    <div class="code-block">
      <pre>mkdocs new source
cd source
mkdocs serve
mkdocs build -d ../docs</pre>
    </div>
  </div>
</section>

<section class="full-section" style="background:#f0e9df">
  <div style="max-width:960px">
    <h3>📌 Вывод</h3>
    <div class="content-box">
      В ходе работы был создан статический сайт с помощью MkDocs и опубликован в интернете через GitHub Pages. Были изучены основы работы с Git и структура документации проекта.
    </div>
  </div>
</section>

<a href="../index.html" class="back-btn">← На главную</a>

</body>
</html>