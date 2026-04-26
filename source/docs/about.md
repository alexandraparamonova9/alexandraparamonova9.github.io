<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Александра Парамонова — Обо мне</title>
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
            max-width: 1200px;
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

        /* Navbar */
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

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 60px 0 40px;
        }

        .avatar {
            width: 220px;
            height: 220px;
            margin: 0 auto 30px;
            border-radius: 24px;
            overflow: hidden;
            box-shadow: 0 25px 40px -12px rgba(0, 0, 0, 0.2);
            border: 2px solid rgba(92, 30, 31, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .avatar:hover {
            transform: scale(1.02);
            box-shadow: 0 30px 50px -16px rgba(92, 30, 31, 0.25);
        }

        .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .hero h1 {
            font-size: clamp(2rem, 5vw, 3rem);
            font-weight: 600;
            letter-spacing: -0.02em;
            color: #1E1E1E;
            margin-bottom: 12px;
        }

        .hero h1 span {
            color: #5C1E1F;
        }

        .hero-sub {
            font-size: 1.1rem;
            color: #677178;
            font-weight: 400;
        }

        /* Glass Card */
        .glass-card {
            background: rgba(239, 234, 212, 0.6);
            backdrop-filter: blur(4px);
            border-radius: 28px;
            padding: 40px;
            margin: 40px 0;
            border: 1px solid rgba(103, 113, 120, 0.2);
            box-shadow: 0 15px 35px -12px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .glass-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 25px 40px -16px rgba(0, 0, 0, 0.08);
        }

        .section-title {
            font-size: 1.6rem;
            font-weight: 600;
            letter-spacing: -0.01em;
            margin-bottom: 28px;
            color: #1E1E1E;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section-title::before {
            content: '✦';
            color: #5C1E1F;
            font-size: 1.8rem;
        }

        /* Info grid */
        .info-grid {
            display: flex;
            flex-direction: column;
            gap: 14px;
        }

        .info-row {
            display: flex;
            align-items: baseline;
            padding: 14px 20px;
            background: rgba(239, 234, 212, 0.9);
            border-radius: 18px;
            border: 1px solid rgba(103, 113, 120, 0.1);
            transition: all 0.2s ease;
        }

        .info-row:hover {
            border-color: rgba(92, 30, 31, 0.2);
            background: #EFEAD4;
        }

        .info-label {
            min-width: 140px;
            font-weight: 600;
            color: #5C1E1F;
        }

        .info-value {
            color: #2C2C2C;
        }

        /* Contacts grid */
        .contacts-grid {
            display: flex;
            justify-content: center;
            gap: 48px;
            flex-wrap: wrap;
            margin: 30px 0;
        }

        .contact-card {
            text-align: center;
            padding: 24px 32px;
            background: rgba(239, 234, 212, 0.7);
            border-radius: 24px;
            border: 1px solid rgba(103, 113, 120, 0.15);
            transition: all 0.3s ease;
            min-width: 160px;
        }

        .contact-card:hover {
            transform: translateY(-6px);
            border-color: rgba(92, 30, 31, 0.3);
            box-shadow: 0 15px 30px -12px rgba(0, 0, 0, 0.1);
        }

        .contact-card svg {
            stroke: #5C1E1F;
            margin-bottom: 12px;
        }

        .contact-card p {
            margin-top: 8px;
        }

        .contact-card a {
            color: #1E1E1E;
            text-decoration: none;
            transition: color 0.2s;
            font-size: 0.9rem;
        }

        .contact-card a:hover {
            color: #5C1E1F;
        }

        /* Form */
        .form-container {
            max-width: 560px;
            margin: 0 auto;
            padding: 40px;
            background: rgba(239, 234, 212, 0.7);
            backdrop-filter: blur(4px);
            border-radius: 28px;
            border: 1px solid rgba(103, 113, 120, 0.2);
        }

        .form-group {
            margin-bottom: 24px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #1E1E1E;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 14px 18px;
            background: #EFEAD4;
            border: 1px solid rgba(103, 113, 120, 0.3);
            border-radius: 16px;
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
            transition: all 0.2s ease;
            color: #1E1E1E;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #5C1E1F;
            box-shadow: 0 0 0 3px rgba(92, 30, 31, 0.1);
        }

        .btn-submit {
            width: 100%;
            padding: 14px;
            background: #5C1E1F;
            color: #EFEAD4;
            border: none;
            border-radius: 40px;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.25s ease;
        }

        .btn-submit:hover {
            background: #3f1415;
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(92, 30, 31, 0.2);
        }

        .footer {
            margin-top: 80px;
            padding: 32px 0;
            border-top: 1px solid rgba(103, 113, 120, 0.2);
            text-align: center;
            color: #677178;
            font-size: 0.85rem;
        }

        @media (max-width: 768px) {
            .container {
                padding: 0 20px;
            }
            .glass-card {
                padding: 24px;
            }
            .info-label {
                min-width: 110px;
            }
            .contacts-grid {
                gap: 24px;
            }
            .contact-card {
                padding: 18px 24px;
            }
            .form-container {
                padding: 28px;
            }
            .nav-container {
                flex-direction: column;
                gap: 12px;
            }
        }
    </style>
</head>
<body>

<nav class="navbar">
    <div class="nav-container">
        <a href="index.md" class="nav-logo">Alexandra Paramonova</a>
        <div class="nav-links">
            <button class="nav-link" onclick="window.location.href='index.md'">Home</button>
            <button class="nav-link" onclick="window.location.href='labs/lab1.md'">Labs</button>
        </div>
    </div>
</nav>

<main class="container">
    <!-- Hero -->
    <div class="hero animate-on-scroll">
        <div class="avatar">
            <img src="https://i.pinimg.com/originals/2c/74/b3/2c74b36ab770ac5d31cdc0946747a0f8.jpg?nii=t" alt="Александра Парамонова">
        </div>
        <h1>✦ <span>Александра Парамонова</span> ✦</h1>
        <div class="hero-sub">студентка группы P3122</div>
    </div>

    <!-- Образование -->
    <div class="glass-card animate-on-scroll">
        <h2 class="section-title">🎓 Образование</h2>
        <div class="info-grid">
            <div class="info-row">
                <span class="info-label">📍 Город:</span>
                <span class="info-value">Санкт-Петербург</span>
            </div>
            <div class="info-row">
                <span class="info-label">🏛️ Университет:</span>
                <span class="info-value">ИТМО</span>
            </div>
            <div class="info-row">
                <span class="info-label">📚 Направление:</span>
                <span class="info-value">Нейротехнологии и программирование 2025</span>
            </div>
            <div class="info-row">
                <span class="info-label">📖 Курс:</span>
                <span class="info-value">1</span>
            </div>
        </div>
    </div>

    <!-- Контакты -->
    <div class="animate-on-scroll">
        <h2 class="section-title" style="margin-bottom: 20px;">✦ Контакты ✦</h2>
        <div class="contacts-grid">
            <div class="contact-card">
                <svg xmlns="http://www.w3.org/2000/svg" width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                    <polyline points="22,6 12,13 2,6"></polyline>
                </svg>
                <p><strong>Email</strong><br>
                <a href="mailto:mailParamonova@yandex.ru">mailParamonova@yandex.ru</a></p>
            </div>
            <div class="contact-card">
                <svg xmlns="http://www.w3.org/2000/svg" width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
                </svg>
                <p><strong>GitHub</strong><br>
                <a href="https://github.com/alexandraparamonova9">@alexandraparamonova9</a></p>
            </div>
            <div class="contact-card">
                <svg xmlns="http://www.w3.org/2000/svg" width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                    <line x1="22" y1="2" x2="11" y2="13"></line>
                    <polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
                </svg>
                <p><strong>Telegram</strong><br>
                <a href="https://t.me/aleqxji">@aleqxji</a></p>
            </div>
        </div>
    </div>

    <!-- Форма связи -->
    <div class="animate-on-scroll" style="margin: 40px 0;">
        <h2 class="section-title" style="justify-content: center; text-align: center;">✦ Свяжитесь со мной ✦</h2>
        <div style="text-align: center; margin-bottom: 30px; color: #677178;">
            Если у вас есть вопросы, предложения, заполните форму ниже, и я обязательно отвечу!
        </div>
        <div class="form-container">
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
</main>

<footer class="footer">
    <div class="container">
        Alexandra Paramonova • P3122 • портфолио
    </div>
</footer>

<script>
    // Анимация при скролле
    const animatedElements = document.querySelectorAll('.animate-on-scroll');
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('animated');
                observer.unobserve(entry.target);
            }
        });
    }, { threshold: 0.1, rootMargin: "0px 0px -40px 0px" });
    animatedElements.forEach(el => observer.observe(el));
</script>

</body>
</html>