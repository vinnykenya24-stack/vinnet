<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SocialPulse Analytics | Social Media Dashboard</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #4361ee;
            --secondary: #3a0ca3;
            --success: #4cc9f0;
            --warning: #f72585;
            --dark: #2b2d42;
            --light: #f8f9fa;
            --gray: #adb5bd;
            --card-bg: rgba(255, 255, 255, 0.95);
        }

        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: var(--dark);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            margin-bottom: 30px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo i {
            font-size: 2.5rem;
            color: var(--light);
        }

        .logo h1 {
            color: white;
            font-size: 2.2rem;
            font-weight: 700;
        }

        .user-info {
            display: flex;
            align-items: center;
            gap: 15px;
            color: white;
        }

        .user-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: var(--primary);
        }

        .dashboard {
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 25px;
        }

        .sidebar {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            height: fit-content;
        }

        .nav-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 15px;
            margin-bottom: 10px;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .nav-item:hover, .nav-item.active {
            background: var(--primary);
            color: white;
        }

        .nav-item i {
            font-size: 1.2rem;
        }

        .main-content {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .profile-section {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .profile-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
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
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
        }

        .profile-details h2 {
            font-size: 1.8rem;
            margin-bottom: 5px;
        }

        .profile-details p {
            color: var(--gray);
        }

        .platform-tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 25px;
        }

        .platform-tab {
            padding: 10px 20px;
            background: var(--light);
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .platform-tab.active {
            background: var(--primary);
            color: white;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .stat-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .stat-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        .icon-followers {
            background: rgba(67, 97, 238, 0.2);
            color: var(--primary);
        }

        .icon-engagement {
            background: rgba(76, 201, 240, 0.2);
            color: var(--success);
        }

        .icon-reach {
            background: rgba(247, 37, 133, 0.2);
            color: var(--warning);
        }

        .icon-posts {
            background: rgba(43, 45, 66, 0.2);
            color: var(--dark);
        }

        .stat-value {
            font-size: 2.2rem;
            font-weight: 700;
        }

        .stat-change {
            display: flex;
            align-items: center;
            gap: 5px;
            font-size: 0.9rem;
        }

        .positive {
            color: #2ecc71;
        }

        .negative {
            color: #e74c3c;
        }

        .charts-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 25px;
        }

        .chart-card {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .chart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .chart-container {
            height: 300px;
            position: relative;
        }

        .insights-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .insight-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .insight-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
        }

        .insight-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            background: rgba(67, 97, 238, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 1.5rem;
        }

        .hashtag-list, .time-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .hashtag-item, .time-item {
            display: flex;
            justify-content: space-between;
            padding-bottom: 10px;
            border-bottom: 1px solid #eee;
        }

        .hashtag-name {
            font-weight: 600;
        }

        .hashtag-count {
            color: var(--gray);
        }

        .time-slot {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .time-bar {
            height: 8px;
            background: #eee;
            border-radius: 4px;
            margin-top: 5px;
            overflow: hidden;
        }

        .time-fill {
            height: 100%;
            background: var(--primary);
            border-radius: 4px;
        }

        .content-suggestions {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .suggestion-item {
            display: flex;
            gap: 15px;
            padding: 15px;
            background: var(--light);
            border-radius: 12px;
        }

        .suggestion-icon {
            width: 40px;
            height: 40px;
            border-radius: 10px;
            background: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
        }

        @media (max-width: 1200px) {
            .charts-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .dashboard {
                grid-template-columns: 1fr;
            }
            
            .sidebar {
                display: none;
            }
            
            .profile-info {
                flex-direction: column;
                text-align: center;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-chart-line"></i>
                <h1>SocialPulse Analytics</h1>
            </div>
            <div class="user-info">
                <div class="user-avatar">JD</div>
                <div>
                    <div>John Doe</div>
                    <div style="font-size: 0.9rem; opacity: 0.8;">Pro Plan</div>
                </div>
            </div>
        </header>

        <div class="dashboard">
            <div class="sidebar">
                <div class="nav-item active">
                    <i class="fas fa-home"></i>
                    <span>Dashboard</span>
                </div>
                <div class="nav-item">
                    <i class="fas fa-chart-bar"></i>
                    <span>Analytics</span>
                </div>
                <div class="nav-item">
                    <i class="fas fa-calendar-alt"></i>
                    <span>Content Planner</span>
                </div>
                <div class="nav-item">
                    <i class="fas fa-hashtag"></i>
                    <span>Hashtag Research</span>
                </div>
                <div class="nav-item">
                    <i class="fas fa-users"></i>
                    <span>Audience Insights</span>
                </div>
                <div class="nav-item">
                    <i class="fas fa-bell"></i>
                    <span>Notifications</span>
                </div>
                <div class="nav-item">
                    <i class="fas fa-cog"></i>
                    <span>Settings</span>
                </div>
            </div>

            <div class="main-content">
                <div class="profile-section">
                    <div class="profile-header">
                        <div class="profile-info">
                            <div class="profile-avatar">
                                <i class="fab fa-instagram"></i>
                            </div>
                            <div class="profile-details">
                                <h2>@creative_mind</h2>
                                <p>Digital Creator • Photography • Art</p>
                            </div>
                        </div>
                        <div class="platform-tabs">
                            <div class="platform-tab active">Instagram</div>
                            <div class="platform-tab">Twitter</div>
                            <div class="platform-tab">TikTok</div>
                            <div class="platform-tab">YouTube</div>
                        </div>
                    </div>

                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-header">
                                <h3>Followers</h3>
                                <div class="stat-icon icon-followers">
                                    <i class="fas fa-users"></i>
                                </div>
                            </div>
                            <div class="stat-value">24.8K</div>
                            <div class="stat-change positive">
                                <i class="fas fa-arrow-up"></i>
                                <span>12.4% from last month</span>
                            </div>
                        </div>

                        <div class="stat-card">
                            <div class="stat-header">
                                <h3>Engagement Rate</h3>
                                <div class="stat-icon icon-engagement">
                                    <i class="fas fa-heart"></i>
                                </div>
                            </div>
                            <div class="stat-value">4.7%</div>
                            <div class="stat-change positive">
                                <i class="fas fa-arrow-up"></i>
                                <span>2.1% from last month</span>
                            </div>
                        </div>

                        <div class="stat-card">
                            <div class="stat-header">
                                <h3>Reach</h3>
                                <div class="stat-icon icon-reach">
                                    <i class="fas fa-eye"></i>
                                </div>
                            </div>
                            <div class="stat-value">148.5K</div>
                            <div class="stat-change positive">
                                <i class="fas fa-arrow-up"></i>
                                <span>8.3% from last month</span>
                            </div>
                        </div>

                        <div class="stat-card">
                            <div class="stat-header">
                                <h3>Posts</h3>
                                <div class="stat-icon icon-posts">
                                    <i class="fas fa-image"></i>
                                </div>
                            </div>
                            <div class="stat-value">247</div>
                            <div class="stat-change">
                                <span>Last 30 days: 18</span>
                            </div>
                        </div>
                    </div>

                    <div class="charts-grid">
                        <div class="chart-card">
                            <div class="chart-header">
                                <h3>Follower Growth</h3>
                                <div>
                                    <select style="padding: 8px 15px; border-radius: 8px; border: 1px solid #ddd;">
                                        <option>Last 7 days</option>
                                        <option>Last 30 days</option>
                                        <option>Last 3 months</option>
                                        <option>Last year</option>
                                    </select>
                                </div>
                            </div>
                            <div class="chart-container">
                                <canvas id="growthChart"></canvas>
                            </div>
                        </div>

                        <div class="chart-card">
                            <div class="chart-header">
                                <h3>Audience Demographics</h3>
                            </div>
                            <div class="chart-container">
                                <canvas id="demographicsChart"></canvas>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="insights-grid">
                    <div class="insight-card">
                        <div class="insight-header">
                            <div class="insight-icon">
                                <i class="fas fa-hashtag"></i>
                            </div>
                            <h3>Top Performing Hashtags</h3>
                        </div>
                        <div class="hashtag-list">
                            <div class="hashtag-item">
                                <div class="hashtag-name">#photography</div>
                                <div class="hashtag-count">24.5K reaches</div>
                            </div>
                            <div class="hashtag-item">
                                <div class="hashtag-name">#creative</div>
                                <div class="hashtag-count">18.7K reaches</div>
                            </div>
                            <div class="hashtag-item">
                                <div class="hashtag-name">#art</div>
                                <div class="hashtag-count">15.2K reaches</div>
                            </div>
                            <div class="hashtag-item">
                                <div class="hashtag-name">#design</div>
                                <div class="hashtag-count">12.8K reaches</div>
                            </div>
                            <div class="hashtag-item">
                                <div class="hashtag-name">#inspiration</div>
                                <div class="hashtag-count">9.4K reaches</div>
                            </div>
                        </div>
                    </div>

                    <div class="insight-card">
                        <div class="insight-header">
                            <div class="insight-icon">
                                <i class="fas fa-clock"></i>
                            </div>
                            <h3>Best Times to Post</h3>
                        </div>
                        <div class="time-list">
                            <div class="time-item">
                                <div class="time-slot">
                                    <span>Monday 7-9 PM</span>
                                    <span>High Engagement</span>
                                </div>
                                <div class="time-bar">
                                    <div class="time-fill" style="width: 92%"></div>
                                </div>
                            </div>
                            <div class="time-item">
                                <div class="time-slot">
                                    <span>Wednesday 12-2 PM</span>
                                    <span>Medium Engagement</span>
                                </div>
                                <div class="time-bar">
                                    <div class="time-fill" style="width: 75%"></div>
                                </div>
                            </div>
                            <div class="time-item">
                                <div class="time-slot">
                                    <span>Friday 5-7 PM</span>
                                    <span>High Engagement</span>
                                </div>
                                <div class="time-bar">
                                    <div class="time-fill" style="width: 88%"></div>
                                </div>
                            </div>
                            <div class="time-item">
                                <div class="time-slot">
                                    <span>Sunday 3-5 PM</span>
                                    <span>Medium Engagement</span>
                                </div>
                                <div class="time-bar">
                                    <div class="time-fill" style="width: 68%"></div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="insight-card">
                        <div class="insight-header">
                            <div class="insight-icon">
                                <i class="fas fa-lightbulb"></i>
                            </div>
                            <h3>Content Suggestions</h3>
                        </div>
                        <div class="content-suggestions">
                            <div class="suggestion-item">
                                <div class="suggestion-icon">
                                    <i class="fas fa-palette"></i>
                                </div>
                                <div>
                                    <h4>Create a color theory tutorial</h4>
                                    <p>Your audience engages well with educational content</p>
                                </div>
                            </div>
                            <div class="suggestion-item">
                                <div class="suggestion-icon">
                                    <i class="fas fa-question"></i>
                                </div>
                                <div>
                                    <h4>Q&A session</h4>
                                    <p>Boost engagement with interactive content</p>
                                </div>
                            </div>
                            <div class="suggestion-item">
                                <div class="suggestion-icon">
                                    <i class="fas fa-video"></i>
                                </div>
                                <div>
                                    <h4>Behind the scenes reel</h4>
                                    <p>Your followers love seeing your creative process</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
        // Initialize charts
        document.addEventListener('DOMContentLoaded', function() {
            // Growth Chart
            const growthCtx = document.getElementById('growthChart').getContext('2d');
            const growthChart = new Chart(growthCtx, {
                type: 'line',
                data: {
                    labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul'],
                    datasets: [{
                        label: 'Followers',
                        data: [16500, 17800, 19200, 20500, 21800, 23000, 24800],
                        borderColor: '#4361ee',
                        backgroundColor: 'rgba(67, 97, 238, 0.1)',
                        borderWidth: 3,
                        fill: true,
                        tension: 0.4
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            display: false
                        }
                    },
                    scales: {
                        y: {
                            beginAtZero: false,
                            grid: {
                                color: 'rgba(0, 0, 0, 0.05)'
                            }
                        },
                        x: {
                            grid: {
                                display: false
                            }
                        }
                    }
                }
            });

            // Demographics Chart
            const demographicsCtx = document.getElementById('demographicsChart').getContext('2d');
            const demographicsChart = new Chart(demographicsCtx, {
                type: 'doughnut',
                data: {
                    labels: ['18-24', '25-34', '35-44', '45+'],
                    datasets: [{
                        data: [35, 40, 15, 10],
                        backgroundColor: [
                            '#4361ee',
                            '#3a0ca3',
                            '#4cc9f0',
                            '#f72585'
                        ],
                        borderWidth: 0
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'bottom'
                        }
                    }
                }
            });

            // Platform tabs functionality
            const platformTabs = document.querySelectorAll('.platform-tab');
            platformTabs.forEach(tab => {
                tab.addEventListener('click', function() {
                    platformTabs.forEach(t => t.classList.remove('active'));
                    this.classList.add('active');
                    
                    // In a real app, this would update the dashboard data
                    // based on the selected platform
                });
            });

            // Navigation items functionality
            const navItems = document.querySelectorAll('.nav-item');
            navItems.forEach(item => {
                item.addEventListener('click', function() {
                    navItems.forEach(i => i.classList.remove('active'));
                    this.classList.add('active');
                });
            });
        });
    </script>
</body>
</html>
