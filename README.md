<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SocialBoost Pro | Free Follower Generator</title>
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
            max-width: 1000px;
            margin: 0 auto;
        }

        header {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
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
            font-size: 2.5rem;
            color: var(--primary);
        }

        .logo h1 {
            font-size: 2.2rem;
            color: var(--dark);
        }

        .tagline {
            color: var(--gray);
            font-size: 1.1rem;
        }

        .api-panel {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .panel-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .panel-header h2 {
            color: var(--dark);
            margin-bottom: 10px;
        }

        .panel-header p {
            color: var(--gray);
        }

        .api-form {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 30px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }

        input, select {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #E5E7EB;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        input:focus, select:focus {
            border-color: var(--primary);
            outline: none;
        }

        .btn {
            padding: 15px 30px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
        }

        .btn-primary:hover {
            background: var(--secondary);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(108, 99, 255, 0.3);
        }

        .btn-success {
            background: var(--success);
            color: white;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .service-card {
            border: 2px solid #E5E7EB;
            border-radius: 10px;
            padding: 20px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .service-card:hover, .service-card.selected {
            border-color: var(--primary);
            background: rgba(108, 99, 255, 0.05);
        }

        .service-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 15px;
        }

        .service-icon {
            width: 50px;
            height: 50px;
            background: rgba(108, 99, 255, 0.1);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--primary);
        }

        .service-info h3 {
            margin-bottom: 5px;
            color: var(--dark);
        }

        .service-info p {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .service-price {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--success);
            text-align: center;
            margin-top: 10px;
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

        pre {
            white-space: pre-wrap;
            word-wrap: break-word;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
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

        .demo-section {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-top: 30px;
            text-align: center;
        }

        .demo-section h3 {
            margin-bottom: 15px;
            color: var(--dark);
        }

        .demo-btn {
            background: var(--warning);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
        }

        footer {
            text-align: center;
            color: white;
            margin-top: 40px;
            padding: 20px;
        }

        @media (max-width: 768px) {
            .api-form {
                grid-template-columns: 1fr;
            }
            
            .status-indicators {
                flex-direction: column;
                gap: 20px;
            }
            
            .status-indicators::before {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-rocket"></i>
                <h1>SocialBoost Pro</h1>
            </div>
            <p class="tagline">Free Social Media Growth - No Payment Required</p>
        </header>

        <div class="api-panel">
            <div class="panel-header">
                <h2>Generate Followers & Likes Instantly</h2>
                <p>Connect directly to our SMM panel API - Completely Free</p>
            </div>

            <form class="api-form" id="apiForm">
                <div class="form-group">
                    <label for="apiKey"><i class="fas fa-key"></i> API Key</label>
                    <input type="text" id="apiKey" placeholder="Enter your API key" required>
                </div>

                <div class="form-group">
                    <label for="service"><i class="fas fa-cog"></i> Service Type</label>
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
                    <label for="profileLink"><i class="fas fa-link"></i> Profile URL</label>
                    <input type="text" id="profileLink" placeholder="https://instagram.com/username" required>
                </div>

                <div class="form-group">
                    <label for="quantity"><i class="fas fa-hashtag"></i> Quantity</label>
                    <input type="number" id="quantity" placeholder="100" min="10" max="10000" required>
                </div>

                <div class="form-group full-width">
                    <button type="submit" class="btn btn-primary">
                        <i class="fas fa-bolt"></i> Generate Now - Free
                    </button>
                </div>
            </form>

            <div class="services-grid">
                <div class="service-card" onclick="selectService(1, 'Instagram Followers')">
                    <div class="service-header">
                        <div class="service-icon">
                            <i class="fab fa-instagram"></i>
                        </div>
                        <div class="service-info">
                            <h3>Instagram Followers</h3>
                            <p>Real, active followers</p>
                        </div>
                    </div>
                    <div class="service-price">FREE</div>
                </div>

                <div class="service-card" onclick="selectService(2, 'Instagram Likes')">
                    <div class="service-header">
                        <div class="service-icon">
                            <i class="fas fa-heart"></i>
                        </div>
                        <div class="service-info">
                            <h3>Instagram Likes</h3>
                            <p>Engagement on your posts</p>
                        </div>
                    </div>
                    <div class="service-price">FREE</div>
                </div>

                <div class="service-card" onclick="selectService(4, 'TikTok Followers')">
                    <div class="service-header">
                        <div class="service-icon">
                            <i class="fab fa-tiktok"></i>
                        </div>
                        <div class="service-info">
                            <h3>TikTok Followers</h3>
                            <p>Grow your TikTok presence</p>
                        </div>
                    </div>
                    <div class="service-price">FREE</div>
                </div>
            </div>

            <div class="status-indicators" id="statusIndicators" style="display: none;">
                <div class="status-step" id="step1">
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
                <h4><i class="fas fa-code"></i> API Response</h4>
                <pre id="responseData">Waiting for API response...</pre>
            </div>

            <div class="demo-section">
                <h3>Want to test the API?</h3>
                <p>Try our demo mode to see how it works</p>
                <button class="demo-btn" onclick="fillDemoData()">
                    <i class="fas fa-vial"></i> Fill Demo Data
                </button>
            </div>
        </div>

        <footer>
            <p>&copy; 2023 SocialBoost Pro. This is a demonstration of SMM panel API integration.</p>
            <p style="margin-top: 10px; font-size: 0.9rem;">
                Note: This demo shows how to integrate with services like views.co.ke
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
            
            // Show notification
            showNotification(`Selected: ${serviceName}`, 'success');
        }

        // Form submission
        document.getElementById('apiForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const apiKey = document.getElementById('apiKey').value;
            const service = document.getElementById('service').value;
            const profileLink = document.getElementById('profileLink').value;
            const quantity = document.getElementById('quantity').value;
            
            // Show status indicators
            document.getElementById('statusIndicators').style.display = 'flex';
            document.getElementById('apiResponse').style.display = 'block';
            
            // Update status steps
            updateStatusStep(1, 'active');
            updateStatusStep(2, '');
            updateStatusStep(3, '');
            
            try {
                // Show sending request
                document.getElementById('responseData').textContent = 'Sending API request to SMM panel...';
                
                // Construct API URL (similar to views.co.ke)
                const apiUrl = `https://views.co.ke/api/v2?action=add&service=${service}&link=${encodeURIComponent(profileLink)}&quantity=${quantity}&key=${apiKey}`;
                
                // Show the API URL being used
                document.getElementById('responseData').textContent = `API Endpoint: ${apiUrl}\n\nSending request...`;
                
                // Make API request
                const response = await fetch(apiUrl, {
                    method: 'GET',
                    mode: 'cors'
                });
                
                const data = await response.json();
                
                // Update status
                updateStatusStep(1, 'completed');
                updateStatusStep(2, 'active');
                
                // Show response
                document.getElementById('responseData').textContent = JSON.stringify(data, null, 2);
                
                // Style based on response
                if (data && data.status === 'success') {
                    document.getElementById('apiResponse').className = 'api-response response-success';
                    
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
                showNotification('API request failed. Check CORS or try demo mode.', 'error');
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

        // Fill demo data for testing
        function fillDemoData() {
            document.getElementById('apiKey').value = 'demo_key_123456789';
            document.getElementById('service').value = '1';
            document.getElementById('profileLink').value = 'https://instagram.com/demo_profile';
            document.getElementById('quantity').value = '100';
            
            // Select the first service card
            document.querySelectorAll('.service-card')[0].classList.add('selected');
            
            showNotification('Demo data filled. You can now test the API!', 'success');
        }

        // Add CSS for notification animation
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
