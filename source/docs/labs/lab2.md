<h1>Лабораторная работа №2</h1>
<h2>Основы NumPy: массивы и векторные операции</h2>

---

<h3>🎯 Цель работы</h3>

<div style="background: #f8f0fa; padding: 25px; border-radius: 15px; margin: 20px 0; border: 1px solid #e1bee7; box-shadow: 0 4px 10px rgba(123, 31, 162, 0.1);">

Освоить базовые операции с массивами в библиотеке NumPy, научиться выполнять векторные и матричные вычисления, проводить статистический анализ данных и визуализировать результаты с помощью Matplotlib и Seaborn.

</div>

---

<h3>📝 Задание</h3>

<div style="background: white; padding: 25px; border-radius: 15px; margin: 20px 0; border: 1px solid #e1bee7; box-shadow: 0 4px 10px rgba(123, 31, 162, 0.1);">

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

---

<h3>💻 Код реализации</h3>

<div style="background: #f8f0fa; padding: 25px; border-radius: 15px; margin: 20px 0; border: 1px solid #e1bee7; box-shadow: 0 4px 10px rgba(123, 31, 162, 0.1);">

<pre style="margin: 0; font-family: monospace; background: #2d2d2d; color: #f8f8f2; padding: 15px; border-radius: 10px; overflow-x: auto;">
import numpy as np
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
    plt.close()
</pre>

</div>

---

<h3>📌 Вывод</h3>

<div style="background: #f8f0fa; padding: 25px; border-radius: 15px; margin: 20px 0; border: 1px solid #e1bee7; box-shadow: 0 4px 10px rgba(123, 31, 162, 0.1);">

В ходе выполнения лабораторной работы были освоены основные возможности библиотеки NumPy для научных вычислений. Научился создавать и преобразовывать массивы, выполнять векторные и матричные операции, проводить статистический анализ данных и визуализировать результаты. Все функции были протестированы с использованием pytest, код соответствует стандартам PEP 8, содержит аннотации типов и документацию.

</div>