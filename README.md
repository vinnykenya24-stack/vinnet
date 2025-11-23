<VIEWS>
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

        /* How It Works Section */
        .steps-container {
            display: flex;
            justify-content: space-between;
            max-width: 900px;
            margin: 0 auto;
            position: relative;
        }

        .steps-container::before {
            content: '';
            position: absolute;
            top: 40px;
            left: 10%;
            right: 10%;
            height: 3px;
            background: var(--primary);
            z-index: 1;
        }

        .step {
            text-align: center;
            position: relative;
            z-index: 2;
            flex: 1;
        }

        .step-number {
            width: 80px;
            height: 80px;
            background: white;
            border: 3px solid var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            margin: 0 auto 25px;
        }

        .step h3 {
            margin-bottom: 15px;
        }

        .step p {
            color: var(--gray);
            max-width: 250px;
            margin: 0 auto;
        }

        /* Testimonials Section */
        .testimonials {
            background: linear-gradient(135deg, #6C63FF 0%, #4A44C6 100%);
            color: white;
            padding: 100px 0;
            border-radius: 30px;
        }

        .testimonials .section-header h2,
        .testimonials .section-header p {
            color: white;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 30px;
        }

        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: white;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-weight: bold;
        }

        .author-info h4 {
            margin-bottom: 5px;
        }

        .author-info p {
            opacity: 0.8;
            font-size: 0.9rem;
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
            .steps-container {
                flex-direction: column;
                gap: 50px;
            }

            .steps-container::before {
                display: none;
            }

            .hero h1 {
                font-size: 2.8rem;
            }

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
                    <li><a href="#testimonials">Testimonials</a></li>
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
                    <input type="text" class="link-input" id="profileLink" placeholder="Paste your profile URL here (e.g., https://instagram.com/yourusername)">
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
                            <p>Get real followers for your profile</p>
                        </div>
                        <div class="service-option" data-service="likes">
                            <div class="service-icon">
                                <i class="fas fa-heart"></i>
                            </div>
                            <h4>Likes</h4>
                            <p>Increase engagement with more likes</p>
                        </div>
                        <div class="service-option" data-service="views">
                            <div class="service-icon">
                                <i class="fas fa-eye"></i>
                            </div>
                            <h4>Views</h4>
                            <p>Boost your video view count</p>
                        </div>
                        <div class="service-option" data-service="comments">
                            <div class="service-icon">
                                <i class="fas fa-comment"></i>
                            </div>
                            <h4>Comments</h4>
                            <p>Get authentic comments on your posts</p>
                        </div>
                    </div>
                    
                    <button class="generate-btn" id="startGeneration" style="width: 100%; margin-top: 20px;">Start Generation</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="section" id="services">
        <div class="container">
            <div class="section-header">
                <h2>Our Social Media Services</h2>
                <p>We offer a variety of services to boost your social media presence across all major platforms</p>
            </div>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fab fa-instagram"></i>
                    </div>
                    <h3>Instagram Growth</h3>
                    <p>Increase your Instagram followers, likes, and comments with our premium service</p>
                    <ul class="service-features">
                        <li><i class="fas fa-check"></i> Real Followers</li>
                        <li><i class="fas fa-check"></i> High-Quality Likes</li>
                        <li><i class="fas fa-check"></i> Engaging Comments</li>
                        <li><i class="fas fa-check"></i> Story Views</li>
                        <li><i class="fas fa-check"></i> 24/7 Support</li>
                    </ul>
                    <a href="#generate" class="cta-button">Generate Now</a>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fab fa-tiktok"></i>
                    </div>
                    <h3>TikTok Promotion</h3>
                    <p>Boost your TikTok profile with followers, likes, views, and shares</p>
                    <ul class="service-features">
                        <li><i class="fas fa-check"></i> TikTok Followers</li>
                        <li><i class="fas fa-check"></i> Video Likes</li>
                        <li><i class="fas fa-check"></i> Video Views</li>
                        <li><i class="fas fa-check"></i> Shares</li>
                        <li><i class="fas fa-check"></i> Profile Visits</li>
                    </ul>
                    <a href="#generate" class="cta-button">Generate Now</a>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fab fa-youtube"></i>
                    </div>
                    <h3>YouTube Growth</h3>
                    <p>Increase your YouTube subscribers, views, likes, and comments</p>
                    <ul class="service-features">
                        <li><i class="fas fa-check"></i> Real Subscribers</li>
                        <li><i class="fas fa-check"></i> High Retention Views</li>
                        <li><i class="fas fa-check"></i> Video Likes</li>
                        <li><i class="fas fa-check"></i> Comments</li>
                        <li><i class="fas fa-check"></i> Watch Time</li>
                    </ul>
                    <a href="#generate" class="cta-button">Generate Now</a>
                </div>
            </div>
        </div>
    </section>

    <!-- How It Works Section -->
    <section class="section" id="how-it-works">
        <div class="container">
            <div class="section-header">
                <h2>How It Works</h2>
                <p>Getting started with our service is quick and easy</p>
            </div>
            <div class="steps-container">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Paste Profile Link</h3>
                    <p>Copy and paste your social media profile URL</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Select Service</h3>
                    <p>Choose followers, likes, views, or comments</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Validate Profile</h3>
                    <p>Our system verifies your profile and prepares the service</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>See Results</h3>
                    <p>Watch as your followers, likes, or views start increasing</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <div class="section-header">
                <h2>What Our Clients Say</h2>
                <p>Don't just take our word for it - hear from some of our satisfied customers</p>
            </div>
            <div class="testimonials-grid">
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "I was skeptical at first, but SocialBoost Pro delivered exactly what they promised. My Instagram following grew by 2,000 real followers in just one week!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">SM</div>
                        <div class="author-info">
                            <h4>Sarah Mitchell</h4>
                            <p>Influencer</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "As a small business owner, social media presence is crucial. Thanks to SocialBoost Pro, my engagement has skyrocketed and I'm reaching more customers than ever."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">JR</div>
                        <div class="author-info">
                            <h4>James Rodriguez</h4>
                            <p>Business Owner</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "The TikTok promotion service helped my videos go viral. I gained 10,000 followers in a month and now brands are reaching out to me for collaborations!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">AP</div>
                        <div class="author-info">
                            <h4>Alexis Parker</h4>
                            <p>Content Creator</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col">
                    <h3>SocialBoost Pro</h3>
                    <p>Helping individuals and businesses grow their social media presence since 2020.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                <div class="footer-col">
                    <h3>Services</h3>
                    <ul>
                        <li><a href="#generate">Instagram Growth</a></li>
                        <li><a href="#generate">TikTok Promotion</a></li>
                        <li><a href="#generate">YouTube Growth</a></li>
                        <li><a href="#generate">Twitter Boost</a></li>
                        <li><a href="#generate">Facebook Likes</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>Company</h3>
                    <ul>
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Careers</a></li>
                        <li><a href="#">Affiliate Program</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>Support</h3>
                    <ul>
                        <li><a href="#">Help Center</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2023 SocialBoost Pro. All rights reserved.
            </div>
        </div>
    </footer>

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
            
            const service = selectedService.getAttribute('data-service');
            const platform = document.querySelector('.platform-tab.active').getAttribute('data-platform');
            const username = document.getElementById('profileName').textContent;
            
            alert(`Starting ${service} generation for ${username} on ${platform}. This is a demonstration - in a real application, this would connect to a backend service.`);
            
            // In a real application, this would make an API call to start the generation process
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

        // Add animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = 1;
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe elements for animation
        document.querySelectorAll('.service-card, .step, .testimonial-card, .service-option').forEach(el => {
            el.style.opacity = 0;
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
