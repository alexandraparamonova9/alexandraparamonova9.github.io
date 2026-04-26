---
title: Александра Парамонова — P3122
---

<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>Александра Парамонова — P3122</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400;1,500&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ── BASE & RESET ─────────────────────────────── */
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --b:#512021;
  --c:#f3e9da;
  --o:#5d6b4d;
  --b2:#3a1617;
  --dark:#1c1410;
  --ease:cubic-bezier(0.23,1,0.32,1);
}
html{scroll-behavior:smooth}
body{
  background:var(--c);
  font-family:'DM Sans',system-ui,sans-serif;
  color:var(--dark);
  overflow-x:hidden;
  -webkit-font-smoothing:antialiased;
}

/* ── NAVBAR ───────────────────────────────────── */
nav{
  position:fixed;
  top:0; left:0; right:0;
  z-index:1000;
  padding:1.4rem 3rem;
  display:flex;
  justify-content:space-between;
  align-items:center;
  transition:all 0.5s var(--ease);
  backdrop-filter:blur(20px);
}
nav.scrolled{
  padding:1rem 3rem;
  background:rgba(243,233,218,0.95);
  border-bottom:1px solid rgba(81,32,33,0.1);
}
.logo{
  font-family:'Playfair Display',serif;
  font-size:1.45rem;
  color:var(--b);
  text-decoration:none;
  letter-spacing:-0.02em;
}
.nav-links{
  display:flex;
  gap:2.8rem;
}
.nav-links a{
  text-decoration:none;
  color:rgba(28,20,16,0.75);
  font-size:0.93rem;
  font-weight:500;
  transition:color 0.3s;
}
.nav-links a:hover{color:var(--b)}

/* ── HERO ─────────────────────────────────────── */
.hero{
  min-height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
  text-align:center;
  padding:0 2rem;
}
.hero-content{
  max-width:820px;
}
.hero-eyebrow{
  font-size:0.82rem;
  letter-spacing:0.25em;
  text-transform:uppercase;
  color:var(--o);
  margin-bottom:1.8rem;
  font-weight:500;
}
.hero-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(3.8rem,9vw,7rem);
  line-height:1.05;
  color:var(--b);
  margin-bottom:1.6rem;
}
.hero-title em{
  font-style:italic;
  color:var(--o);
}
.hero-desc{
  font-size:1.22rem;
  color:rgba(28,20,16,0.6);
  max-width:560px;
  margin:0 auto 3rem;
  line-height:1.55;
}

/* ── BUTTONS ──────────────────────────────────── */
.btn{
  display:inline-block;
  padding:1rem 2.4rem;
  border-radius:50px;
  font-weight:500;
  text-decoration:none;
  transition:all 0.4s var(--ease);
  font-size:0.95rem;
}
.btn-primary{
  background:var(--b);
  color:var(--c);
}
.btn-primary:hover{
  background:var(--b2);
  transform:scale(1.04);
}
.btn-secondary{
  background:transparent;
  color:var(--b);
  border:2px solid var(--b);
}
.btn-secondary:hover{
  background:var(--b);
  color:var(--c);
}

/* ── LABS SECTION ─────────────────────────────── */
#labs{
  padding:8rem 3rem 6rem;
  max-width:1280px;
  margin:0 auto;
}
.section-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.6rem,6vw,4.2rem);
  color:var(--b);
  text-align:center;
  margin-bottom:4rem;
}

/* Labs Grid */
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fill, minmax(340px, 1fr));
  gap:2rem;
}
.lab-card{
  background:white;
  border-radius:28px;
  padding:2.4rem;
  border:1px solid rgba(81,32,33,0.08);
  transition:all 0.5s var(--ease);
  cursor:pointer;
}
.lab-card:hover{
  transform:translateY(-12px);
  box-shadow:0 25px 50px rgba(81,32,33,0.12);
  border-color:rgba(93,107,77,0.25);
}
.lab-number{
  font-size:0.78rem;
  letter-spacing:0.12em;
  text-transform:uppercase;
  color:var(--o);
  margin-bottom:1.2rem;
  font-weight:600;
}
.lab-title{
  font-family:'Playfair Display',serif;
  font-size:1.55rem;
  line-height:1.25;
  color:var(--b);
  margin-bottom:1rem;
}
.lab-description{
  color:rgba(28,20,16,0.65);
  font-size:0.97rem;
  line-height:1.6;
  margin-bottom:1.8rem;
}
.lab-status{
  font-size:0.85rem;
  font-weight:500;
}

/* Progress */
.progress-section{
  background:rgba(81,32,33,0.04);
  border-radius:28px;
  padding:3.5rem 3rem;
  margin-top:5rem;
}
.progress-item{
  margin-bottom:1.6rem;
}
.progress-header{
  display:flex;
  justify-content:space-between;
  margin-bottom:0.6rem;
  font-size:0.92rem;
}
.progress-bar-bg{
  height:5px;
  background:rgba(81,32,33,0.12);
  border-radius:10px;
  overflow:hidden;
}
.progress-fill{
  height:100%;
  border-radius:10px;
  transition:width 1.2s cubic-bezier(0.34,1.56,0.64,1);
}

/* Footer */
footer{
  text-align:center;
  padding:4rem 2rem 3rem;
  color:rgba(28,20,16,0.45);
  font-size:0.85rem;
}

/* Responsive */
@media(max-width:768px){
  nav{padding:1.1rem 1.8rem;}
  .nav-links{gap:1.8rem;}
  .hero{padding:0 1.5rem;}
}
</style>
</head>
<body>

<nav id="navbar">
  <a href="#" class="logo">АП</a>
  <div class="nav-links">
    <a href="#home">Главная</a>
    <a href="#labs">Работы</a>
    <a href="https://alexandraparamonova9.github.io/about/">Обо мне</a>
  </div>
</nav>

<!-- HERO -->
<section id="home" class="hero">
  <div class="hero-content">
    <p class="hero-eyebrow">Портфолио • ИТМО • P3122</p>
    <h1 class="hero-title">Александра<br><em>Парамонова</em></h1>
    <p class="hero-desc">Студентка направления «Нейротехнологии и программирование»</p>
    
    <div style="display:flex; gap:1.2rem; justify-content:center; flex-wrap:wrap;">
      <a href="https://alexandraparamonova9.github.io/about/" class="btn btn-secondary">Обо мне</a>
      <a href="#labs" class="btn btn-primary">Лабораторные работы ↓</a>
    </div>
  </div>
</section>

<!-- LABS -->
<section id="labs">
  <h2 class="section-title">Лабораторные работы</h2>
  
  <div class="grid" id="labsGrid"></div>

  <!-- Progress -->
  <div class="progress-section">
    <h3 style="text-align:center; font-family:'Playfair Display',serif; font-size:2.1rem; color:var(--b); margin-bottom:2.5rem;">Прогресс выполнения</h3>
    <div id="progressList"></div>
  </div>
</section>

<footer>
  <p>© 2026 Александра Парамонова · ИТМО P3122</p>
</footer>

<script>
const labs = [
  { number: 1, title: "Создание и развертывание статического сайта на базе MkDocs", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab1/" },
  { number: 2, title: "Основы NumPy: массивы и векторные операции", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab2/" },
  { number: 3, title: "CI/CD для статического сайта в SourceCraft и GitHub Actions", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab3/" },
  { number: 4, title: "Классификация с применением Scikit-Learn", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab4/" },
  { number: 5, title: "Регрессия с применением Scikit-Learn", status: "complete", percent: 100, url: "https://alexandraparamonova9.github.io/labs/lab5/" },
  { number: 6, title: "Лабораторная работа №6", status: "progress", percent: 40 },
  { number: 7, title: "Лабораторная работа №7", status: "progress", percent: 20 },
  { number: 8, title: "Лабораторная работа №8", status: "pending", percent: 0 }
];

const labDescriptions = {
  1: "Освоение MkDocs и развертывание на GitHub Pages",
  2: "Массивы, векторные операции, статистический анализ данных",
  3: "Автоматическое развертывание на двух платформах",
  4: "Бинарная классификация, предсказание дефолта по кредиту",
  5: "Регрессионный анализ, предсказание стоимости недвижимости"
};

function renderLabs() {
  const grid = document.getElementById('labsGrid');
  grid.innerHTML = labs.map(lab => `
    <div class="lab-card" onclick="${lab.url ? `window.location='${lab.url}'` : "alert('Работа в процессе')"}">
      <div class="lab-number">Лабораторная работа №${lab.number}</div>
      <h3 class="lab-title">${lab.title}</h3>
      <p class="lab-description">${labDescriptions[lab.number] || 'В процессе выполнения'}</p>
      <div class="lab-status" style="color:${lab.status==='complete'?'#5d6b4d':'#cd7a32'}">
        ${lab.status==='complete' ? '✓ Выполнено' : lab.status==='progress' ? '⟳ В процессе' : '○ Не начато'}
      </div>
    </div>
  `).join('');
}

function renderProgress() {
  const container = document.getElementById('progressList');
  container.innerHTML = labs.map(lab => `
    <div class="progress-item">
      <div class="progress-header">
        <span>Лабораторная №${lab.number}</span>
        <span style="color:${lab.percent===100?'#5d6b4d':lab.percent>0?'#cd7a32':'#512021'}">${lab.percent}%</span>
      </div>
      <div class="progress-bar-bg">
        <div class="progress-fill" style="width:${lab.percent}%; background:${lab.percent===100?'#5d6b4d':lab.percent>0?'#cd7a32':'#512021'}"></div>
      </div>
    </div>
  `).join('');
}

// Navbar scroll
window.addEventListener('scroll', () => {
  document.getElementById('navbar').classList.toggle('scrolled', window.scrollY > 80);
});

// Init
renderLabs();
renderProgress();
</script>
</body>
</html>