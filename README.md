<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio Mewah</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
        }

        :root {
            --primary-color: #d4af37; /* Gold */
            --secondary-color: #1a1a1a; /* Dark */
            --accent-color: #f8f8f8; /* Light */
            --text-color: #333;
            --transition: all 0.3s ease;
        }

        body {
            background-color: var(--secondary-color);
            color: var(--accent-color);
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 20px 10%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            transition: var(--transition);
        }

        .navbar.scrolled {
            background-color: rgba(26, 26, 26, 0.9);
            padding: 15px 10%;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        .logo {
            font-size: 28px;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
        }

        .logo span {
            color: var(--accent-color);
        }

        .nav-links {
            display: flex;
            gap: 40px;
        }

        .nav-links a {
            color: var(--accent-color);
            text-decoration: none;
            font-weight: 500;
            font-size: 16px;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            bottom: -5px;
            left: 0;
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .menu-btn {
            display: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--accent-color);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 10%;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(rgba(26, 26, 26, 0.7), rgba(26, 26, 26, 0.7));
            z-index: -1;
        }

        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: -2;
        }

        .hero-content {
            max-width: 600px;
        }

        .hero-content h1 {
            font-size: 56px;
            font-weight: 700;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero-content h1 span {
            color: var(--primary-color);
        }

        .hero-content h3 {
            font-size: 32px;
            font-weight: 600;
            color: var(--primary-color);
            margin-bottom: 15px;
        }

        .hero-content p {
            font-size: 16px;
            margin-bottom: 30px;
            line-height: 1.6;
        }

        .btn-box {
            display: flex;
            gap: 20px;
        }

        .btn {
            padding: 12px 28px;
            background: var(--primary-color);
            color: var(--secondary-color);
            border: 2px solid var(--primary-color);
            border-radius: 30px;
            font-size: 16px;
            font-weight: 600;
            text-decoration: none;
            transition: var(--transition);
        }

        .btn:hover {
            background: transparent;
            color: var(--primary-color);
        }

        .btn-outline {
            background: transparent;
            color: var(--primary-color);
        }

        .btn-outline:hover {
            background: var(--primary-color);
            color: var(--secondary-color);
        }

        .social-icons {
            position: absolute;
            bottom: 40px;
            display: flex;
            gap: 20px;
        }

        .social-icons a {
            display: inline-flex;
            justify-content: center;
            align-items: center;
            width: 40px;
            height: 40px;
            background: transparent;
            border: 2px solid var(--primary-color);
            border-radius: 50%;
            color: var(--primary-color);
            font-size: 20px;
            text-decoration: none;
            transition: var(--transition);
        }

        .social-icons a:hover {
            background: var(--primary-color);
            color: var(--secondary-color);
            box-shadow: 0 0 20px var(--primary-color);
        }

        /* About Section */
        .about {
            padding: 100px 10%;
            background: var(--accent-color);
            color: var(--text-color);
        }

        .section-title {
            text-align: center;
            font-size: 40px;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: var(--primary-color);
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }

        .about-img {
            flex: 1;
            position: relative;
        }

        .about-img img {
            width: 100%;
            max-width: 500px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .about-img::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            border: 5px solid var(--primary-color);
            border-radius: 10px;
            top: 20px;
            left: 20px;
            z-index: -1;
        }

        .about-text {
            flex: 1;
        }

        .about-text h3 {
            font-size: 28px;
            margin-bottom: 20px;
        }

        .about-text h3 span {
            color: var(--primary-color);
        }

        .about-text p {
            font-size: 16px;
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .skills {
            margin-top: 30px;
        }

        .skill-item {
            margin-bottom: 20px;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .skill-bar {
            height: 10px;
            background: #ddd;
            border-radius: 5px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: var(--primary-color);
            border-radius: 5px;
        }

        /* Portfolio Section */
        .portfolio {
            padding: 100px 10%;
            background: var(--secondary-color);
        }

        .portfolio .section-title {
            color: var(--accent-color);
        }

        .portfolio-filter {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 50px;
        }

        .filter-btn {
            padding: 8px 20px;
            background: transparent;
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
        }

        .filter-btn.active, .filter-btn:hover {
            background: var(--primary-color);
            color: var(--secondary-color);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .portfolio-item {
            position: relative;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transition: var(--transition);
        }

        .portfolio-item:hover {
            transform: translateY(-10px);
        }

        .portfolio-img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            display: block;
        }

        .portfolio-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(26, 26, 26, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: var(--transition);
        }

        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }

        .portfolio-overlay h4 {
            color: var(--primary-color);
            font-size: 24px;
            margin-bottom: 10px;
        }

        .portfolio-overlay p {
            color: var(--accent-color);
            text-align: center;
            padding: 0 20px;
            margin-bottom: 20px;
        }

        .portfolio-link {
            display: inline-flex;
            justify-content: center;
            align-items: center;
            width: 50px;
            height: 50px;
            background: var(--primary-color);
            border-radius: 50%;
            color: var(--secondary-color);
            font-size: 20px;
            text-decoration: none;
            transition: var(--transition);
        }

        .portfolio-link:hover {
            transform: rotate(360deg);
            box-shadow: 0 0 20px var(--primary-color);
        }

        /* Contact Section */
        .contact {
            padding: 100px 10%;
            background: var(--accent-color);
            color: var(--text-color);
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .contact-icon {
            display: inline-flex;
            justify-content: center;
            align-items: center;
            width: 60px;
            height: 60px;
            background: var(--primary-color);
            border-radius: 50%;
            color: var(--secondary-color);
            font-size: 24px;
        }

        .contact-text h4 {
            font-size: 20px;
            margin-bottom: 5px;
            color: var(--primary-color);
        }

        .contact-text p {
            font-size: 16px;
        }

        .contact-form {
            background: var(--secondary-color);
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .contact-form h3 {
            color: var(--primary-color);
            font-size: 28px;
            margin-bottom: 20px;
        }

        .input-group {
            margin-bottom: 20px;
        }

        .input-group input,
        .input-group textarea {
            width: 100%;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 5px;
            color: var(--accent-color);
            font-size: 16px;
            transition: var(--transition);
        }

        .input-group input:focus,
        .input-group textarea:focus {
            border-color: var(--primary-color);
            outline: none;
            background: rgba(255, 255, 255, 0.15);
        }

        .input-group textarea {
            resize: vertical;
            min-height: 150px;
        }

        .form-btn {
            width: 100%;
            padding: 15px;
            background: var(--primary-color);
            border: none;
            border-radius: 5px;
            color: var(--secondary-color);
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }

        .form-btn:hover {
            background: #c2a227;
        }

        /* Footer */
        .footer {
            background: var(--secondary-color);
            padding: 30px 10%;
            text-align: center;
            color: var(--accent-color);
        }

        .footer p {
            margin-bottom: 15px;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }

        .footer-links a {
            color: var(--accent-color);
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--primary-color);
        }

        .copyright {
            font-size: 14px;
            opacity: 0.8;
        }

        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: var(--primary-color);
            color: var(--secondary-color);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 20px;
            text-decoration: none;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            z-index: 99;
        }

        .back-to-top.active {
            opacity: 1;
            visibility: visible;
        }

        .back-to-top:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(212, 175, 55, 0.5);
        }

        /* Music Player Styles */
        .music-player {
            position: fixed;
            bottom: 20px;
            left: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            z-index: 100;
            background: rgba(26, 26, 26, 0.8);
            padding: 10px 15px;
            border-radius: 30px;
            border: 1px solid var(--primary-color);
        }

        .music-btn {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--primary-color);
            color: var(--secondary-color);
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .music-btn:hover {
            transform: scale(1.1);
        }

        .music-status {
            color: var(--accent-color);
            font-size: 14px;
            font-weight: 500;
        }

        /* Project Audio Button */
        .play-demo-btn {
            padding: 8px 15px;
            background: var(--primary-color);
            color: var(--secondary-color);
            border: none;
            border-radius: 20px;
            cursor: pointer;
            margin: 10px 0;
            display: flex;
            align-items: center;
            gap: 5px;
            font-weight: 500;
            transition: var(--transition);
        }

        .play-demo-btn:hover {
            background: #c2a227;
        }

        /* Responsive Design */
        @media (max-width: 1200px) {
            .hero-content h1 {
                font-size: 48px;
            }
            
            .hero-content h3 {
                font-size: 28px;
            }
        }

        @media (max-width: 992px) {
            .navbar {
                padding: 15px 5%;
            }
            
            .hero, .about, .portfolio, .contact {
                padding: 80px 5%;
            }
            
            .about-content {
                flex-direction: column;
            }
            
            .about-img, .about-text {
                flex: none;
                width: 100%;
            }
            
            .about-img::before {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .menu-btn {
                display: block;
            }
            
            .nav-links {
                position: fixed;
                top: 80px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 80px);
                background: var(--secondary-color);
                flex-direction: column;
                align-items: center;
                justify-content: center;
                gap: 30px;
                transition: var(--transition);
            }
            
            .nav-links.active {
                left: 0;
            }
            
            .hero-content h1 {
                font-size: 36px;
            }
            
            .hero-content h3 {
                font-size: 24px;
            }
            
            .btn-box {
                flex-direction: column;
                gap: 15px;
            }
            
            .portfolio-grid {
                grid-template-columns: 1fr;
            }

            .music-player {
                bottom: 70px;
                left: 50%;
                transform: translateX(-50%);
            }
        }

        @media (max-width: 576px) {
            .hero-content h1 {
                font-size: 32px;
            }
            
            .section-title {
                font-size: 32px;
            }
            
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .contact-form {
                padding: 30px 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Background Music (hidden) -->
    <audio id="bgMusic" loop>
        <source src="mangu.mp3" type="audio/mpeg">
    </audio>

    <!-- Navigation -->
    <nav class="navbar">
        <a href="#" class="logo">Portfo<span>lio.</span></a>
        <div class="menu-btn">
            <i class="fas fa-bars"></i>
        </div>
        <div class="nav-links">
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#portfolio">Portfolio</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <img src="https://images.unsplash.com/photo-1517502884422-41eaead166d4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Background" class="hero-bg">
        <div class="hero-content">
            <h3>Hello, I'm</h3>
            <h1>Aril <span>Alpiansyah</span></h1>
            <h3>And I'm a <span class="typing">Web Developer</span></h3>
            <p>I create elegant, functional, and responsive websites that deliver exceptional user experiences. Let's build something amazing together.</p>
            <div class="btn-box">
                <a href="#contact" class="btn">Hire Me</a>
                <a href="#about" class="btn btn-outline">About Me</a>
            </div>
        </div>
        <div class="social-icons">
            <a href="#"><i class="fab fa-facebook-f"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-linkedin-in"></i></a>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <h2 class="section-title">About <span>Me</span></h2>
        <div class="about-content">
            <div class="about-img">
                <img src="aril.jpg" alt="Profile">
            </div>
            <div class="about-text">
                <h3>I'm Aril and I'm a <span>Web Developer</span></h3>
                <p>With over 5 years of experience in web development, I specialize in creating modern, responsive websites and web applications. My passion lies in crafting clean, efficient code and designing intuitive user interfaces that engage and delight users.</p>
                <p>I stay up-to-date with the latest technologies and trends in web development to ensure my clients receive cutting-edge solutions tailored to their specific needs.</p>
                <div class="skills">
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>HTML/CSS</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>JavaScript</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>React</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>UI/UX Design</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 75%;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio" id="portfolio">
        <h2 class="section-title">My <span>Portfolio</span></h2>
        <div class="portfolio-filter">
            <button class="filter-btn active" data-filter="all">All</button>
            <button class="filter-btn" data-filter="web">Web Design</button>
            <button class="filter-btn" data-filter="app">App Development</button>
            <button class="filter-btn" data-filter="graphic">Graphic Design</button>
        </div>
        <div class="portfolio-grid">
            <div class="portfolio-item" data-category="web">
                <img src="https://images.unsplash.com/photo-1547658719-da2b51169166?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1528&q=80" alt="Project 1" class="portfolio-img">
                <div class="portfolio-overlay">
                    <h4>E-commerce Website</h4>
                    <p>A fully responsive e-commerce platform with secure payment integration and admin dashboard.</p>
                    <button class="play-demo-btn">
                        <i class="fas fa-play"></i> Audio Demo
                    </button>
                    <audio class="project-audio">
                        <source src="datstick.mp3" type="audio/mpeg">
                    </audio>
                    <a href="#" class="portfolio-link"><i class="fas fa-link"></i></a>
                </div>
            </div>
            <div class="portfolio-item" data-category="app">
                <img src="https://images.unsplash.com/photo-1555774698-0b77e0d5fac6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Project 2" class="portfolio-img">
                <div class="portfolio-overlay">
                    <h4>Fitness App</h4>
                    <p>Mobile application for tracking workouts, nutrition, and progress with personalized recommendations.</p>
                    <button class="play-demo-btn">
                        <i class="fas fa-play"></i> Audio Demo
                    </button>
                    <audio class="project-audio">
                        <source src="dewi.mp3" type="audio/mpeg">
                    </audio>
                    <a href="#" class="portfolio-link"><i class="fas fa-link"></i></a>
                </div>
            </div>
            <div class="portfolio-item" data-category="web">
                <img src="https://images.unsplash.com/photo-1467232004584-a241de8bcf5d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1469&q=80" alt="Project 3" class="portfolio-img">
                <div class="portfolio-overlay">
                    <h4>Corporate Website</h4>
                    <p>Modern corporate website with interactive elements and SEO optimization.</p>
                    <button class="play-demo-btn">
                        <i class="fas fa-play"></i> Audio Demo
                    </button>
                    <audio class="project-audio">
                        <source src="merangkai.mp3" type="audio/mpeg">
                    </audio>
                    <a href="#" class="portfolio-link"><i class="fas fa-link"></i></a>
                </div>
            </div>
            <div class="portfolio-item" data-category="graphic">
                <img src="https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1528&q=80" alt="Project 4" class="portfolio-img">
                <div class="portfolio-overlay">
                    <h4>Brand Identity</h4>
                    <p>Complete brand identity package including logo, color palette, and marketing materials.</p>
                    <button class="play-demo-btn">
                        <i class="fas fa-play"></i> Audio Demo
                    </button>
                    <audio class="project-audio">
                        <source src="niki.mp3" type="audio/mpeg">
                    </audio>
                    <a href="#" class="portfolio-link"><i class="fas fa-link"></i></a>
                </div>
            </div>
            <div class="portfolio-item" data-category="app">
                <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Project 5" class="portfolio-img">
                <div class="portfolio-overlay">
                    <h4>Task Manager</h4>
                    <p>Productivity app for managing tasks, projects, and team collaboration.</p>
                    <button class="play-demo-btn">
                        <i class="fas fa-play"></i> Audio Demo
                    </button>
                    <audio class="project-audio">
                        <source src="tinkywinky.mp3" type="audio/mpeg">
                    </audio>
                    <a href="#" class="portfolio-link"><i class="fas fa-link"></i></a>
                </div>
            </div>
            <div class="portfolio-item" data-category="graphic">
                <img src="https://images.unsplash.com/photo-1542744173-8e7e53415bb0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Project 6" class="portfolio-img">
                <div class="portfolio-overlay">
                    <h4>Marketing Campaign</h4>
                    <p>Visual assets for a comprehensive digital marketing campaign across multiple platforms.</p>
                    <button class="play-demo-btn">
                        <i class="fas fa-play"></i> Audio Demo
                    </button>
                    <audio class="project-audio">
                        <source src="sampainanti.mp3" type="audio/mpeg">
                    </audio>
                    <a href="#" class="portfolio-link"><i class="fas fa-link"></i></a>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2 class="section-title">Contact <span>Me</span></h2>
        <div class="contact-container">
            <div class="contact-info">
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-map-marker-alt"></i>
                    </div>
                    <div class="contact-text">
                        <h4>Location</h4>
                        <p>Cihanjuang dahu 1</p>
                    </div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-phone-alt"></i>
                    </div>
                    <div class="contact-text">
                        <h4>Phone</h4>
                        <p>+62 83141025627</p>
                    </div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-envelope"></i>
                    </div>
                    <div class="contact-text">
                        <h4>Email</h4>
                        <p>arilalpiansyahalpiansyah@gmail.com</p>
                    </div>
                </div>
            </div>
            <div class="contact-form">
                <h3>Send Me a Message</h3>
                <form>
                    <div class="input-group">
                        <input type="text" placeholder="Your Name" required>
                    </div>
                    <div class="input-group">
                        <input type="email" placeholder="Your Email" required>
                    </div>
                    <div class="input-group">
                        <input type="text" placeholder="Subject">
                    </div>
                    <div class="input-group">
                        <textarea placeholder="Your Message" required></textarea>
                    </div>
                    <button type="submit" class="form-btn">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <p>Connect with me on social media</p>
        <div class="footer-links">
            <a href="#"><i class="fab fa-facebook-f"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-linkedin-in"></i></a>
            <a href="#"><i class="fab fa-github"></i></a>
        </div>
        <p class="copyright">© 2023 Portfolio. All Rights Reserved.</p>
    </footer>

    <!-- Back to Top Button -->
    <a href="#" class="back-to-top"><i class="fas fa-arrow-up"></i></a>

    <!-- Music Player -->
    <div class="music-player">
        <button id="musicToggle" class="music-btn">
            <i class="fas fa-music"></i>
        </button>
        <span class="music-status">Background Music</span>
    </div>

    <!-- JavaScript -->
    <script>
        // Mobile Menu Toggle
        const menuBtn = document.querySelector('.menu-btn');
        const navLinks = document.querySelector('.nav-links');

        menuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            menuBtn.innerHTML = navLinks.classList.contains('active') 
                ? '<i class="fas fa-times"></i>' 
                : '<i class="fas fa-bars"></i>';
        });

        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                menuBtn.innerHTML = '<i class="fas fa-bars"></i>';
            });
        });

        // Sticky Navigation
        window.addEventListener('scroll', () => {
            const navbar = document.querySelector('.navbar');
            navbar.classList.toggle('scrolled', window.scrollY > 0);
            
            // Back to top button
            const backToTop = document.querySelector('.back-to-top');
            backToTop.classList.toggle('active', window.scrollY > 500);
        });

        // Typing Animation
        const typingElement = document.querySelector('.typing');
        const professions = ['Web Developer', 'UI/UX Designer', 'Graphic Designer', 'Freelancer'];
        let professionIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        let isEnd = false;

        function type() {
            const currentProfession = professions[professionIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentProfession.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentProfession.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentProfession.length) {
                isEnd = true;
                isDeleting = true;
                setTimeout(type, 1500);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                professionIndex = (professionIndex + 1) % professions.length;
                setTimeout(type, 500);
            } else {
                const typingSpeed = isDeleting ? 100 : 200;
                setTimeout(type, typingSpeed);
            }
        }

        // Start typing animation
        setTimeout(type, 1500);

        // Portfolio Filter
        const filterButtons = document.querySelectorAll('.filter-btn');
        const portfolioItems = document.querySelectorAll('.portfolio-item');

        filterButtons.forEach(button => {
            button.addEventListener('click', () => {
                // Remove active class from all buttons
                filterButtons.forEach(btn => btn.classList.remove('active'));
                // Add active class to clicked button
                button.classList.add('active');
                
                const filterValue = button.getAttribute('data-filter');
                
                portfolioItems.forEach(item => {
                    if (filterValue === 'all' || item.getAttribute('data-category') === filterValue) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetElement.offsetTop - 80,
                    behavior: 'smooth'
                });
            });
        });

        // Audio Controls
        const musicToggle = document.getElementById('musicToggle');
        const bgMusic = document.getElementById('bgMusic');
        const musicStatus = document.querySelector('.music-status');

        // Set initial volume
        bgMusic.volume = 0.3;

        // Load music preference from localStorage
        if(localStorage.getItem('musicEnabled') === 'true') {
            bgMusic.play().catch(e => console.log("Auto-play prevented"));
            musicToggle.innerHTML = '<i class="fas fa-pause"></i>';
            musicStatus.textContent = "Music ON";
        }

        // Music toggle functionality
        musicToggle.addEventListener('click', () => {
            if(bgMusic.paused) {
                bgMusic.play();
                musicToggle.innerHTML = '<i class="fas fa-pause"></i>';
                musicStatus.textContent = "Music ON";
                localStorage.setItem('musicEnabled', 'true');
            } else {
                bgMusic.pause();
                musicToggle.innerHTML = '<i class="fas fa-music"></i>';
                musicStatus.textContent = "Music OFF";
                localStorage.setItem('musicEnabled', 'false');
            }
        });

        // Sound effects for UI interactions
        const hoverSound = new Audio('assets/audio/hover.mp3');
        hoverSound.volume = 0.2;

        const clickSound = new Audio('assets/audio/click.mp3');
        clickSound.volume = 0.3;

        // Add hover sound to buttons
        document.querySelectorAll('.btn, .portfolio-link, .filter-btn').forEach(btn => {
            btn.addEventListener('mouseenter', () => {
                hoverSound.currentTime = 0;
                hoverSound.play().catch(e => console.log("Sound play prevented"));
            });
        });

        // Add click sound to buttons
        document.addEventListener('click', (e) => {
            if(e.target.closest('.btn, .filter-btn, .portfolio-link')) {
                clickSound.currentTime = 0;
                clickSound.play().catch(e => console.log("Sound play prevented"));
            }
        });

        // Project audio demos
        document.querySelectorAll('.play-demo-btn').forEach(btn => {
            btn.addEventListener('click', function(e) {
                e.stopPropagation();
                const audio = this.nextElementSibling;
                const icon = this.querySelector('i');
                
                // Pause all other project audios
                document.querySelectorAll('.project-audio').forEach(a => {
                    if(a !== audio) {
                        a.pause();
                        a.previousElementSibling.querySelector('i').classList.replace('fa-pause', 'fa-play');
                    }
                });
                
                if(audio.paused) {
                    audio.volume = 0.7;
                    audio.play();
                    icon.classList.replace('fa-play', 'fa-pause');
                } else {
                    audio.pause();
                    icon.classList.replace('fa-pause', 'fa-play');
                }
            });
        });
    </script>
</body>
</html>
