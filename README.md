<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Oussama El Boukhari - Developer Portfolio</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Inter:wght@400;500;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #0c0e27 0%, #24243e 50%, #302b63 100%);
            color: #e1e5f2;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        /* Animated background particles */
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #58A6FF;
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.5; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 1; }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
        }
        
        /* Header Section */
        .header {
            text-align: center;
            padding: 4rem 0;
            position: relative;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, rgba(88, 166, 255, 0.3) 0%, transparent 70%);
            border-radius: 50%;
            animation: pulse 3s ease-in-out infinite;
        }
        
        @keyframes pulse {
            0%, 100% { transform: translateX(-50%) scale(1); }
            50% { transform: translateX(-50%) scale(1.1); }
        }
        
        .header h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #58A6FF, #7C3AED, #EC4899);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 4s ease infinite;
        }
        
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        .typing-animation {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.5rem;
            color: #58A6FF;
            margin: 2rem 0;
            min-height: 2rem;
        }
        
        .profile-gif {
            width: 300px;
            height: auto;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(88, 166, 255, 0.3);
            margin: 2rem 0;
            transition: transform 0.3s ease;
        }
        
        .profile-gif:hover {
            transform: scale(1.05) rotate(2deg);
        }
        
        .profile-views {
            display: inline-block;
            padding: 0.5rem 1rem;
            background: rgba(88, 166, 255, 0.1);
            border: 1px solid rgba(88, 166, 255, 0.3);
            border-radius: 25px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }
        
        .profile-views:hover {
            background: rgba(88, 166, 255, 0.2);
            transform: translateY(-2px);
        }
        
        /* About Section */
        .about-section {
            margin: 4rem 0;
            padding: 3rem;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease;
        }
        
        .about-section:hover {
            transform: translateY(-5px);
        }
        
        .code-block {
            background: #1a1b26;
            padding: 2rem;
            border-radius: 15px;
            font-family: 'JetBrains Mono', monospace;
            border: 1px solid #58A6FF;
            position: relative;
            overflow: hidden;
        }
        
        .code-block::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(88, 166, 255, 0.1), transparent);
            animation: scan 3s linear infinite;
        }
        
        @keyframes scan {
            0% { left: -100%; }
            100% { left: 100%; }
        }
        
        .code-line {
            margin: 0.5rem 0;
            animation: fadeInUp 0.6s ease forwards;
            opacity: 0;
        }
        
        .code-line:nth-child(1) { animation-delay: 0.1s; }
        .code-line:nth-child(2) { animation-delay: 0.2s; }
        .code-line:nth-child(3) { animation-delay: 0.3s; }
        .code-line:nth-child(4) { animation-delay: 0.4s; }
        .code-line:nth-child(5) { animation-delay: 0.5s; }
        .code-line:nth-child(6) { animation-delay: 0.6s; }
        .code-line:nth-child(7) { animation-delay: 0.7s; }
        .code-line:nth-child(8) { animation-delay: 0.8s; }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .key { color: #7C3AED; }
        .string { color: #10B981; }
        .value { color: #F59E0B; }
        .bracket { color: #58A6FF; }
        
        /* Tech Stack Section */
        .tech-stack {
            margin: 4rem 0;
            text-align: center;
        }
        
        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            position: relative;
            display: inline-block;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #58A6FF, #7C3AED);
            border-radius: 2px;
        }
        
        .tech-category {
            margin: 3rem 0;
        }
        
        .tech-category h3 {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: #58A6FF;
        }
        
        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
        }
        
        .tech-badge {
            padding: 0.8rem 1.5rem;
            background: rgba(88, 166, 255, 0.1);
            border: 1px solid rgba(88, 166, 255, 0.3);
            border-radius: 30px;
            color: #e1e5f2;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }
        
        .tech-badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }
        
        .tech-badge:hover::before {
            left: 100%;
        }
        
        .tech-badge:hover {
            background: rgba(88, 166, 255, 0.2);
            border-color: #58A6FF;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 25px rgba(88, 166, 255, 0.3);
        }
        
        /* Stats Section */
        .stats-section {
            margin: 4rem 0;
            text-align: center;
        }
        
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(45deg, #58A6FF, #7C3AED, #EC4899);
            background-size: 300% 300%;
            animation: gradientShift 3s ease infinite;
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(88, 166, 255, 0.2);
        }
        
        /* What I'm About Section */
        .about-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }
        
        .about-item {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-radius: 15px;
            padding: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            position: relative;
        }
        
        .about-item:hover {
            transform: translateY(-5px);
            border-color: #58A6FF;
        }
        
        .about-item::before {
            content: '';
            position: absolute;
            top: 1rem;
            left: 1rem;
            width: 8px;
            height: 8px;
            background: #58A6FF;
            border-radius: 50%;
            animation: blink 2s ease-in-out infinite;
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }
        
        .about-item h4 {
            color: #58A6FF;
            margin-bottom: 1rem;
            font-size: 1.2rem;
            padding-left: 1.5rem;
        }
        
        .about-item p {
            line-height: 1.6;
            padding-left: 1.5rem;
        }
        
        /* Connect Section */
        .connect-section {
            text-align: center;
            margin: 4rem 0;
            padding: 3rem;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 2rem 0;
            flex-wrap: wrap;
        }
        
        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 1rem 2rem;
            background: rgba(88, 166, 255, 0.1);
            border: 1px solid rgba(88, 166, 255, 0.3);
            border-radius: 50px;
            color: #e1e5f2;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }
        
        .social-link:hover {
            background: rgba(88, 166, 255, 0.2);
            border-color: #58A6FF;
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(88, 166, 255, 0.3);
        }
        
        .quote {
            font-style: italic;
            font-size: 1.2rem;
            margin: 2rem 0;
            padding: 2rem;
            background: rgba(124, 58, 237, 0.1);
            border-left: 4px solid #7C3AED;
            border-radius: 10px;
        }
        
        .footer-gifs {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 1rem;
            margin-top: 2rem;
        }
        
        .footer-gif {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            animation: bounce 2s ease-in-out infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .typing-animation {
                font-size: 1.2rem;
            }
            
            .profile-gif {
                width: 250px;
            }
            
            .container {
                padding: 1rem;
            }
            
            .about-section, .connect-section {
                padding: 2rem;
            }
            
            .social-links {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Background Particles -->
    <div class="particles" id="particles"></div>
    
    <div class="container">
        <!-- Header Section -->
        <div class="header">
            <h1>👋 Hi there, I'm Oussama El Boukhari</h1>
            <div class="typing-animation" id="typing"></div>
            <img src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" alt="Coding GIF" class="profile-gif">
            <div class="profile-views">
                👀 Profile Views: <span id="viewCount">1337</span>
            </div>
        </div>
        
        <!-- About Section -->
        <div class="about-section">
            <h2 class="section-title">🧑‍💻 About Me</h2>
            <div class="code-block">
                <div class="code-line"><span class="key">const</span> <span class="value">oussama</span> <span class="bracket">=</span> <span class="bracket">{</span></div>
                <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="key">location</span><span class="bracket">:</span> <span class="string">"Morocco 🇲🇦"</span><span class="bracket">,</span></div>
                <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="key">education</span><span class="bracket">:</span> <span class="string">"1337 School (42 Network) Graduate"</span><span class="bracket">,</span></div>
                <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="key">currentStatus</span><span class="bracket">:</span> <span class="string">"Software Developer seeking new opportunities"</span><span class="bracket">,</span></div>
                <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="key">languages</span><span class="bracket">:</span> <span class="bracket">[</span><span class="string">"Arabic (Native)"</span><span class="bracket">,</span> <span class="string">"English (Intermediate)"</span><span class="bracket">,</span> <span class="string">"French"</span><span class="bracket">],</span></div>
                <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="key">passion</span><span class="bracket">:</span> <span class="string">"Building systems from scratch & solving complex problems"</span><span class="bracket">,</span></div>
                <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="key">contact</span><span class="bracket">:</span> <span class="string">"oussamaelboukhari11@gmail.com"</span></div>
                <div class="code-line"><span class="bracket">};</span></div>
            </div>
            
            <h3 style="margin: 2rem 0 1rem 0; color: #58A6FF;">🎓 Background</h3>
            <p style="line-height: 1.8; font-size: 1.1rem;">
                Recent graduate from <strong>1337 School</strong> (part of the prestigious <strong>42 Network</strong>) with a strong foundation in system programming and web development. I'm passionate about creating efficient, scalable solutions and love tackling challenging problems from the ground up.
            </p>
        </div>
        
        <!-- Tech Stack Section -->
        <div class="tech-stack">
            <h2 class="section-title">🛠️ Tech Stack</h2>
            
            <div class="tech-category">
                <h3>💻 Programming Languages</h3>
                <div class="tech-badges">
                    <div class="tech-badge">C</div>
                    <div class="tech-badge">C++</div>
                    <div class="tech-badge">JavaScript</div>
                </div>
            </div>
            
            <div class="tech-category">
                <h3>🌐 Web Technologies</h3>
                <div class="tech-badges">
                    <div class="tech-badge">HTML5</div>
                    <div class="tech-badge">CSS3</div>
                    <div class="tech-badge">React</div>
                    <div class="tech-badge">Django</div>
                </div>
            </div>
            
            <div class="tech-category">
                <h3>🔧 Tools & Systems</h3>
                <div class="tech-badges">
                    <div class="tech-badge">Docker</div>
                    <div class="tech-badge">Git</div>
                    <div class="tech-badge">Linux</div>
                    <div class="tech-badge">NGINX</div>
                </div>
            </div>
        </div>
        
        <!-- Stats Section -->
        <div class="stats-section">
            <h2 class="section-title">📊 GitHub Stats</h2>
            <div class="stats-container">
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=oelboukh&show_icons=true&theme=github_dark&include_all_commits=true&count_private=true&border_color=58A6FF" alt="GitHub Stats" style="max-width: 100%; height: auto; border-radius: 10px;">
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=oelboukh&layout=compact&theme=github_dark&border_color=58A6FF" alt="Top Languages" style="max-width: 100%; height: auto; border-radius: 10px;">
                </div>
            </div>
        </div>
        
        <!-- What I'm About Section -->
        <div class="about-section">
            <h2 class="section-title">💡 What I'm About</h2>
            <div class="about-list">
                <div class="about-item">
                    <h4>🔭 System Programming</h4>
                    <p>Love working with low-level systems and understanding how things work under the hood</p>
                </div>
                <div class="about-item">
                    <h4>🌱 Continuous Learning</h4>
                    <p>Always exploring new technologies and improving my skills</p>
                </div>
                <div class="about-item">
                    <h4>👥 Collaboration</h4>
                    <p>Experienced in peer learning and team-based development through 42's methodology</p>
                </div>
                <div class="about-item">
                    <h4>🧩 Problem Solving</h4>
                    <p>Enjoy breaking down complex problems into manageable solutions</p>
                </div>
                <div class="about-item">
                    <h4>🚀 Building from Scratch</h4>
                    <p>Passionate about creating systems and applications from the ground up</p>
                </div>
            </div>
        </div>
        
        <!-- Connect Section -->
        <div class="connect-section">
            <h2 class="section-title">📫 Let's Connect</h2>
            <div class="social-links">
                <a href="mailto:oussamaelboukhari11@gmail.com" class="social-link">
                    📧 Email
                </a>
                <a href="https://linkedin.com/in/oussama-elboukhari" class="social-link">
                    💼 LinkedIn
                </a>
                <a href="https://your-portfolio.com" class="social-link">
                    🌐 Portfolio
                </a>
            </div>
            
            <div class="quote">
                <em>"Code is like humor. When you have to explain it, it's bad."</em> - Cory House
            </div>
            
            <div class="footer-gifs">
                <img src="https://media.giphy.com/media/LnQjpWaON8nhr21vNW/giphy.gif" alt="Hello" class="footer-gif">
                <span style="font-size: 1.5rem; font-weight: 600;">Thanks for visiting!</span>
                <img src="https://media.giphy.com/media/7j2hfyeVcDtf2/giphy.gif" alt="Cat typing" class="footer-gif">
            </div>
        </div>
    </div>
    
    <script>
        // Typing Animation
        const phrases = [
            "Software Developer",
            "1337 School Graduate", 
            "System Programming Enthusiast",
            "Always Learning 🚀"
        ];
        
        let currentPhrase = 0;
        let currentChar = 0;
        let isDeleting = false;
        
        function typeAnimation() {
            const typingElement = document.getElementById('typing');
            const currentText = phrases[currentPhrase];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, currentChar - 1);
                currentChar--;
            } else {
                typingElement.textContent = currentText.substring(0, currentChar + 1);
                currentChar++;
            }
            
            let typeSpeed = isDeleting ? 50 : 100;
            
            if (!isDeleting && currentChar === currentText.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && currentChar === 0) {
                isDeleting = false;
                currentPhrase = (currentPhrase + 1) % phrases.length;
                typeSpeed = 500;
            }
            
            setTimeout(typeAnimation, typeSpeed);
        }
        
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particlesContainer.appendChild(particle);
            }
        }
        
        // Animate view counter
        function animateCounter() {
            const counter = document.getElementById('viewCount');
            let count = 0;
            const target = 1337;
            const increment = target / 100;
            
            const timer = setInterval(() => {
                count += increment;
                counter.textContent = Math.floor(count);
                
                if (count >= target) {
                    counter.textContent = target;
                    clearInterval(timer);
                }
            }, 30);
        }
        
        // Initialize animations
        window.addEventListener('load', () => {
            typeAnimation();
            createParticles();
            animateCounter();
        });
        
        // Add scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);
        
        // Observe all sections for scroll animations
        document.addEventListener('DOMContentLoaded', () => {
            const sections = document.querySelectorAll('.about-section, .tech-stack, .stats-section, .connect-section');
            sections.forEach(section => {
                section.style.opacity = '0';
                section.style.transform = 'translateY(30px)';
                section.style.transition = 'all 0.6s ease';
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
