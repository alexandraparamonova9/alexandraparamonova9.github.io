---
title: Александра Парамонова — Обо мне
---

<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>Александра Парамонова — Обо мне</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400;1,500&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ── BASE ─────────────────────────────── */
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --b:#512021;
  --c:#f3e9da;
  --o:#5d6b4d;
  --b2:#3a1617;
  --dark:#1c1410;
  --ease:cubic-bezier(0.23,1,0.32,1);
}
body{
  background:var(--c);
  font-family:'DM Sans',system-ui,sans-serif;
  color:var(--dark);
  line-height:1.6;
  overflow-x:hidden;
}

/* ── NAVBAR ─────────────────────────────── */
nav{
  position:fixed;
  top:0; left:0; right:0;
  z-index:1000;
  padding:1.4rem 3rem;
  display:flex;
  justify-content:space-between;
  align-items:center;
  transition:all 0.5s var(--ease);
  backdrop-filter:blur(24px);
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
}
.nav-links a:hover{color:var(--b)}

/* ── CONTAINER ─────────────────────────────── */
.container{
  max-width:1080px;
  margin:0 auto;
  padding:160px 2rem 6rem;
}

/* ── PROFILE ─────────────────────────────── */
.profile{
  text-align:center;
  margin-bottom:5rem;
}
.avatar{
  width:210px;
  height:210px;
  border-radius:28px;
  overflow:hidden;
  margin:0 auto 2.5rem;
  box-shadow:0 25px 50px rgba(81,32,33,0.18);
}
.avatar img{
  width:100%;
  height:100%;
  object-fit:cover;
}
.profile h1{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.8rem,7vw,4.2rem);
  color:var(--b);
  margin-bottom:0.6rem;
}
.subtitle{
  color:var(--o);
  font-size:1.15rem;
  letter-spacing:0.06em;
  font-weight:500;
}

/* ── CARDS ─────────────────────────────── */
.card{
  background:white;
  border-radius:32px;
  padding:3rem;
  margin-bottom:2.5rem;
  border:1px solid rgba(81,32,33,0.06);
  box-shadow:0 10px 30px rgba(0,0,0,0.04);
}
.card h2{
  font-family:'Playfair Display',serif;
  font-size:2.1rem;
  color:var(--b);
  margin-bottom:2rem;
}

/* Info rows */
.info-row{
  display:flex;
  padding:1.1rem 0;
  border-bottom:1px solid rgba(81,32,33,0.08);
  align-items:baseline;
}
.info-row:last-child{border-bottom:none;}
.info-label{
  min-width:160px;
  font-weight:600;
  color:var(--o);
}
.info-value{
  color:#333;
  flex:1;
}

/* Contacts */
.contacts{
  display:flex;
  justify-content:center;
  gap:3.5rem;
  flex-wrap:wrap;
  margin:3rem 0;
}
.contact-item{
  text-align:center;
}
.contact-icon{
  width:52px;
  height:52px;
  margin:0 auto 1rem;
  color:var(--o);
}
.contact-item h4{
  color:var(--b);
  margin-bottom:0.4rem;
}
.contact-item a{
  color:#555;
  text-decoration:none;
  transition:color 0.3s;
}
.contact-item a:hover{color:var(--b);}

/* Form */
.form-group{
  margin-bottom:1.8rem;
}
.form-group label{
  display:block;
  margin-bottom:0.6rem;
  font-weight:500;
  color:var(--b);
}
.form-group input,
.form-group textarea{
  width:100%;
  padding:1.1rem 1.4rem;
  border:1px solid rgba(81,32,33,0.15);
  border-radius:18px;
  background:#fcfaf5;
  font-family:inherit;
  font-size:1rem;
}
.form-group input:focus,
.form-group textarea:focus{
  outline:none;
  border-color:var(--o);
}
.btn-submit{
  width:100%;
  padding:1.15rem;
  background:var(--b);
  color:var(--c);
  border:none;
  border-radius:50px;
  font-size:1.02rem;
  font-weight:500;
  cursor:pointer;
  transition:all 0.4s var(--ease);
}
.btn-submit:hover{
  background:var(--b2);
  transform:scale(1.03);
}

/* Footer */
footer{
  text-align:center;
  padding:4rem 2rem 3rem;
  color:rgba(28,20,16,0.45);
  font-size:0.85rem;
  border-top:1px solid rgba(81,32,33,0.1);
}

/* Responsive */
@media(max-width:768px){
  .container{padding:120px 1.5rem 4rem;}
  .card{padding:2rem;}
  .info-row{flex-direction:column; gap:0.4rem;}
  .contacts{gap:2.5rem;}
}
</style>
</head>
<body>

<nav id="navbar">
  <a href="https://alexandraparamonova9.github.io/" class="logo">АП</a>
  <div class="nav-links">
    <a href="https://alexandraparamonova9.github.io/">Главная</a>
    <a href="https://alexandraparamonova9.github.io/#labs">Работы</a>
    <a href="#">Обо мне</a>
  </div>
</nav>

<div class="container">

  <div class="profile">
    <div class="avatar">
      <img src="https://i.pinimg.com/originals/2c/74/b3/2c74b36ab770ac5d31cdc0946747a0f8.jpg?nii=t" alt="Александра Парамонова">
    </div>
    <h1>Александра Парамонова</h1>
    <div class="subtitle">студентка группы P3122 · ИТМО</div>
  </div>

  <div class="card">
    <h2>Образование</h2>
    <div class="info-row">
      <div class="info-label">Город</div>
      <div class="info-value">Санкт-Петербург</div>
    </div>
    <div class="info-row">
      <div class="info-label">Университет</div>
      <div class="info-value">ИТМО</div>
    </div>
    <div class="info-row">
      <div class="info-label">Направление</div>
      <div class="info-value">Нейротехнологии и программирование</div>
    </div>
    <div class="info-row">
      <div class="info-label">Год поступления</div>
      <div class="info-value">2025</div>
    </div>
    <div class="info-row">
      <div class="info-label">Курс</div>
      <div class="info-value">1 курс</div>
    </div>
  </div>

  <div class="card">
    <h2>Контакты</h2>
    <div class="contacts">
      <div class="contact-item">
        <svg class="contact-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        <h4>Email</h4>
        <a href="mailto:mailParamonova@yandex.ru">mailParamonova@yandex.ru</a>
      </div>
      <div class="contact-item">
        <svg class="contact-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
        <h4>GitHub</h4>
        <a href="https://github.com/alexandraparamonova9" target="_blank">@alexandraparamonova9</a>
      </div>
      <div class="contact-item">
        <svg class="contact-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
        <h4>Telegram</h4>
        <a href="https://t.me/aleqxji" target="_blank">@aleqxji</a>
      </div>
    </div>
  </div>

  <div class="card">
    <h2>Свяжитесь со мной</h2>
    <p style="margin-bottom:2rem; color:#666; max-width:680px;">Если у вас есть вопросы по лабораторным работам или предложения сотрудничества — пишите, я обязательно отвечу.</p>
    
    <form action="https://formsubmit.co/mailParamonova@yandex.ru" method="POST">
      <div class="form-group">
        <label for="name">Имя</label>
        <input type="text" id="name" name="name" placeholder="Ваше имя" required>
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" name="email" placeholder="example@email.com" required>
      </div>
      <div class="form-group">
        <label for="message">Сообщение</label>
        <textarea id="message" name="message" rows="6" placeholder="Напишите ваше сообщение..." required></textarea>
      </div>
      <input type="hidden" name="_captcha" value="false">
      <input type="hidden" name="_template" value="table">
      <button type="submit" class="btn-submit">Отправить сообщение</button>
    </form>
  </div>

</div>

<footer>
  <p>© 2026 Александра Парамонова · ИТМО P3122</p>
</footer>

<script>
// Navbar scroll effect
const navbar = document.getElementById('navbar');
window.addEventListener('scroll', () => {
  navbar.classList.toggle('scrolled', window.scrollY > 80);
});

// Mobile menu (если понадобится позже)
</script>
</body>
</html>