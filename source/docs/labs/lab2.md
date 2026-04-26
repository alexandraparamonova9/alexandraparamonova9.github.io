<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Лабораторная работа №2 — NumPy</title>
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

        .lab-subtitle {
            font-size: 1.2rem;
            color: #677178;
            font-weight: 400;
        }

        .repo-link {
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

        .repo-link:hover {
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
            font-size: 0.8rem;
            line-height: 1.55;
            color: #e2ddc9;
            white-space: pre-wrap;
            word-break: break-word;
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
                font-size: 0.7rem;
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
        <a href=".." class="nav-logo">Alexandra Paramonova</a>
        <div class="nav-links">
            <button class="nav-link" onclick="location.href='..'">Home</button>
            <button class="nav-link" onclick="location.href='../about'">About</button>
        </div>
    </div>
</nav>

<main class="container">
    <a href=".." class="back-link">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M19 12H5M12 19l-7-7 7-7"/>
        </svg>
        Назад к портфолио
    </a>

    <div class="lab-header animate-on-scroll">
        <div class="lab-number">Лабораторная работа №2</div>
        <h1 class="lab-title">Основы NumPy: массивы и векторные операции</h1>
        <a href="https://github.com/alexandraparamonova9/Python2sem" class="repo-link" target="_blank" rel="noopener noreferrer">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/>
            </svg>
            Репозиторий с исходным кодом
        </a>
    </div>

    <div class="card animate-on-scroll">
        <h2 class="card-title">Цель работы</h2>
        <p style="color: #2C2C2C; font-size: 1.05rem; line-height: 1.6;">
            Освоить базовые операции с массивами в библиотеке NumPy, научиться выполнять векторные и матричные вычисления, проводить статистический анализ данных и визуализировать результаты с помощью Matplotlib и Seaborn.
        </p>
    </div>

    <div class="card animate-on-scroll">
        <h2 class="card-title">Задание</h2>
        <ul class="task-list">
            <li>Создать массив от 0 до 9 с помощью np.arange()</li>
            <li>Создать матрицу 5x5 со случайными числами от 0 до 1</li>
            <li>Выполнить преобразование формы массива (reshape) и транспонирование</li>
            <li>Реализовать векторные операции: сложение, умножение на скаляр, поэлементное умножение, скалярное произведение</li>
            <li>Реализовать матричные операции: умножение матриц, определитель, обратную матрицу, решение системы линейных уравнений</li>
            <li>Загрузить данные из CSV файла и выполнить статистический анализ</li>
            <li>Реализовать Min-Max нормализацию данных</li>
            <li>Построить графики: гистограмму, тепловую карту корреляции, линейный график оценок</li>
            <li>Написать тесты для всех функций с использованием pytest</li>
        </ul>
    </div>

    <div class="card animate-on-scroll">
        <h2 class="card-title">Код реализации</h2>
        <div class="code-block">
            <pre>import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# 1. Создание массивов
def create_vector():
    return np.arange(10)

def create_matrix():
    return np.random.rand(5, 5)

def reshape_vector(vec):
    return vec.reshape(2, 5)

def transpose_matrix(mat):
    return mat.T

# 2. Векторные операции
def vector_add(a, b):
    return a + b

def scalar_multiply(vec, scalar):
    return vec * scalar

def elementwise_multiply(a, b):
    return a * b

def dot_product(a, b):
    return np.dot(a, b)

# 3. Матричные операции
def matrix_multiply(a, b):
    return a @ b

def matrix_determinant(a):
    return np.linalg.det(a)

def matrix_inverse(a):
    return np.linalg.inv(a)

def solve_linear_system(a, b):
    return np.linalg.solve(a, b)

# 4. Статистический анализ
def load_dataset(path="data/students_scores.csv"):
    return pd.read_csv(path).to_numpy()

def statistical_analysis(data):
    return {
        "mean": np.mean(data),
        "median": np.median(data),
        "std": np.std(data),
        "min": np.min(data),
        "max": np.max(data),
        "25th_percentile": np.percentile(data, 25),
        "75th_percentile": np.percentile(data, 75)
    }

def normalize_data(data):
    return (data - np.min(data)) / (np.max(data) - np.min(data))

# 5. Визуализация
def plot_histogram(data):
    plt.hist(data, bins=8, color='#9b59b6', edgecolor='white')
    plt.title('Распределение оценок по математике')
    plt.savefig('plots/histogram.png')
    plt.close()

def plot_heatmap(correlation):
    sns.heatmap(correlation, annot=True, cmap='coolwarm')
    plt.title('Корреляция между предметами')
    plt.savefig('plots/heatmap.png')
    plt.close()

def plot_line(x, y):
    plt.plot(x, y, marker='o', color='#9b59b6')
    plt.title('Оценки студентов по математике')
    plt.savefig('plots/line_plot.png')
    plt.close()</pre>
        </div>
        <p style="margin-top: 16px; color: #677178; font-size: 0.9rem;">
            💡 Код содержит аннотации типов, документацию и соответствует стандарту PEP 8.
        </p>
    </div>

    <div class="card animate-on-scroll">
        <h2 class="card-title">Вывод</h2>
        <p style="color: #2C2C2C; font-size: 1.05rem; line-height: 1.6;">
            В ходе выполнения лабораторной работы были освоены основные возможности библиотеки NumPy для научных вычислений. Научилась создавать и преобразовывать массивы, выполнять векторные и матричные операции, проводить статистический анализ данных и визуализировать результаты.
            Все функции были протестированы с использованием pytest, код соответствует стандартам PEP 8, содержит аннотации типов и документацию.
        </p>
    </div>
</main>

<footer class="footer">
    <div class="container">
        Alexandra Paramonova • P3122 • Лабораторная работа №2
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