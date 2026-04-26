---
title: Лабораторная работа №2 — Основы NumPy
---

<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>Лабораторная работа №2</title>
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
.code-block{background:#1c1410;color:#d4c4b0;padding:2.2rem;border-radius:24px;font-family:'DM Mono',monospace;overflow-x:auto;line-height:1.65;margin:2rem 0;}
.back-btn{position:fixed;bottom:40px;left:50%;transform:translateX(-50%);background:var(--b);color:white;padding:14px 34px;border-radius:50px;text-decoration:none;font-weight:500;z-index:100;box-shadow:0 10px 30px rgba(81,32,33,0.3);}
</style>
</head>
<body>

<nav>
  <a href="../index.html" class="logo">← Главная</a>
</nav>

<section class="full-section">
  <div style="max-width:1100px">
    <h1>Лабораторная работа №2</h1>
    <h2>Основы NumPy: массивы и векторные операции</h2>
    <p style="font-size:1.1rem;color:#666;margin-bottom:2rem;">Репозиторий с исходным кодом — <a href="https://github.com/alexandraparamonova9/Python2sem" target="_blank">github.com/alexandraparamonova9/Python2sem</a></p>
    
    <h3>🎯 Цель работы</h3>
    <div class="content-box">
      Освоить базовые операции с массивами в библиотеке NumPy, научиться выполнять векторные и матричные вычисления, проводить статистический анализ данных и визуализировать результаты с помощью Matplotlib и Seaborn.
    </div>
  </div>
</section>

<section class="full-section" style="background:#f9f4eb">
  <div style="max-width:1100px">
    <h3>📝 Задание</h3>
    <div class="content-box">
      1. Создать массив от 0 до 9 с помощью np.arange()<br>
      2. Создать матрицу 5x5 со случайными числами от 0 до 1<br>
      3. Выполнить преобразование формы массива (reshape) и транспонирование<br>
      4. Реализовать векторные операции: сложение, умножение на скаляр, поэлементное умножение, скалярное произведение<br>
      5. Реализовать матричные операции: умножение матриц, определитель, обратную матрицу, решение системы линейных уравнений<br>
      6. Загрузить данные из CSV файла и выполнить статистический анализ<br>
      7. Реализовать Min-Max нормализацию данных<br>
      8. Построить графики: гистограмму, тепловую карту корреляции, линейный график оценок<br>
      9. Написать тесты для всех функций с использованием pytest
    </div>
  </div>
</section>

<section class="full-section">
  <div style="max-width:1100px">
    <h3>💻 Код реализации</h3>
    <div class="code-block">
      <pre><code>import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# 1. Создание массивов
def create_vector(): return np.arange(10)
def create_matrix(): return np.random.rand(5, 5)
def reshape_vector(vec): return vec.reshape(2, 5)
def transpose_matrix(mat): return mat.T

# 2. Векторные операции
def vector_add(a, b): return a + b
def scalar_multiply(vec, scalar): return vec * scalar
def elementwise_multiply(a, b): return a * b
def dot_product(a, b): return np.dot(a, b)

# 3. Матричные операции
def matrix_multiply(a, b): return a @ b
def matrix_determinant(a): return np.linalg.det(a)
def matrix_inverse(a): return np.linalg.inv(a)
def solve_linear_system(a, b): return np.linalg.solve(a, b)

# 4. Статистический анализ и визуализация
def load_dataset(path="data/students_scores.csv"): return pd.read_csv(path).to_numpy()
def statistical_analysis(data): ... 
def normalize_data(data): return (data - np.min(data)) / (np.max(data) - np.min(data))
def plot_histogram(data): ...</code></pre>
    </div>
  </div>
</section>

<section class="full-section" style="background:#f0e9df">
  <div style="max-width:960px">
    <h3>📌 Вывод</h3>
    <div class="content-box">
      В ходе выполнения лабораторной работы были освоены основные возможности библиотеки NumPy для научных вычислений. Научилась создавать и преобразовывать массивы, выполнять векторные и матричные операции, проводить статистический анализ данных и визуализировать результаты.<br><br>
      Все функции были протестированы с использованием pytest, код соответствует стандартам PEP 8, содержит аннотации типов и документацию.
    </div>
  </div>
</section>

<a href="../index.html" class="back-btn">← На главную</a>

</body>
</html>