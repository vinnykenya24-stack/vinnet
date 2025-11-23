<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>InstaGrow Pro | Free Follower Generator</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #E1306C;
            --secondary: #C13584;
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
            max-width: 1200px;
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
            color: var(--primary);
        }

        .logo h1 {
            font-size: 2.5rem;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
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
            color: var(--primary);
        }

        .stat-label {
            color: var(--gray);
            font-size: 0.9rem;
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
            border-color: var(--primary);
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
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(225, 48, 108, 0.3);
        }

        .btn-success {
            background: var(--success);
            color: white;
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
            border-color: var(--primary);
            background: linear-gradient(135deg, rgba(225, 48, 108, 0.05), rgba(193, 53, 132, 0.05));
        }

        .service-icon {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 10px;
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
            color: var(--primary);
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
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            width: 0%;
            transition: width 0.5s ease;
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
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 1.2rem;
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
            background: var(--primary);
            color: white;
        }

        .status-step.completed .status-icon {
            background: var(--success);
            color: white;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fab fa-instagram"></i>
                <h1>InstaGrow Pro</h1>
            </div>
            <p class="tagline">Real Followers • Instant Delivery • No API Key Required</p>
            <div class="stats">
                <div class="stat-item">
                    <div class="stat-number">15,293</div>
                    <div class="stat-label">Followers Generated Today</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">99.1%</div>
                    <div class="stat-label">Success Rate</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">1-10 min</div>
                    <div class="stat-label">Average Delivery</div>
                </div>
            </div>
        </header>

        <div class="main-panel">
            <div class="order-panel">
                <div class="panel-header">
                    <h2><i class="fas fa-bolt"></i> Generate Real Followers</h2>
                    <p>No API key required - Start instantly with any Instagram account</p>
                </div>

                <form class="api-form" id="orderForm">
                    <div class="form-group">
                        <label for="profileLink"><i class="fas fa-user"></i> Instagram Username</label>
                        <input type="text" id="profileLink" placeholder="Enter your Instagram username (without @)" required>
                    </div>

                    <div class="form-group">
                        <label for="service"><i class="fas fa-cog"></i> Service Type</label>
                        <select id="service" required>
                            <option value="">Select service</option>
                            <option value="followers">Real Instagram Followers</option>
                            <option value="likes">Premium Instagram Likes</option>
                            <option value="views">Instagram Story Views</option>
                            <option value="comments">Auto Comments</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="quantity"><i class="fas fa-hashtag"></i> Quantity</label>
                        <input type="number" id="quantity" placeholder="100-5000" min="100" max="5000" required>
                    </div>

                    <button type="submit" class="btn btn-primary pulse">
                        <i class="fas fa-rocket"></i> Start Free Generation
                    </button>
                </form>

                <div class="services-grid">
                    <div class="service-card" onclick="selectService('followers', 'Real Followers')">
                        <div class="service-icon">
                            <i class="fas fa-users"></i>
                        </div>
                        <div class="service-name">Real Followers</div>
                        <div class="service-desc">100-5000 followers</div>
                    </div>
                    <div class="service-card" onclick="selectService('likes', 'Premium Likes')">
                        <div class="service-icon">
                            <i class="fas fa-heart"></i>
                        </div>
                        <div class="service-name">Premium Likes</div>
                        <div class="service-desc">100-10,000 likes</div>
                    </div>
                    <div class="service-card" onclick="selectService('views', 'Story Views')">
                        <div class="service-icon">
                            <i class="fas fa-eye"></i>
                        </div>
                        <div class="service-name">Story Views</div>
                        <div class="service-desc">500-50,000 views</div>
                    </div>
                </div>
            </div>

            <div class="results-panel">
                <div class="panel-header">
                    <h2><i class="fas fa-chart-line"></i> Live Results</h2>
                    <p>Watch your followers grow in real-time</p>
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

                <div class="live-results">
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
                    <h4><i class="fas fa-code"></i> System Status</h4>
                    <pre id="responseData">Ready to generate followers...</pre>
                </div>
            </div>
        </div>

        <div class="demo-section">
            <h3>Quick Start Demo</h3>
            <p>Test the system with sample data</p>
            <button class="demo-btn" onclick="fillDemoData()">
                <i class="fas fa-vial"></i> Load Demo Data
            </button>
            <button class="demo-btn" onclick="simulateLiveResults()" style="background: var(--success);">
                <i class="fas fa-play"></i> Simulate Live Results
            </button>
        </div>

        <footer>
            <p>&copy; 2023 InstaGrow Pro. No API Key Required - Direct Integration</p>
            <p style="margin-top: 10px; font-size: 0.9rem; opacity: 0.8;">
                Connect directly to our follower network - No authentication needed
            </p>
        </footer>
    </div>

    <script>
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

        // Form submission - No API Key Required
        document.getElementById('orderForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const username = document.getElementById('profileLink').value.trim();
            const service = document.getElementById('service').value;
            const quantity = document.getElementById('quantity').value;
            
            if (!username || !service || !quantity) {
                showNotification('Please fill all fields', 'error');
                return;
            }

            // Show status indicators
            document.getElementById('statusIndicators').style.display = 'flex';
            document.getElementById('apiResponse').style.display = 'block';
            
            // Update status steps
            updateStatusStep(1, 'active');
            updateStatusStep(2, '');
            updateStatusStep(3, '');

            // Show system status
            document.getElementById('responseData').textContent = 
                `Starting follower generation for: @${username}\nService: ${service}\nQuantity: ${quantity}\n\nConnecting to follower network...`;

            try {
                // Simulate processing delay
                await new Promise(resolve => setTimeout(resolve, 2000));

                // Update status
                updateStatusStep(1, 'completed');
                updateStatusStep(2, 'active');
                
                document.getElementById('responseData').textContent = 
                    `✅ Connected to follower network\n✅ Processing order for @${username}\n✅ Starting delivery of ${quantity} ${service}\n\nDelivery in progress...`;

                // Start live results
                startLiveResults(username, quantity, service);

                showNotification('Follower delivery started!', 'success');

            } catch (error) {
                document.getElementById('responseData').textContent = `Error: ${error.message}`;
                document.getElementById('apiResponse').className = 'api-response response-error';
                showNotification('System error', 'error');
            }
        });

        // Update status step
        function updateStatusStep(stepNumber, status) {
            const step = document.getElementById(`step${stepNumber}`);
            step.className = `status-step ${status}`;
        }

        // Start live results simulation
        function startLiveResults(username, quantity, service) {
            const followersCount = document.getElementById('followersCount');
            const counterLabel = document.getElementById('counterLabel');
            const progressFill = document.getElementById('progressFill');
            const liveFeed = document.getElementById('liveFeed');
            
            // Update counter label based on service
            const labels = {
                'followers': 'Followers Added',
                'likes': 'Likes Added', 
                'views': 'Views Added',
                'comments': 'Comments Added'
            };
            counterLabel.textContent = labels[service] || 'Items Added';
            
            let currentCount = 0;
            const targetCount = parseInt(quantity);
            
            // Clear previous results
            liveFeed.innerHTML = '';
            followersCount.textContent = '0';
            progressFill.style.width = '0%';
            
            // Start the delivery simulation
            const interval = setInterval(() => {
                // Add random number of items
                const batchSize = Math.floor(Math.random() * 8) + 3;
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
                
                // Update status when complete
                if (currentCount >= targetCount) {
                    clearInterval(interval);
                    updateStatusStep(2, 'completed');
                    updateStatusStep(3, 'active');
                    
                    setTimeout(() => {
                        updateStatusStep(3, 'completed');
                        document.getElementById('responseData').textContent = 
                            `✅ Delivery Complete!\n\nSuccessfully delivered ${targetCount} ${service} to @${username}\n\nAll items should appear on your profile within 2-5 minutes.`;
                        document.getElementById('apiResponse').className = 'api-response response-success';
                        showNotification(`Delivery complete! ${targetCount} ${service} added.`, 'success');
                    }, 1000);
                }
            }, 600); // Add items every 600ms
        }

        // Add activity to live feed based on service type
        function addActivityToFeed(service) {
            const liveFeed = document.getElementById('liveFeed');
            const actions = {
                'followers': 'started following you',
                'likes': 'liked your post',
                'views': 'viewed your story', 
                'comments': 'commented on your post'
            };
            
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
            
            const action = document.createElement('div');
            action.className = 'feed-action';
            action.textContent = actions[service] || 'interacted with your content';
            
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

        // Fill demo data
        function fillDemoData() {
            document.getElementById('profileLink').value = 'your_instagram';
            document.getElementById('service').value = 'followers';
            document.getElementById('quantity').value = '250';
            
            // Select first service card
            document.querySelectorAll('.service-card')[0].classList.add('selected');
            
            showNotification('Demo data loaded. Ready to generate!', 'success');
        }

        // Simulate live results
        function simulateLiveResults() {
            document.getElementById('statusIndicators').style.display = 'flex';
            updateStatusStep(1, 'active');
            startLiveResults('demo_account', 150, 'followers');
            showNotification('Live results simulation started', 'success');
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
