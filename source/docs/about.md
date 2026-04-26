---
title: Обо мне
hide:
  - navigation
  - toc
---

<style>
  .premium-card {
    background: rgba(20, 20, 35, 0.6);
    backdrop-filter: blur(12px);
    border: 1px solid rgba(0, 198, 255, 0.2);
    border-radius: 24px;
    transition: all 0.3s ease;
  }
  
  .premium-card:hover {
    border-color: rgba(0, 198, 255, 0.5);
    transform: translateY(-3px);
    box-shadow: 0 15px 40px rgba(0, 198, 255, 0.1);
  }
  
  .avatar-wrapper {
    position: relative;
    width: 220px;
    height: 220px;
    margin: 0 auto;
  }
  
  .avatar-wrapper::before {
    content: '';
    position: absolute;
    inset: -3px;
    background: linear-gradient(135deg, #00c6ff, #7c3aed, #ff00cc);
    border-radius: 50%;
    animation: rotate 3s linear infinite;
  }
  
  @keyframes rotate {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }
  
  .avatar-inner {
    position: relative;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    overflow: hidden;
    z-index: 1;
  }
  
  .info-row {
    display: flex;
    align-items: baseline;
    gap: 1rem;
    flex-wrap: wrap;
    padding: 1rem 1.2rem;
    background: rgba(0, 198, 255, 0.05);
    border-radius: 16px;
    transition: all 0.3s ease;
  }
  
  .info-row:hover {
    background: rgba(0, 198, 255, 0.1);
    transform: translateX(5px);
  }
  
  .contact-icon {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    padding: 1.5rem;
    background: rgba(20, 20, 35, 0.6);
    backdrop-filter: blur(12px);
    border: 1px solid rgba(0, 198, 255, 0.2);
    border-radius: 20px;
    transition: all 0.3s ease;
    text-decoration: none;
  }
  
  .contact-icon:hover {
    transform: translateY(-5px);
    border-color: #00c6ff;
    box-shadow: 0 10px 30px rgba(0, 198, 255, 0.2);
  }
  
  .contact-icon svg {
    stroke: #00c6ff;
    transition: all 0.3s ease;
  }
  
  .contact-icon:hover svg {
    stroke: #7c3aed;
    transform: scale(1.1);
  }
  
  .form-input {
    width: 100%;
    padding: 1rem;
    background: rgba(10, 10, 15, 0.8);
    border: 1px solid rgba(0, 198, 255, 0.3);
    border-radius: 16px;
    color: white;
    font-size: 1rem;
    transition: all 0.3s ease;
  }
  
  .form-input:focus {
    outline: none;
    border-color: #00c6ff;
    box-shadow: 0 0 15px rgba(0, 198, 255, 0.2);
  }
  
  .form-input::placeholder {
    color: #64748b;
  }
  
  .btn-submit {
    width: 100%;
    padding: 1rem;
    background: linear-gradient(90deg, #00c6ff, #7c3aed);
    border: none;
    border-radius: 16px;
    color: white;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
  }
  
  .btn-submit:hover {
    transform: scale(1.02);
    box-shadow: 0 0 25px rgba(0, 198, 255, 0.4);
  }
  
  .gradient-text {
    background: linear-gradient(135deg, #00c6ff, #7c3aed);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }
</style>

<!-- ЗАГОЛОВОК -->
<div align="center" style="margin-bottom: 3rem;">
  <h1 style="font-size: clamp(2rem, 6vw, 3rem); font-weight: 700;">
    <span class="gradient-text">✦ Обо мне ✦</span>
  </h1>
</div>

<!-- АВАТАР -->
<div class="avatar-wrapper">
  <div class="avatar-inner">
    <img src="https://images.unsplash.com/photo-1592194996308-7b43878e84a6?ixlib=rb-4.0.3&auto=format&fit=crop&w=634&q=80" 
         alt="Александра Парамонова" 
         style="width: 100%; height: 100%; object-fit: cover;">
  </div>
</div>

<div align="center" style="margin: 1.5rem 0;">
  <h2 style="font-size: 1.8rem; font-weight: 600; color: white;">Александра Парамонова</h2>
  <p style="color: #00c6ff; font-size: 1.1rem; margin-top: 0.5rem;">студентка группы P3122</p>
</div>

---

<!-- ОБРАЗОВАНИЕ -->
<div class="premium-card" style="padding: 2rem; margin: 2rem 0;">
  
  <h2 style="font-size: 1.5rem; margin-bottom: 1.5rem; display: flex; align-items: center; gap: 0.5rem;">
    <span>🎓</span> <span class="gradient-text">Образование</span>
  </h2>
  
  <div style="display: flex; flex-direction: column; gap: 12px;">
    
    <div class="info-row">
      <span style="color: #00c6ff; font-weight: 600; min-width: 120px;">📍 Город:</span>
      <span style="color: #cbd5e1;">Санкт-Петербург</span>
    </div>
    
    <div class="info-row">
      <span style="color: #00c6ff; font-weight: 600; min-width: 120px;">🏛️ Университет:</span>
      <span style="color: #cbd5e1;">ИТМО</span>
    </div>
    
    <div class="info-row">
      <span style="color: #00c6ff; font-weight: 600; min-width: 120px;">📚 Направление:</span>
      <span style="color: #cbd5e1;">Нейротехнологии и программирование 2025</span>
    </div>
    
    <div class="info-row">
      <span style="color: #00c6ff; font-weight: 600; min-width: 120px;">📖 Курс:</span>
      <span style="color: #cbd5e1;">1</span>
    </div>
    
  </div>
  
</div>

---

<!-- КОНТАКТЫ -->
<h2 align="center" style="font-size: 1.5rem; margin: 2rem 0 1.5rem 0;">
  <span class="gradient-text">✦ Контакты ✦</span>
</h2>

<div align="center" style="display: flex; justify-content: center; gap: 2rem; flex-wrap: wrap; margin: 2rem 0;">
  
  <a href="mailto:mailParamonova@yandex.ru" class="contact-icon">
    <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
      <polyline points="22,6 12,13 2,6"></polyline>
    </svg>
    <p><strong style="color: white;">Email</strong></p>
    <p style="color: #94a3b8; font-size: 0.85rem; margin: 0;">mailParamonova@yandex.ru</p>
  </a>
  
  <a href="https://github.com/alexandraparamonova9" target="_blank" class="contact-icon">
    <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
    </svg>
    <p><strong style="color: white;">GitHub</strong></p>
    <p style="color: #94a3b8; font-size: 0.85rem; margin: 0;">@alexandraparamonova9</p>
  </a>
  
  <a href="https://t.me/aleqxji" target="_blank" class="contact-icon">
    <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <line x1="22" y1="2" x2="11" y2="13"></line>
      <polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
    </svg>
    <p><strong style="color: white;">Telegram</strong></p>
    <p style="color: #94a3b8; font-size: 0.85rem; margin: 0;">@aleqxji</p>
  </a>
  
</div>

---

<!-- ФОРМА СВЯЗИ -->
<h2 align="center" style="font-size: 1.5rem; margin: 2rem 0 1rem 0;">
  <span class="gradient-text">✦ Свяжитесь со мной ✦</span>
</h2>

<div align="center" style="margin: 1rem 0 2rem 0;">
  <p style="color: #94a3b8;">Если у вас есть вопросы, предложения, то заполните форму ниже, и я обязательно отвечу!</p>
</div>

<div class="premium-card" style="max-width: 550px; margin: 0 auto; padding: 2rem;">
  
  <form action="https://formsubmit.co/mailParamonova@yandex.ru" method="POST">
    
    <div style="margin-bottom: 1.5rem;">
      <label for="name" style="display: block; margin-bottom: 0.5rem; color: #cbd5e1; font-weight: 500;">Имя</label>
      <input type="text" id="name" name="name" class="form-input" placeholder="Введите ваше имя" required>
    </div>
    
    <div style="margin-bottom: 1.5rem;">
      <label for="email" style="display: block; margin-bottom: 0.5rem; color: #cbd5e1; font-weight: 500;">Email</label>
      <input type="email" id="email" name="email" class="form-input" placeholder="example@email.com" required>
    </div>
    
    <div style="margin-bottom: 1.5rem;">
      <label for="message" style="display: block; margin-bottom: 0.5rem; color: #cbd5e1; font-weight: 500;">Сообщение</label>
      <textarea id="message" name="message" rows="5" class="form-input" placeholder="Ваше сообщение..." required></textarea>
    </div>
    
    <input type="hidden" name="_captcha" value="false">
    <input type="hidden" name="_template" value="table">
    <input type="hidden" name="_next" value="/thanks.html">
    
    <button type="submit" class="btn-submit">
      Отправить сообщение ✨
    </button>
    
  </form>
  
</div>