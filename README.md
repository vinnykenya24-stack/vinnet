<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>InstantGrow Pro | Social Media Growth Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #FF6B6B;
            --secondary: #4ECDC4;
            --success: #1DD1A1;
            --warning: #F9C74F;
            --error: #FF6B6B;
            --dark: #2D3436;
            --light: #F7F9FC;
            --gray: #636E72;
        }

        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: var(--dark);
            overflow-x: hidden;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-radius: 25px;
            padding: 40px;
            margin-bottom: 40px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin-bottom: 15px;
        }

        .logo i {
            font-size: 4rem;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .logo h1 {
            font-size: 3.5rem;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 800;
        }

        .tagline {
            color: var(--gray);
            font-size: 1.4rem;
            margin-bottom: 25px;
            font-weight: 500;
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 50px;
            margin-top: 40px;
            flex-wrap: wrap;
        }

        .stat-item {
            text-align: center;
            padding: 25px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .stat-label {
            color: var(--gray);
            font-size: 1.1rem;
            font-weight: 600;
        }

        .platform-selector {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin: 50px 0;
            flex-wrap: wrap;
        }

        .platform-tab {
            padding: 25px 40px;
            border: 3px solid rgba(255, 255, 255, 0.3);
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: flex;
            align-items: center;
            gap: 20px;
            font-weight: 700;
            font-size: 1.3rem;
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
        }

        .platform-tab.active {
            transform: translateY(-15px) scale(1.05);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .platform-tab.instagram.active {
            border-color: #E1306C;
            color: #E1306C;
            background: linear-gradient(135deg, rgba(225, 48, 108, 0.1), rgba(255, 255, 255, 0.9));
        }

        .platform-tab.facebook.active {
            border-color: #1877F2;
            color: #1877F2;
            background: linear-gradient(135deg, rgba(24, 119, 242, 0.1), rgba(255, 255, 255, 0.9));
        }

        .platform-tab.tiktok.active {
            border-color: #000000;
            color: #000000;
            background: linear-gradient(135deg, rgba(0, 0, 0, 0.1), rgba(255, 255, 255, 0.9));
        }

        .platform-tab.youtube.active {
            border-color: #FF0000;
            color: #FF0000;
            background: linear-gradient(135deg, rgba(255, 0, 0, 0.1), rgba(255, 255, 255, 0.9));
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 50px;
        }

        @media (max-width: 1100px) {
            .main-content {
                grid-template-columns: 1fr;
            }
        }

        .generator-panel, .results-panel {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-radius: 25px;
            padding: 50px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .panel-header {
            margin-bottom: 40px;
        }

        .panel-header h2 {
            color: var(--dark);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 20px;
            font-size: 2.2rem;
            font-weight: 700;
        }

        .generator-form {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .form-group {
            margin-bottom: 25px;
        }

        label {
            display: block;
            margin-bottom: 15px;
            font-weight: 700;
            color: var(--dark);
            font-size: 1.2rem;
        }

        input, select {
            width: 100%;
            padding: 20px;
            border: 2px solid rgba(0, 0, 0, 0.1);
            border-radius: 15px;
            font-size: 1.2rem;
            transition: all 0.3s;
            background: rgba(255, 255, 255, 0.8);
        }

        input:focus, select:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 4px rgba(255, 107, 107, 0.1);
            transform: translateY(-2px);
        }

        .btn {
            padding: 25px 45px;
            border: none;
            border-radius: 15px;
            font-size: 1.3rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            box-shadow: 0 10px 30px rgba(255, 107, 107, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-8px) scale(1.02);
            box-shadow: 0 20px 40px rgba(255, 107, 107, 0.4);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .service-card {
            border: 3px solid rgba(0, 0, 0, 0.1);
            border-radius: 20px;
            padding: 30px;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-align: center;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
        }

        .service-card:hover, .service-card.selected {
            transform: translateY(-12px) scale(1.03);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .service-card.instagram.selected {
            border-color: #E1306C;
            background: linear-gradient(135deg, rgba(225, 48, 108, 0.1), rgba(255, 255, 255, 0.9));
        }

        .service-card.facebook.selected {
            border-color: #1877F2;
            background: linear-gradient(135deg, rgba(24, 119, 242, 0.1), rgba(255, 255, 255, 0.9));
        }

        .service-card.tiktok.selected {
            border-color: #000000;
            background: linear-gradient(135deg, rgba(0, 0, 0, 0.1), rgba(255, 255, 255, 0.9));
        }

        .service-card.youtube.selected {
            border-color: #FF0000;
            background: linear-gradient(135deg, rgba(255, 0, 0, 0.1), rgba(255, 255, 255, 0.9));
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .service-card.instagram .service-icon {
            color: #E1306C;
        }

        .service-card.facebook .service-icon {
            color: #1877F2;
        }

        .service-card.tiktok .service-icon {
            color: #000000;
        }

        .service-card.youtube .service-icon {
            color: #FF0000;
        }

        .service-name {
            font-weight: 700;
            margin-bottom: 15px;
            font-size: 1.4rem;
        }

        .service-desc {
            color: var(--gray);
            font-size: 1.1rem;
            line-height: 1.5;
        }

        .live-results {
            background: var(--light);
            border-radius: 20px;
            padding: 40px;
            margin-top: 40px;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .results-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .counter {
            text-align: center;
            margin-bottom: 40px;
        }

        .counter-value {
            font-size: 5rem;
            font-weight: 800;
            margin-bottom: 15px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .counter-label {
            color: var(--gray);
            font-size: 1.4rem;
            font-weight: 600;
        }

        .progress-container {
            margin: 40px 0;
        }

        .progress-bar {
            height: 20px;
            background: rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .progress-fill {
            height: 100%;
            width: 0%;
            transition: width 0.5s ease;
            border-radius: 10px;
        }

        .instagram .progress-fill {
            background: linear-gradient(135deg, #E1306C, #F77737);
        }

        .facebook .progress-fill {
            background: linear-gradient(135deg, #1877F2, #1877F2);
        }

        .tiktok .progress-fill {
            background: linear-gradient(135deg, #000000, #69C9D0, #EE1D52);
        }

        .youtube .progress-fill {
            background: linear-gradient(135deg, #FF0000, #FF0000);
        }

        .live-feed {
            max-height: 450px;
            overflow-y: auto;
            border: 2px solid rgba(0, 0, 0, 0.1);
            border-radius: 15px;
            padding: 25px;
            background: rgba(255, 255, 255, 0.8);
        }

        .feed-item {
            display: flex;
            align-items: center;
            gap: 25px;
            padding: 20px;
            border-bottom: 2px solid rgba(0, 0, 0, 0.05);
            animation: slideIn 0.5s ease;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 12px;
            margin-bottom: 10px;
            transition: all 0.3s;
        }

        .feed-item:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .feed-item:last-child {
            border-bottom: none;
            margin-bottom: 0;
        }

        .feed-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 800;
            font-size: 1.8rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .instagram .feed-avatar {
            background: linear-gradient(135deg, #E1306C, #F77737);
        }

        .facebook .feed-avatar {
            background: linear-gradient(135deg, #1877F2, #1877F2);
        }

        .tiktok .feed-avatar {
            background: linear-gradient(135deg, #000000, #69C9D0, #EE1D52);
        }

        .youtube .feed-avatar {
            background: linear-gradient(135deg, #FF0000, #FF0000);
        }

        .feed-content {
            flex: 1;
        }

        .feed-username {
            font-weight: 700;
            margin-bottom: 8px;
            font-size: 1.3rem;
            color: var(--dark);
        }

        .feed-action {
            color: var(--gray);
            font-size: 1.1rem;
        }

        .feed-time {
            color: var(--gray);
            font-size: 1rem;
            font-weight: 600;
        }

        .api-response {
            background: rgba(248, 249, 250, 0.9);
            border-radius: 20px;
            padding: 30px;
            margin-top: 40px;
            font-family: 'Courier New', monospace;
            font-size: 1.1rem;
            display: none;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .response-success {
            border-left: 6px solid var(--success);
        }

        .response-error {
            border-left: 6px solid var(--error);
        }

        .impact-metrics {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin: 40px 0;
        }

        .metric-card {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            border: 2px solid transparent;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            backdrop-filter: blur(10px);
        }

        .metric-card:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: var(--primary);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .metric-value {
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 15px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .metric-label {
            color: var(--gray);
            font-size: 1.1rem;
            font-weight: 600;
        }

        .status-indicators {
            display: flex;
            justify-content: space-between;
            margin: 40px 0;
            position: relative;
        }

        .status-indicators::before {
            content: '';
            position: absolute;
            top: 30px;
            left: 10%;
            right: 10%;
            height: 6px;
            background: rgba(0, 0, 0, 0.1);
            z-index: 1;
            border-radius: 3px;
        }

        .status-step {
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .status-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(0, 0, 0, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            font-size: 1.5rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .status-step.active .status-icon {
            background: var(--primary);
            color: white;
            transform: scale(1.2);
            box-shadow: 0 10px 25px rgba(255, 107, 107, 0.3);
        }

        .status-step.completed .status-icon {
            background: var(--success);
            color: white;
            transform: scale(1.1);
        }

        .demo-section {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 40px;
            margin-top: 50px;
            text-align: center;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .demo-btn {
            background: var(--warning);
            color: white;
            border: none;
            padding: 20px 40px;
            border-radius: 15px;
            cursor: pointer;
            font-weight: 700;
            margin: 20px;
            font-size: 1.2rem;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 10px 30px rgba(249, 199, 79, 0.3);
        }

        .demo-btn:hover {
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 20px 40px rgba(249, 199, 79, 0.4);
        }

        footer {
            text-align: center;
            color: white;
            margin-top: 60px;
            padding: 40px;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .reality-check {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 40px;
            margin-top: 50px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .reality-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .reality-card {
            background: rgba(255, 255, 255, 0.8);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s;
            border: 2px solid transparent;
        }

        .reality-card:hover {
            transform: translateY(-8px);
            border-color: var(--primary);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .reality-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .reality-title {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--dark);
        }

        .reality-desc {
            color: var(--gray);
            font-size: 1.1rem;
            line-height: 1.6;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-bolt"></i>
                <h1>InstantGrow Pro</h1>
            </div>
            <p class="tagline">Instant Social Media Growth - See Results in Minutes</p>
            <div class="stats">
                <div class="stat-item">
                    <div class="stat-number">128K+</div>
                    <div class="stat-label">Followers Delivered Today</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">99.8%</div>
                    <div class="stat-label">Instant Delivery Rate</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">2-5 min</div>
                    <div class="stat-label">Average Delivery Time</div>
                </div>
            </div>

            <div class="platform-selector">
                <div class="platform-tab instagram active" data-platform="instagram">
                    <i class="fab fa-instagram"></i>
                    <span>Instagram</span>
                </div>
                <div class="platform-tab facebook" data-platform="facebook">
                    <i class="fab fa-facebook"></i>
                    <span>Facebook</span>
                </div>
                <div class="platform-tab tiktok" data-platform="tiktok">
                    <i class="fab fa-tiktok"></i>
                    <span>TikTok</span>
                </div>
                <div class="platform-tab youtube" data-platform="youtube">
                    <i class="fab fa-youtube"></i>
                    <span>YouTube</span>
                </div>
            </div>
        </header>

        <div class="main-content">
            <div class="generator-panel">
                <div class="panel-header">
                    <h2><i class="fas fa-magic"></i> Instant Follower Generator</h2>
                    <p>Get real followers delivered instantly to your profile</p>
                </div>

                <form class="generator-form" id="generatorForm">
                    <div class="form-group">
                        <label for="profileLink"><i class="fas fa-user-circle"></i> Your Profile URL</label>
                        <input type="url" id="profileLink" placeholder="https://instagram.com/yourusername" required>
                        <small style="color: var(--gray); margin-top: 10px; display: block;">
                            Enter your exact profile URL for instant delivery
                        </small>
                    </div>

                    <div class="form-group">
                        <label for="service"><i class="fas fa-cogs"></i> Service Type</label>
                        <select id="service" required>
                            <option value="">Select growth service</option>
                            <!-- Options populated by JavaScript -->
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="quantity"><i class="fas fa-hashtag"></i> Quantity</label>
                        <input type="number" id="quantity" placeholder="100-10,000" min="100" max="10000" required>
                        <small style="color: var(--gray); margin-top: 10px; display: block;">
                            Choose how many followers you want (100-10,000)
                        </small>
                    </div>

                    <div class="form-group">
                        <label for="deliverySpeed"><i class="fas fa-tachometer-alt"></i> Delivery Speed</label>
                        <select id="deliverySpeed" required>
                            <option value="">Select delivery speed</option>
                            <option value="instant">Instant (2-5 minutes)</option>
                            <option value="fast">Fast (5-15 minutes)</option>
                            <option value="standard">Standard (15-30 minutes)</option>
                        </select>
                    </div>

                    <button type="submit" class="btn btn-primary">
                        <i class="fas fa-bolt"></i> Generate Followers Instantly
                    </button>
                </form>

                <div class="services-grid" id="servicesGrid">
                    <!-- Services populated by JavaScript -->
                </div>
            </div>

            <div class="results-panel">
                <div class="panel-header">
                    <h2><i class="fas fa-chart-line"></i> Live Delivery Results</h2>
                    <p>Watch your followers grow in real-time</p>
                </div>

                <div class="status-indicators" id="statusIndicators" style="display: none;">
                    <div class="status-step" id="step1">
                        <div class="status-icon">
                            <i class="fas fa-search"></i>
                        </div>
                        <div>Verifying Profile</div>
                    </div>
                    <div class="status-step" id="step2">
                        <div class="status-icon">
                            <i class="fas fa-bolt"></i>
                        </div>
                        <div>Starting Delivery</div>
                    </div>
                    <div class="status-step" id="step3">
                        <div class="status-icon">
                            <i class="fas fa-rocket"></i>
                        </div>
                        <div>Mass Delivery</div>
                    </div>
                    <div class="status-step" id="step4">
                        <div class="status-icon">
                            <i class="fas fa-check"></i>
                        </div>
                        <div>Completed</div>
                    </div>
                </div>

                <div class="impact-metrics" id="impactMetrics" style="display: none;">
                    <div class="metric-card">
                        <div class="metric-value" id="metricFollowers">0</div>
                        <div class="metric-label">Followers Added</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricEngagement">0%</div>
                        <div class="metric-label">Engagement Boost</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricReach">0</div>
                        <div class="metric-label">Reach Increased</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricGrowth">+0%</div>
                        <div class="metric-label">Profile Growth</div>
                    </div>
                </div>

                <div class="live-results instagram" id="liveResults">
                    <div class="counter">
                        <div class="counter-value" id="followersCount">0</div>
                        <div class="counter-label" id="counterLabel">Followers Delivered</div>
                    </div>

                    <div class="progress-container">
                        <div class="progress-bar">
                            <div class="progress-fill" id="progressFill"></div>
                        </div>
                    </div>

                    <div class="live-feed" id="liveFeed">
                        <div class="feed-item">
                            <div class="feed-avatar">S</div>
                            <div class="feed-content">
                                <div class="feed-username">sarah_miller</div>
                                <div class="feed-action">started following you</div>
                            </div>
                            <div class="feed-time">just now</div>
                        </div>
                    </div>
                </div>

                <div class="api-response" id="apiResponse">
                    <h4><i class="fas fa-terminal"></i> Delivery System Status</h4>
                    <pre id="responseData">Ready to generate instant followers...</pre>
                </div>
            </div>
        </div>

        <div class="reality-check">
            <h2 style="text-align: center; margin-bottom: 30px; color: var(--dark);">
                <i class="fas fa-info-circle"></i> Important Reality Check
            </h2>
            <div class="reality-content">
                <div class="reality-card">
                    <div class="reality-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <div class="reality-title">Platform Security</div>
                    <div class="reality-desc">
                        Social media platforms have advanced systems to detect and remove artificial followers. Instant follower services often violate platform terms.
                    </div>
                </div>
                <div class="reality-card">
                    <div class="reality-icon">
                        <i class="fas fa-clock"></i>
                    </div>
                    <div class="reality-title">Temporary Results</div>
                    <div class="reality-desc">
                        Artificially generated followers are often removed within days or weeks, wasting your investment and potentially harming your account.
                    </div>
                </div>
                <div class="reality-card">
                    <div class="reality-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="reality-title">Real Growth Takes Time</div>
                    <div class="reality-desc">
                        Authentic growth comes from quality content, genuine engagement, and building real relationships with your audience over time.
                    </div>
                </div>
            </div>
        </div>

        <div class="demo-section">
            <h3>Ready to See Instant Growth?</h3>
            <p>Test our system with a demo profile to see how instant delivery works</p>
            <button class="demo-btn" onclick="fillDemoData()">
                <i class="fas fa-vial"></i> Load Demo Profile
            </button>
            <button class="demo-btn" onclick="startInstantDelivery()" style="background: var(--success);">
                <i class="fas fa-play"></i> Start Instant Delivery
            </button>
        </div>

        <footer>
            <p>&copy; 2023 InstantGrow Pro. This is a demonstration of instant follower delivery simulation.</p>
            <p style="margin-top: 20px; font-size: 1.1rem; opacity: 0.9;">
                For real social media growth, focus on authentic content and genuine audience engagement
            </p>
        </footer>
    </div>

    <script>
        // Platform configuration
        const platforms = {
            instagram: {
                name: 'Instagram',
                color: '#E1306C',
                services: [
                    { id: 'real_followers', name: 'Real Followers', desc: 'Active Instagram users', icon: 'fas fa-users' },
                    { id: 'premium_likes', name: 'Premium Likes', desc: 'High-quality post engagement', icon: 'fas fa-heart' },
                    { id: 'story_views', name: 'Story Views', desc: '24-hour story engagement', icon: 'fas fa-eye' },
                    { id: 'auto_comments', name: 'Auto Comments', desc: 'Genuine-looking comments', icon: 'fas fa-comment' }
                ],
                placeholder: 'https://instagram.com/username'
            },
            facebook: {
                name: 'Facebook',
                color: '#1877F2',
                services: [
                    { id: 'page_likes', name: 'Page Likes', desc: 'Real Facebook users', icon: 'fas fa-thumbs-up' },
                    { id: 'post_engagement', name: 'Post Engagement', desc: 'Likes and shares', icon: 'fas fa-share' },
                    { id: 'video_views', name: 'Video Views', desc: 'Organic video engagement', icon: 'fas fa-play' },
                    { id: 'group_members', name: 'Group Members', desc: 'Active group participants', icon: 'fas fa-users' }
                ],
                placeholder: 'https://facebook.com/pagename'
            },
            tiktok: {
                name: 'TikTok',
                color: '#000000',
                services: [
                    { id: 'tiktok_followers', name: 'TikTok Followers', desc: 'Active TikTok users', icon: 'fas fa-users' },
                    { id: 'video_likes', name: 'Video Likes', desc: 'Genuine video engagement', icon: 'fas fa-heart' },
                    { id: 'video_views', name: 'Video Views', desc: 'Organic view count', icon: 'fas fa-eye' },
                    { id: 'shares', name: 'Video Shares', desc: 'Content sharing', icon: 'fas fa-share' }
                ],
                placeholder: 'https://tiktok.com/@username'
            },
            youtube: {
                name: 'YouTube',
                color: '#FF0000',
                services: [
                    { id: 'subscribers', name: 'Subscribers', desc: 'Active channel subscribers', icon: 'fas fa-users' },
                    { id: 'video_likes', name: 'Video Likes', desc: 'Genuine video engagement', icon: 'fas fa-thumbs-up' },
                    { id: 'video_views', name: 'Video Views', desc: 'Organic view count', icon: 'fas fa-eye' },
                    { id: 'comments', name: 'Comments', desc: 'Engaging discussions', icon: 'fas fa-comment' }
                ],
                placeholder: 'https://youtube.com/c/channelname'
            }
        };

        let currentPlatform = 'instagram';

        // Initialize platform
        function initializePlatform(platformId) {
            currentPlatform = platformId;
            const platform = platforms[platformId];
            
            // Update platform tabs
            document.querySelectorAll('.platform-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            document.querySelector(`.platform-tab.${platformId}`).classList.add('active');
            
            // Update results panel styling
            document.getElementById('liveResults').className = `live-results ${platformId}`;
            
            // Update placeholder
            document.getElementById('profileLink').placeholder = platform.placeholder;
            
            // Update services dropdown
            const serviceSelect = document.getElementById('service');
            serviceSelect.innerHTML = '<option value="">Select growth service</option>';
            platform.services.forEach(service => {
                const option = document.createElement('option');
                option.value = service.id;
                option.textContent = service.name;
                serviceSelect.appendChild(option);
            });
            
            // Update services grid
            const servicesGrid = document.getElementById('servicesGrid');
            servicesGrid.innerHTML = '';
            platform.services.forEach(service => {
                const serviceCard = document.createElement('div');
                serviceCard.className = `service-card ${platformId}`;
                serviceCard.onclick = () => selectService(service.id, service.name);
                serviceCard.innerHTML = `
                    <div class="service-icon">
                        <i class="${service.icon}"></i>
                    </div>
                    <div class="service-name">${service.name}</div>
                    <div class="service-desc">${service.desc}</div>
                `;
                servicesGrid.appendChild(serviceCard);
            });
        }

        // Platform tab selection
        document.querySelectorAll('.platform-tab').forEach(tab => {
            tab.addEventListener('click', function() {
                const platformId = this.getAttribute('data-platform');
                initializePlatform(platformId);
            });
        });

        // Service selection
        function selectService(serviceId, serviceName) {
            document.getElementById('service').value = serviceId;
            
            // Update all service cards
            document.querySelectorAll('.service-card').forEach(card => {
                card.classList.remove('selected');
            });
            
            // Highlight selected card
            event.currentTarget.classList.add('selected');
            
            showNotification(`Selected: ${serviceName}`, 'success');
        }

        // Form submission - Instant Delivery Simulation
        document.getElementById('generatorForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const profileLink = document.getElementById('profileLink').value.trim();
            const service = document.getElementById('service').value;
            const quantity = document.getElementById('quantity').value;
            const deliverySpeed = document.getElementById('deliverySpeed').value;
            
            if (!profileLink || !service || !quantity || !deliverySpeed) {
                showNotification('Please fill all fields to start instant delivery', 'error');
                return;
            }

            // Validate URL format
            if (!isValidUrl(profileLink, currentPlatform)) {
                showNotification('Please enter a valid URL for the selected platform', 'error');
                return;
            }

            // Show status indicators and impact metrics
            document.getElementById('statusIndicators').style.display = 'flex';
            document.getElementById('impactMetrics').style.display = 'grid';
            document.getElementById('apiResponse').style.display = 'block';
            
            // Update status steps
            updateStatusStep(1, 'active');
            updateStatusStep(2, '');
            updateStatusStep(3, '');
            updateStatusStep(4, '');

            // Show delivery status
            document.getElementById('responseData').textContent = 
                `🚀 Starting Instant Delivery System\n📱 Platform: ${platforms[currentPlatform].name}\n🎯 Service: ${service}\n📦 Quantity: ${quantity}\n⚡ Speed: ${deliverySpeed}\n\nInitializing delivery network...`;

            try {
                // Simulate profile verification
                await new Promise(resolve => setTimeout(resolve, 2000));
                updateStatusStep(1, 'completed');
                updateStatusStep(2, 'active');
                
                document.getElementById('responseData').textContent = 
                    `✅ Profile Verified: ${profileLink}\n✅ Network Connection Established\n✅ Delivery Resources Allocated\n\nStarting instant follower delivery...`;

                // Start instant delivery simulation
                startInstantDelivery(profileLink, quantity, service, deliverySpeed);

                showNotification('Instant delivery started! Followers arriving now...', 'success');

            } catch (error) {
                document.getElementById('responseData').textContent = `Delivery Error: ${error.message}`;
                document.getElementById('apiResponse').className = 'api-response response-error';
                showNotification('Delivery failed to start', 'error');
            }
        });

        // URL validation
        function isValidUrl(url, platform) {
            const patterns = {
                instagram: /^(https?:\/\/)?(www\.)?instagram\.com\/[a-zA-Z0-9._]+\/?$/,
                facebook: /^(https?:\/\/)?(www\.)?facebook\.com\/[a-zA-Z0-9._]+\/?$/,
                tiktok: /^(https?:\/\/)?(www\.)?tiktok\.com\/@[a-zA-Z0-9._]+\/?$/,
                youtube: /^(https?:\/\/)?(www\.)?(youtube\.com\/(c\/|channel\/|@)?[a-zA-Z0-9._-]+|youtu\.be\/[a-zA-Z0-9._-]+)\/?$/
            };
            return patterns[platform].test(url);
        }

        // Update status step
        function updateStatusStep(stepNumber, status) {
            const step = document.getElementById(`step${stepNumber}`);
            step.className = `status-step ${status}`;
        }

        // Start instant delivery simulation
        function startInstantDelivery(profileLink, quantity, service, speed) {
            const followersCount = document.getElementById('followersCount');
            const counterLabel = document.getElementById('counterLabel');
            const progressFill = document.getElementById('progressFill');
            const liveFeed = document.getElementById('liveFeed');
            
            // Set delivery speed
            const speedMultipliers = {
                instant: 100,
                fast: 200,
                standard: 400
            };
            
            const deliveryInterval = speedMultipliers[speed] || 200;
            
            let currentCount = 0;
            const targetCount = parseInt(quantity);
            
            // Clear previous results
            liveFeed.innerHTML = '';
            followersCount.textContent = '0';
            progressFill.style.width = '0%';
            
            // Reset impact metrics
            resetImpactMetrics();
            
            // Start the delivery simulation
            const interval = setInterval(() => {
                // Add followers based on speed
                const batchSize = Math.floor(Math.random() * 20) + 10;
                currentCount = Math.min(currentCount + batchSize, targetCount);
                
                // Update counter
                followersCount.textContent = currentCount;
                
                // Update progress bar
                const progress = (currentCount / targetCount) * 100;
                progressFill.style.width = progress + '%';
                
                // Add to live feed
                for (let i = 0; i < batchSize && currentCount <= targetCount; i++) {
                    addFollowerToFeed(service);
                }
                
                // Update impact metrics
                updateImpactMetrics(currentCount, targetCount);
                
                // Update status when mass delivery starts
                if (currentCount > targetCount * 0.3) {
                    updateStatusStep(2, 'completed');
                    updateStatusStep(3, 'active');
                }
                
                // Complete when target reached
                if (currentCount >= targetCount) {
                    clearInterval(interval);
                    updateStatusStep(3, 'completed');
                    updateStatusStep(4, 'active');
                    
                    setTimeout(() => {
                        updateStatusStep(4, 'completed');
                        document.getElementById('responseData').textContent = 
                            `🎉 INSTANT DELIVERY COMPLETE!\n\n✅ Successfully delivered ${targetCount} ${service}\n✅ To: ${profileLink}\n✅ Time: ${Math.floor(targetCount/deliveryInterval)} seconds\n\n📊 Delivery Summary:\n• ${targetCount} followers added instantly\n• Engagement rate increased significantly\n• Profile visibility maximized\n• All followers are live on your profile!\n\nYour ${platforms[currentPlatform].name} growth is complete!`;
                        document.getElementById('apiResponse').className = 'api-response response-success';
                        showNotification(`Delivery complete! ${targetCount} followers added.`, 'success');
                    }, 1000);
                }
            }, deliveryInterval);
        }

        // Add follower to live feed
        function addFollowerToFeed(service) {
            const liveFeed = document.getElementById('liveFeed');
            const platform = platforms[currentPlatform];
            
            const actions = {
                real_followers: 'started following you',
                premium_likes: 'liked your post',
                story_views: 'viewed your story',
                auto_comments: 'commented on your post',
                page_likes: 'liked your page',
                post_engagement: 'engaged with your post',
                video_views: 'watched your video',
                group_members: 'joined your group',
                tiktok_followers: 'started following you',
                video_likes: 'liked your video',
                shares: 'shared your content',
                subscribers: 'subscribed to your channel'
            };
            
            const usernames = [
                "alex_johnson", "sarah_miller", "mike_taylor", "emma_wilson", 
                "james_brown", "lisa_davis", "robert_garcia", "mia_martinez",
                "david_lee", "sophia_rodriguez", "chris_moore", "olivia_clark",
                "ryan_hernandez", "ava_young", "matthew_king", "isabella_scott"
            ];
            
            const username = usernames[Math.floor(Math.random() * usernames.length)];
            const action = actions[service] || 'started following you';
            
            const feedItem = document.createElement('div');
            feedItem.className = 'feed-item';
            
            const avatar = document.createElement('div');
            avatar.className = 'feed-avatar';
            avatar.textContent = username.charAt(0).toUpperCase();
            
            const feedContent = document.createElement('div');
            feedContent.className = 'feed-content';
            
            const usernameEl = document.createElement('div');
            usernameEl.className = 'feed-username';
            usernameEl.textContent = username;
            
            const actionEl = document.createElement('div');
            actionEl.className = 'feed-action';
            actionEl.textContent = action;
            
            const time = document.createElement('div');
            time.className = 'feed-time';
            time.textContent = 'just now';
            
            feedContent.appendChild(usernameEl);
            feedContent.appendChild(actionEl);
            feedItem.appendChild(avatar);
            feedItem.appendChild(feedContent);
            feedItem.appendChild(time);
            
            // Add to top of feed
            liveFeed.insertBefore(feedItem, liveFeed.firstChild);
            
            // Limit feed items
            if (liveFeed.children.length > 10) {
                liveFeed.removeChild(liveFeed.lastChild);
            }
        }

        // Reset impact metrics
        function resetImpactMetrics() {
            document.getElementById('metricFollowers').textContent = '0';
            document.getElementById('metricEngagement').textContent = '0%';
            document.getElementById('metricReach').textContent = '0';
            document.getElementById('metricGrowth').textContent = '+0%';
        }

        // Update impact metrics
        function updateImpactMetrics(currentCount, targetCount) {
            const progress = currentCount / targetCount;
            
            document.getElementById('metricFollowers').textContent = currentCount;
            document.getElementById('metricEngagement').textContent = Math.floor(progress * 25) + '%';
            document.getElementById('metricReach').textContent = Math.floor(progress * 5000);
            document.getElementById('metricGrowth').textContent = '+' + Math.floor(progress * 35) + '%';
        }

        // Fill demo data
        function fillDemoData() {
            const demoUrls = {
                instagram: 'https://instagram.com/your_profile',
                facebook: 'https://facebook.com/your_page',
                tiktok: 'https://tiktok.com/@your_username',
                youtube: 'https://youtube.com/c/your_channel'
            };
            
            document.getElementById('profileLink').value = demoUrls[currentPlatform];
            document.getElementById('service').value = platforms[currentPlatform].services[0].id;
            document.getElementById('quantity').value = '1000';
            document.getElementById('deliverySpeed').value = 'instant';
            
            // Select first service card
            document.querySelectorAll('.service-card')[0].classList.add('selected');
            
            showNotification(`Demo ${platforms[currentPlatform].name} profile loaded`, 'success');
        }

        // Global start instant delivery
        function startInstantDelivery() {
            const profileLink = document.getElementById('profileLink').value || 
                               `https://${currentPlatform}.com/your_profile`;
            const service = document.getElementById('service').value || platforms[currentPlatform].services[0].id;
            const quantity = document.getElementById('quantity').value || '500';
            const speed = document.getElementById('deliverySpeed').value || 'instant';
            
            document.getElementById('statusIndicators').style.display = 'flex';
            document.getElementById('impactMetrics').style.display = 'grid';
            updateStatusStep(1, 'active');
            updateStatusStep(2, 'active');
            
            startInstantDelivery(profileLink, quantity, service, speed);
            showNotification('Instant delivery simulation started!', 'success');
        }

        // Show notification
        function showNotification(message, type) {
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 40px;
                right: 40px;
                padding: 25px 35px;
                border-radius: 15px;
                color: white;
                font-weight: 700;
                z-index: 10000;
                animation: slideIn 0.4s ease;
                max-width: 450px;
                font-size: 1.2rem;
                box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
                backdrop-filter: blur(10px);
            `;
            
            if (type === 'success') {
                notification.style.background = 'linear-gradient(135deg, var(--success), var(--secondary))';
            } else if (type === 'error') {
                notification.style.background = 'linear-gradient(135deg, var(--error), #FF8E8E)';
            } else {
                notification.style.background = 'linear-gradient(135deg, var(--warning), #F9D976)';
            }
            
            notification.textContent = message;
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.remove();
            }, 5000);
        }

        // Initialize the platform
        initializePlatform('instagram');

        // Add CSS for animations
        const style = document.createElement('style');
        style.textContent = `
            @keyframes slideIn {
                from { transform: translateX(100%); opacity: 0; }
                to { transform: translateX(0); opacity: 1; }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
