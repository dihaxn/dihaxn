<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cosmic Developer | dihaxn</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --cosmic-primary: #0a0a1a;
            --cosmic-secondary: #001220;
            --neon-blue: #00d9ff;
            --neon-purple: #b967ff;
            --text-light: #ffffff;
            --text-dim: #a0aec0;
            --transition-speed: 0.4s;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, var(--cosmic-primary), var(--cosmic-secondary));
            color: var(--text-light);
            min-height: 100vh;
            overflow-x: hidden;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        /* Header Animation */
        .header {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            margin-bottom: 40px;
            box-shadow: 0 10px 30px rgba(0, 217, 255, 0.1);
            animation: cosmicPulse 6s infinite alternate;
        }

        .header-content {
            padding: 50px 20px;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .header h1 {
            font-size: 3rem;
            margin-bottom: 15px;
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            transition: all var(--transition-speed);
        }

        .header p {
            font-size: 1.3rem;
            color: var(--text-dim);
            max-width: 800px;
            margin: 0 auto;
            transition: all var(--transition-speed);
        }

        .stars {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle var(--duration, 3s) infinite var(--delay, 0s);
            opacity: 0;
        }

        /* Profile Intro */
        .profile-intro {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
            margin-bottom: 40px;
            text-align: center;
        }

        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 3px solid var(--neon-blue);
            box-shadow: 0 0 30px rgba(0, 217, 255, 0.5);
            overflow: hidden;
            transition: all var(--transition-speed);
            position: relative;
        }

        .avatar:hover {
            transform: scale(1.05);
            box-shadow: 0 0 50px rgba(0, 217, 255, 0.8);
        }

        .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .typing-container {
            min-height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .typing-text {
            font-size: 1.8rem;
            font-weight: bold;
            text-align: center;
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            transition: all var(--transition-speed);
        }

        /* Sections */
        .section {
            background: rgba(10, 15, 30, 0.6);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 40px;
            border: 1px solid rgba(0, 217, 255, 0.1);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            transition: all var(--transition-speed);
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 217, 255, 0.2);
            border-color: rgba(0, 217, 255, 0.3);
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 25px;
            position: relative;
            display: inline-block;
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple));
            border-radius: 2px;
        }

        /* Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: rgba(20, 25, 50, 0.5);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all var(--transition-speed);
            border: 1px solid rgba(0, 217, 255, 0.1);
        }

        .stat-card:hover {
            transform: translateY(-8px);
            background: rgba(30, 35, 60, 0.7);
            box-shadow: 0 10px 25px rgba(0, 217, 255, 0.2);
        }

        .stat-value {
            font-size: 2.5rem;
            font-weight: bold;
            margin: 10px 0;
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-label {
            color: var(--text-dim);
            font-size: 1.1rem;
        }

        /* Connect Grid */
        .connect-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 30px;
        }

        .connect-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 15px;
            border-radius: 12px;
            background: rgba(20, 25, 50, 0.5);
            color: white;
            text-decoration: none;
            font-weight: 600;
            transition: all var(--transition-speed);
            border: 1px solid rgba(0, 217, 255, 0.1);
        }

        .connect-btn:hover {
            transform: translateY(-5px);
            background: rgba(30, 35, 60, 0.7);
            box-shadow: 0 10px 25px rgba(0, 217, 255, 0.2);
        }

        .connect-btn.twitter { background: rgba(29, 161, 242, 0.15); }
        .connect-btn.linkedin { background: rgba(10, 102, 194, 0.15); }
        .connect-btn.github { background: rgba(24, 23, 23, 0.15); }
        .connect-btn.email { background: rgba(220, 53, 69, 0.15); }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .skill-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            padding: 15px;
            border-radius: 12px;
            background: rgba(20, 25, 50, 0.5);
            transition: all var(--transition-speed);
            border: 1px solid rgba(0, 217, 255, 0.1);
        }

        .skill-item:hover {
            transform: translateY(-5px) scale(1.1);
            background: rgba(30, 35, 60, 0.7);
            box-shadow: 0 10px 25px rgba(0, 217, 255, 0.2);
        }

        .skill-icon {
            font-size: 2.5rem;
            transition: all var(--transition-speed);
        }

        .skill-label {
            font-size: 0.9rem;
            text-align: center;
            color: var(--text-dim);
        }

        /* Stats Section */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stats-card {
            background: rgba(20, 25, 50, 0.5);
            border-radius: 15px;
            padding: 20px;
            transition: all var(--transition-speed);
            border: 1px solid rgba(0, 217, 255, 0.1);
        }

        .stats-card:hover {
            transform: translateY(-5px);
            background: rgba(30, 35, 60, 0.7);
            box-shadow: 0 10px 25px rgba(0, 217, 255, 0.2);
        }

        .stats-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        /* Fun Facts */
        .facts-container {
            background: rgba(20, 25, 50, 0.5);
            border-radius: 15px;
            padding: 25px;
            margin-top: 20px;
            border: 1px solid rgba(0, 217, 255, 0.1);
        }

        .fact-item {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid rgba(0, 217, 255, 0.1);
        }

        .fact-item:last-child {
            border-bottom: none;
            margin-bottom: 0;
            padding-bottom: 0;
        }

        .fact-icon {
            font-size: 1.5rem;
            min-width: 30px;
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 20px;
            color: var(--text-dim);
            font-size: 1.1rem;
        }

        .footer a {
            color: var(--neon-blue);
            text-decoration: none;
            transition: all var(--transition-speed);
        }

        .footer a:hover {
            text-decoration: underline;
            color: var(--neon-purple);
        }

        /* Animations */
        @keyframes cosmicPulse {
            0% { box-shadow: 0 0 30px rgba(0, 217, 255, 0.1); }
            100% { box-shadow: 0 0 50px rgba(183, 103, 255, 0.3); }
        }

        @keyframes twinkle {
            0% { opacity: 0; }
            50% { opacity: 1; }
            100% { opacity: 0; }
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .floating {
            animation: float 4s ease-in-out infinite;
        }

        .gradient-animation {
            background-size: 200% 200%;
            animation: gradientShift 6s ease infinite;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header h1 { font-size: 2.2rem; }
            .header p { font-size: 1.1rem; }
            .typing-text { font-size: 1.4rem; }
            .section-title { font-size: 1.8rem; }
            .stat-value { font-size: 2rem; }
        }

        @media (max-width: 480px) {
            .header h1 { font-size: 1.8rem; }
            .typing-text { font-size: 1.2rem; }
            .section-title { font-size: 1.6rem; }
            .stats-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="header-content">
                <h1>Welcome to My Universe</h1>
                <p>Where Code Meets Creativity</p>
            </div>
            <div class="stars" id="stars-container"></div>
        </div>

        <!-- Profile Intro -->
        <div class="profile-intro">
            <div class="avatar floating">
                <img src="https://github.com/7oSkaaa/7oSkaaa/blob/main/Images/about_me.gif?raw=true" alt="Profile">
            </div>
            <div class="typing-container">
                <div class="typing-text">
                    🚀 Full-Stack Developer<br>
                    🌟 Open-Source Enthusiast<br>
                    💡 Problem Solver<br>
                    🔥 Code Architect<br>
                    ✨ Digital Innovator
                </div>
            </div>
        </div>

        <!-- Profile Analytics -->
        <div class="section">
            <h2 class="section-title">🌟 Profile Analytics</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-value">15.8K</div>
                    <div class="stat-label">Cosmic Visitors</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">1.2K</div>
                    <div class="stat-label">GitHub Followers</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">320</div>
                    <div class="stat-label">GitHub Stars</div>
                </div>
            </div>
        </div>

        <!-- Connect Section -->
        <div class="section">
            <h2 class="section-title">🎯 Connect With Me</h2>
            <div class="connect-grid">
                <a href="https://twitter.com/dihaxn" class="connect-btn twitter">
                    <i class="fab fa-twitter"></i> Twitter
                </a>
                <a href="https://www.linkedin.com/in/dihanlaknuka/" class="connect-btn linkedin">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://github.com/dihaxn" class="connect-btn github">
                    <i class="fab fa-github"></i> GitHub
                </a>
                <a href="mailto:ihanlaknuka@gmail.com" class="connect-btn email">
                    <i class="fas fa-envelope"></i> Email
                </a>
            </div>
        </div>

        <!-- Tech Skills -->
        <div class="section">
            <h2 class="section-title">🛠️ Tech Arsenal & Skills</h2>
            <h3 class="subtitle">Languages</h3>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-cuttlefish skill-icon"></i>
                    <span class="skill-label">C++</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-java skill-icon"></i>
                    <span class="skill-label">Java</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-js skill-icon"></i>
                    <span class="skill-label">JavaScript</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-python skill-icon"></i>
                    <span class="skill-label">Python</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-php skill-icon"></i>
                    <span class="skill-label">PHP</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-go skill-icon"></i>
                    <span class="skill-label">Go</span>
                </div>
            </div>

            <h3 class="subtitle" style="margin-top: 30px;">Frontend Development</h3>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-react skill-icon"></i>
                    <span class="skill-label">React</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-vuejs skill-icon"></i>
                    <span class="skill-label">Vue.js</span>
                </div>
                <div class="skill-item">
                    <i class="fas fa-code skill-icon"></i>
                    <span class="skill-label">HTML5</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-css3-alt skill-icon"></i>
                    <span class="skill-label">CSS3</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-sass skill-icon"></i>
                    <span class="skill-label">Sass</span>
                </div>
            </div>
        </div>

        <!-- Stats Section -->
        <div class="section">
            <h2 class="section-title">📊 Cosmic Statistics</h2>
            <div class="stats-container">
                <div class="stats-card">
                    <div class="stats-header">
                        <h3>GitHub Stats</h3>
                        <i class="fas fa-chart-bar"></i>
                    </div>
                    <div class="stat-placeholder"></div>
                </div>
                <div class="stats-card">
                    <div class="stats-header">
                        <h3>Streak Stats</h3>
                        <i class="fas fa-fire"></i>
                    </div>
                    <div class="stat-placeholder"></div>
                </div>
            </div>
            <div class="stats-card">
                <div class="stats-header">
                    <h3>Top Languages</h3>
                    <i class="fas fa-code"></i>
                </div>
                <div class="stat-placeholder"></div>
            </div>
        </div>

        <!-- Fun Facts -->
        <div class="section">
            <h2 class="section-title">🌟 Fun Facts About Me</h2>
            <div class="facts-container">
                <div class="fact-item">
                    <div class="fact-icon">🌍</div>
                    <div class="fact-text">Based in: "The Cloud"</div>
                </div>
                <div class="fact-item">
                    <div class="fact-icon">🎯</div>
                    <div class="fact-text">Currently learning: "Everything I can get my hands on"</div>
                </div>
                <div class="fact-item">
                    <div class="fact-icon">🎨</div>
                    <div class="fact-text">Hobbies: ["Coding", "Reading", "Gaming", "Coffee Tasting"]</div>
                </div>
                <div class="fact-item">
                    <div class="fact-icon">🚀</div>
                    <div class="fact-text">2024 Goals: "Contribute to more open source projects"</div>
                </div>
                <div class="fact-item">
                    <div class="fact-icon">💬</div>
                    <div class="fact-text">Ask me about: "Web Development, Cloud Computing, or anything tech!"</div>
                </div>
                <div class="fact-item">
                    <div class="fact-icon">⚡</div>
                    <div class="fact-text">Fun fact: "I debug with console.log() and I'm not ashamed"</div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>Thanks for Visiting! Let's build something amazing together!</p>
            <p>⭐ Star some repositories if you found them interesting! ⭐</p>
        </div>
    </div>

    <script>
        // Create stars for background
        function createStars() {
            const container = document.getElementById('stars-container');
            const starCount = 150;
            
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                
                // Random position
                const posX = Math.random() * 100;
                const posY = Math.random() * 100;
                star.style.left = `${posX}%`;
                star.style.top = `${posY}%`;
                
                // Random size
                const size = Math.random() * 3 + 1;
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                
                // Random animation
                const duration = Math.random() * 5 + 3;
                const delay = Math.random() * 5;
                star.style.setProperty('--duration', `${duration}s`);
                star.style.setProperty('--delay', `${delay}s`);
                
                container.appendChild(star);
            }
        }

        // Initialize on load
        document.addEventListener('DOMContentLoaded', () => {
            createStars();
            
            // Add hover effect to all interactive elements
            const interactiveElements = document.querySelectorAll(
                '.stat-card, .connect-btn, .skill-item, .stats-card, .section'
            );
            
            interactiveElements.forEach(el => {
                el.addEventListener('mouseenter', () => {
                    el.style.transition = 'all 0.3s ease';
                });
                
                el.addEventListener('mouseleave', () => {
                    el.style.transition = 'all 0.4s ease';
                });
            });
            
            // Animated typing effect
            const typingText = document.querySelector('.typing-text');
            const lines = typingText.innerHTML.split('<br>');
            typingText.innerHTML = '';
            
            let lineIndex = 0;
            let charIndex = 0;
            let isDeleting = false;
            
            function type() {
                const currentLine = lines[lineIndex];
                
                if (isDeleting) {
                    typingText.innerHTML = currentLine.substring(0, charIndex - 1);
                    charIndex--;
                    
                    if (charIndex === 0) {
                        isDeleting = false;
                        lineIndex = (lineIndex + 1) % lines.length;
                        setTimeout(type, 500);
                        return;
                    }
                } else {
                    typingText.innerHTML = currentLine.substring(0, charIndex + 1);
                    charIndex++;
                    
                    if (charIndex === currentLine.length) {
                        isDeleting = true;
                        setTimeout(type, 2000);
                        return;
                    }
                }
                
                setTimeout(type, isDeleting ? 50 : 100);
            }
            
            setTimeout(type, 1000);
        });
    </script>
</body>
</html>
