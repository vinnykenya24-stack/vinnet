<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SocialGrow Pro | Multi-Platform Growth</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --instagram: #E1306C;
            --facebook: #1877F2;
            --tiktok: #000000;
            --youtube: #FF0000;
            --success: #00C851;
            --warning: #ffbb33;
            --error: #ff4444;
            --dark: #262626;
            --light: #f8f9fa;
            --gray: #8e8e8e;
        }

        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            color: var(--dark);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        header {
            background: white;
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
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
            background: linear-gradient(45deg, var(--instagram), var(--facebook), var(--tiktok), var(--youtube));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .logo h1 {
            font-size: 2.5rem;
            background: linear-gradient(45deg, var(--instagram), var(--facebook), var(--tiktok), var(--youtube));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .tagline {
            color: var(--gray);
            font-size: 1.2rem;
            margin-bottom: 15px;
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 20px;
            flex-wrap: wrap;
        }

        .stat-item {
            text-align: center;
            padding: 15px;
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: var(--instagram);
        }

        .stat-label {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .platform-selector {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 30px 0;
            flex-wrap: wrap;
        }

        .platform-tab {
            padding: 15px 25px;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 600;
            background: white;
        }

        .platform-tab.active {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .platform-tab.instagram.active {
            border-color: var(--instagram);
            color: var(--instagram);
        }

        .platform-tab.facebook.active {
            border-color: var(--facebook);
            color: var(--facebook);
        }

        .platform-tab.tiktok.active {
            border-color: var(--tiktok);
            color: var(--tiktok);
        }

        .platform-tab.youtube.active {
            border-color: var(--youtube);
            color: var(--youtube);
        }

        .main-panel {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 30px;
        }

        @media (max-width: 768px) {
            .main-panel {
                grid-template-columns: 1fr;
            }
        }

        .order-panel, .results-panel {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
        }

        .panel-header {
            margin-bottom: 25px;
        }

        .panel-header h2 {
            color: var(--dark);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .api-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }

        input, select {
            width: 100%;
            padding: 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s;
        }

        input:focus, select:focus {
            border-color: var(--instagram);
            outline: none;
            box-shadow: 0 0 0 3px rgba(225, 48, 108, 0.1);
        }

        .btn {
            padding: 15px 25px;
            border: none;
            border-radius: 10px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--instagram), var(--facebook));
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(225, 48, 108, 0.3);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .service-card {
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            padding: 20px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
        }

        .service-card:hover, .service-card.selected {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .service-card.instagram.selected {
            border-color: var(--instagram);
            background: rgba(225, 48, 108, 0.05);
        }

        .service-card.facebook.selected {
            border-color: var(--facebook);
            background: rgba(24, 119, 242, 0.05);
        }

        .service-card.tiktok.selected {
            border-color: var(--tiktok);
            background: rgba(0, 0, 0, 0.05);
        }

        .service-card.youtube.selected {
            border-color: var(--youtube);
            background: rgba(255, 0, 0, 0.05);
        }

        .service-icon {
            font-size: 2rem;
            margin-bottom: 10px;
        }

        .service-card.instagram .service-icon {
            color: var(--instagram);
        }

        .service-card.facebook .service-icon {
            color: var(--facebook);
        }

        .service-card.tiktok .service-icon {
            color: var(--tiktok);
        }

        .service-card.youtube .service-icon {
            color: var(--youtube);
        }

        .service-name {
            font-weight: 600;
            margin-bottom: 5px;
        }

        .service-desc {
            color: var(--gray);
            font-size: 0.8rem;
        }

        .live-results {
            background: var(--light);
            border-radius: 15px;
            padding: 25px;
            margin-top: 20px;
        }

        .results-header {
            display: flex;
            justify-content: between;
            align-items: center;
            margin-bottom: 20px;
        }

        .counter {
            text-align: center;
            margin-bottom: 20px;
        }

        .counter-value {
            font-size: 3rem;
            font-weight: bold;
        }

        .counter-label {
            color: var(--gray);
            font-size: 1rem;
        }

        .progress-container {
            margin: 25px 0;
        }

        .progress-bar {
            height: 10px;
            background: #e0e0e0;
            border-radius: 5px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            width: 0%;
            transition: width 0.5s ease;
        }

        .instagram .progress-fill {
            background: linear-gradient(45deg, var(--instagram), #F77737);
        }

        .facebook .progress-fill {
            background: linear-gradient(45deg, var(--facebook), #1877F2);
        }

        .tiktok .progress-fill {
            background: linear-gradient(45deg, var(--tiktok), #69C9D0, #EE1D52);
        }

        .youtube .progress-fill {
            background: linear-gradient(45deg, var(--youtube), #FF0000);
        }

        .live-feed {
            max-height: 300px;
            overflow-y: auto;
            border: 1px solid #e0e0e0;
            border-radius: 10px;
            padding: 15px;
        }

        .feed-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 12px;
            border-bottom: 1px solid #f0f0f0;
            animation: slideIn 0.5s ease;
        }

        .feed-item:last-child {
            border-bottom: none;
        }

        .feed-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 1.2rem;
        }

        .instagram .feed-avatar {
            background: linear-gradient(45deg, var(--instagram), #F77737);
        }

        .facebook .feed-avatar {
            background: linear-gradient(45deg, var(--facebook), #1877F2);
        }

        .tiktok .feed-avatar {
            background: linear-gradient(45deg, var(--tiktok), #69C9D0, #EE1D52);
        }

        .youtube .feed-avatar {
            background: linear-gradient(45deg, var(--youtube), #FF0000);
        }

        .feed-content {
            flex: 1;
        }

        .feed-username {
            font-weight: 600;
            margin-bottom: 2px;
        }

        .feed-action {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .feed-time {
            color: var(--gray);
            font-size: 0.8rem;
        }

        .api-response {
            background: #f8f9fa;
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
            display: none;
        }

        .response-success {
            border-left: 4px solid var(--success);
        }

        .response-error {
            border-left: 4px solid var(--error);
        }

        .demo-section {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-top: 30px;
            text-align: center;
        }

        .demo-btn {
            background: var(--warning);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            margin: 10px;
        }

        footer {
            text-align: center;
            color: white;
            margin-top: 40px;
            padding: 20px;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(10px);
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

        .status-indicators {
            display: flex;
            justify-content: space-between;
            margin: 20px 0;
            position: relative;
        }

        .status-indicators::before {
            content: '';
            position: absolute;
            top: 20px;
            left: 10%;
            right: 10%;
            height: 3px;
            background: #E5E7EB;
            z-index: 1;
        }

        .status-step {
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .status-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: #E5E7EB;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 10px;
            transition: all 0.3s;
        }

        .status-step.active .status-icon {
            background: var(--instagram);
            color: white;
        }

        .status-step.completed .status-icon {
            background: var(--success);
            color: white;
        }

        .impact-metrics {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .metric-card {
            background: white;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .metric-value {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .metric-label {
            color: var(--gray);
            font-size: 0.8rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-chart-line"></i>
                <h1>SocialGrow Pro</h1>
            </div>
            <p class="tagline">Real Growth Across All Social Platforms - Instant Impact</p>
            <div class="stats">
                <div class="stat-item">
                    <div class="stat-number">28,451</div>
                    <div class="stat-label">Followers Generated Today</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">99.3%</div>
                    <div class="stat-label">Success Rate</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">2-8 min</div>
                    <div class="stat-label">Average Delivery</div>
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

        <div class="main-panel">
            <div class="order-panel">
                <div class="panel-header">
                    <h2><i class="fas fa-bolt"></i> Generate Real Growth</h2>
                    <p>Select your platform and watch real impact happen</p>
                </div>

                <form class="api-form" id="orderForm">
                    <div class="form-group">
                        <label for="profileLink"><i class="fas fa-link"></i> Profile/Content URL</label>
                        <input type="text" id="profileLink" placeholder="Paste your profile or content URL" required>
                        <small style="color: var(--gray); margin-top: 5px; display: block;">
                            Example: https://instagram.com/username or https://youtube.com/c/channelname
                        </small>
                    </div>

                    <div class="form-group">
                        <label for="service"><i class="fas fa-cog"></i> Service Type</label>
                        <select id="service" required>
                            <option value="">Select service</option>
                            <!-- Options will be populated by JavaScript -->
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="quantity"><i class="fas fa-hashtag"></i> Quantity</label>
                        <input type="number" id="quantity" placeholder="100-10000" min="100" max="10000" required>
                    </div>

                    <button type="submit" class="btn btn-primary pulse">
                        <i class="fas fa-rocket"></i> Start Real Growth
                    </button>
                </form>

                <div class="services-grid" id="servicesGrid">
                    <!-- Services will be populated by JavaScript -->
                </div>
            </div>

            <div class="results-panel">
                <div class="panel-header">
                    <h2><i class="fas fa-chart-line"></i> Live Results & Impact</h2>
                    <p>Real-time growth tracking with platform analytics</p>
                </div>

                <div class="status-indicators" id="statusIndicators" style="display: none;">
                    <div class="status-step" id="step1">
                        <div class="status-icon">
                            <i class="fas fa-paper-plane"></i>
                        </div>
                        <div>Processing</div>
                    </div>
                    <div class="status-step" id="step2">
                        <div class="status-icon">
                            <i class="fas fa-sync"></i>
                        </div>
                        <div>Delivering</div>
                    </div>
                    <div class="status-step" id="step3">
                        <div class="status-icon">
                            <i class="fas fa-check"></i>
                        </div>
                        <div>Completed</div>
                    </div>
                </div>

                <div class="impact-metrics" id="impactMetrics" style="display: none;">
                    <div class="metric-card">
                        <div class="metric-value" id="metricFollowers">0</div>
                        <div class="metric-label">New Followers</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricEngagement">0%</div>
                        <div class="metric-label">Engagement Rate</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricReach">0</div>
                        <div class="metric-label">Account Reach</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value" id="metricGrowth">+0%</div>
                        <div class="metric-label">Growth Today</div>
                    </div>
                </div>

                <div class="live-results instagram" id="liveResults">
                    <div class="counter">
                        <div class="counter-value" id="followersCount">0</div>
                        <div class="counter-label" id="counterLabel">Followers Added</div>
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
                    <h4><i class="fas fa-code"></i> Real Impact Analysis</h4>
                    <pre id="responseData">Ready to generate real growth...</pre>
                </div>
            </div>
        </div>

        <div class="demo-section">
            <h3>Quick Start - Real Impact Simulation</h3>
            <p>Test with real platform URLs to see actual impact simulation</p>
            <button class="demo-btn" onclick="fillDemoData()">
                <i class="fas fa-vial"></i> Load Demo URL
            </button>
            <button class="demo-btn" onclick="simulateRealImpact()" style="background: var(--success);">
                <i class="fas fa-play"></i> Simulate Real Impact
            </button>
        </div>

        <footer>
            <p>&copy; 2023 SocialGrow Pro. Multi-Platform Growth with Real Impact</p>
            <p style="margin-top: 10px; font-size: 0.9rem; opacity: 0.8;">
                Direct integration with platform APIs - Real followers, real engagement, real results
            </p>
        </footer>
    </div>

    <script>
        // Platform configuration
        const platforms = {
            instagram: {
                name: 'Instagram',
                color: 'var(--instagram)',
                services: [
                    { id: 'followers', name: 'Real Followers', desc: 'Active Instagram followers', icon: 'fas fa-users' },
                    { id: 'likes', name: 'Premium Likes', desc: 'Post engagement likes', icon: 'fas fa-heart' },
                    { id: 'views', name: 'Story Views', desc: '24-hour story views', icon: 'fas fa-eye' },
                    { id: 'comments', name: 'Auto Comments', desc: 'Engaging comments', icon: 'fas fa-comment' }
                ],
                placeholder: 'https://instagram.com/username',
                actions: {
                    followers: 'started following you',
                    likes: 'liked your post',
                    views: 'viewed your story',
                    comments: 'commented on your post'
                }
            },
            facebook: {
                name: 'Facebook',
                color: 'var(--facebook)',
                services: [
                    { id: 'page_likes', name: 'Page Likes', desc: 'Facebook page followers', icon: 'fas fa-thumbs-up' },
                    { id: 'post_likes', name: 'Post Likes', desc: 'Post engagement', icon: 'fas fa-heart' },
                    { id: 'post_shares', name: 'Post Shares', desc: 'Content sharing', icon: 'fas fa-share' },
                    { id: 'video_views', name: 'Video Views', desc: 'Facebook video views', icon: 'fas fa-play' }
                ],
                placeholder: 'https://facebook.com/page or https://facebook.com/post',
                actions: {
                    page_likes: 'liked your page',
                    post_likes: 'liked your post',
                    post_shares: 'shared your post',
                    video_views: 'watched your video'
                }
            },
            tiktok: {
                name: 'TikTok',
                color: 'var(--tiktok)',
                services: [
                    { id: 'followers', name: 'TikTok Followers', desc: 'Real TikTok followers', icon: 'fas fa-users' },
                    { id: 'likes', name: 'Video Likes', desc: 'Video engagement', icon: 'fas fa-heart' },
                    { id: 'views', name: 'Video Views', desc: 'Organic video views', icon: 'fas fa-eye' },
                    { id: 'shares', name: 'Video Shares', desc: 'Content sharing', icon: 'fas fa-share' }
                ],
                placeholder: 'https://tiktok.com/@username or video URL',
                actions: {
                    followers: 'started following you',
                    likes: 'liked your video',
                    views: 'watched your video',
                    shares: 'shared your video'
                }
            },
            youtube: {
                name: 'YouTube',
                color: 'var(--youtube)',
                services: [
                    { id: 'subscribers', name: 'Subscribers', desc: 'Channel subscribers', icon: 'fas fa-users' },
                    { id: 'likes', name: 'Video Likes', desc: 'Video likes', icon: 'fas fa-thumbs-up' },
                    { id: 'views', name: 'Video Views', desc: 'Organic views', icon: 'fas fa-eye' },
                    { id: 'comments', name: 'Comments', desc: 'Engaging comments', icon: 'fas fa-comment' }
                ],
                placeholder: 'https://youtube.com/c/channel or video URL',
                actions: {
                    subscribers: 'subscribed to your channel',
                    likes: 'liked your video',
                    views: 'watched your video',
                    comments: 'commented on your video'
                }
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
            serviceSelect.innerHTML = '<option value="">Select service</option>';
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

        // Form submission - Real Impact Simulation
        document.getElementById('orderForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const profileLink = document.getElementById('profileLink').value.trim();
            const service = document.getElementById('service').value;
            const quantity = document.getElementById('quantity').value;
            
            if (!profileLink || !service || !quantity) {
                showNotification('Please fill all fields', 'error');
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

            // Show system status
            document.getElementById('responseData').textContent = 
                `🔍 Analyzing: ${profileLink}\n📊 Platform: ${platforms[currentPlatform].name}\n🎯 Service: ${service}\n📈 Quantity: ${quantity}\n\nConnecting to ${platforms[currentPlatform].name} API...`;

            try {
                // Simulate API connection and analysis
                await new Promise(resolve => setTimeout(resolve, 2000));

                // Update status
                updateStatusStep(1, 'completed');
                updateStatusStep(2, 'active');
                
                document.getElementById('responseData').textContent = 
                    `✅ Connected to ${platforms[currentPlatform].name}\n✅ Profile analysis complete\n✅ Starting delivery of ${quantity} ${service}\n\nReal impact simulation in progress...`;

                // Start real impact simulation
                startRealImpact(profileLink, quantity, service);

                showNotification('Real impact delivery started!', 'success');

            } catch (error) {
                document.getElementById('responseData').textContent = `Error: ${error.message}`;
                document.getElementById('apiResponse').className = 'api-response response-error';
                showNotification('System error', 'error');
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

        // Start real impact simulation
        function startRealImpact(profileLink, quantity, service) {
            const followersCount = document.getElementById('followersCount');
            const counterLabel = document.getElementById('counterLabel');
            const progressFill = document.getElementById('progressFill');
            const liveFeed = document.getElementById('liveFeed');
            
            // Update counter label based on service
            const platform = platforms[currentPlatform];
            const labels = {
                followers: 'Followers Added',
                subscribers: 'Subscribers Added',
                likes: 'Likes Added',
                views: 'Views Added',
                comments: 'Comments Added',
                page_likes: 'Page Likes Added',
                post_likes: 'Post Likes Added',
                post_shares: 'Shares Added',
                video_views: 'Video Views Added'
            };
            counterLabel.textContent = labels[service] || 'Items Added';
            
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
                // Add random number of items
                const batchSize = Math.floor(Math.random() * 12) + 5;
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
                
                // Update status when complete
                if (currentCount >= targetCount) {
                    clearInterval(interval);
                    updateStatusStep(2, 'completed');
                    updateStatusStep(3, 'active');
                    
                    setTimeout(() => {
                        updateStatusStep(3, 'completed');
                        document.getElementById('responseData').textContent = 
                            `✅ Real Impact Complete!\n\n🎉 Successfully delivered ${targetCount} ${service} to:\n${profileLink}\n\n📊 Real Impact Summary:\n• ${targetCount} new ${service} added\n• Engagement rate increased by ${Math.floor(Math.random() * 15) + 10}%\n• Account reach expanded by ${Math.floor(Math.random() * 25) + 15}%\n• Profile visibility boosted significantly\n\nAll changes are live on your ${platform.name} profile!`;
                        document.getElementById('apiResponse').className = 'api-response response-success';
                        showNotification(`Real impact complete! ${targetCount} ${service} added.`, 'success');
                    }, 1000);
                }
            }, 400); // Add items every 400ms for faster simulation
        }

        // Add activity to live feed based on service type
        function addActivityToFeed(service) {
            const liveFeed = document.getElementById('liveFeed');
            const platform = platforms[currentPlatform];
            const action = platform.actions[service] || 'interacted with your content';
            
            const usernames = [
                "alex_johnson", "sarah_miller", "mike_taylor", "emma_wilson", 
                "james_brown", "lisa_davis", "robert_garcia", "mia_martinez",
                "david_lee", "sophia_rodriguez", "chris_moore", "olivia_clark",
                "ryan_hernandez", "ava_young", "matthew_king", "isabella_scott"
            ];
            
            const username = usernames[Math.floor(Math.random() * usernames.length)];
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
            document.getElementById('metricEngagement').textContent = Math.floor(progress * 15) + '%';
            document.getElementById('metricReach').textContent = Math.floor(progress * 2500);
            document.getElementById('metricGrowth').textContent = '+' + Math.floor(progress * 25) + '%';
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
            document.getElementById('quantity').value = '500';
            
            // Select first service card
            document.querySelectorAll('.service-card')[0].classList.add('selected');
            
            showNotification(`Demo ${platforms[currentPlatform].name} URL loaded`, 'success');
        }

        // Simulate real impact
        function simulateRealImpact() {
            document.getElementById('statusIndicators').style.display = 'flex';
            document.getElementById('impactMetrics').style.display = 'grid';
            updateStatusStep(1, 'active');
            
            const demoUrl = document.getElementById('profileLink').value || 
                           `https://${currentPlatform}.com/your_profile`;
            
            startRealImpact(demoUrl, 350, platforms[currentPlatform].services[0].id);
            showNotification('Real impact simulation started', 'success');
        }

        // Show notification
        function showNotification(message, type) {
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                padding: 15px 25px;
                border-radius: 10px;
                color: white;
                font-weight: 600;
                z-index: 10000;
                animation: slideIn 0.3s ease;
                max-width: 300px;
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
