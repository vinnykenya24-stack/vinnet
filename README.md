<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SocialBoost Pro | Real API Integration</title>
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
            --warning: #F39C12;
            --error: #E74C3C;
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

        /* API Configuration Section */
        .api-config {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin: 40px 0;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
        }

        .api-config h2 {
            margin-bottom: 20px;
            color: var(--dark);
        }

        .api-form {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--dark);
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .form-group input:focus, .form-group select:focus {
            border-color: var(--primary);
            outline: none;
        }

        /* Order Status Section */
        .order-status {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin: 40px 0;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            display: none;
        }

        .status-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .status-indicators {
            display: flex;
            justify-content: space-between;
            margin-bottom: 40px;
            position: relative;
        }

        .status-indicators::before {
            content: '';
            position: absolute;
            top: 20px;
            left: 10%;
            right: 10%;
            height: 3px;
            background: #eee;
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
            background: #eee;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 10px;
            transition: all 0.3s ease;
        }

        .status-step.active .status-icon {
            background: var(--primary);
            color: white;
        }

        .status-step.completed .status-icon {
            background: var(--success);
            color: white;
        }

        .api-response {
            background: var(--light);
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
            display: none;
        }

        .response-success {
            border-left: 4px solid var(--success);
        }

        .response-error {
            border-left: 4px solid var(--error);
        }

        .response-warning {
            border-left: 4px solid var(--warning);
        }

        /* Services Section */
        .services-section {
            padding: 80px 0;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: white;
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease;
        }

        .service-card:hover {
            transform: translateY(-5px);
        }

        .service-icon {
            width: 70px;
            height: 70px;
            background: rgba(108, 99, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 1.8rem;
            color: var(--primary);
        }

        .service-card h3 {
            margin-bottom: 15px;
            color: var(--dark);
        }

        .service-card p {
            color: var(--gray);
            margin-bottom: 20px;
        }

        .service-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 20px;
        }

        /* Responsive Design */
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

            .api-form {
                grid-template-columns: 1fr;
            }

            .status-indicators {
                flex-direction: column;
                gap: 30px;
            }

            .status-indicators::before {
                display: none;
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
                    <li><a href="#order">Place Order</a></li>
                    <li><a href="#services">Services</a></li>
                </ul>
            </nav>
            <a href="#order" class="cta-button">Place Order</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1>Real Social Media Growth API</h1>
            <p>Connect to actual follower generation services with real API integration</p>
        </div>
    </section>

    <!-- API Configuration Section -->
    <section class="container" id="order">
        <div class="api-config">
            <h2>Place Your Order</h2>
            <form class="api-form" id="orderForm">
                <div class="form-group">
                    <label for="apiKey">API Key</label>
                    <input type="text" id="apiKey" placeholder="Enter your API key" required>
                </div>
                <div class="form-group">
                    <label for="service">Service Type</label>
                    <select id="service" required>
                        <option value="">Select a service</option>
                        <option value="1">Instagram Followers</option>
                        <option value="2">Instagram Likes</option>
                        <option value="3">Instagram Views</option>
                        <option value="4">TikTok Followers</option>
                        <option value="5">TikTok Likes</option>
                        <option value="6">YouTube Subscribers</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="profileLink">Profile/Post URL</label>
                    <input type="text" id="profileLink" placeholder="https://instagram.com/username" required>
                </div>
                <div class="form-group">
                    <label for="quantity">Quantity</label>
                    <input type="number" id="quantity" placeholder="100" min="10" max="10000" required>
                </div>
                <div class="form-group full-width">
                    <button type="submit" class="cta-button" style="width: 100%;">Place Order via API</button>
                </div>
            </form>
        </div>

        <!-- Order Status Section -->
        <div class="order-status" id="orderStatus">
            <div class="status-header">
                <h2>Order Status</h2>
                <p>Tracking your API request in real-time</p>
            </div>
            
            <div class="status-indicators">
                <div class="status-step active" id="step1">
                    <div class="status-icon">
                        <i class="fas fa-paper-plane"></i>
                    </div>
                    <div>Request Sent</div>
                </div>
                <div class="status-step" id="step2">
                    <div class="status-icon">
                        <i class="fas fa-server"></i>
                    </div>
                    <div>Processing</div>
                </div>
                <div class="status-step" id="step3">
                    <div class="status-icon">
                        <i class="fas fa-check"></i>
                    </div>
                    <div>Completed</div>
                </div>
            </div>

            <div class="api-response" id="apiResponse">
                <h4>API Response</h4>
                <pre id="responseData">Waiting for response...</pre>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services-section" id="services">
        <div class="container">
            <h2 style="text-align: center; margin-bottom: 50px;">Available Services</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fab fa-instagram"></i>
                    </div>
                    <h3>Instagram Followers</h3>
                    <p>High-quality real Instagram followers</p>
                    <div class="service-price">$2.99 / 100 followers</div>
                    <button class="cta-button" onclick="selectService(1, 'Instagram Followers')">Select</button>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fab fa-instagram"></i>
                    </div>
                    <h3>Instagram Likes</h3>
                    <p>Real likes on your Instagram posts</p>
                    <div class="service-price">$1.99 / 100 likes</div>
                    <button class="cta-button" onclick="selectService(2, 'Instagram Likes')">Select</button>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fab fa-tiktok"></i>
                    </div>
                    <h3>TikTok Followers</h3>
                    <p>Active TikTok followers</p>
                    <div class="service-price">$3.99 / 100 followers</div>
                    <button class="cta-button" onclick="selectService(4, 'TikTok Followers')">Select</button>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Service selection
        function selectService(serviceId, serviceName) {
            document.getElementById('service').value = serviceId;
            document.getElementById('profileLink').focus();
            
            // Show notification
            showNotification(`Selected: ${serviceName}`, 'success');
        }

        // Form submission
        document.getElementById('orderForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const apiKey = document.getElementById('apiKey').value;
            const service = document.getElementById('service').value;
            const profileLink = document.getElementById('profileLink').value;
            const quantity = document.getElementById('quantity').value;
            
            // Show order status
            document.getElementById('orderStatus').style.display = 'block';
            document.getElementById('apiResponse').style.display = 'block';
            
            // Update status steps
            updateStatusStep(1, 'active');
            updateStatusStep(2, '');
            updateStatusStep(3, '');
            
            try {
                // Show sending request
                document.getElementById('responseData').textContent = 'Sending API request...';
                
                // Construct API URL (similar to views.co.ke)
                const apiUrl = `https://views.co.ke/api/v2?action=add&service=${service}&link=${encodeURIComponent(profileLink)}&quantity=${quantity}&key=${apiKey}`;
                
                // Make API request
                const response = await fetch(apiUrl);
                const data = await response.json();
                
                // Update status
                updateStatusStep(1, 'completed');
                updateStatusStep(2, 'active');
                
                // Show response
                document.getElementById('responseData').textContent = JSON.stringify(data, null, 2);
                
                // Check if order was successful
                if (data && data.status === 'success') {
                    setTimeout(() => {
                        updateStatusStep(2, 'completed');
                        updateStatusStep(3, 'active');
                        
                        // Final completion
                        setTimeout(() => {
                            updateStatusStep(3, 'completed');
                            showNotification('Order completed successfully!', 'success');
                        }, 1500);
                    }, 2000);
                } else {
                    document.getElementById('apiResponse').className = 'api-response response-error';
                    showNotification('Order failed: ' + (data.error || 'Unknown error'), 'error');
                }
                
            } catch (error) {
                document.getElementById('responseData').textContent = 'Error: ' + error.message;
                document.getElementById('apiResponse').className = 'api-response response-error';
                showNotification('API request failed', 'error');
            }
        });

        // Update status step
        function updateStatusStep(stepNumber, status) {
            const step = document.getElementById(`step${stepNumber}`);
            step.className = `status-step ${status}`;
        }

        // Show notification
        function showNotification(message, type) {
            // Create notification element
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                padding: 15px 20px;
                border-radius: 8px;
                color: white;
                font-weight: 500;
                z-index: 10000;
                animation: slideIn 0.3s ease;
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
            
            // Remove after 3 seconds
            setTimeout(() => {
                notification.remove();
            }, 3000);
        }

        // Auto-fill demo data for testing
        function fillDemoData() {
            document.getElementById('apiKey').value = 'demo_key_123456';
            document.getElementById('service').value = '1';
            document.getElementById('profileLink').value = 'https://instagram.com/demo_profile';
            document.getElementById('quantity').value = '100';
            
            showNotification('Demo data filled for testing', 'success');
        }

        // Add demo button
        const demoButton = document.createElement('button');
        demoButton.textContent = 'Fill Demo Data';
        demoButton.className = 'cta-button';
        demoButton.style.background = 'var(--warning)';
        demoButton.style.marginTop = '10px';
        demoButton.onclick = fillDemoData;
        document.querySelector('.api-form').appendChild(demoButton);
    </script>
</body>
</html>
