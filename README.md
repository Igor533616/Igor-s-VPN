<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Igor's VPN</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #2F4F4F;
            --secondary-color: #3a9f9f;
            --accent-color: #4fc3c3;
            --light-color: #f8f9fa;
            --dark-color: #1a2c2c;
            --gray-color: #6c757d;
            --success-color: #28a745;
            --danger-color: #dc3545;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Roboto', sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f4f4f4;
        }
        
        a {
            text-decoration: none;
            color: var(--secondary-color);
        }
        
        ul {
            list-style: none;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: 700;
        }
        
        .nav-menu {
            display: flex;
        }
        
        .nav-menu li {
            margin-left: 1.5rem;
        }
        
        .nav-menu a {
            color: white;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-menu a:hover {
            color: var(--accent-color);
        }
        
        .btn {
            display: inline-block;
            padding: 0.5rem 1.5rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
        }
        
        .btn-primary {
            background-color: var(--secondary-color);
            color: white;
        }
        
        .btn-primary:hover {
            background-color: var(--accent-color);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--secondary-color);
            color: var(--secondary-color);
        }
        
        .btn-outline:hover {
            background-color: var(--secondary-color);
            color: white;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--dark-color) 100%);
            color: white;
            padding: 4rem 0;
            text-align: center;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }
        
        /* Features Section */
        .features {
            padding: 4rem 0;
            background-color: white;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--primary-color);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .feature-card {
            background-color: var(--light-color);
            border-radius: 8px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .feature-card:hover {
            transform: translateY(-5px);
        }
        
        .feature-icon {
            font-size: 2.5rem;
            color: var(--secondary-color);
            margin-bottom: 1rem;
        }
        
        /* Dashboard Styles */
        .dashboard {
            display: none;
            min-height: 100vh;
            background-color: #f4f4f4;
        }
        
        .dashboard-header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 0;
        }
        
        .dashboard-nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .user-info {
            display: flex;
            align-items: center;
        }
        
        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--secondary-color);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 10px;
            font-weight: bold;
        }
        
        .dashboard-content {
            padding: 2rem 0;
        }
        
        .dashboard-card {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            margin-bottom: 2rem;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        .connection-status {
            text-align: center;
            padding: 2rem;
        }
        
        .status-indicator {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin: 0 auto 1.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: bold;
            color: white;
        }
        
        .status-connected {
            background-color: var(--success-color);
        }
        
        .status-disconnected {
            background-color: var(--danger-color);
        }
        
        .server-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        .server-item {
            background-color: var(--light-color);
            padding: 1rem;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
        }
        
        .server-item:hover {
            background-color: var(--secondary-color);
            color: white;
        }
        
        .server-item.active {
            background-color: var(--secondary-color);
            color: white;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }
        
        .stat-card {
            background-color: var(--light-color);
            padding: 1.5rem;
            border-radius: 8px;
            text-align: center;
        }
        
        .stat-value {
            font-size: 2rem;
            font-weight: bold;
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }
        
        /* Subscription Page */
        .subscription-plans {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .plan-card {
            background-color: white;
            border-radius: 8px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
            border: 2px solid transparent;
        }
        
        .plan-card:hover {
            transform: translateY(-5px);
            border-color: var(--secondary-color);
        }
        
        .plan-card.featured {
            border-color: var(--secondary-color);
            position: relative;
            overflow: hidden;
        }
        
        .plan-card.featured::before {
            content: "Most Popular";
            position: absolute;
            top: 0;
            right: 0;
            background-color: var(--secondary-color);
            color: white;
            padding: 0.5rem 1rem;
            font-size: 0.8rem;
            font-weight: bold;
        }
        
        .plan-price {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--primary-color);
            margin: 1rem 0;
        }
        
        .plan-features {
            margin: 1.5rem 0;
        }
        
        .plan-features li {
            padding: 0.5rem 0;
            border-bottom: 1px solid #eee;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 3rem 0 1.5rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-section h3 {
            margin-bottom: 1rem;
            color: var(--accent-color);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Landing Page -->
    <div id="landing-page">
        <header>
            <div class="container header-content">
                <div class="logo">Igor's VPN</div>
                <ul class="nav-menu">
                    <li><a href="#" onclick="showPage('landing-page')">Home</a></li>
                    <li><a href="#" onclick="showPage('dashboard')">Dashboard</a></li>
                    <li><a href="#" onclick="showPage('subscription-page')">Pricing</a></li>
                    <li><a href="#footer">Contact</a></li>
                </ul>
                <a href="#" class="btn btn-primary" onclick="showPage('dashboard')">Connect</a>
            </div>
        </header>

        <section class="hero">
            <div class="container hero-content">
                <h1>Secure Your Digital Life with Igor's VPN</h1>
                <p>Protect your privacy, bypass restrictions, and secure your internet connection with our military-grade encryption technology.</p>
                <a href="#" class="btn btn-primary" onclick="showPage('subscription-page')">Get Started</a>
            </div>
        </section>

        <section class="features">
            <div class="container">
                <h2 class="section-title">Why Choose Igor's VPN?</h2>
                <div class="features-grid">
                    <div class="feature-card">
                        <div class="feature-icon">🔒</div>
                        <h3>Military-Grade Encryption</h3>
                        <p>Our AES-256 encryption ensures your data remains private and secure from prying eyes.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🌍</div>
                        <h3>Global Server Network</h3>
                        <p>Access content from anywhere with our network of servers in 50+ countries worldwide.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">⚡</div>
                        <h3>Lightning Fast Speeds</h3>
                        <p>Enjoy buffer-free streaming and lag-free gaming with our optimized servers.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">📱</div>
                        <h3>Cross-Platform Support</h3>
                        <p>Protect all your devices with apps for iOS, Android, Windows, and macOS.</p>
                    </div>
                </div>
            </div>
        </section>

        <footer id="footer">
            <div class="container">
                <div class="footer-content">
                    <div class="footer-section">
                        <h3>Igor's VPN</h3>
                        <p>Protecting your digital privacy since 2023. Our mission is to provide secure and private internet access for everyone.</p>
                    </div>
                    <div class="footer-section">
                        <h3>Quick Links</h3>
                        <ul>
                            <li><a href="#" onclick="showPage('landing-page')">Home</a></li>
                            <li><a href="#" onclick="showPage('dashboard')">Dashboard</a></li>
                            <li><a href="#" onclick="showPage('subscription-page')">Pricing</a></li>
                        </ul>
                    </div>
                    <div class="footer-section">
                        <h3>Contact Us</h3>
                        <p>Email: support@securevpn.com</p>
                        <p>Phone: +1 (555) 123-4567</p>
                    </div>
                </div>
                <div class="footer-bottom">
                    <p>&copy; 2023 Igor's VPN. All rights reserved.</p>
                </div>
            </div>
        </footer>
    </div>

    <!-- Dashboard Page -->
    <div id="dashboard" class="dashboard">
        <div class="dashboard-header">
            <div class="container dashboard-nav">
                <div class="logo">Igor's VPN</div>
                <div class="user-info">
                    <div class="user-avatar">JS</div>
                    <span>Igor Sigma</span>
                </div>
            </div>
        </div>

        <div class="container dashboard-content">
            <div class="dashboard-card connection-status">
                <h2>VPN Connection</h2>
                <div class="status-indicator status-disconnected" id="status-indicator">Disconnected</div>
                <button class="btn btn-primary" id="connect-btn" onclick="toggleConnection()">Connect</button>
                
                <div class="current-server">
                    <p>Selected Server: <span id="selected-server">United States</span></p>
                </div>
                
                <div class="server-selection">
                    <h3>Select Server Location</h3>
                    <div class="server-list">
                        <div class="server-item active" data-country="United States">United States</div>
                        <div class="server-item" data-country="United Kingdom">United Kingdom</div>
                        <div class="server-item" data-country="Germany">Germany</div>
                        <div class="server-item" data-country="Japan">Japan</div>
                        <div class="server-item" data-country="Australia">Australia</div>
                        <div class="server-item" data-country="Canada">Canada</div>
                    </div>
                </div>
            </div>
            
            <div class="dashboard-card">
                <h2>Connection Statistics</h2>
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-value" id="download-speed">0 Mbps</div>
                        <div class="stat-label">Download Speed</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="upload-speed">0 Mbps</div>
                        <div class="stat-label">Upload Speed</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="data-usage">0.0 GB</div>
                        <div class="stat-label">Data Used Today</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="connection-time">00:00:00</div>
                        <div class="stat-label">Connection Time</div>
                    </div>
                </div>
            </div>
            
            <div class="dashboard-card">
                <h2>Subscription Details</h2>
                <p>Your current plan: <strong>Premium Monthly</strong></p>
                <p>Status: <strong class="text-success">Active</strong></p>
                <p>Renewal date: <strong>December 15, 2023</strong></p>
                <a href="#" class="btn btn-outline" onclick="showPage('subscription-page')">Manage Subscription</a>
            </div>
        </div>
    </div>

    <!-- Subscription Page -->
    <div id="subscription-page" class="dashboard">
        <div class="dashboard-header">
            <div class="container dashboard-nav">
                <div class="logo">Igor's VPN</div>
                <div class="user-info">
                    <div class="user-avatar">JS</div>
                    <span>Igor Sigma</span>
                </div>
            </div>
        </div>

        <div class="container dashboard-content">
            <h2 class="section-title">Choose Your Plan</h2>
            
            <div class="subscription-plans">
                <div class="plan-card">
                    <h3>Basic</h3>
                    <div class="plan-price">$4.99<span>/month</span></div>
                    <ul class="plan-features">
                        <li>1 Device Connection</li>
                        <li>50 GB Monthly Data</li>
                        <li>30+ Server Locations</li>
                        <li>Basic Support</li>
                    </ul>
                    <button class="btn btn-outline">Select Plan</button>
                </div>
                
                <div class="plan-card featured">
                    <h3>Premium</h3>
                    <div class="plan-price">$9.99<span>/month</span></div>
                    <ul class="plan-features">
                        <li>5 Device Connections</li>
                        <li>Unlimited Data</li>
                        <li>50+ Server Locations</li>
                        <li>Priority Support</li>
                        <li>Ad Blocker</li>
                    </ul>
                    <button class="btn btn-primary">Select Plan</button>
                </div>
                
                <div class="plan-card">
                    <h3>Family</h3>
                    <div class="plan-price">$14.99<span>/month</span></div>
                    <ul class="plan-features">
                        <li>10 Device Connections</li>
                        <li>Unlimited Data</li>
                        <li>50+ Server Locations</li>
                        <li>24/7 Support</li>
                        <li>Ad Blocker</li>
                        <li>Malware Protection</li>
                    </ul>
                    <button class="btn btn-outline">Select Plan</button>
                </div>
            </div>
            
            <div class="dashboard-card">
                <h2>Payment Methods</h2>
                <p>Your current payment method: <strong>Credit Card ending in 4567</strong></p>
                <button class="btn btn-outline">Update Payment Method</button>
            </div>
        </div>
    </div>

    <script>
        // Page navigation
        function showPage(pageId) {
            document.getElementById('landing-page').style.display = 'none';
            document.getElementById('dashboard').style.display = 'none';
            document.getElementById('subscription-page').style.display = 'none';
            
            document.getElementById(pageId).style.display = 'block';
            
            // Scroll to top when changing pages
            window.scrollTo(0, 0);
        }
        
        // Initialize by showing landing page
        showPage('landing-page');
        
        // VPN connection simulation
        let isConnected = false;
        let connectionTimer = null;
        let connectionTime = 0;
        
        function toggleConnection() {
            const statusIndicator = document.getElementById('status-indicator');
            const connectBtn = document.getElementById('connect-btn');
            
            if (!isConnected) {
                // Simulate connection process
                statusIndicator.textContent = 'Connecting...';
                statusIndicator.classList.remove('status-disconnected');
                statusIndicator.classList.add('status-connected');
                
                setTimeout(() => {
                    isConnected = true;
                    statusIndicator.textContent = 'Connected';
                    connectBtn.textContent = 'Disconnect';
                    
                    // Start connection timer
                    startConnectionTimer();
                    
                    // Simulate data usage and speed
                    simulateConnectionStats();
                }, 2000);
            } else {
                // Disconnect
                isConnected = false;
                statusIndicator.textContent = 'Disconnected';
                statusIndicator.classList.remove('status-connected');
                statusIndicator.classList.add('status-disconnected');
                connectBtn.textContent = 'Connect';
                
                // Stop timers
                clearInterval(connectionTimer);
                connectionTime = 0;
                
                // Reset stats
                document.getElementById('download-speed').textContent = '0 Mbps';
                document.getElementById('upload-speed').textContent = '0 Mbps';
                document.getElementById('connection-time').textContent = '00:00:00';
            }
        }
        
        function startConnectionTimer() {
            clearInterval(connectionTimer);
            
            connectionTimer = setInterval(() => {
                connectionTime++;
                
                const hours = Math.floor(connectionTime / 3600);
                const minutes = Math.floor((connectionTime % 3600) / 60);
                const seconds = connectionTime % 60;
                
                document.getElementById('connection-time').textContent = 
                    `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
            }, 1000);
        }
        
        function simulateConnectionStats() {
            // Simulate download speed (20-80 Mbps)
            setInterval(() => {
                if (isConnected) {
                    const downloadSpeed = Math.floor(Math.random() * 60) + 20;
                    const uploadSpeed = Math.floor(Math.random() * 30) + 10;
                    
                    document.getElementById('download-speed').textContent = `${downloadSpeed} Mbps`;
                    document.getElementById('upload-speed').textContent = `${uploadSpeed} Mbps`;
                    
                    // Update data usage (approx 0.1-0.5 MB per second)
                    const dataElement = document.getElementById('data-usage');
                    const currentData = parseFloat(dataElement.textContent);
                    const newData = currentData + (Math.random() * 0.4 + 0.1) / 1000;
                    dataElement.textContent = newData.toFixed(1) + ' GB';
                }
            }, 1000);
        }
        
        // Server selection
        document.querySelectorAll('.server-item').forEach(item => {
            item.addEventListener('click', function() {
                document.querySelectorAll('.server-item').forEach(i => i.classList.remove('active'));
                this.classList.add('active');
                document.getElementById('selected-server').textContent = this.getAttribute('data-country');
            });
        });
    </script>
</body>
</html>
