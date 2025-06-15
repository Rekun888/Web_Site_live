<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Заброшенное Возрождение | Пространство для подростков</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Roboto+Slab:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #2c3e50;
            --secondary: #e74c3c;
            --accent: #3498db;
            --light: #ecf0f1;
            --dark: #1a2530;
            --gray: #7f8c8d;
            --brick: #c0392b;
        }

        body {
            background-color: #121212;
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: radial-gradient(circle at 10% 20%, rgba(44, 62, 80, 0.1) 0%, rgba(44, 62, 80, 0) 20%), radial-gradient(circle at 90% 80%, rgba(231, 76, 60, 0.1) 0%, rgba(231, 76, 60, 0) 20%), linear-gradient(to bottom, #0a0a0a, #121212 800px);
            font-family: 'Montserrat', sans-serif;
        }

        h1, h2, h3, h4 {
            font-family: 'Roboto Slab', serif;
            font-weight: 700;
        }

        /* Навигация */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 50px;
            background-color: rgba(18, 18, 18, 0.95);
            z-index: 1000;
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(231, 76, 60, 0.3);
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--light);
            text-decoration: none;
        }

            .logo i {
                color: var(--secondary);
                margin-right: 10px;
            }

        .nav-links {
            display: flex;
            list-style: none;
        }

            .nav-links li {
                margin-left: 30px;
            }

            .nav-links a {
                color: var(--light);
                text-decoration: none;
                font-weight: 500;
                position: relative;
                transition: all 0.3s ease;
            }

                .nav-links a:after {
                    content: '';
                    position: absolute;
                    width: 0;
                    height: 2px;
                    bottom: -5px;
                    left: 0;
                    background-color: var(--secondary);
                    transition: width 0.3s ease;
                }

                .nav-links a:hover {
                    color: var(--secondary);
                }

                    .nav-links a:hover:after {
                        width: 100%;
                    }

        /* Герой секция */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 900px;
            z-index: 2;
            padding: 20px;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            animation: fadeInDown 1s ease;
        }

            .hero h1 span {
                color: var(--secondary);
            }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 40px;
            animation: fadeInUp 1s ease 0.3s both;
        }

        .cta-button {
            display: inline-block;
            padding: 15px 40px;
            background: var(--secondary);
            color: white;
            text-decoration: none;
            font-weight: 700;
            border-radius: 30px;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            border: 2px solid var(--secondary);
            font-size: 1.1rem;
            animation: fadeInUp 1s ease 0.6s both;
        }

            .cta-button:hover {
                background: transparent;
                transform: translateY(-3px);
                box-shadow: 0 10px 20px rgba(231, 76, 60, 0.2);
            }

        /* О проекте */
        .section {
            padding: 100px 50px;
        }

        .dark-bg {
            background-color: var(--dark);
        }

        .darker-bg {
            background-color: #0f151b;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            color: var(--light);
            position: relative;
        }

            .section-title:after {
                content: '';
                position: absolute;
                width: 100px;
                height: 4px;
                background: var(--secondary);
                bottom: -15px;
                left: 50%;
                transform: translateX(-50%);
            }

        .about-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 50px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .about-text {
            flex: 1;
        }

            .about-text h3 {
                font-size: 2rem;
                margin-bottom: 20px;
                color: var(--secondary);
            }

            .about-text p {
                margin-bottom: 20px;
                font-size: 1.1rem;
                line-height: 1.8;
            }

        .about-image {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 3px solid rgba(231, 76, 60, 0.3);
            min-height: 400px;
            background: linear-gradient(45deg, #2c3e50, #4a6491);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            text-align: center;
            padding: 20px;
        }

        /* Комнаты */
        .rooms-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .room-card {
            background: rgba(26, 37, 48, 0.7);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(127, 140, 141, 0.2);
        }

            .room-card:hover {
                transform: translateY(-10px);
                box-shadow: 0 15px 30px rgba(231, 76, 60, 0.2);
            }

        .room-image {
            height: 250px;
            overflow: hidden;
            background: linear-gradient(45deg, #3498db, #2c3e50);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.1rem;
            text-align: center;
            padding: 20px;
        }

        .room-info {
            padding: 25px;
        }

            .room-info h3 {
                font-size: 1.5rem;
                margin-bottom: 10px;
                color: var(--accent);
            }

            .room-info p {
                color: var(--gray);
                margin-bottom: 15px;
                line-height: 1.6;
            }

        .room-creator {
            display: flex;
            align-items: center;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid rgba(127, 140, 141, 0.2);
        }

        .creator-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 10px;
            background: var(--secondary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        .creator-info h4 {
            font-size: 1rem;
            color: var(--light);
        }

        .creator-info p {
            font-size: 0.8rem;
            color: var(--gray);
            margin: 0;
        }

        /* Правила */
        .rules-container {
            max-width: 1000px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .rule-card {
            background: rgba(26, 37, 48, 0.7);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            border-left: 4px solid var(--secondary);
            transition: transform 0.3s ease;
        }

            .rule-card:hover {
                transform: translateY(-5px);
            }

            .rule-card i {
                font-size: 2.5rem;
                color: var(--secondary);
                margin-bottom: 20px;
            }

            .rule-card h3 {
                font-size: 1.3rem;
                margin-bottom: 15px;
                color: var(--light);
            }

            .rule-card p {
                color: var(--gray);
                line-height: 1.6;
            }

        /* Присоединиться */
        .join-container {
            max-width: 700px;
            margin: 0 auto;
        }

        .join-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin-top: 40px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            gap: 8px;
        }

            .form-group label {
                font-weight: 500;
                color: var(--light);
                font-size: 1.1rem;
            }

            .form-group input,
            .form-group textarea,
            .form-group select {
                width: 100%;
                padding: 15px;
                background: rgba(26, 37, 48, 0.7);
                border: 1px solid rgba(127, 140, 141, 0.3);
                border-radius: 5px;
                color: var(--light);
                font-size: 1rem;
                font-family: 'Montserrat', sans-serif;
            }

            .form-group textarea {
                min-height: 150px;
                resize: vertical;
            }

        .submit-btn {
            align-self: center;
            padding: 15px 50px;
            background: var(--secondary);
            color: white;
            border: none;
            border-radius: 30px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 20px;
            font-size: 1.1rem;
        }

            .submit-btn:hover {
                background: #c0392b;
                transform: translateY(-3px);
                box-shadow: 0 10px 20px rgba(231, 76, 60, 0.3);
            }

        /* Футер */
        .footer {
            background-color: #0a0e12;
            padding: 70px 50px 30px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto 50px;
        }

        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 25px;
            color: var(--secondary);
            position: relative;
            padding-bottom: 10px;
        }

            .footer-column h3:after {
                content: '';
                position: absolute;
                width: 40px;
                height: 3px;
                background: var(--secondary);
                bottom: 0;
                left: 0;
            }

        .footer-column p, .footer-column a {
            color: var(--gray);
            margin-bottom: 10px;
            text-decoration: none;
            transition: color 0.3s ease;
            line-height: 1.6;
        }

            .footer-column a:hover {
                color: var(--secondary);
            }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

            .social-links a {
                display: flex;
                align-items: center;
                justify-content: center;
                width: 40px;
                height: 40px;
                background: rgba(127, 140, 141, 0.1);
                border-radius: 50%;
                transition: all 0.3s ease;
                color: var(--light);
                font-size: 1.2rem;
            }

                .social-links a:hover {
                    background: var(--secondary);
                    transform: translateY(-3px);
                }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(127, 140, 141, 0.1);
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* Анимации */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Адаптивность */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 3rem;
            }

            .about-content {
                flex-direction: column;
            }
        }

        @media (max-width: 768px) {
            .navbar {
                padding: 15px 20px;
            }

            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .section {
                padding: 70px 20px;
            }

            .about-image {
                min-height: 300px;
            }
        }
    </style>
</head>
<body>
    <!-- Навигация -->
    <nav class="navbar">
        <a href="#" class="logo">
            <i class="fas fa-warehouse"></i>
            Заброшенное Возрождение
        </a>
        <ul class="nav-links">
            <li><a href="#about">О проекте</a></li>
            <li><a href="#rooms">Комнаты</a></li>
            <li><a href="#rules">Правила</a></li>
            <li><a href="#join">Присоединиться</a></li>
            <li><a href="#contact">Контакты</a></li>
        </ul>
    </nav>

    <!-- Герой секция -->
    <section class="hero">
        <div class="hero-content">
            <h1>Пространство <span>свободы</span> и творчества</h1>
            <p>Заброшенное здание, ставшее домом для подростков, где каждый может создать свою уникальную комнату и найти сообщество единомышленников</p>
            <a href="#join" class="cta-button">Стать частью проекта</a>
        </div>
    </section>

    <!-- О проекте -->
    <section id="about" class="section dark-bg">
        <h2 class="section-title">О нашем проекте</h2>
        <div class="about-content">
            <div class="about-text">
                <h3>Как заброшка стала домом</h3>
                <p>Когда-то это было забытое всеми здание на окраине города. Но группа подростков увидела в нем потенциал - пространство, где можно творить, жить и строить сообщество.</p>
                <p>Мы верим, что каждый молодой человек заслуживает место, где он может выразить себя, развить творческие способности и найти поддержку. Наш проект дает подросткам возможность самостоятельно обустроить свое жилое пространство, взяв ответственность за его создание и поддержание.</p>
                <p>Это не просто место для жизни - это пространство для роста, экспериментов и создания чего-то настоящего своими руками. Мы превратили заброшенное здание в живой организм, где каждый уголок дышит творчеством и свободой.</p>
            </div>
            <div class="about-image">
                <div>Изображение заброшенного здания до и после преобразования</div>
            </div>
        </div>
    </section>

    <!-- Комнаты -->
    <section id="rooms" class="section darker-bg">
        <h2 class="section-title">Комнаты участников</h2>
        <div class="rooms-container">
            <div class="room-card">
                <div class="room-image">
                    <div>Арт-бункер - комната для творчества</div>
                </div>
                <div class="room-info">
                    <h3>Арт-бункер</h3>
                    <p>Пространство, полностью посвященное творчеству. Стены покрыты граффити и картинами, в углу - мольберты и материалы для творчества. Здесь проводятся мастер-классы по рисованию и созданию уличного искусства.</p>
                    <div class="room-creator">
                        <div class="creator-avatar">А</div>
                        <div class="creator-info">
                            <h4>Аня, 17 лет</h4>
                            <p>Художница, живет здесь 6 месяцев</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="room-card">
                <div class="room-image">
                    <div>Техно-уголок - место для инноваций</div>
                </div>
                <div class="room-info">
                    <h3>Техно-уголок</h3>
                    <p>Царство технологий и инноваций. Здесь подростки собирают компьютеры, занимаются программированием и робототехникой. По вечерам проходят хакатоны и воркшопы по созданию гаджетов из подручных материалов.</p>
                    <div class="room-creator">
                        <div class="creator-avatar">М</div>
                        <div class="creator-info">
                            <h4>Максим, 16 лет</h4>
                            <p>Программист, живет здесь 4 месяца</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="room-card">
                <div class="room-image">
                    <div>Музыкальное гнездо - звуковая лаборатория</div>
                </div>
                <div class="room-info">
                    <h3>Музыкальное гнездо</h3>
                    <p>Комната, где всегда звучит музыка. Здесь проходят репетиции местной группы и джем-сейшены по выходным. Инструменты собраны из старых деталей и восстановлены силами участников проекта.</p>
                    <div class="room-creator">
                        <div class="creator-avatar">Д</div>
                        <div class="creator-info">
                            <h4>Денис, 18 лет</h4>
                            <p>Музыкант, живет здесь 8 месяцев</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Правила -->
    <section id="rules" class="section dark-bg">
        <h2 class="section-title">Наши правила</h2>
        <div class="rules-container">
            <div class="rule-card">
                <i class="fas fa-hands-helping"></i>
                <h3>Взаимоуважение</h3>
                <p>Мы уважаем личное пространство и выбор каждого. Любые конфликты решаем через диалог и медитацию. Оскорбления и насилие недопустимы.</p>
            </div>

            <div class="rule-card">
                <i class="fas fa-hammer"></i>
                <h3>Совместное созидание</h3>
                <p>Каждый участник вносит вклад в обустройство пространства - ремонт, уборка, создание зон общего пользования. Минимум 10 часов в неделю на общие дела.</p>
            </div>

            <div class="rule-card">
                <i class="fas fa-seedling"></i>
                <h3>Экологичность</h3>
                <p>Мы стремимся к минимальному воздействию на окружающую среду: переработка, повторное использование, экологичные материалы. Энергия от солнечных батарей.</p>
            </div>

            <div class="rule-card">
                <i class="fas fa-book"></i>
                <h3>Обучение и развитие</h3>
                <p>Каждый участник делится своими навыками с другими через мастер-классы и воркшопы. Еженедельные образовательные встречи обязательны.</p>
            </div>

            <div class="rule-card">
                <i class="fas fa-ban"></i>
                <h3>Нет наркотикам</h3>
                <p>Абсолютное табу на любые наркотические вещества. Наше пространство - территория чистого сознания. Алкоголь только для совершеннолетних в ограниченных количествах.</p>
            </div>

            <div class="rule-card">
                <i class="fas fa-users"></i>
                <h3>Сообщество</h3>
                <p>Мы принимаем решения сообща на еженедельных собраниях, где каждый голос имеет значение. Важные вопросы решаются большинством голосов.</p>
            </div>
        </div>
    </section>

    <!-- Присоединиться -->
    <section id="join" class="section darker-bg">
        <h2 class="section-title">Стать частью сообщества</h2>
        <div class="join-container">
            <p>У тебя есть возможность создать свою комнату в нашем пространстве. Расскажи о себе, своих интересах и том, какой вклад ты можешь внести в наше сообщество.</p>

            <form class="join-form">
                <div class="form-group">
                    <label for="name">Твое имя</label>
                    <input type="text" id="name" placeholder="Как тебя зовут?" required>
                </div>

                <div class="form-group">
                    <label for="age">Возраст</label>
                    <input type="number" id="age" min="14" max="19" placeholder="От 14 до 19 лет" required>
                </div>

                <div class="form-group">
                    <label for="interests">Твои интересы и навыки</label>
                    <textarea id="interests" placeholder="Искусство, музыка, программирование, строительство, дизайн..." required></textarea>
                </div>

                <div class="form-group">
                    <label for="room-idea">Идея для твоей комнаты</label>
                    <textarea id="room-idea" placeholder="Опиши, как ты видишь свое пространство, что будешь создавать..." required></textarea>
                </div>

                <div class="form-group">
                    <label for="contribution">Чем ты можешь помочь сообществу?</label>
                    <textarea id="contribution" placeholder="Какие навыки можешь передать другим? Как будешь участвовать в жизни проекта?" required></textarea>
                </div>

                <button type="submit" class="submit-btn">Отправить заявку</button>
            </form>
        </div>
    </section>

    <!-- Футер -->
    <footer id="contact" class="footer">
        <div class="footer-content">
            <div class="footer-column">
                <h3>Заброшенное Возрождение</h3>
                <p>Пространство, созданное подростками для подростков, где каждый может найти свой уголок и реализовать творческие идеи. Мы преобразуем заброшенные здания в центры молодежной культуры и творчества.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-telegram"></i></a>
                    <a href="#"><i class="fab fa-tiktok"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>

            <div class="footer-column">
                <h3>Контакты</h3>
                <p><i class="fas fa-map-marker-alt"></i>Москва, 9-я Чоботовская аллея, 35с1</p>
                <p><i class="fas fa-envelope"></i> revival@zabroshka.org</p>
                <p><i class="fas fa-phone"></i> +7 (XXX) XXX-XX-XX</p>
                <p><i class="fas fa-clock"></i> Посещение по предварительной договоренности</p>
                <p><i class="fas fa-users"></i> Прием заявок: круглосуточно</p>
            </div>

            <div class="footer-column">
                <h3>Поддержать проект</h3>
                <p>Нам всегда нужны строительные материалы, инструменты, краски и другие материалы для обустройства пространства.</p>
                <p>Если вы хотите помочь материально или привезти необходимые вещи, свяжитесь с нами! Мы с благодарностью принимаем любую помощь.</p>
                <p>Также мы ищем менторов и профессионалов, готовых делиться знаниями с подростками.</p>
            </div>
        </div>

        <div class="copyright">
            <p>&copy; 2023 Заброшенное Возрождение. Проект создан подростками для подростков. Никакие права не защищены - распространяйте свободно!</p>
        </div>
    </footer>

    <script>
        // Плавная прокрутка для навигационных ссылок
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();

                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Анимация при прокрутке
        const observerOptions = {
            root: null,
            rootMargin: '0px',
            threshold: 0.1
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Применяем ко всем секциям
        document.querySelectorAll('section').forEach(section => {
            if (!section.classList.contains('hero')) {
                section.style.opacity = '0';
                section.style.transform = 'translateY(30px)';
                section.style.transition = 'opacity 0.8s ease, transform 0.8s ease';
                observer.observe(section);
            }
        });

        // Обработка отправки формы
        const form = document.querySelector('.join-form');
        form.addEventListener('submit', function (e) {
            e.preventDefault();

            // Сбор данных формы
            const name = document.getElementById('name').value;

            // Показ сообщения
            alert(`Спасибо, ${name}! Твоя заявка принята. Мы свяжемся с тобой в течение 3-х дней для обсуждения деталей.`);

            // Сброс формы
            form.reset();
        });

        // Анимация для героя
        window.addEventListener('load', function () {
            const hero = document.querySelector('.hero');
            hero.style.background = 'linear-gradient(rgba(0, 0, 0, 0.7), url(https://images.unsplash.com/photo-1558036117-15d82a90b9b1?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80)';
            hero.style.backgroundSize = 'cover';
            hero.style.backgroundPosition = 'center';
        });
    </script>
</body>
</html>
