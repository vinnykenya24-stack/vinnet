<pyegon>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>InstantSocial | Get Followers Instantly</title>
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
            --accent: #FF6584;
            --dark: #2A2D3E;
            --light: #F7F9FC;
            --gray: #8C8E9A;
            --success: #2ECC71;
        }

        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: white;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.05);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
        }

        .logo i {
            font-size: 2rem;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--primary);
        }

        .cta-button {
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            background: var(--primary);
            color: white;
            border: 2px solid var(--primary);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(108, 99, 255, 0.3);
        }

        /* Hero Section */
        .hero {
            padding: 100px 0;
            background: linear-gradient(135deg, #6C63FF 0%, #4A44C6 100%);
            color: white;
            text-align: center;
            border-radius: 0 0 30px 30px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000" opacity="0.1"><path fill="white" d="M500,200c150,0,250,100,250,250S650,700,500,700S250,600,250,450S350,200,500,200z"/></svg>') center/contain no-repeat;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 40px;
            opacity: 0.9;
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .btn-light {
            background: white;
            color: var(--primary);
            border: 2px solid white;
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .btn-light:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 255, 255, 0.3);
        }

        /* Profile Link Section */
        .profile-link-section {
            padding: 80px 0;
            background: white;
        }

        .profile-link-container {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .profile-link-container h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }

        .profile-link-container p {
            color: var(--gray);
            margin-bottom: 40px;
        }

        .platform-tabs {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .platform-tab {
            padding: 12px 25px;
            background: var(--light);
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 500;
        }

        .platform-tab.active {
            background: var(--primary);
            color: white;
        }

        .platform-tab i {
            font-size: 1.2rem;
        }

        .link-input-container {
            display: flex;
            gap: 15px;
            margin-bottom: 30px;
        }

        .link-input {
            flex: 1;
            padding: 15px 20px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .link-input:focus {
            border-color: var(--primary);
            outline: none;
        }

        .generate-btn {
            padding: 15px 30px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .generate-btn:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(108, 99, 255, 0.3);
        }

        .profile-preview {
            background: var(--light);
            border-radius: 15px;
            padding: 30px;
            margin-top: 30px;
            display: none;
            text-align: left;
        }

        .profile-info {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .profile-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
        }

        .profile-details h3 {
            font-size: 1.5rem;
            margin-bottom: 5px;
        }

        .profile-details p {
            color: var(--gray);
            margin-bottom: 0;
        }

        .service-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .service-option {
            background: white;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .service-option:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .service-option.selected {
            border-color: var(--primary);
            background: rgba(108, 99, 255, 0.05);
        }

        .service-icon {
            font-size: 2rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .service-option h4 {
            margin-bottom: 10px;
        }

        .service-option p {
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* Instant Results Section */
        .instant-results {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-top: 30px;
            display: none;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .results-header {
            margin-bottom: 30px;
        }

        .results-header h3 {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--success);
        }

        .counter-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .counter {
            background: var(--light);
            border-radius: 15px;
            padding: 20px;
            min-width: 150px;
        }

        .counter-value {
            font-size: 3rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .counter-label {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .live-feed {
            background: var(--light);
            border-radius: 15px;
            padding: 20px;
            max-height: 300px;
            overflow-y: auto;
            margin-bottom: 30px;
            text-align: left;
        }

        .feed-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 10px 0;
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
            animation: slideIn 0.5s ease;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-20px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .feed-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        .feed-text {
            flex: 1;
        }

        .feed-username {
            font-weight: 600;
        }

        .feed-action {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .completion-message {
            padding: 30px;
            background: rgba(46, 204, 113, 0.1);
            border-radius: 15px;
            margin-top: 30px;
        }

        .completion-message i {
            font-size: 3rem;
            color: var(--success);
            margin-bottom: 20px;
        }

        .completion-message h3 {
            margin-bottom: 10px;
            color: var(--success);
        }

        .action-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 20px;
        }

        /* Services Section */
        .section {
            padding: 100px 0;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }

        .section-header p {
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: white;
            border-radius: 15px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.1);
        }

        .service-card .service-icon {
            width: 80px;
            height: 80px;
            background: rgba(108, 99, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 25px;
            font-size: 2rem;
            color: var(--primary);
        }

        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .service-card p {
            color: var(--gray);
            margin-bottom: 25px;
        }

        .service-features {
            list-style: none;
            text-align: left;
            margin-bottom: 30px;
        }

        .service-features li {
            padding: 8px 0;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .service-features i {
            color: var(--success);
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 80px 0 30px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 50px;
        }

        .footer-col h3 {
            margin-bottom: 25px;
            font-size: 1.2rem;
        }

        .footer-col ul {
            list-style: none;
        }

        .footer-col ul li {
            margin-bottom: 15px;
        }

        .footer-col a {
            color: rgba(255, 255, 255, 0.7);
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-col a:hover {
            color: white;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.3s;
        }

        .social-links a:hover {
            background: var(--primary);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .link-input-container {
                flex-direction: column;
            }
            
            .counter-container {
                flex-direction: column;
            }
        }

        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 20px;
            }

            nav ul {
                gap: 15px;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn-light, .cta-button {
                width: 100%;
                max-width: 250px;
                text-align: center;
            }

            .profile-info {
                flex-direction: column;
                text-align: center;
            }

            .action-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-bolt"></i>
                <span>InstantSocial</span>
            </div>
            <nav>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#generate">Generate</a></li>
                    <li><a href="#services">Services</a></li>
                </ul>
            </nav>
            <a href="#generate" class="cta-button">Get Followers Now</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1>Get Followers & Likes INSTANTLY</h1>
            <p>Watch your social media accounts grow in real-time. No waiting, no delays - see results the moment you click!</p>
            <div class="hero-buttons">
                <a href="#generate" class="btn-light">Generate Now</a>
                <a href="#services" class="cta-button" style="background: transparent; border-color: white;">Our Services</a>
            </div>
        </div>
    </section>

    <!-- Profile Link Section -->
    <section class="profile-link-section" id="generate">
        <div class="container">
            <div class="profile-link-container">
                <h2>Get Followers Instantly</h2>
                <p>Paste your profile link and watch followers appear in real-time</p>
                
                <div class="platform-tabs">
                    <div class="platform-tab active" data-platform="instagram">
                        <i class="fab fa-instagram"></i>
                        <span>Instagram</span>
                    </div>
                    <div class="platform-tab" data-platform="tiktok">
                        <i class="fab fa-tiktok"></i>
                        <span>TikTok</span>
                    </div>
                    <div class="platform-tab" data-platform="youtube">
                        <i class="fab fa-youtube"></i>
                        <span>YouTube</span>
                    </div>
                </div>
                
                <div class="link-input-container">
                    <input type="text" class="link-input" id="profileLink" placeholder="Paste your Instagram profile URL here (e.g., https://instagram.com/yourusername)">
                    <button class="generate-btn" id="validateBtn">Validate Profile</button>
                </div>
                
                <div class="profile-preview" id="profilePreview">
                    <div class="profile-info">
                        <div class="profile-avatar" id="profileAvatar">
                            <i class="fab fa-instagram"></i>
                        </div>
                        <div class="profile-details">
                            <h3 id="profileName">@yourusername</h3>
                            <p id="profileBio">Your profile bio will appear here</p>
                        </div>
                    </div>
                    
                    <div class="service-options">
                        <div class="service-option" data-service="followers">
                            <div class="service-icon">
                                <i class="fas fa-users"></i>
                            </div>
                            <h4>500 Followers</h4>
                            <p>Get 500 real followers instantly</p>
                        </div>
                        <div class="service-option" data-service="likes">
                            <div class="service-icon">
                                <i class="fas fa-heart"></i>
                            </div>
                            <h4>1000 Likes</h4>
                            <p>Get 1000 likes on your posts instantly</p>
                        </div>
                        <div class="service-option" data-service="views">
                            <div class="service-icon">
                                <i class="fas fa-eye"></i>
                            </div>
                            <h4>5000 Views</h4>
                            <p>Get 5000 views on your videos instantly</p>
                        </div>
                    </div>
                    
                    <button class="generate-btn" id="startGeneration" style="width: 100%; margin-top: 20px;">Generate Instantly</button>
                </div>

                <!-- Instant Results Section -->
                <div class="instant-results" id="instantResults">
                    <div class="results-header">
                        <h3><i class="fas fa-bolt"></i> Generating Followers Instantly!</h3>
                        <p>Watch your followers count grow in real-time</p>
                    </div>
                    
                    <div class="counter-container">
                        <div class="counter">
                            <div class="counter-value" id="followersCount">0</div>
                            <div class="counter-label">Followers Added</div>
                        </div>
                        <div class="counter">
                            <div class="counter-value" id="likesCount">0</div>
                            <div class="counter-label">Likes Added</div>
                        </div>
                        <div class="counter">
                            <div class="counter-value" id="viewsCount">0</div>
                            <div class="counter-label">Views Added</div>
                        </div>
                    </div>
                    
                    <div class="live-feed" id="liveFeed">
                        <div class="feed-item">
                            <div class="feed-avatar">J</div>
                            <div class="feed-text">
                                <div class="feed-username">jessica_ray</div>
                                <div class="feed-action">started following you</div>
                            </div>
                            <div class="feed-time">just now</div>
                        </div>
                    </div>

                    <div class="completion-message" id="completionMessage">
                        <i class="fas fa-check-circle"></i>
                        <h3>Generation Complete!</h3>
                        <p>We've successfully added <span id="totalFollowers">500</span> followers to your profile.</p>
                        <p>Your new followers are visible on your profile RIGHT NOW!</p>
                        <div class="action-buttons">
                            <button class="generate-btn" id="generateMore">Generate More</button>
                            <button class="generate-btn" style="background: var(--success);">Check Your Profile</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Platform Tabs Functionality
        document.querySelectorAll('.platform-tab').forEach(tab => {
            tab.addEventListener('click', () => {
                document.querySelectorAll('.platform-tab').forEach(t => t.classList.remove('active'));
                tab.classList.add('active');
                
                // Update placeholder based on platform
                const platform = tab.getAttribute('data-platform');
                const placeholder = getPlaceholderForPlatform(platform);
                document.getElementById('profileLink').placeholder = placeholder;
                
                // Update profile avatar icon
                document.getElementById('profileAvatar').innerHTML = `<i class="fab fa-${platform}"></i>`;
            });
        });

        // Get placeholder text for platform
        function getPlaceholderForPlatform(platform) {
            switch(platform) {
                case 'instagram':
                    return 'Paste your Instagram profile URL (e.g., https://instagram.com/yourusername)';
                case 'tiktok':
                    return 'Paste your TikTok profile URL (e.g., https://tiktok.com/@yourusername)';
                case 'youtube':
                    return 'Paste your YouTube channel URL (e.g., https://youtube.com/c/yourchannel)';
                default:
                    return 'Paste your profile URL here';
            }
        }

        // Service Options Selection
        document.querySelectorAll('.service-option').forEach(option => {
            option.addEventListener('click', () => {
                document.querySelectorAll('.service-option').forEach(o => o.classList.remove('selected'));
                option.classList.add('selected');
            });
        });

        // Validate Profile Button
        document.getElementById('validateBtn').addEventListener('click', () => {
            const profileLink = document.getElementById('profileLink').value.trim();
            
            if (!profileLink) {
                alert('Please enter your profile URL');
                return;
            }
            
            // Show loading state
            const validateBtn = document.getElementById('validateBtn');
            validateBtn.textContent = 'Validating...';
            validateBtn.disabled = true;
            
            // Simulate validation process
            setTimeout(() => {
                // Extract username from URL
                const platform = document.querySelector('.platform-tab.active').getAttribute('data-platform');
                const username = extractUsername(profileLink, platform);
                
                if (username) {
                    // Show profile preview
                    document.getElementById('profileName').textContent = '@' + username;
                    document.getElementById('profileBio').textContent = getRandomBio();
                    document.getElementById('profilePreview').style.display = 'block';
                    
                    // Reset button
                    validateBtn.textContent = 'Validate Profile';
                    validateBtn.disabled = false;
                } else {
                    alert('Invalid profile URL. Please check the URL and try again.');
                    validateBtn.textContent = 'Validate Profile';
                    validateBtn.disabled = false;
                }
            }, 1000);
        });

        // Extract username from URL
        function extractUsername(url, platform) {
            // Simple extraction logic for demonstration
            if (url.includes('instagram.com')) {
                const parts = url.split('/');
                return parts[parts.length - 1] || 'instagram_user';
            }
            if (url.includes('tiktok.com')) {
                const match = url.match(/@([^/?]+)/);
                return match ? match[1] : 'tiktok_user';
            }
            if (url.includes('youtube.com')) {
                return 'youtube_channel';
            }
            return 'user_' + Math.floor(Math.random() * 1000);
        }

        // Get random bio
        function getRandomBio() {
            const bios = [
                "Digital creator | Photography enthusiast",
                "Just living my best life 🌟",
                "Professional content creator",
                "Travel • Food • Lifestyle",
                "Making the world a better place",
                "Tech geek and coffee lover",
                "Fitness enthusiast | Healthy lifestyle",
                "Artist and dreamer"
            ];
            return bios[Math.floor(Math.random() * bios.length)];
        }

        // Start Generation Button
        document.getElementById('startGeneration').addEventListener('click', () => {
            const selectedService = document.querySelector('.service-option.selected');
            
            if (!selectedService) {
                alert('Please select a service (followers, likes, or views)');
                return;
            }
            
            // Hide profile preview and show instant results
            document.getElementById('profilePreview').style.display = 'none';
            document.getElementById('instantResults').style.display = 'block';
            
            // Start the instant generation simulation
            startInstantGeneration();
        });

        // Start instant generation
        function startInstantGeneration() {
            const followersCount = document.getElementById('followersCount');
            const likesCount = document.getElementById('likesCount');
            const viewsCount = document.getElementById('viewsCount');
            const liveFeed = document.getElementById('liveFeed');
            const completionMessage = document.getElementById('completionMessage');
            const totalFollowers = document.getElementById('totalFollowers');
            
            // Reset counters
            followersCount.textContent = '0';
            likesCount.textContent = '0';
            viewsCount.textContent = '0';
            liveFeed.innerHTML = '';
            completionMessage.style.display = 'none';
            
            const selectedService = document.querySelector('.service-option.selected').getAttribute('data-service');
            let targetCount = 0;
            
            // Set target based on service
            if (selectedService === 'followers') {
                targetCount = 500;
            } else if (selectedService === 'likes') {
                targetCount = 1000;
            } else if (selectedService === 'views') {
                targetCount = 5000;
            }
            
            totalFollowers.textContent = targetCount;
            
            let currentCount = 0;
            const interval = setInterval(() => {
                // Increase counters
                currentCount += Math.floor(Math.random() * 10) + 5;
                
                if (currentCount >= targetCount) {
                    currentCount = targetCount;
                    clearInterval(interval);
                    
                    // Show completion message after a short delay
                    setTimeout(() => {
                        completionMessage.style.display = 'block';
                    }, 500);
                }
                
                // Update counters based on service
                if (selectedService === 'followers') {
                    followersCount.textContent = currentCount;
                    addFollowerToFeed();
                } else if (selectedService === 'likes') {
                    likesCount.textContent = currentCount;
                    addLikeToFeed();
                } else if (selectedService === 'views') {
                    viewsCount.textContent = currentCount;
                    addViewToFeed();
                }
            }, 50);
        }

        // Add follower to live feed
        function addFollowerToFeed() {
            const liveFeed = document.getElementById('liveFeed');
            const usernames = [
                "jessica_ray", "mike_tyson", "sarah_j", "travel_diaries", 
                "foodie_adventures", "tech_guru", "fitness_freak", "art_lover",
                "music_maniac", "bookworm", "nature_photographer", "fashion_icon",
                "gaming_pro", "pet_lover", "movie_buff", "fitness_model"
            ];
            
            const username = usernames[Math.floor(Math.random() * usernames.length)];
            const feedItem = document.createElement('div');
            feedItem.className = 'feed-item';
            
            const avatar = document.createElement('div');
            avatar.className = 'feed-avatar';
            avatar.textContent = username.charAt(0).toUpperCase();
            
            const feedText = document.createElement('div');
            feedText.className = 'feed-text';
            
            const usernameEl = document.createElement('div');
            usernameEl.className = 'feed-username';
            usernameEl.textContent = username;
            
            const action = document.createElement('div');
            action.className = 'feed-action';
            action.textContent = 'started following you';
            
            const time = document.createElement('div');
            time.className = 'feed-time';
            time.textContent = 'just now';
            
            feedText.appendChild(usernameEl);
            feedText.appendChild(action);
            feedItem.appendChild(avatar);
            feedItem.appendChild(feedText);
            feedItem.appendChild(time);
            
            // Add to top of feed
            liveFeed.insertBefore(feedItem, liveFeed.firstChild);
            
            // Limit feed items
            if (liveFeed.children.length > 10) {
                liveFeed.removeChild(liveFeed.lastChild);
            }
        }

        // Add like to live feed
        function addLikeToFeed() {
            const liveFeed = document.getElementById('liveFeed');
            const usernames = [
                "jessica_ray", "mike_tyson", "sarah_j", "travel_diaries", 
                "foodie_adventures", "tech_guru", "fitness_freak", "art_lover"
            ];
            
            const username = usernames[Math.floor(Math.random() * usernames.length)];
            const feedItem = document.createElement('div');
            feedItem.className = 'feed-item';
            
            const avatar = document.createElement('div');
            avatar.className = 'feed-avatar';
            avatar.textContent = username.charAt(0).toUpperCase();
            
            const feedText = document.createElement('div');
            feedText.className = 'feed-text';
            
            const usernameEl = document.createElement('div');
            usernameEl.className = 'feed-username';
            usernameEl.textContent = username;
            
            const action = document.createElement('div');
            action.className = 'feed-action';
            action.textContent = 'liked your post';
            
            const time = document.createElement('div');
            time.className = 'feed-time';
            time.textContent = 'just now';
            
            feedText.appendChild(usernameEl);
            feedText.appendChild(action);
            feedItem.appendChild(avatar);
            feedItem.appendChild(feedText);
            feedItem.appendChild(time);
            
            // Add to top of feed
            liveFeed.insertBefore(feedItem, liveFeed.firstChild);
            
            // Limit feed items
            if (liveFeed.children.length > 10) {
                liveFeed.removeChild(liveFeed.lastChild);
            }
        }

        // Add view to live feed
        function addViewToFeed() {
            const liveFeed = document.getElementById('liveFeed');
            const usernames = [
                "user_123", "viewer_456", "watcher_789", "video_fan", 
                "content_lover", "stream_buddy", "media_follower"
            ];
            
            const username = usernames[Math.floor(Math.random() * usernames.length)];
            const feedItem = document.createElement('div');
            feedItem.className = 'feed-item';
            
            const avatar = document.createElement('div');
            avatar.className = 'feed-avatar';
            avatar.textContent = username.charAt(0).toUpperCase();
            
            const feedText = document.createElement('div');
            feedText.className = 'feed-text';
            
            const usernameEl = document.createElement('div');
            usernameEl.className = 'feed-username';
            usernameEl.textContent = username;
            
            const action = document.createElement('div');
            action.className = 'feed-action';
            action.textContent = 'watched your video';
            
            const time = document.createElement('div');
            time.className = 'feed-time';
            time.textContent = 'just now';
            
            feedText.appendChild(usernameEl);
            feedText.appendChild(action);
            feedItem.appendChild(avatar);
            feedItem.appendChild(feedText);
            feedItem.appendChild(time);
            
            // Add to top of feed
            liveFeed.insertBefore(feedItem, liveFeed.firstChild);
            
            // Limit feed items
            if (liveFeed.children.length > 10) {
                liveFeed.removeChild(liveFeed.lastChild);
            }
        }

        // Generate More Button
        document.getElementById('generateMore').addEventListener('click', () => {
            document.getElementById('instantResults').style.display = 'none';
            document.getElementById('profilePreview').style.display = 'block';
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a, .hero-buttons a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                if (this.getAttribute('href').startsWith('#')) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
