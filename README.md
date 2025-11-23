<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>InstantGrow Pro | Social Media Growth</title>
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
            padding: 20px;
            color: var(--dark);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
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

        .generator-panel, .results-panel {
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

        .generator-form {
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

        input, select {
            width: 100%;
            padding: 18px;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            font-size: 1.1rem;
            transition: all 0.3s;
        }

        input:focus, select:focus {
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

        .service-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }

        .service-card.instagram .service-icon {
            color: #E1306C;
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
            background: linear-gradient(45deg, var(--primary), var(--secondary));
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
            background: linear-gradient(45deg, var(--primary), var(--secondary));
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

        .reality-check {
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
                <i class="fas fa-bolt"></i>
                <h1>InstantGrow Pro</h1>
            </div>
            <p class="tagline">Instant Social Media Growth - Working Simulation</p>
            <div class="stats">
                <div class="stat-item">
                    <div class="stat-number">89,427</div>
                    <div class="stat-label">Followers Delivered Today</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">99.9%</div>
                    <div class="stat-label">Success Rate</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">1-3 min</div>
                    <div class="stat-label">Average Delivery</div>
                </div>
            </div>

            <div class="platform-selector">
                <div class="platform-tab instagram active" data-platform="instagram">
                    <i class="fab fa-instagram"></i>
                    <span>Instagram</span>
                </div>
                <div class="platform-tab tiktok" data-platform="tiktok">
                    <i class="fab fa-tiktok"></i>
                    <span>TikTok</span>
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
                        <label for="profileLink"><i class="fas fa-user-circle"></i> Your Instagram Username</label>
                        <input type="text" id="profileLink" placeholder="Enter your username (without @)" required>
                        <small style="color: var(--gray); margin-top: 10px; display: block;">
                            Example: yourusername (no @ symbol needed)
                        </small>
                    </div>

                    <div class="form-group">
                        <label for="quantity"><i class="fas fa-hashtag"></i> Number of Followers</label>
                        <input type="number" id="quantity" placeholder="100-5000" min="100" max="5000" required>
                        <small style="color: var(--gray); margin-top: 10px; display: block;">
                            Choose how many followers you want (100-5000)
                        </small>
                    </div>

                    <div class="form-group">
                        <label for="deliverySpeed"><i class="fas fa-tachometer-alt"></i> Delivery Speed</label>
                        <select id="deliverySpeed" required>
                            <option value="">Select delivery speed</option>
                            <option value="instant">⚡ Instant (1-2 minutes)</option>
                            <option value="fast">🚀 Fast (2-5 minutes)</option>
                            <option value="standard">📦 Standard (5-10 minutes)</option>
                        </select>
                    </div>

                    <button type="submit" class="btn btn-primary pulse">
                        <i class="fas fa-rocket"></i> Generate Followers Instantly
                    </button>
                </form>

                <div class="services-grid">
                    <div class="service-card instagram selected" onclick="selectService('followers')">
                        <div class="service-icon">
                            <i class="fas fa-users"></i>
                        </div>
                        <div class="service-name">Real Followers</div>
                        <div class="service-desc">Active Instagram users that engage with your content</div>
                    </div>
                    <div class="service-card instagram" onclick="selectService('likes')">
                        <div class="service-icon">
                            <i class="fas fa-heart"></i>
                        </div>
                        <div class="service-name">Premium Likes</div>
                        <div class="service-desc">High-quality likes on your posts</div>
                    </div>
                    <div class="service-card instagram" onclick="selectService('views')">
                        <div class="service-icon">
                            <i class="fas fa-eye"></i>
                        </div>
                        <div class="service-name">Story Views</div>
                        <div class="service-desc">24-hour story engagement</div>
                    </div>
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
                        <div>Verifying</div>
                    </div>
                    <div class="status-step" id="step2">
                        <div class="status-icon">
                            <i class="fas fa-bolt"></i>
                        </div>
                        <div>Starting</div>
                    </div>
                    <div class="status-step" id="step3">
                        <div class="status-icon">
                            <i class="fas fa-rocket"></i>
                        </div>
                        <div>Delivering</div>
                    </div>
                    <div class="status-step" id="step4">
                        <div class="status-icon">
                            <i class="fas fa-check"></i>
                        </div>
                        <div>Complete</div>
                    </div>
                </div>

                <div class="impact-metrics" id="impactMetrics" style="display: none;">
                    <div class="metric-card">
                        <div class="metric-value" id="metricFollowers">0</div>
                        <div class="metric-label">Followers Added</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricEngagement">0%</div>
                        <div class="metric-label">Engagement Rate</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricReach">0</div>
                        <div class="metric-label">Profile Reach</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricGrowth">+0%</div>
                        <div class="metric-label">Growth Today</div>
                    </div>
                </div>

                <div class="live-results">
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
                    <pre id="responseData">Ready to generate instant followers. Enter your username and click Generate!</pre>
                </div>
            </div>
        </div>

        <div class="reality-check">
            <h2 style="text-align: center; margin-bottom: 30px; color: var(--dark);">
                <i class="fas fa-info-circle"></i> Important: This is a Simulation
            </h2>
            <div class="tips-grid">
                <div class="tip-card">
                    <div class="tip-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <div class="tip-title">Platform Security</div>
                    <div class="tip-desc">
                        Real social media platforms have advanced security that prevents instant follower generation. This simulation shows what services promise, not what they can actually deliver.
                    </div>
                </div>
                <div class="tip-card">
                    <div class="tip-icon">
                        <i class="fas fa-clock"></i>
                    </div>
                    <div class="tip-title">Real Growth Takes Time</div>
                    <div class="tip-desc">
                        Authentic growth comes from quality content, genuine engagement, and building real relationships with your audience over time.
                    </div>
                </div>
                <div class="tip-card">
                    <div class="tip-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="tip-title">Focus on Real Engagement</div>
                    <div class="tip-desc">
                        Instead of fake followers, focus on creating valuable content that resonates with real people and builds genuine community.
                    </div>
                </div>
            </div>
        </div>

        <div class="demo-section">
            <h3>Ready to See the Simulation?</h3>
            <p>Test the instant follower generator with demo data</p>
            <button class="demo-btn" onclick="fillDemoData()">
                <i class="fas fa-vial"></i> Load Demo Data
            </button>
            <button class="demo-btn" onclick="startInstantDelivery()" style="background: var(--success);">
                <i class="fas fa-play"></i> Start Simulation
            </button>
        </div>

        <footer>
            <p>&copy; 2023 InstantGrow Pro. This is a working simulation for demonstration purposes.</p>
            <p style="margin-top: 20px; font-size: 1.1rem; opacity: 0.9;">
                Real social media growth requires authentic engagement and quality content
            </p>
        </footer>
    </div>

    <script>
        let currentService = 'followers';

        // Service selection
        function selectService(serviceId) {
            currentService = serviceId;
            
            // Update all service cards
            document.querySelectorAll('.service-card').forEach(card => {
                card.classList.remove('selected');
            });
            
            // Highlight selected card
            event.currentTarget.classList.add('selected');
            
            const serviceNames = {
                'followers': 'Real Followers',
                'likes': 'Premium Likes', 
                'views': 'Story Views'
            };
            
            showNotification(`Selected: ${serviceNames[serviceId]}`, 'success');
        }

        // Form submission - Working Simulation
        document.getElementById('generatorForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const username = document.getElementById('profileLink').value.trim();
            const quantity = document.getElementById('quantity').value;
            const deliverySpeed = document.getElementById('deliverySpeed').value;
            
            if (!username || !quantity || !deliverySpeed) {
                showNotification('Please fill all fields to start delivery', 'error');
                return;
            }

            if (username.includes('@')) {
                showNotification('Please enter username without @ symbol', 'error');
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
                `🔍 Verifying Instagram profile: @${username}\n⚡ Delivery speed: ${deliverySpeed}\n🎯 Service: ${currentService}\n📦 Quantity: ${quantity}\n\nStarting delivery system...`;

            try {
                // Simulate profile verification
                await new Promise(resolve => setTimeout(resolve, 1500));
                updateStatusStep(1, 'completed');
                updateStatusStep(2, 'active');
                
                document.getElementById('responseData').textContent = 
                    `✅ Profile Verified: @${username}\n✅ Instagram API Connected\n✅ Delivery Network Ready\n\nStarting instant follower delivery...`;

                await new Promise(resolve => setTimeout(resolve, 1000));
                updateStatusStep(2, 'completed');
                updateStatusStep(3, 'active');

                // Start the working simulation
                startWorkingSimulation(username, quantity, currentService, deliverySpeed);

                showNotification('Delivery started successfully!', 'success');

            } catch (error) {
                document.getElementById('responseData').textContent = `Delivery Error: ${error.message}`;
                document.getElementById('apiResponse').className = 'api-response response-error';
                showNotification('Delivery failed', 'error');
            }
        });

        // Update status step
        function updateStatusStep(stepNumber, status) {
            const step = document.getElementById(`step${stepNumber}`);
            step.className = `status-step ${status}`;
        }

        // Start working simulation
        function startWorkingSimulation(username, quantity, service, speed) {
            const followersCount = document.getElementById('followersCount');
            const counterLabel = document.getElementById('counterLabel');
            const progressFill = document.getElementById('progressFill');
            const liveFeed = document.getElementById('liveFeed');
            
            // Set delivery speed
            const speedMultipliers = {
                instant: 80,
                fast: 150,
                standard: 300
            };
            
            const deliveryInterval = speedMultipliers[speed] || 150;
            
            let currentCount = 0;
            const targetCount = parseInt(quantity);
            
            // Update counter label
            const serviceLabels = {
                'followers': 'Followers Delivered',
                'likes': 'Likes Added',
                'views': 'Views Added'
            };
            counterLabel.textContent = serviceLabels[service] || 'Items Delivered';
            
            // Clear previous results
            liveFeed.innerHTML = '';
            followersCount.textContent = '0';
            progressFill.style.width = '0%';
            
            // Reset impact metrics
            resetImpactMetrics();
            
            // Start the delivery simulation
            const interval = setInterval(() => {
                // Add items based on speed
                const batchSize = Math.floor(Math.random() * 15) + 8;
                currentCount = Math.min(currentCount + batchSize, targetCount);
                
                // Update counter
                followersCount.textContent = currentCount;
                
                // Update progress bar
                const progress = (currentCount / targetCount) * 100;
                progressFill.style.width = progress + '%';
                
                // Add to live feed
                for (let i = 0; i < batchSize && currentCount <= targetCount; i++) {
                    addActivityToFeed(service);
                }
                
                // Update impact metrics
                updateImpactMetrics(currentCount, targetCount);
                
                // Complete when target reached
                if (currentCount >= targetCount) {
                    clearInterval(interval);
                    updateStatusStep(3, 'completed');
                    updateStatusStep(4, 'active');
                    
                    setTimeout(() => {
                        updateStatusStep(4, 'completed');
                        document.getElementById('responseData').textContent = 
                            `🎉 DELIVERY COMPLETE!\n\n✅ Successfully delivered ${targetCount} ${service}\n✅ To: @${username}\n✅ Time: ${Math.floor(targetCount/deliveryInterval)} seconds\n\n📊 Simulation Results:\n• ${targetCount} ${service} added\n• Profile engagement increased\n• Account visibility boosted\n• All items delivered successfully!\n\nThis simulation demonstrates what instant follower services typically promise.`;
                        document.getElementById('apiResponse').className = 'api-response response-success';
                        showNotification(`Simulation complete! ${targetCount} ${service} delivered.`, 'success');
                    }, 1000);
                }
            }, deliveryInterval);
        }

        // Add activity to live feed
        function addActivityToFeed(service) {
            const liveFeed = document.getElementById('liveFeed');
            
            const actions = {
                'followers': 'started following you',
                'likes': 'liked your post',
                'views': 'viewed your story'
            };
            
            const usernames = [
                "alex_johnson", "sarah_miller", "mike_taylor", "emma_wilson", 
                "james_brown", "lisa_davis", "robert_garcia", "mia_martinez",
                "david_lee", "sophia_rodriguez", "chris_moore", "olivia_clark"
            ];
            
            const username = usernames[Math.floor(Math.random() * usernames.length)];
            const action = actions[service] || 'interacted with your content';
            
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
        function updateImpactMetrics(currentCount, targetCount) {
            const progress = currentCount / targetCount;
            
            document.getElementById('metricFollowers').textContent = currentCount;
            document.getElementById('metricEngagement').textContent = Math.floor(progress * 20) + '%';
            document.getElementById('metricReach').textContent = Math.floor(progress * 3500);
            document.getElementById('metricGrowth').textContent = '+' + Math.floor(progress * 30) + '%';
        }

        // Fill demo data
        function fillDemoData() {
            document.getElementById('profileLink').value = 'yourinstagram';
            document.getElementById('quantity').value = '1000';
            document.getElementById('deliverySpeed').value = 'instant';
            
            showNotification('Demo data loaded successfully!', 'success');
        }

        // Global start simulation
        function startInstantDelivery() {
            const username = document.getElementById('profileLink').value || 'yourinstagram';
            const quantity = document.getElementById('quantity').value || '500';
            const speed = document.getElementById('deliverySpeed').value || 'instant';
            
            document.getElementById('statusIndicators').style.display = 'flex';
            document.getElementById('impactMetrics').style.display = 'grid';
            updateStatusStep(1, 'active');
            updateStatusStep(2, 'active');
            updateStatusStep(3, 'active');
            
            startWorkingSimulation(username, quantity, currentService, speed);
            showNotification('Simulation started successfully!', 'success');
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
                box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
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
            }, 4000);
        }

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
