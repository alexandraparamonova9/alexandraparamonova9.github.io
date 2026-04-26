<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Александра Парамонова — Обо мне</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&family=Cormorant+Garamond:wght@400;500;600&display=swap" rel="stylesheet">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #f3e9da;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            color: #1a1a1a;
            line-height: 1.5;
        }

        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            padding: 1.5rem 2rem;
            backdrop-filter: blur(20px);
            background: rgba(243, 233, 218, 0.85);
            z-index: 1000;
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            border-bottom: 1px solid rgba(81, 32, 33, 0.08);
        }

        .navbar.hidden {
            transform: translateY(-100%);
        }

        .navbar.scrolled {
            padding: 1rem 2rem;
            background: rgba(243, 233, 218, 0.95);
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.25rem;
            font-weight: 500;
            letter-spacing: -0.02em;
            color: #512021;
            text-decoration: none;
        }

        .logo:hover { opacity: 0.7; }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: #2a2a2a;
            font-size: 0.9rem;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 1px;
            background: #5d6b4d;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after { width: 100%; }
        .nav-links a:hover { color: #512021; }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            cursor: pointer;
        }

        .mobile-menu-btn span {
            display: block;
            width: 24px;
            height: 2px;
            background: #512021;
            margin: 5px 0;
            transition: 0.3s;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 8rem 1.5rem 4rem;
        }

        .profile {
            text-align: center;
            margin-bottom: 4rem;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .profile.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .avatar {
            width: 200px;
            height: 200px;
            border-radius: 24px;
            overflow: hidden;
            margin: 0 auto 2rem;
            box-shadow: 0 20px 40px rgba(81, 32, 33, 0.15);
        }

        .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .profile h1 {
            font-size: clamp(2.5rem, 6vw, 3.5rem);
            color: #512021;
            font-family: 'Cormorant Garamond', serif;
            font-weight: 500;
            margin-bottom: 0.5rem;
        }

        .profile .subtitle {
            color: #5d6b4d;
            font-size: 1.1rem;
            letter-spacing: 0.05em;
        }

        .card {
            background: white;
            border-radius: 32px;
            padding: 2.5rem;
            margin-bottom: 2rem;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease 0.2s;
            border: 1px solid rgba(81, 32, 33, 0.05);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.02);
        }

        .card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .card h2 {
            font-size: 1.8rem;
            color: #512021;
            margin-bottom: 1.5rem;
            font-family: 'Cormorant Garamond', serif;
            font-weight: 500;
        }

        .info-row {
            display: flex;
            align-items: baseline;
            padding: 1rem 0;
            border-bottom: 1px solid rgba(81, 32, 33, 0.08);
        }

        .info-label {
            min-width: 140px;
            font-weight: 600;
            color: #5d6b4d;
        }

        .info-value {
            color: #333;
        }

        .contacts {
            display: flex;
            justify-content: center;
            gap: 3rem;
            flex-wrap: wrap;
            margin: 2rem 0;
        }

        .contact-item {
            text-align: center;
        }

        .contact-icon {
            width: 48px;
            height: 48px;
            margin: 0 auto 0.75rem;
            color: #5d6b4d;
        }

        .contact-item h4 {
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: #512021;
        }

        .contact-item a {
            color: #666;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-item a:hover {
            color: #512021;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: #512021;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 1px solid rgba(81, 32, 33, 0.15);
            border-radius: 16px;
            font-family: 'Inter', sans-serif;
            transition: border-color 0.3s ease;
            background: #fcfaf5;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #5d6b4d;
        }

        .btn-submit {
            width: 100%;
            padding: 1rem;
            background: #512021;
            color: #f3e9da;
            border: none;
            border-radius: 100px;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-submit:hover {
            background: #3a1718;
            transform: scale(1.02);
        }

        .footer {
            text-align: center;
            padding: 3rem 1.5rem;
            border-top: 1px solid rgba(81, 32, 33, 0.1);
            color: #888;
            font-size: 0.8rem;
        }

        @media (max-width: 768px) {
            .navbar { padding: 1rem; }
            
            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 70%;
                height: 100vh;
                background: #f3e9da;
                flex-direction: column;
                justify-content: center;
                gap: 2rem;
                transition: right 0.4s ease;
            }
            
            .nav-links.active { right: 0; }
            .mobile-menu-btn { display: block; }
            
            .mobile-menu-btn.active span:nth-child(1) {
                transform: rotate(45deg) translate(5px, 5px);
            }
            .mobile-menu-btn.active span:nth-child(2) { opacity: 0; }
            .mobile-menu-btn.active span:nth-child(3) {
                transform: rotate(-45deg) translate(7px, -7px);
            }
            
            .container { padding-top: 6rem; }
            .card { padding: 1.5rem; }
            .info-row { flex-direction: column; gap: 0.5rem; }
            .contacts { gap: 2rem; }
        }
    </style>
</head>
<body>

<nav class="navbar" id="navbar">
    <div class="nav-container">
        <a href="https://alexandraparamonova9.github.io/" class="logo">AP</a>
        <div class="nav-links" id="navLinks">
            <a href="https://alexandraparamonova9.github.io/">Главная</a>
            <a href="#" id="labsLink">Работы</a>
            <a href="https://alexandraparamonova9.github.io/about/">Обо мне</a>
        </div>
        <button class="mobile-menu-btn" id="mobileMenuBtn">
            <span></span>
            <span></span>
            <span></span>
        </button>
    </div>
</nav>

<div class="container">
    <div class="profile" id="profile">
        <div class="avatar">
            <img src="https://i.pinimg.com/originals/2c/74/b3/2c74b36ab770ac5d31cdc0946747a0f8.jpg?nii=t" alt="Александра Парамонова">
        </div>
        <h1>Александра Парамонова</h1>
        <div class="subtitle">студентка группы P3122</div>
    </div>

    <div class="card" id="educationCard">
        <h2>Образование</h2>
        <div class="info-row">
            <div class="info-label">Город:</div>
            <div class="info-value">Санкт-Петербург</div>
        </div>
        <div class="info-row">
            <div class="info-label">Университет:</div>
            <div class="info-value">ИТМО</div>
        </div>
        <div class="info-row">
            <div class="info-label">Направление:</div>
            <div class="info-value">Нейротехнологии и программирование 2025</div>
        </div>
        <div class="info-row">
            <div class="info-label">Курс:</div>
            <div class="info-value">1</div>
        </div>
    </div>

    <div class="card" id="contactsCard">
        <h2>Контакты</h2>
        <div class="contacts">
            <div class="contact-item">
                <svg class="contact-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                    <polyline points="22,6 12,13 2,6"/>
                </svg>
                <h4>Email</h4>
                <a href="mailto:mailParamonova@yandex.ru">mailParamonova@yandex.ru</a>
            </div>
            <div class="contact-item">
                <svg class="contact-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                    <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/>
                </svg>
                <h4>GitHub</h4>
                <a href="https://github.com/alexandraparamonova9">@alexandraparamonova9</a>
            </div>
            <div class="contact-item">
                <svg class="contact-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                    <line x1="22" y1="2" x2="11" y2="13"/>
                    <polygon points="22 2 15 22 11 13 2 9 22 2"/>
                </svg>
                <h4>Telegram</h4>
                <a href="https://t.me/aleqxji">@aleqxji</a>
            </div>
        </div>
    </div>

    <div class="card" id="formCard">
        <h2>Свяжитесь со мной</h2>
        <p style="margin-bottom: 1.5rem; color: #666;">Если у вас есть вопросы или предложения, заполните форму ниже — я обязательно отвечу!</p>
        
        <form action="https://formsubmit.co/mailParamonova@yandex.ru" method="POST">
            <div class="form-group">
                <label for="name">Имя</label>
                <input type="text" id="name" name="name" placeholder="Введите ваше имя" required>
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" name="email" placeholder="example@email.com" required>
            </div>
            <div class="form-group">
                <label for="message">Сообщение</label>
                <textarea id="message" name="message" rows="5" placeholder="Ваше сообщение..." required></textarea>
            </div>
            <input type="hidden" name="_captcha" value="false">
            <input type="hidden" name="_template" value="table">
            <button type="submit" class="btn-submit">Отправить сообщение</button>
        </form>
    </div>
</div>

<footer class="footer">
    <p>© 2026 Александра Парамонова</p>
</footer>

<script>
    function navigateTo(url) {
        window.location.href = url;
    }

    document.getElementById('labsLink')?.addEventListener('click', (e) => {
        e.preventDefault();
        navigateTo('https://alexandraparamonova9.github.io/#labs');
    });

    const navbar = document.getElementById('navbar');
    let lastScroll = 0;

    window.addEventListener('scroll', () => {
        const currentScroll = window.pageYOffset;
        
        if (currentScroll > 100) {
            navbar.classList.add('scrolled');
        } else {
            navbar.classList.remove('scrolled');
        }
        
        if (currentScroll > lastScroll && currentScroll > 100) {
            navbar.classList.add('hidden');
        } else {
            navbar.classList.remove('hidden');
        }
        
        lastScroll = currentScroll;
    });

    const mobileBtn = document.getElementById('mobileMenuBtn');
    const navLinks = document.getElementById('navLinks');

    mobileBtn?.addEventListener('click', () => {
        mobileBtn.classList.toggle('active');
        navLinks.classList.toggle('active');
    });

    navLinks?.querySelectorAll('a').forEach(link => {
        link.addEventListener('click', () => {
            mobileBtn?.classList.remove('active');
            navLinks.classList.remove('active');
        });
    });

    const observerOptions = { threshold: 0.1, rootMargin: '0px 0px -50px 0px' };
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, observerOptions);

    document.querySelectorAll('.profile, .card').forEach(el => observer.observe(el));
</script>

</body>
</html>