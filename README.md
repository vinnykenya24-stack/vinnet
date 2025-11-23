<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SocialBoost Pro | Generate Followers & Likes</title>
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

        /* Generation Progress Section */
        .generation-progress {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-top: 30px;
            display: none;
            text-align: center;
        }

        .progress-header {
            margin-bottom: 30px;
        }

        .progress-bar {
            height: 20px;
            background: #eee;
            border-radius: 10px;
            margin-bottom: 20px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: var(--primary);
            width: 0%;
            transition: width 0.5s ease;
            border-radius: 10px;
        }

        .progress-text {
            margin-bottom: 30px;
            font-size: 1.1rem;
        }

        .followers-added {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
            margin-top: 20px;
        }

        .follower-item {
            background: var(--light);
            border-radius: 10px;
            padding: 10px 15px;
            display: flex;
            align-items: center;
            gap: 10px;
            animation: fadeIn 0.5s ease;
        }

        .follower-avatar {
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

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .completion-message {
            display: none;
            padding: 30px;
            background: rgba(46, 204, 113, 0.1);
            border-radius: 15px;
            margin-top: 30px;
            text-align: center;
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

        /* Responsive Design */
        @media (max-width: 992px) {
            .link-input-container {
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
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-rocket"></i>
                <span>SocialBoost Pro</span>
            </div>
            <nav>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#generate">Generate</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#how-it-works">How It Works</a></li>
                </ul>
            </nav>
            <a href="#generate" class="cta-button">Get Started</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1>Boost Your Social Media Presence Instantly</h1>
            <p>Get real followers, likes, views, and comments to grow your social media accounts organically. Start seeing results in minutes!</p>
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
                <h2>Generate Followers & Likes</h2>
                <p>Paste your profile link below and select the service you need</p>
                
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
                    <div class="platform-tab" data-platform="twitter">
                        <i class="fab fa-twitter"></i>
                        <span>Twitter</span>
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
                            <h4>Followers</h4>
                            <p>Get 100-500 real followers</p>
                        </div>
                        <div class="service-option" data-service="likes">
                            <div class="service-icon">
                                <i class="fas fa-heart"></i>
                            </div>
                            <h4>Likes</h4>
                            <p>Get 200-1000 likes on your posts</p>
                        </div>
                        <div class="service-option" data-service="views">
                            <div class="service-icon">
                                <i class="fas fa-eye"></i>
                            </div>
                            <h4>Views</h4>
                            <p>Get 500-5000 views on your videos</p>
                        </div>
                        <div class="service-option" data-service="comments">
                            <div class="service-icon">
                                <i class="fas fa-comment"></i>
                            </div>
                            <h4>Comments</h4>
                            <p>Get 50-200 authentic comments</p>
                        </div>
                    </div>
                    
                    <button class="generate-btn" id="startGeneration" style="width: 100%; margin-top: 20px;">Start Generating Now</button>
                </div>

                <!-- Generation Progress Section -->
                <div class="generation-progress" id="generationProgress">
                    <div class="progress-header">
                        <h3>Generating Followers</h3>
                        <p>We're adding followers to your profile. This may take a few minutes.</p>
                    </div>
                    
                    <div class="progress-bar">
                        <div class="progress-fill" id="progressFill"></div>
                    </div>
                    
                    <div class="progress-text" id="progressText">Initializing generation process...</div>
                    
                    <div class="followers-added" id="followersAdded">
                        <!-- Followers will be added here dynamically -->
                    </div>

                    <div class="completion-message" id="completionMessage">
                        <i class="fas fa-check-circle"></i>
                        <h3>Generation Complete!</h3>
                        <p>We've successfully added <span id="followersCount">0</span> followers to your profile.</p>
                        <p>Your new followers will appear within the next 24 hours.</p>
                        <button class="generate-btn" id="generateMore" style="margin-top: 20px;">Generate More Followers</button>
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
                case 'twitter':
                    return 'Paste your Twitter profile URL (e.g., https://twitter.com/yourusername)';
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
            }, 1500);
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
            if (url.includes('twitter.com')) {
                const parts = url.split('/');
                return parts[parts.length - 1] || 'twitter_user';
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
                alert('Please select a service (followers, likes, views, or comments)');
                return;
            }
            
            // Hide profile preview and show generation progress
            document.getElementById('profilePreview').style.display = 'none';
            document.getElementById('generationProgress').style.display = 'block';
            
            // Start the generation simulation
            simulateGeneration();
        });

        // Simulate the generation process
        function simulateGeneration() {
            const progressFill = document.getElementById('progressFill');
            const progressText = document.getElementById('progressText');
            const followersAdded = document.getElementById('followersAdded');
            const completionMessage = document.getElementById('completionMessage');
            const followersCount = document.getElementById('followersCount');
            
            let progress = 0;
            let followersGenerated = 0;
            const targetFollowers = 250; // Target number of followers to generate
            
            // Reset
            progressFill.style.width = '0%';
            followersAdded.innerHTML = '';
            completionMessage.style.display = 'none';
            
            // Start the progress simulation
            const interval = setInterval(() => {
                progress += 1;
                progressFill.style.width = `${progress}%`;
                
                // Update progress text based on progress
                if (progress <= 20) {
                    progressText.textContent = 'Connecting to social media API...';
                } else if (progress <= 40) {
                    progressText.textContent = 'Setting up follower generation...';
                } else if (progress <= 60) {
                    progressText.textContent = 'Generating follower profiles...';
                } else if (progress <= 80) {
                    progressText.textContent = 'Adding followers to your account...';
                } else {
                    progressText.textContent = 'Finalizing...';
                }
                
                // Add followers during the process
                if (progress % 5 === 0 && followersGenerated < targetFollowers) {
                    const followersToAdd = Math.min(10, targetFollowers - followersGenerated);
                    addFollowers(followersToAdd);
                    followersGenerated += followersToAdd;
                }
                
                // Complete the process
                if (progress >= 100) {
                    clearInterval(interval);
                    progressText.textContent = 'Generation complete!';
                    
                    // Show completion message after a short delay
                    setTimeout(() => {
                        completionMessage.style.display = 'block';
                        followersCount.textContent = followersGenerated;
                    }, 1000);
                }
            }, 50);
        }

        // Add followers to the display
        function addFollowers(count) {
            const followersAdded = document.getElementById('followersAdded');
            const usernames = [
                "jessica_ray", "mike_tyson", "sarah_j", "travel_diaries", 
                "foodie_adventures", "tech_guru", "fitness_freak", "art_lover",
                "music_maniac", "bookworm", "nature_photographer", "fashion_icon",
                "gaming_pro", "pet_lover", "movie_buff", "fitness_model",
                "coding_ninja", "business_mind", "yoga_teacher", "chef_life"
            ];
            
            for (let i = 0; i < count; i++) {
                const username = usernames[Math.floor(Math.random() * usernames.length)];
                const followerItem = document.createElement('div');
                followerItem.className = 'follower-item';
                
                const avatar = document.createElement('div');
                avatar.className = 'follower-avatar';
                avatar.textContent = username.charAt(0).toUpperCase();
                
                const name = document.createElement('div');
                name.textContent = username;
                
                followerItem.appendChild(avatar);
                followerItem.appendChild(name);
                followersAdded.appendChild(followerItem);
            }
        }

        // Generate More Button
        document.getElementById('generateMore').addEventListener('click', () => {
            document.getElementById('generationProgress').style.display = 'none';
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
