<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lakshita Pandey | Full-Stack Engineer</title>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=Orbitron:wght@700;900&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-primary: #0d1117;
      --bg-secondary: #161b22;
      --bg-card: #21262d;
      --gold: #FFD700;
      --gold-dim: #b8860b;
      --cyan: #61DAFB;
      --purple: #a855f7;
      --green: #3ECF8E;
      --text-primary: #f0f6fc;
      --text-secondary: #8b949e;
      --gradient-gold: linear-gradient(135deg, #FFD700, #FFA500, #FF6347);
      --gradient-cyber: linear-gradient(135deg, #00d4ff, #a855f7, #ff006e);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'JetBrains Mono', monospace;
      background: var(--bg-primary);
      color: var(--text-primary);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Animated Background */
    .bg-animation {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      background: 
        radial-gradient(ellipse at 20% 20%, rgba(255, 215, 0, 0.08) 0%, transparent 50%),
        radial-gradient(ellipse at 80% 80%, rgba(168, 85, 247, 0.08) 0%, transparent 50%),
        radial-gradient(ellipse at 50% 50%, rgba(97, 218, 251, 0.05) 0%, transparent 70%);
    }

    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      overflow: hidden;
    }

    .particle {
      position: absolute;
      width: 4px;
      height: 4px;
      background: var(--gold);
      border-radius: 50%;
      animation: float 15s infinite;
      opacity: 0.3;
    }

    @keyframes float {
      0%, 100% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
      10% { opacity: 0.3; }
      90% { opacity: 0.3; }
      100% { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px;
    }

    /* Header Section */
    .header {
      text-align: center;
      padding: 60px 20px;
      position: relative;
    }

    .header-wave {
      width: 100%;
      height: 200px;
      background: var(--gradient-gold);
      clip-path: polygon(0 0, 100% 0, 100% 70%, 50% 100%, 0 70%);
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 40px;
      position: relative;
      overflow: hidden;
    }

    .header-wave::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 200%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
      animation: shimmer 3s infinite;
    }

    @keyframes shimmer {
      0% { left: -100%; }
      100% { left: 100%; }
    }

    .header-title {
      font-family: 'Orbitron', sans-serif;
      font-size: clamp(2rem, 6vw, 4rem);
      font-weight: 900;
      color: #000;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .lightning {
      font-size: 1.2em;
      animation: pulse 1.5s infinite;
    }

    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.2); }
    }

    .subtitle {
      font-size: clamp(1rem, 3vw, 1.5rem);
      color: var(--gold);
      margin-top: 20px;
      text-shadow: 0 0 20px rgba(255, 215, 0, 0.5);
    }

    .typing-text {
      font-size: 1.1rem;
      color: var(--cyan);
      margin-top: 30px;
      padding: 15px 30px;
      background: var(--bg-card);
      border-radius: 50px;
      display: inline-block;
      border: 1px solid rgba(97, 218, 251, 0.3);
      position: relative;
      overflow: hidden;
    }

    .typing-text::after {
      content: '|';
      animation: blink 1s infinite;
    }

    @keyframes blink {
      0%, 50% { opacity: 1; }
      51%, 100% { opacity: 0; }
    }

    /* Section Styles */
    .section {
      margin: 60px 0;
      padding: 40px;
      background: var(--bg-secondary);
      border-radius: 20px;
      border: 1px solid rgba(255, 215, 0, 0.1);
      position: relative;
      overflow: hidden;
    }

    .section::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 3px;
      background: var(--gradient-gold);
    }

    .section-title {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.8rem;
      color: var(--gold);
      margin-bottom: 30px;
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .section-title span {
      font-size: 1.5em;
    }

    /* About Section */
    .about-content {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
    }

    @media (max-width: 768px) {
      .about-content {
        grid-template-columns: 1fr;
      }
    }

    .about-text p {
      color: var(--text-secondary);
      margin-bottom: 15px;
      font-size: 1rem;
    }

    .highlight {
      color: var(--gold);
      font-weight: 600;
    }

    .focus-list {
      list-style: none;
      margin-top: 20px;
    }

    .focus-list li {
      padding: 10px 0;
      display: flex;
      align-items: center;
      gap: 10px;
      color: var(--text-secondary);
      transition: transform 0.3s, color 0.3s;
    }

    .focus-list li:hover {
      transform: translateX(10px);
      color: var(--cyan);
    }

    .focus-list li span {
      font-size: 1.2em;
    }

    .quote {
      margin-top: 30px;
      padding: 20px;
      background: var(--bg-card);
      border-left: 4px solid var(--gold);
      border-radius: 0 10px 10px 0;
      font-style: italic;
      color: var(--text-secondary);
    }

    /* Tech Stack */
    .tech-category {
      margin-bottom: 30px;
    }

    .tech-category-title {
      font-size: 1.2rem;
      color: var(--text-primary);
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .tech-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .badge {
      padding: 10px 20px;
      background: var(--bg-card);
      border-radius: 8px;
      font-size: 0.9rem;
      color: var(--text-primary);
      border: 1px solid rgba(255, 255, 255, 0.1);
      transition: all 0.3s;
      cursor: pointer;
      position: relative;
      overflow: hidden;
    }

    .badge::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
      transition: left 0.5s;
    }

    .badge:hover::before {
      left: 100%;
    }

    .badge:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 30px rgba(255, 215, 0, 0.2);
      border-color: var(--gold);
    }

    .badge.js { border-left: 3px solid #F7DF1E; }
    .badge.java { border-left: 3px solid #007396; }
    .badge.cpp { border-left: 3px solid #00599C; }
    .badge.go { border-left: 3px solid #00ADD8; }
    .badge.react { border-left: 3px solid #61DAFB; }
    .badge.vue { border-left: 3px solid #4FC08D; }
    .badge.tailwind { border-left: 3px solid #38B2AC; }
    .badge.aws { border-left: 3px solid #FF9900; }
    .badge.azure { border-left: 3px solid #0072C6; }
    .badge.python { border-left: 3px solid #3776AB; }

    /* GitHub Stats Section */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
      margin-top: 30px;
    }

    .stat-card {
      background: var(--bg-card);
      border-radius: 15px;
      padding: 25px;
      text-align: center;
      border: 1px solid rgba(255, 215, 0, 0.1);
      transition: all 0.3s;
    }

    .stat-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 20px 40px rgba(255, 215, 0, 0.15);
      border-color: var(--gold);
    }

    .stat-card img {
      width: 100%;
      height: auto;
      border-radius: 10px;
    }

    /* Trophies Section */
    .trophies-container {
      text-align: center;
      padding: 20px;
      background: var(--bg-card);
      border-radius: 15px;
      overflow-x: auto;
    }

    .trophies-container img {
      max-width: 100%;
      height: auto;
    }

    /* Connect Section */
    .connect-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
    }

    .connect-card {
      display: flex;
      align-items: center;
      gap: 15px;
      padding: 20px;
      background: var(--bg-card);
      border-radius: 12px;
      text-decoration: none;
      color: var(--text-primary);
      border: 1px solid rgba(255, 255, 255, 0.1);
      transition: all 0.3s;
    }

    .connect-card:hover {
      transform: translateX(10px);
      border-color: var(--gold);
      box-shadow: 0 10px 30px rgba(255, 215, 0, 0.15);
    }

    .connect-icon {
      width: 50px;
      height: 50px;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5rem;
    }

    .connect-icon.email { background: linear-gradient(135deg, #EA4335, #FBBC04); }
    .connect-icon.portfolio { background: linear-gradient(135deg, #000, #333); }
    .connect-icon.linkedin { background: linear-gradient(135deg, #0A66C2, #00a0dc); }
    .connect-icon.leetcode { background: linear-gradient(135deg, #FFA116, #FFD700); }

    .connect-info h4 {
      font-size: 1rem;
      margin-bottom: 5px;
    }

    .connect-info p {
      font-size: 0.85rem;
      color: var(--text-secondary);
    }

    /* Visitor Counter */
    .visitor-section {
      text-align: center;
      padding: 40px;
    }

    .visitor-badge {
      display: inline-flex;
      align-items: center;
      gap: 15px;
      padding: 15px 30px;
      background: var(--bg-card);
      border-radius: 50px;
      border: 2px solid var(--gold);
    }

    .visitor-badge span {
      font-size: 1.2rem;
    }

    /* Footer */
    .footer {
      text-align: center;
      padding: 40px;
      background: linear-gradient(to bottom, transparent, var(--bg-secondary));
    }

    .footer-wave {
      width: 100%;
      height: 100px;
      background: var(--gradient-cyber);
      clip-path: polygon(0 30%, 50% 0, 100% 30%, 100% 100%, 0 100%);
    }

    /* Glowing Effects */
    .glow {
      animation: glow 2s ease-in-out infinite alternate;
    }

    @keyframes glow {
      from { text-shadow: 0 0 5px var(--gold), 0 0 10px var(--gold); }
      to { text-shadow: 0 0 20px var(--gold), 0 0 30px var(--gold-dim); }
    }

    /* Scrollbar */
    ::-webkit-scrollbar {
      width: 10px;
    }

    ::-webkit-scrollbar-track {
      background: var(--bg-primary);
    }

    ::-webkit-scrollbar-thumb {
      background: var(--gradient-gold);
      border-radius: 5px;
    }

    /* Loading Animation */
    .loading-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: var(--bg-primary);
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 9999;
      transition: opacity 0.5s, visibility 0.5s;
    }

    .loading-overlay.hidden {
      opacity: 0;
      visibility: hidden;
    }

    .loader {
      width: 60px;
      height: 60px;
      border: 4px solid transparent;
      border-top-color: var(--gold);
      border-radius: 50%;
      animation: spin 1s linear infinite;
    }

    @keyframes spin {
      to { transform: rotate(360deg); }
    }
  </style>
</head>
<body>
  <!-- Loading Overlay -->
  <div class="loading-overlay" id="loader">
    <div class="loader"></div>
  </div>

  <!-- Background Animation -->
  <div class="bg-animation"></div>
  <div class="particles" id="particles"></div>

  <div class="container">
    <!-- Header -->
    <header class="header">
      <div class="header-wave">
        <h1 class="header-title">
          <span class="lightning">⚡</span>
          LAKSHITA PANDEY
          <span class="lightning">⚡</span>
        </h1>
      </div>
      <p class="subtitle">🚀 Full-Stack Engineer | ⚛️ React & MERN Stack Specialist | 🧠 DSA Grandmaster | ☁️ Cloud Pioneer</p>
      <div class="typing-text">
        Building High-Performance Web Applications with Elegance & Scale
      </div>
    </header>

    <!-- About Section -->
    <section class="section">
      <h2 class="section-title"><span>🧑‍💻</span> About Me</h2>
      <div class="about-content">
        <div class="about-text">
          <p>💡 I'm <span class="highlight">Lakshita Pandey</span>, a passionate <span class="highlight">Full-Stack Web Developer</span> committed to building <span class="highlight">clean, efficient, and scalable web products</span>. I thrive on challenges and continuous improvement.</p>
          <p>My philosophy revolves around:</p>
          <ul class="focus-list">
            <li><span>🎯</span> <strong>Scalability:</strong> Designing systems that can grow with demand</li>
            <li><span>✨</span> <strong>Maintainability:</strong> Writing high-quality, readable, and efficient code</li>
            <li><span>🔧</span> <strong>Systematic Approach:</strong> Deeply understanding the how and why</li>
          </ul>
        </div>
        <div class="about-focus">
          <h3 style="color: var(--gold); margin-bottom: 20px;">🔥 Current Focus</h3>
          <ul class="focus-list">
            <li><span>🧠</span> Deep diving into Data Structures & Algorithms</li>
            <li><span>⚛️</span> Developing high-performance React & MERN apps</li>
            <li><span>☁️</span> Exploring Cloud Infrastructure (AWS/Azure)</li>
            <li><span>🐍</span> Expanding with Go and Python frameworks</li>
          </ul>
          <div class="quote">
            💬 "The only way to do great work is to love what you do."
          </div>
        </div>
      </div>
    </section>

    <!-- Tech Stack Section -->
    <section class="section">
      <h2 class="section-title"><span>🛠️</span> Tech Arsenal</h2>
      
      <div class="tech-category">
        <h3 class="tech-category-title">🌐 Languages & Core Development</h3>
        <div class="tech-badges">
          <div class="badge js">⚡ JavaScript</div>
          <div class="badge java">☕ Java</div>
          <div class="badge cpp">🔷 C++</div>
          <div class="badge go">🐹 Go</div>
          <div class="badge">🎯 Dart</div>
          <div class="badge python">🐍 Python</div>
        </div>
      </div>

      <div class="tech-category">
        <h3 class="tech-category-title">⚛️ Frontend & UI/UX</h3>
        <div class="tech-badges">
          <div class="badge react">⚛️ React</div>
          <div class="badge vue">💚 Vue.js</div>
          <div class="badge tailwind">🎨 TailwindCSS</div>
          <div class="badge">🎲 Three.js</div>
          <div class="badge">🎨 Figma</div>
        </div>
      </div>

      <div class="tech-category">
        <h3 class="tech-category-title">⚙️ Backend & Frameworks</h3>
        <div class="tech-badges">
          <div class="badge">🚂 Express.js</div>
          <div class="badge">🐍 Django</div>
          <div class="badge">⚡ FastAPI</div>
          <div class="badge">📊 GraphQL</div>
          <div class="badge">🔌 Socket.io</div>
        </div>
      </div>

      <div class="tech-category">
        <h3 class="tech-category-title">☁️ Cloud, DevOps & Database</h3>
        <div class="tech-badges">
          <div class="badge aws">☁️ AWS</div>
          <div class="badge azure">🔷 Azure</div>
          <div class="badge">🔧 Jenkins</div>
          <div class="badge">🌐 Nginx</div>
          <div class="badge">🐬 MySQL</div>
          <div class="badge">💚 Supabase</div>
          <div class="badge">🍃 MongoDB</div>
        </div>
      </div>
    </section>

    <!-- GitHub Trophies Section -->
    <section class="section">
      <h2 class="section-title"><span>🏆</span> GitHub Trophies</h2>
      <div class="trophies-container">
        <img src="https://github-profile-trophy.vercel.app/?username=lakshitapandey&theme=onestar&no-frame=true&column=7&margin-w=15&margin-h=15" alt="GitHub Trophies" onerror="this.src='https://via.placeholder.com/800x150/21262d/FFD700?text=🏆+GitHub+Trophies+Loading...'"/>
      </div>
    </section>

    <!-- GitHub Analytics Section -->
    <section class="section">
      <h2 class="section-title"><span>📊</span> GitHub Analytics</h2>
      <div class="stats-grid">
        <div class="stat-card">
          <img src="https://github-readme-stats.vercel.app/api?username=lakshitapandey&show_icons=true&theme=github_dark&hide_border=true&bg_color=21262d&title_color=FFD700&icon_color=61DAFB&text_color=f0f6fc" alt="GitHub Stats" onerror="this.src='https://via.placeholder.com/400x200/21262d/FFD700?text=📊+Stats+Loading...'"/>
        </div>
        <div class="stat-card">
          <img src="https://github-readme-streak-stats.herokuapp.com/?user=lakshitapandey&theme=github-dark-blue&hide_border=true&background=21262d&ring=FFD700&fire=FF6347&currStreakLabel=61DAFB" alt="GitHub Streak" onerror="this.src='https://via.placeholder.com/400x200/21262d/FFD700?text=🔥+Streak+Loading...'"/>
        </div>
        <div class="stat-card">
          <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=lakshitapandey&layout=compact&theme=github_dark&hide_border=true&bg_color=21262d&title_color=FFD700&text_color=f0f6fc" alt="Top Languages" onerror="this.src='https://via.placeholder.com/400x200/21262d/FFD700?text=💻+Languages+Loading...'"/>
        </div>
        <div class="stat-card">
          <img src="https://github-readme-activity-graph.vercel.app/graph?username=lakshitapandey&theme=github-dark&hide_border=true&bg_color=21262d&color=FFD700&line=61DAFB&point=FF6347" alt="Activity Graph" onerror="this.src='https://via.placeholder.com/400x200/21262d/FFD700?text=📈+Activity+Loading...'"/>
        </div>
      </div>
    </section>

    <!-- Connect Section -->
    <section class="section">
      <h2 class="section-title"><span>🌍</span> Connect With Me</h2>
      <div class="connect-grid">
        <a href="mailto:lakshitapandey18@gmail.com" class="connect-card">
          <div class="connect-icon email">📧</div>
          <div class="connect-info">
            <h4>Email</h4>
            <p>lakshitapandey18@gmail.com</p>
          </div>
        </a>
        <a href="https://your-portfolio-link.com" class="connect-card" target="_blank">
          <div class="connect-icon portfolio">🌐</div>
          <div class="connect-info">
            <h4>Portfolio</h4>
            <p>View My Work</p>
          </div>
        </a>
        <a href="https://www.linkedin.com/in/your-linkedin-profile" class="connect-card" target="_blank">
          <div class="connect-icon linkedin">💼</div>
          <div class="connect-info">
            <h4>LinkedIn</h4>
            <p>Let's Connect</p>
          </div>
        </a>
        <a href="https://leetcode.com/u/Amaan_Khan1/" class="connect-card" target="_blank">
          <div class="connect-icon leetcode">🧩</div>
          <div class="connect-info">
            <h4>LeetCode</h4>
            <p>Problem Solving</p>
          </div>
        </a>
      </div>
    </section>

    <!-- Visitor Counter -->
    <div class="visitor-section">
      <div class="visitor-badge">
        <span>👀</span>
        <strong>Profile Views:</strong>
        <img src="https://komarev.com/ghpvc/?username=lakshitapandey&style=flat-square&color=FFD700" alt="Profile Views" />
      </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
      <div class="footer-wave"></div>
      <p style="margin-top: 20px; color: var(--text-secondary);">
        Built with 💛 by Lakshita Pandey | © 2026
      </p>
    </footer>
  </div>

  <script>
    // Hide loader after page loads
    window.addEventListener('load', () => {
      setTimeout(() => {
        document.getElementById('loader').classList.add('hidden');
      }, 800);
    });

    // Create floating particles
    const particlesContainer = document.getElementById('particles');
    for (let i = 0; i < 30; i++) {
      const particle = document.createElement('div');
      particle.className = 'particle';
      particle.style.left = Math.random() * 100 + '%';
      particle.style.animationDelay = Math.random() * 15 + 's';
      particle.style.animationDuration = (10 + Math.random() * 20) + 's';
      particlesContainer.appendChild(particle);
    }

    // Typing effect
    const typingTexts = [
      'Building High-Performance Web Applications',
      'Engineering Solutions with System Design',
      'MERN Stack | Go | AWS/Azure',
      'The Goal: Elegance, Efficiency, Scale.'
    ];
    let textIndex = 0;
    let charIndex = 0;
    let isDeleting = false;
    const typingElement = document.querySelector('.typing-text');

    function typeEffect() {
      const currentText = typingTexts[textIndex];
      
      if (isDeleting) {
        typingElement.textContent = currentText.substring(0, charIndex - 1);
        charIndex--;
      } else {
        typingElement.textContent = currentText.substring(0, charIndex + 1);
        charIndex++;
      }

      let typeSpeed = isDeleting ? 30 : 80;

      if (!isDeleting && charIndex === currentText.length) {
        typeSpeed = 2000;
        isDeleting = true;
      } else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        textIndex = (textIndex + 1) % typingTexts.length;
        typeSpeed = 500;
      }

      setTimeout(typeEffect, typeSpeed);
    }

    setTimeout(typeEffect, 1000);

    // Badge hover effects with sound (optional)
    document.querySelectorAll('.badge').forEach(badge => {
      badge.addEventListener('mouseenter', () => {
        badge.style.transform = 'translateY(-5px) scale(1.05)';
      });
      badge.addEventListener('mouseleave', () => {
        badge.style.transform = 'translateY(0) scale(1)';
      });
    });
  </script>
</body>
</html>
