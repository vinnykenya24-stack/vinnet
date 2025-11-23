<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GrowthMaster Pro | Real Social Media Growth</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #6C63FF;
            --secondary: #4A44C6;
            --success: #10B981;
            --warning: #F59E0B;
            --error: #EF4444;
            --dark: #1F2937;
            --light: #F9FAFB;
            --gray: #6B7280;
        }

        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: var(--dark);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            background: white;
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 10px;
        }

        .logo i {
            font-size: 3rem;
            color: var(--primary);
        }

        .logo h1 {
            font-size: 2.8rem;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .tagline {
            color: var(--gray);
            font-size: 1.3rem;
            margin-bottom: 20px;
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .stat-item {
            text-align: center;
            padding: 20px;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .stat-label {
            color: var(--gray);
            font-size: 1rem;
        }

        .platform-selector {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .platform-tab {
            padding: 20px 30px;
            border: 3px solid #e0e0e0;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 15px;
            font-weight: 600;
            font-size: 1.1rem;
            background: white;
        }

        .platform-tab.active {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .platform-tab.instagram.active {
            border-color: #E1306C;
            color: #E1306C;
        }

        .platform-tab.facebook.active {
            border-color: #1877F2;
            color: #1877F2;
        }

        .platform-tab.tiktok.active {
            border-color: #000000;
            color: #000000;
        }

        .platform-tab.youtube.active {
            border-color: #FF0000;
            color: #FF0000;
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 40px;
        }

        @media (max-width: 968px) {
            .main-content {
                grid-template-columns: 1fr;
            }
        }

        .growth-panel, .results-panel {
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .panel-header {
            margin-bottom: 30px;
        }

        .panel-header h2 {
            color: var(--dark);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1.8rem;
        }

        .growth-form {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 12px;
            font-weight: 600;
            color: var(--dark);
            font-size: 1.1rem;
        }

        input, select, textarea {
            width: 100%;
            padding: 18px;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            font-size: 1.1rem;
            transition: all 0.3s;
        }

        input:focus, select:focus, textarea:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 4px rgba(108, 99, 255, 0.1);
        }

        .btn {
            padding: 20px 35px;
            border: none;
            border-radius: 12px;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(108, 99, 255, 0.3);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .service-card {
            border: 3px solid #e0e0e0;
            border-radius: 15px;
            padding: 25px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
        }

        .service-card:hover, .service-card.selected {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .service-card.instagram.selected {
            border-color: #E1306C;
            background: rgba(225, 48, 108, 0.05);
        }

        .service-card.facebook.selected {
            border-color: #1877F2;
            background: rgba(24, 119, 242, 0.05);
        }

        .service-card.tiktok.selected {
            border-color: #000000;
            background: rgba(0, 0, 0, 0.05);
        }

        .service-card.youtube.selected {
            border-color: #FF0000;
            background: rgba(255, 0, 0, 0.05);
        }

        .service-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
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
            font-weight: 600;
            margin-bottom: 10px;
            font-size: 1.3rem;
        }

        .service-desc {
            color: var(--gray);
            font-size: 1rem;
        }

        .live-results {
            background: var(--light);
            border-radius: 20px;
            padding: 30px;
            margin-top: 30px;
        }

        .results-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
        }

        .counter {
            text-align: center;
            margin-bottom: 30px;
        }

        .counter-value {
            font-size: 4rem;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .counter-label {
            color: var(--gray);
            font-size: 1.3rem;
        }

        .progress-container {
            margin: 30px 0;
        }

        .progress-bar {
            height: 15px;
            background: #e0e0e0;
            border-radius: 10px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            width: 0%;
            transition: width 0.5s ease;
            border-radius: 10px;
        }

        .instagram .progress-fill {
            background: linear-gradient(45deg, #E1306C, #F77737);
        }

        .facebook .progress-fill {
            background: linear-gradient(45deg, #1877F2, #1877F2);
        }

        .tiktok .progress-fill {
            background: linear-gradient(45deg, #000000, #69C9D0, #EE1D52);
        }

        .youtube .progress-fill {
            background: linear-gradient(45deg, #FF0000, #FF0000);
        }

        .live-feed {
            max-height: 400px;
            overflow-y: auto;
            border: 2px solid #e0e0e0;
            border-radius: 15px;
            padding: 20px;
        }

        .feed-item {
            display: flex;
            align-items: center;
            gap: 20px;
            padding: 18px;
            border-bottom: 2px solid #f0f0f0;
            animation: slideIn 0.5s ease;
        }

        .feed-item:last-child {
            border-bottom: none;
        }

        .feed-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 1.5rem;
        }

        .instagram .feed-avatar {
            background: linear-gradient(45deg, #E1306C, #F77737);
        }

        .facebook .feed-avatar {
            background: linear-gradient(45deg, #1877F2, #1877F2);
        }

        .tiktok .feed-avatar {
            background: linear-gradient(45deg, #000000, #69C9D0, #EE1D52);
        }

        .youtube .feed-avatar {
            background: linear-gradient(45deg, #FF0000, #FF0000);
        }

        .feed-content {
            flex: 1;
        }

        .feed-username {
            font-weight: 600;
            margin-bottom: 5px;
            font-size: 1.2rem;
        }

        .feed-action {
            color: var(--gray);
            font-size: 1rem;
        }

        .feed-time {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .api-response {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 25px;
            margin-top: 30px;
            font-family: 'Courier New', monospace;
            font-size: 1rem;
            display: none;
        }

        .response-success {
            border-left: 6px solid var(--success);
        }

        .response-error {
            border-left: 6px solid var(--error);
        }

        .impact-metrics {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .metric-card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            border: 2px solid transparent;
            transition: all 0.3s;
        }

        .metric-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary);
        }

        .metric-value {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .metric-label {
            color: var(--gray);
            font-size: 1rem;
        }

        .status-indicators {
            display: flex;
            justify-content: space-between;
            margin: 30px 0;
            position: relative;
        }

        .status-indicators::before {
            content: '';
            position: absolute;
            top: 25px;
            left: 10%;
            right: 10%;
            height: 4px;
            background: #E5E7EB;
            z-index: 1;
        }

        .status-step {
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .status-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: #E5E7EB;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            transition: all 0.3s;
            font-size: 1.3rem;
        }

        .status-step.active .status-icon {
            background: var(--primary);
            color: white;
            transform: scale(1.1);
        }

        .status-step.completed .status-icon {
            background: var(--success);
            color: white;
        }

        .demo-section {
            background: white;
            border-radius: 20px;
            padding: 30px;
            margin-top: 40px;
            text-align: center;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .demo-btn {
            background: var(--warning);
            color: white;
            border: none;
            padding: 18px 35px;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 600;
            margin: 15px;
            font-size: 1.1rem;
            transition: all 0.3s;
        }

        .demo-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(245, 158, 11, 0.3);
        }

        footer {
            text-align: center;
            color: white;
            margin-top: 50px;
            padding: 30px;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .pulse {
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .real-growth-tips {
            background: white;
            border-radius: 20px;
            padding: 40px;
            margin-top: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .tips-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .tip-card {
            background: var(--light);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s;
        }

        .tip-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .tip-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .tip-title {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--dark);
        }

        .tip-desc {
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
                <i class="fas fa-chart-line"></i>
                <h1>GrowthMaster Pro</h1>
            </div>
            <p class="tagline">Real Social Media Growth Through Legitimate Strategies</p>
            <div class="stats">
                <div class="stat-item">
                    <div class="stat-number">47,892</div>
                    <div class="stat-label">Accounts Successfully Grown</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">98.7%</div>
                    <div class="stat-label">Client Satisfaction Rate</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">2-4 Weeks</div>
                    <div class="stat-label">Average Growth Timeline</div>
                </div>
            </div>

            <div class="platform-selector">
                <div class="platform-tab instagram active" data-platform="instagram">
                    <i class="fab fa-instagram"></i>
                    <span>Instagram Growth</span>
                </div>
                <div class="platform-tab facebook" data-platform="facebook">
                    <i class="fab fa-facebook"></i>
                    <span>Facebook Growth</span>
                </div>
                <div class="platform-tab tiktok" data-platform="tiktok">
                    <i class="fab fa-tiktok"></i>
                    <span>TikTok Growth</span>
                </div>
                <div class="platform-tab youtube" data-platform="youtube">
                    <i class="fab fa-youtube"></i>
                    <span>YouTube Growth</span>
                </div>
            </div>
        </header>

        <div class="main-content">
            <div class="growth-panel">
                <div class="panel-header">
                    <h2><i class="fas fa-seedling"></i> Start Your Growth Journey</h2>
                    <p>Get real, organic growth through proven strategies</p>
                </div>

                <form class="growth-form" id="growthForm">
                    <div class="form-group">
                        <label for="profileLink"><i class="fas fa-link"></i> Your Profile URL</label>
                        <input type="url" id="profileLink" placeholder="https://instagram.com/yourusername" required>
                        <small style="color: var(--gray); margin-top: 8px; display: block;">
                            We'll analyze your profile and create a customized growth plan
                        </small>
                    </div>

                    <div class="form-group">
                        <label for="growthGoal"><i class="fas fa-bullseye"></i> Growth Goal</label>
                        <select id="growthGoal" required>
                            <option value="">Select your primary goal</option>
                            <option value="followers">Increase Followers</option>
                            <option value="engagement">Boost Engagement</option>
                            <option value="brand">Build Brand Awareness</option>
                            <option value="sales">Drive Sales/Leads</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="contentType"><i class="fas fa-palette"></i> Content Type</label>
                        <select id="contentType" required>
                            <option value="">Select your content focus</option>
                            <option value="photos">Photos & Images</option>
                            <option value="videos">Videos & Reels</option>
                            <option value="stories">Stories & Live</option>
                            <option value="mixed">Mixed Content</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="growthTimeline"><i class="fas fa-calendar"></i> Growth Timeline</label>
                        <select id="growthTimeline" required>
                            <option value="">Select preferred timeline</option>
                            <option value="quick">Quick Growth (2-4 weeks)</option>
                            <option value="steady">Steady Growth (1-3 months)</option>
                            <option value="longterm">Long-term Building (3-6 months)</option>
                        </select>
                    </div>

                    <button type="submit" class="btn btn-primary pulse">
                        <i class="fas fa-rocket"></i> Analyze & Create Growth Plan
                    </button>
                </form>

                <div class="services-grid" id="servicesGrid">
                    <!-- Services will be populated by JavaScript -->
                </div>
            </div>

            <div class="results-panel">
                <div class="panel-header">
                    <h2><i class="fas fa-chart-line"></i> Growth Progress & Results</h2>
                    <p>Track your real growth journey with detailed analytics</p>
                </div>

                <div class="status-indicators" id="statusIndicators" style="display: none;">
                    <div class="status-step" id="step1">
                        <div class="status-icon">
                            <i class="fas fa-search"></i>
                        </div>
                        <div>Profile Analysis</div>
                    </div>
                    <div class="status-step" id="step2">
                        <div class="status-icon">
                            <i class="fas fa-cogs"></i>
                        </div>
                        <div>Strategy Creation</div>
                    </div>
                    <div class="status-step" id="step3">
                        <div class="status-icon">
                            <i class="fas fa-play"></i>
                        </div>
                        <div>Implementation</div>
                    </div>
                    <div class="status-step" id="step4">
                        <div class="status-icon">
                            <i class="fas fa-chart-bar"></i>
                        </div>
                        <div>Growth Tracking</div>
                    </div>
                </div>

                <div class="impact-metrics" id="impactMetrics" style="display: none;">
                    <div class="metric-card">
                        <div class="metric-value" id="metricFollowers">0</div>
                        <div class="metric-label">Projected Followers</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricEngagement">0%</div>
                        <div class="metric-label">Engagement Rate</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricReach">0</div>
                        <div class="metric-label">Estimated Reach</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricGrowth">+0%</div>
                        <div class="metric-label">Growth Potential</div>
                    </div>
                </div>

                <div class="live-results instagram" id="liveResults">
                    <div class="counter">
                        <div class="counter-value" id="followersCount">0</div>
                        <div class="counter-label" id="counterLabel">Projected Growth</div>
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
                                <div class="feed-action">engaged with your content</div>
                            </div>
                            <div class="feed-time">just now</div>
                        </div>
                    </div>
                </div>

                <div class="api-response" id="apiResponse">
                    <h4><i class="fas fa-code"></i> Growth Strategy Analysis</h4>
                    <pre id="responseData">Ready to analyze your profile and create a customized growth plan...</pre>
                </div>
            </div>
        </div>

        <div class="real-growth-tips">
            <h2 style="text-align: center; margin-bottom: 30px; color: var(--dark);">
                <i class="fas fa-lightbulb"></i> Real Growth Strategies That Work
            </h2>
            <div class="tips-grid">
                <div class="tip-card">
                    <div class="tip-icon">
                        <i class="fas fa-camera"></i>
                    </div>
                    <div class="tip-title">Quality Content Creation</div>
                    <div class="tip-desc">
                        Create high-quality, engaging content that provides value to your audience and encourages sharing.
                    </div>
                </div>
                <div class="tip-card">
                    <div class="tip-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="tip-title">Community Engagement</div>
                    <div class="tip-desc">
                        Actively engage with your audience through comments, messages, and community features.
                    </div>
                </div>
                <div class="tip-card">
                    <div class="tip-icon">
                        <i class="fas fa-hashtag"></i>
                    </div>
                    <div class="tip-title">Strategic Hashtags</div>
                    <div class="tip-desc">
                        Use relevant hashtags to increase discoverability and reach new audiences interested in your content.
                    </div>
                </div>
            </div>
        </div>

        <div class="demo-section">
            <h3>Ready to See Real Growth?</h3>
            <p>Start your journey with a free profile analysis and growth plan</p>
            <button class="demo-btn" onclick="fillDemoData()">
                <i class="fas fa-vial"></i> Try Demo Analysis
            </button>
            <button class="demo-btn" onclick="startGrowthSimulation()" style="background: var(--success);">
                <i class="fas fa-play"></i> Start Growth Simulation
            </button>
        </div>

        <footer>
            <p>&copy; 2023 GrowthMaster Pro. Real Social Media Growth Through Legitimate Strategies</p>
            <p style="margin-top: 15px; font-size: 1rem; opacity: 0.9;">
                We help you grow authentically through proven strategies, not fake followers
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
                    { id: 'content_strategy', name: 'Content Strategy', desc: 'Optimized posting schedule and content plan', icon: 'fas fa-calendar' },
                    { id: 'engagement_boost', name: 'Engagement Boost', desc: 'Increase comments and interactions', icon: 'fas fa-comments' },
                    { id: 'hashtag_research', name: 'Hashtag Research', desc: 'Strategic hashtag optimization', icon: 'fas fa-hashtag' },
                    { id: 'story_optimization', name: 'Story Optimization', desc: 'Maximize story engagement', icon: 'fas fa-history' }
                ],
                placeholder: 'https://instagram.com/username'
            },
            facebook: {
                name: 'Facebook',
                color: '#1877F2',
                services: [
                    { id: 'page_optimization', name: 'Page Optimization', desc: 'Optimize your Facebook page', icon: 'fas fa-flag' },
                    { id: 'content_calendar', name: 'Content Calendar', desc: 'Strategic posting schedule', icon: 'fas fa-calendar-alt' },
                    { id: 'group_engagement', name: 'Group Engagement', desc: 'Build community in groups', icon: 'fas fa-users' },
                    { id: 'ad_strategy', name: 'Ad Strategy', desc: 'Cost-effective advertising', icon: 'fas fa-ad' }
                ],
                placeholder: 'https://facebook.com/pagename'
            },
            tiktok: {
                name: 'TikTok',
                color: '#000000',
                services: [
                    { id: 'video_strategy', name: 'Video Strategy', desc: 'Optimized video content plan', icon: 'fas fa-video' },
                    { id: 'trend_research', name: 'Trend Research', desc: 'Stay on top of trends', icon: 'fas fa-chart-line' },
                    { id: 'sound_optimization', name: 'Sound Optimization', desc: 'Strategic sound selection', icon: 'fas fa-music' },
                    { id: 'duet_strategy', name: 'Duet Strategy', desc: 'Collaboration opportunities', icon: 'fas fa-user-friends' }
                ],
                placeholder: 'https://tiktok.com/@username'
            },
            youtube: {
                name: 'YouTube',
                color: '#FF0000',
                services: [
                    { id: 'seo_optimization', name: 'SEO Optimization', desc: 'Video title and description SEO', icon: 'fas fa-search' },
                    { id: 'thumbnail_design', name: 'Thumbnail Design', desc: 'Click-worthy thumbnails', icon: 'fas fa-image' },
                    { id: 'content_planning', name: 'Content Planning', desc: 'Strategic video topics', icon: 'fas fa-tasks' },
                    { id: 'audience_retention', name: 'Audience Retention', desc: 'Keep viewers engaged', icon: 'fas fa-user-clock' }
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
            // Update all service cards
            document.querySelectorAll('.service-card').forEach(card => {
                card.classList.remove('selected');
            });
            
            // Highlight selected card
            event.currentTarget.classList.add('selected');
            
            showNotification(`Selected: ${serviceName}`, 'success');
        }

        // Form submission - Real Growth Analysis
        document.getElementById('growthForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const profileLink = document.getElementById('profileLink').value.trim();
            const growthGoal = document.getElementById('growthGoal').value;
            const contentType = document.getElementById('contentType').value;
            const growthTimeline = document.getElementById('growthTimeline').value;
            
            if (!profileLink || !growthGoal || !contentType || !growthTimeline) {
                showNotification('Please fill all fields to create your growth plan', 'error');
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

            // Show analysis status
            document.getElementById('responseData').textContent = 
                `🔍 Analyzing: ${profileLink}\n🎯 Growth Goal: ${growthGoal}\n📊 Content Type: ${contentType}\n⏰ Timeline: ${growthTimeline}\n\nStarting comprehensive profile analysis...`;

            try {
                // Simulate analysis process
                await new Promise(resolve => setTimeout(resolve, 3000));
                updateStatusStep(1, 'completed');
                updateStatusStep(2, 'active');
                
                document.getElementById('responseData').textContent = 
                    `✅ Profile Analysis Complete\n✅ Content Strategy Developed\n✅ Engagement Plan Created\n\nCreating your customized ${platforms[currentPlatform].name} growth strategy...`;

                await new Promise(resolve => setTimeout(resolve, 2500));
                updateStatusStep(2, 'completed');
                updateStatusStep(3, 'active');
                
                // Start growth simulation
                startGrowthSimulation(profileLink, growthGoal, contentType, growthTimeline);

                showNotification('Growth strategy implemented successfully!', 'success');

            } catch (error) {
                document.getElementById('responseData').textContent = `Analysis Error: ${error.message}`;
                document.getElementById('apiResponse').className = 'api-response response-error';
                showNotification('Analysis failed', 'error');
            }
        });

        // Update status step
        function updateStatusStep(stepNumber, status) {
            const step = document.getElementById(`step${stepNumber}`);
            step.className = `status-step ${status}`;
        }

        // Start growth simulation
        function startGrowthSimulation(profileLink, growthGoal, contentType, timeline) {
            const followersCount = document.getElementById('followersCount');
            const progressFill = document.getElementById('progressFill');
            const liveFeed = document.getElementById('liveFeed');
            
            // Calculate growth potential based on inputs
            const growthMultipliers = {
                quick: 1.5,
                steady: 2.0,
                longterm: 3.0
            };
            
            const baseGrowth = 250;
            const projectedGrowth = Math.floor(baseGrowth * growthMultipliers[timeline]);
            
            let currentGrowth = 0;
            const targetGrowth = projectedGrowth;
            
            // Clear previous results
            liveFeed.innerHTML = '';
            followersCount.textContent = '0';
            progressFill.style.width = '0%';
            
            // Reset impact metrics
            resetImpactMetrics();
            
            // Start the growth simulation
            const interval = setInterval(() => {
                // Simulate growth
                const growthIncrement = Math.floor(Math.random() * 15) + 5;
                currentGrowth = Math.min(currentGrowth + growthIncrement, targetGrowth);
                
                // Update counter
                followersCount.textContent = currentGrowth;
                
                // Update progress bar
                const progress = (currentGrowth / targetGrowth) * 100;
                progressFill.style.width = progress + '%';
                
                // Add to live feed
                if (Math.random() > 0.3) {
                    addGrowthActivity();
                }
                
                // Update impact metrics
                updateImpactMetrics(currentGrowth, targetGrowth);
                
                // Complete when target reached
                if (currentGrowth >= targetGrowth) {
                    clearInterval(interval);
                    updateStatusStep(3, 'completed');
                    updateStatusStep(4, 'active');
                    
                    setTimeout(() => {
                        updateStatusStep(4, 'completed');
                        document.getElementById('responseData').textContent = 
                            `🎉 Growth Strategy Complete!\n\n📈 Projected Results:\n• ${targetGrowth} new engaged followers\n• ${Math.floor(Math.random() * 20) + 15}% increase in engagement\n• ${Math.floor(targetGrowth * 2.5)} estimated reach increase\n• Significant brand visibility growth\n\nYour customized ${platforms[currentPlatform].name} growth plan is ready!`;
                        document.getElementById('apiResponse').className = 'api-response response-success';
                        showNotification(`Growth plan complete! Projected ${targetGrowth} new followers.`, 'success');
                    }, 1500);
                }
            }, 300);
        }

        // Add growth activity to feed
        function addGrowthActivity() {
            const liveFeed = document.getElementById('liveFeed');
            const activities = [
                'engaged with your content',
                'shared your post',
                'commented on your video',
                'saved your content',
                'started following you',
                'liked multiple posts',
                'sent your content to friends'
            ];
            
            const usernames = [
                "alex_johnson", "sarah_miller", "mike_taylor", "emma_wilson", 
                "james_brown", "lisa_davis", "robert_garcia", "mia_martinez",
                "david_lee", "sophia_rodriguez", "chris_moore", "olivia_clark"
            ];
            
            const username = usernames[Math.floor(Math.random() * usernames.length)];
            const activity = activities[Math.floor(Math.random() * activities.length)];
            
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
            
            const action = document.createElement('div');
            action.className = 'feed-action';
            action.textContent = activity;
            
            const time = document.createElement('div');
            time.className = 'feed-time';
            time.textContent = 'just now';
            
            feedContent.appendChild(usernameEl);
            feedContent.appendChild(action);
            feedItem.appendChild(avatar);
            feedItem.appendChild(feedContent);
            feedItem.appendChild(time);
            
            // Add to top of feed
            liveFeed.insertBefore(feedItem, liveFeed.firstChild);
            
            // Limit feed items
            if (liveFeed.children.length > 8) {
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
        function updateImpactMetrics(currentGrowth, targetGrowth) {
            const progress = currentGrowth / targetGrowth;
            
            document.getElementById('metricFollowers').textContent = currentGrowth;
            document.getElementById('metricEngagement').textContent = Math.floor(progress * 18) + '%';
            document.getElementById('metricReach').textContent = Math.floor(progress * 2500);
            document.getElementById('metricGrowth').textContent = '+' + Math.floor(progress * 25) + '%';
        }

        // Fill demo data
        function fillDemoData() {
            const demoUrls = {
                instagram: 'https://instagram.com/your_business',
                facebook: 'https://facebook.com/your_page',
                tiktok: 'https://tiktok.com/@your_brand',
                youtube: 'https://youtube.com/c/your_channel'
            };
            
            document.getElementById('profileLink').value = demoUrls[currentPlatform];
            document.getElementById('growthGoal').value = 'followers';
            document.getElementById('contentType').value = 'mixed';
            document.getElementById('growthTimeline').value = 'steady';
            
            showNotification(`Demo ${platforms[currentPlatform].name} profile loaded`, 'success');
        }

        // Global start growth simulation
        function startGrowthSimulation() {
            const profileLink = document.getElementById('profileLink').value || 
                               `https://${currentPlatform}.com/your_profile`;
            const growthGoal = document.getElementById('growthGoal').value || 'followers';
            const contentType = document.getElementById('contentType').value || 'mixed';
            const timeline = document.getElementById('growthTimeline').value || 'steady';
            
            document.getElementById('statusIndicators').style.display = 'flex';
            document.getElementById('impactMetrics').style.display = 'grid';
            updateStatusStep(1, 'active');
            updateStatusStep(2, 'active');
            updateStatusStep(3, 'active');
            
            startGrowthSimulation(profileLink, growthGoal, contentType, timeline);
            showNotification('Growth simulation started', 'success');
        }

        // Show notification
        function showNotification(message, type) {
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 30px;
                right: 30px;
                padding: 20px 30px;
                border-radius: 12px;
                color: white;
                font-weight: 600;
                z-index: 10000;
                animation: slideIn 0.4s ease;
                max-width: 400px;
                font-size: 1.1rem;
                box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            `;
            
            if (type === 'success') {
                notification.style.background = 'var(--success)';
            } else if (type === 'error') {
                notification.style.background = 'var(--error)';
            } else {
                notification.style.background = 'var(--warning)';
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
