<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FollowerBoost Pro | Generate Followers</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            color: white;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            padding: 30px 0;
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto 30px;
        }
        
        .dashboard {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .follower-counter {
            flex: 1;
            min-width: 300px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .counter-value {
            font-size: 4rem;
            font-weight: bold;
            margin: 20px 0;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }
        
        .platform-selector {
            flex: 1;
            min-width: 300px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .platforms {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 20px;
        }
        
        .platform {
            flex: 1;
            min-width: 120px;
            background: rgba(255, 255, 255, 0.15);
            border-radius: 15px;
            padding: 15px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .platform:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateY(-5px);
        }
        
        .platform.active {
            background: rgba(255, 255, 255, 0.3);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .platform-icon {
            font-size: 2rem;
            margin-bottom: 10px;
        }
        
        .generator {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 40px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .slider-container {
            margin: 30px 0;
        }
        
        .slider {
            width: 100%;
            height: 15px;
            -webkit-appearance: none;
            appearance: none;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            outline: none;
        }
        
        .slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background: white;
            cursor: pointer;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
        }
        
        .slider-labels {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
            font-size: 0.9rem;
        }
        
        .generate-btn {
            display: block;
            width: 100%;
            padding: 18px;
            background: linear-gradient(to right, #ff8a00, #ff2070);
            color: white;
            border: none;
            border-radius: 15px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 138, 0, 0.4);
        }
        
        .generate-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 138, 0, 0.6);
        }
        
        .generate-btn:active {
            transform: translateY(1px);
        }
        
        .results {
            display: none;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 40px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.2);
            text-align: center;
        }
        
        .results h2 {
            margin-bottom: 20px;
        }
        
        .progress-bar {
            height: 20px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            margin: 30px 0;
            overflow: hidden;
        }
        
        .progress {
            height: 100%;
            background: linear-gradient(to right, #00b09b, #96c93d);
            width: 0%;
            transition: width 0.5s ease;
        }
        
        .follower-list {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
            margin-top: 20px;
        }
        
        .follower {
            background: rgba(255, 255, 255, 0.15);
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
            background: rgba(255, 255, 255, 0.3);
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .features {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 40px;
        }
        
        .feature {
            flex: 1;
            min-width: 250px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .feature-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }
        
        footer {
            text-align: center;
            padding: 20px;
            font-size: 0.9rem;
            opacity: 0.7;
        }
        
        @media (max-width: 768px) {
            .dashboard {
                flex-direction: column;
            }
            
            h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>FollowerBoost Pro</h1>
            <p class="subtitle">Generate real-looking followers for your social media profiles. Boost your online presence instantly!</p>
        </header>
        
        <div class="dashboard">
            <div class="follower-counter">
                <h2>Current Followers</h2>
                <div class="counter-value" id="currentFollowers">1,247</div>
                <p>Your follower count will update here</p>
            </div>
            
            <div class="platform-selector">
                <h2>Select Platform</h2>
                <div class="platforms">
                    <div class="platform active" data-platform="instagram">
                        <div class="platform-icon">📷</div>
                        <div>Instagram</div>
                    </div>
                    <div class="platform" data-platform="twitter">
                        <div class="platform-icon">🐦</div>
                        <div>Twitter</div>
                    </div>
                    <div class="platform" data-platform="tiktok">
                        <div class="platform-icon">🎵</div>
                        <div>TikTok</div>
                    </div>
                    <div class="platform" data-platform="youtube">
                        <div class="platform-icon">▶️</div>
                        <div>YouTube</div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="generator">
            <h2>Generate Followers</h2>
            <p>Select how many followers you want to generate</p>
            
            <div class="slider-container">
                <input type="range" min="100" max="10000" value="1000" step="100" class="slider" id="followerSlider">
                <div class="slider-labels">
                    <span>100</span>
                    <span>5,000</span>
                    <span>10,000</span>
                </div>
            </div>
            
            <div style="text-align: center; margin: 20px 0; font-size: 1.5rem;">
                <span id="followerCount">1,000</span> followers
            </div>
            
            <button class="generate-btn" id="generateBtn">Generate Followers Now</button>
        </div>
        
        <div class="results" id="results">
            <h2>Generating Followers...</h2>
            <div class="progress-bar">
                <div class="progress" id="progressBar"></div>
            </div>
            <p id="progressText">Starting follower generation process...</p>
            
            <div class="follower-list" id="followerList">
                <!-- Followers will be generated here -->
            </div>
        </div>
        
        <div class="features">
            <div class="feature">
                <div class="feature-icon">⚡</div>
                <h3>Instant Results</h3>
                <p>See your follower count increase in real-time with our advanced generation technology.</p>
            </div>
            <div class="feature">
                <div class="feature-icon">🔒</div>
                <h3>Safe & Secure</h3>
                <p>Our methods comply with platform policies to ensure your account remains secure.</p>
            </div>
            <div class="feature">
                <div class="feature-icon">👥</div>
                <h3>Real-looking Profiles</h3>
                <p>Generated followers have realistic profile pictures and activity patterns.</p>
            </div>
        </div>
        
        <footer>
            <p>FollowerBoost Pro &copy; 2023 | This is a simulation for demonstration purposes only</p>
        </footer>
    </div>

    <script>
        // DOM Elements
        const followerSlider = document.getElementById('followerSlider');
        const followerCount = document.getElementById('followerCount');
        const currentFollowers = document.getElementById('currentFollowers');
        const generateBtn = document.getElementById('generateBtn');
        const results = document.getElementById('results');
        const progressBar = document.getElementById('progressBar');
        const progressText = document.getElementById('progressText');
        const followerList = document.getElementById('followerList');
        const platforms = document.querySelectorAll('.platform');
        
        // Update follower count display when slider changes
        followerSlider.addEventListener('input', function() {
            const count = parseInt(this.value);
            followerCount.textContent = count.toLocaleString();
        });
        
        // Platform selection
        platforms.forEach(platform => {
            platform.addEventListener('click', function() {
                platforms.forEach(p => p.classList.remove('active'));
                this.classList.add('active');
            });
        });
        
        // Generate followers
        generateBtn.addEventListener('click', function() {
            const count = parseInt(followerSlider.value);
            const currentCount = parseInt(currentFollowers.textContent.replace(/,/g, ''));
            const targetCount = currentCount + count;
            
            // Show results section
            results.style.display = 'block';
            progressBar.style.width = '0%';
            progressText.textContent = 'Starting follower generation process...';
            followerList.innerHTML = '';
            
            // Scroll to results
            results.scrollIntoView({ behavior: 'smooth' });
            
            // Simulate generation process
            let progress = 0;
            const interval = setInterval(() => {
                progress += 1;
                progressBar.style.width = `${progress}%`;
                
                if (progress <= 30) {
                    progressText.textContent = 'Connecting to server...';
                } else if (progress <= 60) {
                    progressText.textContent = 'Generating follower profiles...';
                } else if (progress <= 90) {
                    progressText.textContent = 'Adding followers to your account...';
                } else {
                    progressText.textContent = 'Finalizing...';
                }
                
                // Add some random followers to the list during generation
                if (progress % 15 === 0 && progress < 100) {
                    addFollowerToDisplay();
                }
                
                if (progress >= 100) {
                    clearInterval(interval);
                    progressText.textContent = `Successfully added ${count.toLocaleString()} followers!`;
                    
                    // Update the follower count
                    animateValue(currentFollowers, currentCount, targetCount, 2000);
                    
                    // Add remaining followers to display
                    const followersToAdd = Math.min(20, count);
                    for (let i = 0; i < followersToAdd; i++) {
                        setTimeout(() => addFollowerToDisplay(), i * 100);
                    }
                }
            }, 30);
        });
        
        // Function to add a follower to the display list
        function addFollowerToDisplay() {
            const usernames = [
                "jessica_ray", "mike_tyson", "sarah_j", "travel_diaries", 
                "foodie_adventures", "tech_guru", "fitness_freak", "art_lover",
                "music_maniac", "bookworm", "nature_photographer", "fashion_icon",
                "gaming_pro", "pet_lover", "movie_buff", "fitness_model",
                "coding_ninja", "business_mind", "yoga_teacher", "chef_life"
            ];
            
            const follower = document.createElement('div');
            follower.className = 'follower';
            
            const avatar = document.createElement('div');
            avatar.className = 'follower-avatar';
            
            const name = document.createElement('div');
            name.textContent = usernames[Math.floor(Math.random() * usernames.length)];
            
            follower.appendChild(avatar);
            follower.appendChild(name);
            followerList.appendChild(follower);
        }
        
        // Function to animate the counter
        function animateValue(element, start, end, duration) {
            let startTimestamp = null;
            const step = (timestamp) => {
                if (!startTimestamp) startTimestamp = timestamp;
                const progress = Math.min((timestamp - startTimestamp) / duration, 1);
                const value = Math.floor(progress * (end - start) + start);
                element.textContent = value.toLocaleString();
                if (progress < 1) {
                    window.requestAnimationFrame(step);
                }
            };
            window.requestAnimationFrame(step);
        }
    </script>
</body>
</html>
