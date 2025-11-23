<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SocialBoost Pro | Social Media Growth Services</title>
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

        .auth-buttons {
            display: flex;
            gap: 15px;
        }

        .btn {
            padding: 10px 25px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-outline {
            border: 2px solid var(--primary);
            color: var(--primary);
            background: transparent;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
            border: 2px solid var(--primary);
        }

        .btn:hover {
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

        .service-icon {
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

        /* Pricing Section */
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .pricing-card {
            background: white;
            border-radius: 15px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            position: relative;
            transition: transform 0.3s ease;
        }

        .pricing-card:hover {
            transform: translateY(-10px);
        }

        .pricing-card.popular {
            border: 2px solid var(--primary);
            transform: scale(1.05);
        }

        .popular-badge {
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--primary);
            color: white;
            padding: 5px 20px;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 600;
        }

        .pricing-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .price {
            font-size: 3rem;
            font-weight: 700;
            color: var(--primary);
            margin: 20px 0;
        }

        .price span {
            font-size: 1rem;
            color: var(--gray);
        }

        .pricing-features {
            list-style: none;
            margin: 30px 0;
            text-align: left;
        }

        .pricing-features li {
            padding: 10px 0;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .pricing-features i {
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

        /* FAQ Section */
        .faq-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .faq-item {
            background: white;
            border-radius: 10px;
            margin-bottom: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .faq-question {
            padding: 20px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            font-weight: 600;
        }

        .faq-answer {
            padding: 0 30px;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease, padding 0.3s ease;
        }

        .faq-item.active .faq-answer {
            padding: 0 30px 20px;
            max-height: 200px;
        }

        .faq-item.active .faq-toggle i {
            transform: rotate(180deg);
        }

        .faq-toggle {
            transition: transform 0.3s ease;
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

            .btn {
                width: 100%;
                max-width: 250px;
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
                    <li><a href="#services">Services</a></li>
                    <li><a href="#pricing">Pricing</a></li>
                    <li><a href="#how-it-works">How It Works</a></li>
                    <li><a href="#testimonials">Testimonials</a></li>
                </ul>
            </nav>
            <div class="auth-buttons">
                <a href="#" class="btn btn-outline">Login</a>
                <a href="#" class="btn btn-primary">Sign Up</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1>Boost Your Social Media Presence Instantly</h1>
            <p>Get real followers, likes, views, and comments to grow your social media accounts organically. Start seeing results in minutes!</p>
            <div class="hero-buttons">
                <a href="#services" class="btn btn-light">Our Services</a>
                <a href="#pricing" class="btn btn-outline" style="border-color: white; color: white;">View Pricing</a>
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
                    <a href="#" class="btn btn-primary">Get Started</a>
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
                    <a href="#" class="btn btn-primary">Get Started</a>
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
                    <a href="#" class="btn btn-primary">Get Started</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section class="section" id="pricing">
        <div class="container">
            <div class="section-header">
                <h2>Affordable Pricing Plans</h2>
                <p>Choose the plan that works best for your needs and budget</p>
            </div>
            <div class="pricing-grid">
                <div class="pricing-card">
                    <h3>Starter</h3>
                    <div class="price">$9.99<span>/month</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> 500 Followers</li>
                        <li><i class="fas fa-check"></i> 1,000 Likes</li>
                        <li><i class="fas fa-check"></i> 24/7 Support</li>
                        <li><i class="fas fa-check"></i> 1 Social Platform</li>
                        <li><i class="fas fa-times"></i> Priority Delivery</li>
                    </ul>
                    <a href="#" class="btn btn-outline">Select Plan</a>
                </div>
                <div class="pricing-card popular">
                    <div class="popular-badge">Most Popular</div>
                    <h3>Professional</h3>
                    <div class="price">$24.99<span>/month</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> 2,500 Followers</li>
                        <li><i class="fas fa-check"></i> 5,000 Likes</li>
                        <li><i class="fas fa-check"></i> 24/7 Support</li>
                        <li><i class="fas fa-check"></i> 3 Social Platforms</li>
                        <li><i class="fas fa-check"></i> Priority Delivery</li>
                    </ul>
                    <a href="#" class="btn btn-primary">Select Plan</a>
                </div>
                <div class="pricing-card">
                    <h3>Business</h3>
                    <div class="price">$49.99<span>/month</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> 10,000 Followers</li>
                        <li><i class="fas fa-check"></i> 25,000 Likes</li>
                        <li><i class="fas fa-check"></i> 24/7 Support</li>
                        <li><i class="fas fa-check"></i> All Social Platforms</li>
                        <li><i class="fas fa-check"></i> Priority Delivery</li>
                    </ul>
                    <a href="#" class="btn btn-outline">Select Plan</a>
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
                    <h3>Select Service</h3>
                    <p>Choose the social media platform and service you want to boost</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Provide Details</h3>
                    <p>Enter your account details and the quantity you want to purchase</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Make Payment</h3>
                    <p>Complete the secure payment process using your preferred method</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>See Results</h3>
                    <p>Watch as your followers, likes, or views start increasing rapidly</p>
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

    <!-- FAQ Section -->
    <section class="section">
        <div class="container">
            <div class="section-header">
                <h2>Frequently Asked Questions</h2>
                <p>Find answers to the most common questions about our services</p>
            </div>
            <div class="faq-container">
                <div class="faq-item">
                    <div class="faq-question">
                        <span>Are the followers real people?</span>
                        <div class="faq-toggle"><i class="fas fa-chevron-down"></i></div>
                    </div>
                    <div class="faq-answer">
                        <p>Yes, we provide real followers from active social media users. We do not use bots or fake accounts to inflate your numbers.</p>
                    </div>
                </div>
                <div class="faq-item">
                    <div class="faq-question">
                        <span>How quickly will I see results?</span>
                        <div class="faq-toggle"><i class="fas fa-chevron-down"></i></div>
                    </div>
                    <div class="faq-answer">
                        <p>Most clients start seeing results within a few hours of placing an order, with the full delivery typically completed within 24-72 hours depending on the service and quantity.</p>
                    </div>
                </div>
                <div class="faq-item">
                    <div class="faq-question">
                        <span>Is my account safe?</span>
                        <div class="faq-toggle"><i class="fas fa-chevron-down"></i></div>
                    </div>
                    <div class="faq-answer">
                        <p>Absolutely. We use secure methods that comply with all platform terms of service. Your account security is our top priority.</p>
                    </div>
                </div>
                <div class="faq-item">
                    <div class="faq-question">
                        <span>What payment methods do you accept?</span>
                        <div class="faq-toggle"><i class="fas fa-chevron-down"></i></div>
                    </div>
                    <div class="faq-answer">
                        <p>We accept all major credit cards, PayPal, and various cryptocurrencies for your convenience.</p>
                    </div>
                </div>
                <div class="faq-item">
                    <div class="faq-question">
                        <span>Do you offer refunds?</span>
                        <div class="faq-toggle"><i class="fas fa-chevron-down"></i></div>
                    </div>
                    <div class="faq-answer">
                        <p>We offer a satisfaction guarantee. If you're not happy with our service, we provide refunds according to our refund policy.</p>
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
                        <li><a href="#">Instagram Growth</a></li>
                        <li><a href="#">TikTok Promotion</a></li>
                        <li><a href="#">YouTube Growth</a></li>
                        <li><a href="#">Twitter Boost</a></li>
                        <li><a href="#">Facebook Likes</a></li>
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
                        <li><a href="#">Refund Policy</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2023 SocialBoost Pro. All rights reserved.
            </div>
        </div>
    </footer>

    <script>
        // FAQ Toggle Functionality
        document.querySelectorAll('.faq-question').forEach(question => {
            question.addEventListener('click', () => {
                const item = question.parentNode;
                item.classList.toggle('active');
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetElement.offsetTop - 80,
                    behavior: 'smooth'
                });
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
        document.querySelectorAll('.service-card, .pricing-card, .step, .testimonial-card').forEach(el => {
            el.style.opacity = 0;
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
