---
hide:
  - navigation
  - toc
---

<style>
  /* Дополнительные стили специально для главной страницы */
  .hero-gradient {
    background: radial-gradient(ellipse at 50% 50%, rgba(0, 198, 255, 0.15) 0%, rgba(10, 10, 15, 0) 70%);
  }
  
  .glow-text {
    text-shadow: 0 0 20px rgba(0, 198, 255, 0.5);
  }
  
  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
  }
  
  .floating-element {
    animation: float 6s ease-in-out infinite;
  }
  
  @keyframes bounce {
    0%, 100% { transform: translateX(-50%) translateY(0); }
    50% { transform: translateX(-50%) translateY(10px); }
  }
  
  @keyframes scroll-pulse {
    0% { opacity: 1; transform: translateY(0); }
    100% { opacity: 0; transform: translateY(15px); }
  }
  
  .progress-bar {
    background: rgba(255, 255, 255, 0.1);
    border-radius: 1rem;
    height: 0.6rem;
    overflow: hidden;
  }
  
  .progress-fill {
    height: 100%;
    border-radius: 1rem;
  }
</style>

<!-- HERO БЛОК — первый экран -->
<div class="hero-gradient" style="min-height: 100vh; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; position: relative; overflow: hidden; margin: -2rem -1rem 0 -1rem; padding: 4rem 2rem;">

  <!-- Декоративные элементы -->
  <div style="position: absolute; top: 20%; left: 10%; width: 300px; height: 300px; background: radial-gradient(circle, rgba(0,198,255,0.2) 0%, transparent 70%); filter: blur(60px);"></div>
  <div style="position: absolute; bottom: 20%; right: 10%; width: 250px; height: 250px; background: radial-gradient(circle, rgba(124,58,237,0.2) 0%, transparent 70%); filter: blur(60px);"></div>

  <div class="floating-element" style="position: relative; z-index: 2;">
    <p style="color: #00c6ff; letter-spacing: 4px; font-size: 0.85rem; font-weight: 500; margin-bottom: 1rem;">
      ✦ FULL-STACK & CREATIVE TECHNOLOGIST ✦
    </p>
    
    <h1 style="font-size: clamp(2.5rem, 8vw, 5.5rem); font-weight: 800; line-height: 1.1; margin-bottom: 1rem;">
      <span style="background: linear-gradient(135deg, #ffffff 0%, #a5f3ff 50%, #00c6ff 100%); -webkit-background-clip: text; background-clip: text; color: transparent;">
        Александра
      </span>
      <br>
      <span style="background: linear-gradient(135deg, #00c6ff 0%, #7c3aed 50%, #ff00cc 100%); -webkit-background-clip: text; background-clip: text; color: transparent;">
        Парамонова
      </span>
    </h1>
    
    <p style="font-size: clamp(1rem, 4vw, 1.3rem); color: #94a3b8; max-width: 600px; margin: 1.5rem auto;">
      студентка группы P3122 
    </p>
    
    <div style="display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; margin-top: 2rem;">
      <a href="about.md" class="btn-glow" style="background: linear-gradient(90deg, #00c6ff, #7c3aed); border: none; padding: 0.8rem 2rem; border-radius: 3rem; color: white; font-weight: 600; text-decoration: none; transition: all 0.3s ease; display: inline-block; box-shadow: 0 0 15px rgba(0,198,255,0.3);">
        🎯 Обо мне
      </a>
      <a href="lab1.md" class="btn-outline" style="background: rgba(255,255,255,0.05); backdrop-filter: blur(10px); border: 1px solid rgba(0,198,255,0.4); padding: 0.8rem 2rem; border-radius: 3rem; color: #00c6ff; font-weight: 600; text-decoration: none; transition: all 0.3s ease; display: inline-block;">
        📚 Лабораторные работы
      </a>
    </div>
  </div>
  
  <!-- Скролл индикатор -->
  <div style="position: absolute; bottom: 2rem; left: 50%; transform: translateX(-50%); animation: bounce 2s infinite;">
    <div style="width: 30px; height: 50px; border: 2px solid rgba(0,198,255,0.5); border-radius: 20px; display: flex; justify-content: center;">
      <div style="width: 4px; height: 12px; background: #00c6ff; border-radius: 2px; margin-top: 8px; animation: scroll-pulse 1.5s infinite;"></div>
    </div>
  </div>
</div>

---

<!-- ПРОГРЕСС ВЫПОЛНЕНИЯ ЛАБОРАТОРНЫХ РАБОТ (в стиле технологического стека) -->
<h2 class="gradient-title" style="font-size: clamp(1.8rem, 5vw, 2.2rem); margin: 2rem 0 1rem 0; text-align: center;">📊 Прогресс выполнения</h2>

<div class="glass-card" style="padding: 2rem;">
  
  <!-- Лабораторная работа №1 - 100% -->
  <div style="margin-bottom: 1.5rem;">
    <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
      <span style="font-weight: 500;">
        <a href="lab1.md" style="color: white; text-decoration: none;">Лабораторная работа №1</a>
      </span>
      <span style="color: #22c55e; font-weight: 600;">100%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 100%; background: linear-gradient(90deg, #22c55e, #00c6ff);"></div>
    </div>
  </div>
  
  <!-- Лабораторная работа №2 - 100% -->
  <div style="margin-bottom: 1.5rem;">
    <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
      <span style="font-weight: 500;">
        <a href="lab2.md" style="color: white; text-decoration: none;">Лабораторная работа №2</a>
      </span>
      <span style="color: #22c55e; font-weight: 600;">100%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 100%; background: linear-gradient(90deg, #22c55e, #00c6ff);"></div>
    </div>
  </div>
  
  <!-- Лабораторная работа №3 - 100% -->
  <div style="margin-bottom: 1.5rem;">
    <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
      <span style="font-weight: 500;">
        <a href="lab3.md" style="color: white; text-decoration: none;">Лабораторная работа №3</a>
      </span>
      <span style="color: #22c55e; font-weight: 600;">100%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 100%; background: linear-gradient(90deg, #22c55e, #00c6ff);"></div>
    </div>
  </div>
  
  <!-- Лабораторная работа №4 - 100% -->
  <div style="margin-bottom: 1.5rem;">
    <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
      <span style="font-weight: 500;">
        <a href="lab4.md" style="color: white; text-decoration: none;">Лабораторная работа №4</a>
      </span>
      <span style="color: #22c55e; font-weight: 600;">100%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 100%; background: linear-gradient(90deg, #22c55e, #00c6ff);"></div>
    </div>
  </div>
  
  <!-- Лабораторная работа №5 - 100% -->
  <div style="margin-bottom: 1.5rem;">
    <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
      <span style="font-weight: 500;">
        <a href="lab5.md" style="color: white; text-decoration: none;">Лабораторная работа №5</a>
      </span>
      <span style="color: #22c55e; font-weight: 600;">100%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 100%; background: linear-gradient(90deg, #22c55e, #00c6ff);"></div>
    </div>
  </div>
  
  <!-- Лабораторная работа №6 - 40% -->
  <div style="margin-bottom: 1.5rem;">
    <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
      <span style="font-weight: 500;">
        <span style="color: #94a3b8;">Лабораторная работа №6</span>
      </span>
      <span style="color: #eab308; font-weight: 600;">40%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 40%; background: linear-gradient(90deg, #eab308, #f59e0b);"></div>
    </div>
  </div>
  
  <!-- Лабораторная работа №7 - 20% -->
  <div style="margin-bottom: 1.5rem;">
    <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
      <span style="font-weight: 500;">
        <span style="color: #94a3b8;">Лабораторная работа №7</span>
      </span>
      <span style="color: #eab308; font-weight: 600;">20%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 20%; background: linear-gradient(90deg, #eab308, #f59e0b);"></div>
    </div>
  </div>
  
  <!-- Лабораторная работа №8 - 0% -->
  <div style="margin-bottom: 0rem;">
    <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
      <span style="font-weight: 500;">
        <span style="color: #94a3b8;">Лабораторная работа №8</span>
      </span>
      <span style="color: #ef4444; font-weight: 600;">0%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 0%; background: linear-gradient(90deg, #ef4444, #dc2626);"></div>
    </div>
  </div>

</div>

---

<!-- ФУТЕР -->
<div style="text-align: center; padding: 2rem 0 1rem 0; border-top: 1px solid rgba(0,198,255,0.1); margin-top: 2rem;">
  <p style="color: #475569; font-size: 0.85rem;">
    © 2026 Александра Парамонова • студентка группы P3122 • ИТМО
  </p>
  <div style="display: flex; justify-content: center; gap: 1rem; margin-top: 0.5rem;">
    <span style="color: #475569;">✦</span>
    <span style="color: #475569;">Neural Technologies</span>
    <span style="color: #475569;">✦</span>
  </div>
</div>