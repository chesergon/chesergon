<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Lyne Chesergon · Data Scientist & Full Stack Engineer</title>
    <!-- Google Fonts: Fira Code + Poppins for cuteness & readability -->
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 (free icons) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #0a0a1a 0%, #0d0b1a 100%);
            font-family: 'Poppins', 'Fira Code', monospace, sans-serif;
            color: #f0f0ff;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 2rem 1.5rem;
        }

        /* main card container — fancy glassmorphism + cute rounded edges */
        .readme-card {
            max-width: 1100px;
            width: 100%;
            background: rgba(10, 10, 25, 0.65);
            backdrop-filter: blur(12px);
            border-radius: 3rem;
            border: 1px solid rgba(162, 136, 245, 0.35);
            box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.6), 0 0 0 1px rgba(110, 64, 201, 0.2) inset;
            padding: 2rem 2rem 2.5rem;
            transition: all 0.2s ease;
        }

        /* header wave area (capsule render simulation) */
        .capsule-header {
            position: relative;
            text-align: center;
            margin-bottom: 2rem;
        }
        .wave-bg {
            position: absolute;
            top: -2rem;
            left: -2rem;
            right: -2rem;
            height: 200px;
            background: linear-gradient(90deg, #000000, #2a1b5e, #6e40c9);
            opacity: 0.2;
            filter: blur(60px);
            z-index: 0;
            border-radius: 100%;
            pointer-events: none;
        }
        .header-title {
            position: relative;
            z-index: 2;
        }
        .glow-name {
            font-size: 4.2rem;
            font-weight: 800;
            background: linear-gradient(135deg, #ffffff, #c3abff, #a288f5);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            text-shadow: 0 2px 10px rgba(110, 64, 201, 0.3);
            letter-spacing: -0.02em;
        }
        .sub-badge {
            font-size: 1.2rem;
            font-weight: 400;
            letter-spacing: 1px;
            color: #cdc5ff;
            background: rgba(110, 64, 201, 0.25);
            display: inline-block;
            padding: 0.3rem 1.2rem;
            border-radius: 60px;
            backdrop-filter: blur(4px);
            margin-top: 0.5rem;
        }
        .desc-line {
            font-size: 1rem;
            color: #a288f5;
            margin-top: 0.6rem;
            font-family: 'Fira Code', monospace;
        }

        /* typing SVG simulation (fancy static but animated style) */
        .typing-area {
            text-align: center;
            margin: 1.8rem 0 1rem;
        }
        .typing-text {
            font-family: 'Fira Code', monospace;
            font-size: 1.3rem;
            font-weight: 500;
            background: linear-gradient(120deg, #b49aff, #d9c8ff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            display: inline-block;
            border-right: 3px solid #a288f5;
            white-space: nowrap;
            overflow: hidden;
            animation: blinkCursor 0.75s step-end infinite, typingFlow 8s steps(40) infinite;
            width: fit-content;
            max-width: 100%;
        }
        @keyframes blinkCursor {
            0%, 100% { border-color: #a288f5; }
            50% { border-color: transparent; }
        }
        @keyframes typingFlow {
            0% { width: 0; }
            25% { width: 100%; }
            80% { width: 100%; }
            100% { width: 0; }
        }

        /* two column layout: who am i left + stats right (responsive) */
        .two-columns {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            margin: 2.2rem 0 2rem;
        }
        .bio-box {
            flex: 1.5;
            background: rgba(0, 0, 0, 0.35);
            border-radius: 2rem;
            padding: 1.5rem 1.8rem;
            border: 1px solid rgba(110, 64, 201, 0.5);
            backdrop-filter: blur(4px);
            transition: 0.2s;
        }
        .stats-box {
            flex: 1;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 2rem;
            padding: 1rem;
            text-align: center;
            border: 1px solid rgba(162, 136, 245, 0.4);
        }
        .greeting-icon {
            font-size: 2rem;
            margin-right: 0.5rem;
            vertical-align: middle;
        }
        .bio-box h2 {
            font-size: 1.8rem;
            font-weight: 600;
            background: linear-gradient(130deg, #fff, #c8b6ff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .bio-text {
            font-size: 1.05rem;
            line-height: 1.55;
            margin-bottom: 1.2rem;
            color: #e9e6ff;
        }
        .highlight-quote {
            font-family: 'Fira Code', monospace;
            background: rgba(110, 64, 201, 0.2);
            border-left: 4px solid #a288f5;
            padding: 0.8rem 1.2rem;
            border-radius: 1rem;
            font-style: italic;
            font-weight: 500;
            margin-top: 1rem;
        }

        .stats-box img {
            max-width: 100%;
            border-radius: 1.2rem;
            box-shadow: 0 8px 20px rgba(0,0,0,0.4);
        }
        .github-stats-placeholder {
            background: #0f0c1c;
            border-radius: 1.2rem;
            padding: 0.8rem;
        }
        .stat-metrics {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
            font-size: 0.8rem;
            font-family: monospace;
            color: #bcacff;
        }

        /* tech stacks — fancy icons */
        .stack-section {
            margin: 2.2rem 0 1.5rem;
        }
        .stack-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.6rem;
            border-bottom: 2px dashed #6e40c9;
            width: fit-content;
            padding-right: 1rem;
        }
        .badge-container {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin-bottom: 1.8rem;
        }
        .badge {
            background: rgba(20, 15, 45, 0.9);
            border-radius: 40px;
            padding: 0.5rem 1.2rem;
            font-size: 0.85rem;
            font-weight: 500;
            font-family: 'Fira Code', monospace;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            border: 1px solid rgba(162, 136, 245, 0.5);
            transition: all 0.2s;
            backdrop-filter: blur(2px);
        }
        .badge i, .badge img {
            font-size: 1.1rem;
            color: #a288f5;
        }
        .badge:hover {
            transform: translateY(-2px);
            border-color: #a288f5;
            background: rgba(110, 64, 201, 0.25);
            box-shadow: 0 5px 12px rgba(110,64,201,0.2);
        }

        /* cute data science extra flair */
        .data-fun {
            background: linear-gradient(115deg, #0c0922, #110e2a);
            border-radius: 1.8rem;
            padding: 1rem 1.6rem;
            margin: 1.2rem 0 1rem;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            border: 1px solid #6e40c970;
        }
        .data-quote {
            font-size: 0.9rem;
            font-weight: 400;
            color: #cfc4ff;
        }
        .data-quote i {
            margin-right: 8px;
            color: #ffb86c;
        }
        .sparkle {
            font-size: 1.3rem;
            filter: drop-shadow(0 0 4px #a288f5);
        }

        hr {
            border: none;
            height: 1px;
            background: linear-gradient(90deg, transparent, #6e40c9, #a288f5, transparent);
            margin: 1rem 0;
        }

        footer {
            text-align: center;
            margin-top: 2rem;
            font-size: 0.75rem;
            color: #928cd0;
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
        }

        @media (max-width: 780px) {
            .readme-card {
                padding: 1.5rem;
            }
            .glow-name {
                font-size: 2.2rem;
            }
            .typing-text {
                font-size: 0.9rem;
                white-space: normal;
                animation: none;
                border-right: none;
            }
            .badge-container {
                gap: 0.5rem;
            }
        }
        .cute-icon {
            filter: drop-shadow(0 2px 5px rgba(162,136,245,0.4));
        }
        a {
            color: inherit;
            text-decoration: none;
        }
    </style>
</head>
<body>
<div class="readme-card">
    
    <!-- Header wave + title (capsule style) -->
    <div class="capsule-header">
        <div class="wave-bg"></div>
        <div class="header-title">
            <div class="glow-name">Lyne Chesergon</div>
            <div class="sub-badge">
                <i class="fas fa-chart-line"></i> Data Scientist &nbsp;|&nbsp; <i class="fas fa-code"></i> Full Stack Engineer
            </div>
            <div class="desc-line">
                <i class="fas fa-database"></i> insights · products · impact
            </div>
        </div>
    </div>

    <!-- Typing SVG Simulation (cute animated data scientist phrase) -->
    <div class="typing-area">
        <div class="typing-text">
            🧠 Python · ML · Next.js · Vue.js · Data is the new oil — and I'm drilling ✨
        </div>
    </div>

    <!-- Two columns: about + stats (github readme style) -->
    <div class="two-columns">
        <!-- left: who am I -->
        <div class="bio-box">
            <h2>
                <span class="greeting-icon">🦄</span> Who Am I
            </h2>
            <div class="bio-text">
                I'm <strong>Lyne Chesergon</strong> — a Full Stack Engineer turned <strong class="highlight">Data Scientist</strong> from Kenya 🌍.
                <br><br>
                I don't just write code. I build products, extract insights from messy data, and turn numbers into decisions that matter.
                <br><br>
                Currently deep in the world of <strong>Machine Learning</strong> and <strong>Statistical Analysis</strong> while carrying years of full stack experience.
            </div>
            <div class="highlight-quote">
                <i class="fas fa-chart-simple"></i> “Data is the new oil — and I'm drilling.” 
                <span style="display: inline-block; margin-left: 8px;">⛏️✨</span>
            </div>
        </div>

        <!-- right: fancy stats card like github readme stats -->
        <div class="stats-box">
            <div class="github-stats-placeholder">
                <!-- Simulated github stats card but cute + data scientist vibe -->
                <img src="https://github-readme-stats.vercel.app/api?username=chesergon&show_icons=true&theme=midnight-purple&hide_border=true&title_color=a288f5&icon_color=6e40c9&text_color=ffffff&bg_color=0d0b1a" 
                     alt="GitHub Stats" style="width:100%; border-radius: 1rem;" 
                     onerror="this.src='https://via.placeholder.com/400x180?text=Stats+:+Data+Driven+Mind'">
                <div class="stat-metrics">
                    <span><i class="fas fa-chart-line"></i> ML explorer</span>
                    <span><i class="fas fa-brain"></i> 2+ years DS</span>
                    <span><i class="fas fa-laptop-code"></i> full stack soul</span>
                </div>
            </div>
        </div>
    </div>

    <!-- The Stack — Both Worlds (Data Science + Software Engineering) -->
    <div class="stack-section">
        <div class="stack-title">
            <i class="fas fa-microchip cute-icon"></i> The Stack — Both Worlds
            <span style="font-size: 1rem;">🐍✨</span>
        </div>
        
        <!-- Data Science row -->
        <div style="margin-bottom: 1rem;">
            <span style="font-weight: 600; background: #6e40c930; padding: 0.2rem 0.8rem; border-radius: 30px; font-size: 0.85rem;"><i class="fas fa-chart-column"></i> Data Science & Analytics</span>
        </div>
        <div class="badge-container">
            <div class="badge"><i class="fab fa-python"></i> Python</div>
            <div class="badge"><i class="fas fa-table"></i> Pandas</div>
            <div class="badge"><i class="fas fa-calculator"></i> NumPy</div>
            <div class="badge"><i class="fas fa-chart-line"></i> Matplotlib</div>
            <div class="badge"><i class="fas fa-book"></i> Jupyter</div>
            <div class="badge"><i class="fas fa-robot"></i> Scikit-Learn</div>
            <div class="badge"><i class="fas fa-chart-scatter"></i> Seaborn</div>
            <div class="badge"><i class="fas fa-database"></i> SQL · Statsmodels</div>
        </div>

        <!-- Software Engineering row -->
        <div style="margin-bottom: 1rem; margin-top: 0.5rem;">
            <span style="font-weight: 600; background: #6e40c930; padding: 0.2rem 0.8rem; border-radius: 30px; font-size: 0.85rem;"><i class="fas fa-code"></i> Software Engineering & Full Stack</span>
        </div>
        <div class="badge-container">
            <div class="badge"><i class="fab fa-js"></i> JavaScript</div>
            <div class="badge"><i class="fab fa-typescript"></i> TypeScript</div>
            <div class="badge"><i class="fab fa-react"></i> Next.js</div>
            <div class="badge"><i class="fab fa-vuejs"></i> Vue.js</div>
            <div class="badge"><i class="fas fa-server"></i> Node.js</div>
            <div class="badge"><i class="fas fa-cloud"></i> FastAPI · Flask</div>
            <div class="badge"><i class="fas fa-database"></i> PostgreSQL · MongoDB</div>
            <div class="badge"><i class="fab fa-git-alt"></i> Git · Docker</div>
        </div>
    </div>

    <!-- cute extra: Data scientist in action + drilling oil animation fun -->
    <div class="data-fun">
        <div class="data-quote">
            <i class="fas fa-chalkboard-user"></i> currently building: <strong>ML-driven analytics dashboards</strong> + realtime inference engines
        </div>
        <div class="sparkle">
            🧪🔮📊
        </div>
    </div>

    <!-- Additional mini stats and cute footprints -->
    <hr>
    <div style="display: flex; justify-content: space-between; flex-wrap: wrap; gap: 1rem; margin: 0.5rem 0 0.5rem;">
        <div><i class="fas fa-chart-pie"></i> <strong>Model playground:</strong> regression, classification, clustering</div>
        <div><i class="fas fa-mug-hot"></i> <strong>toolkit:</strong> Pandas, scikit-learn, TensorFlow (beginner✨)</div>
        <div><i class="fas fa-heart" style="color:#ff88b5;"></i> <strong>cute corner:</strong> data storytelling + visualizations</div>
    </div>
    
    <!-- Fancy footer with contact / social mockup (github style) -->
    <footer>
        <span><i class="fab fa-github"></i> github.com/chesergon</span>
        <span><i class="fas fa-envelope"></i> lyne.data@drillinsights.com</span>
        <span><i class="fab fa-linkedin"></i> Lyne Chesergon</span>
        <span><i class="fas fa-chart-simple"></i> #DataDriller</span>
    </footer>

    <!-- tiny badge: "made with data & cuteness" -->
    <div style="text-align: center; margin-top: 1.2rem; font-size: 0.7rem; opacity: 0.7;">
        ✨  pandas · matplotlib · next.js · love for insights  ✨
    </div>
</div>

<!-- tiny script to simulate typewriter effect sync (just for cuteness) optional but keeps vibe -->
<script>
    (function() {
        // just to ensure the typing animation works well on resize? no big deal
        // but we add a small effect for hover on badges
        const badges = document.querySelectorAll('.badge');
        badges.forEach(b => {
            b.addEventListener('mouseenter', () => {
                b.style.transform = 'translateY(-3px)';
            });
            b.addEventListener('mouseleave', () => {
                b.style.transform = 'translateY(0px)';
            });
        });
        // set dynamic typing text for smaller screens? but the css works
        const typingDiv = document.querySelector('.typing-text');
        if(window.innerWidth < 600) {
            typingDiv.style.whiteSpace = 'normal';
            typingDiv.style.animation = 'none';
            typingDiv.style.borderRight = 'none';
        }
    })();
</script>
</body>
</html>
