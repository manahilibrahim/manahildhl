<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DHL Express | The logistics company for the world</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
        }

        /* Header Styles */
        .header {
            background: #fff;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        .top-bar {
            background: #f8f9fa;
            padding: 8px 0;
            font-size: 12px;
            text-align: center;
            color: #666;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
            height: 70px;
        }

        .logo {
            font-size: 36px;
            font-weight: bold;
            color: #D40511;
            text-decoration: none;
            letter-spacing: 2px;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 35px;
        }

        .nav-menu a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }

        .nav-menu a:hover {
            color: #D40511;
        }

        .nav-menu a:hover::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: #D40511;
        }

        .nav-actions {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .btn-track {
            background: #D40511;
            color: white;
            padding: 12px 25px;
            text-decoration: none;
            border-radius: 25px;
            font-weight: bold;
            transition: all 0.3s;
            box-shadow: 0 3px 10px rgba(212, 5, 17, 0.3);
        }

        .btn-track:hover {
            background: #b8040e;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(212, 5, 17, 0.4);
        }

        .login-btn {
            color: #666;
            text-decoration: none;
            font-weight: 500;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #D40511 0%, #FFCC00 100%);
            color: white;
            padding: 140px 20px 100px;
            text-align: center;
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="white" opacity="0.1"/><circle cx="75" cy="75" r="1" fill="white" opacity="0.1"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            opacity: 0.3;
        }

        .hero-container {
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            font-weight: 700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.4rem;
            margin-bottom: 50px;
            opacity: 0.95;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .tracking-section {
            background: white;
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.2);
            max-width: 700px;
            margin: 0 auto;
            position: relative;
        }

        .tracking-section::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #D40511, #FFCC00);
            border-radius: 22px;
            z-index: -1;
        }

        .tracking-section h2 {
            color: #333;
            margin-bottom: 25px;
            font-size: 2rem;
            text-align: center;
        }

        .tracking-tabs {
            display: flex;
            margin-bottom: 30px;
            border-bottom: 1px solid #eee;
        }

        .tab-btn {
            flex: 1;
            padding: 15px;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 500;
            color: #666;
            transition: all 0.3s;
        }

        .tab-btn.active {
            color: #D40511;
            border-bottom: 3px solid #D40511;
        }

        .tracking-form {
            display: flex;
            gap: 15px;
            margin-bottom: 25px;
        }

        .tracking-input {
            flex: 1;
            padding: 18px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-size: 16px;
            transition: border-color 0.3s;
        }

        .tracking-input:focus {
            outline: none;
            border-color: #D40511;
            box-shadow: 0 0 0 3px rgba(212, 5, 17, 0.1);
        }

        .btn-primary {
            background: #D40511;
            color: white;
            padding: 18px 35px;
            border: none;
            border-radius: 10px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-primary:hover {
            background: #b8040e;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(212, 5, 17, 0.3);
        }

        .sample-tracking {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 8px;
            font-size: 14px;
            color: #666;
        }

        /* Live Tracking Section */
        .live-tracking {
            background: #f8f9fa;
            padding: 60px 20px;
        }

        .live-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .live-tracking h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 50px;
            color: #333;
        }

        .tracking-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .tracking-card {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            border-left: 5px solid #D40511;
        }

        .tracking-number {
            font-weight: bold;
            color: #D40511;
            font-size: 1.1rem;
            margin-bottom: 15px;
        }

        .tracking-status {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 15px;
        }

        .status-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #28a745;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.5; }
            100% { opacity: 1; }
        }

        .tracking-details {
            font-size: 14px;
            color: #666;
            line-height: 1.6;
        }

        /* Services Section */
        .services {
            padding: 100px 20px;
            background: white;
        }

        .services-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .services h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 20px;
            color: #333;
        }

        .services-subtitle {
            text-align: center;
            font-size: 1.2rem;
            color: #666;
            margin-bottom: 60px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }

        .service-card {
            background: white;
            padding: 50px 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            text-align: center;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
            transition: left 0.5s;
        }

        .service-card:hover::before {
            left: 100%;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .service-icon {
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, #FFCC00, #FFD700);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 30px;
            font-size: 2.5rem;
            box-shadow: 0 10px 25px rgba(255, 204, 0, 0.3);
        }

        .service-card h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #333;
        }

        .service-card p {
            color: #666;
            line-height: 1.8;
            margin-bottom: 25px;
        }

        .service-price {
            font-size: 1.1rem;
            font-weight: bold;
            color: #D40511;
        }

        /* Stats Section */
        .stats {
            background: linear-gradient(135deg, #D40511 0%, #b8040e 100%);
            color: white;
            padding: 80px 20px;
            position: relative;
        }

        .stats::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><polygon points="0,0 100,0 80,100 0,100" fill="rgba(255,255,255,0.05)"/></svg>');
        }

        .stats-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 50px;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .stat-item {
            padding: 20px;
        }

        .stat-item h3 {
            font-size: 4rem;
            margin-bottom: 15px;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            counter-reset: number;
            animation: countUp 2s ease-out;
        }

        .stat-item p {
            font-size: 1.2rem;
            opacity: 0.95;
            font-weight: 500;
        }

        /* Testimonials */
        .testimonials {
            padding: 100px 20px;
            background: #f8f9fa;
        }

        .testimonials-container {
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }

        .testimonials h2 {
            font-size: 3rem;
            margin-bottom: 60px;
            color: #333;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }

        .testimonial-card {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            position: relative;
        }

        .testimonial-card::before {
            content: '"';
            position: absolute;
            top: -10px;
            left: 30px;
            font-size: 4rem;
            color: #FFCC00;
            font-weight: bold;
        }

        .testimonial-text {
            font-style: italic;
            margin-bottom: 25px;
            line-height: 1.8;
            color: #555;
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
            background: linear-gradient(135deg, #D40511, #FFCC00);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        .author-info h4 {
            margin-bottom: 5px;
            color: #333;
        }

        .author-info p {
            color: #666;
            font-size: 14px;
        }

        /* Footer */
        .footer {
            background: #1a1a1a;
            color: white;
            padding: 80px 20px 30px;
        }

        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-top {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr 1fr;
            gap: 50px;
            margin-bottom: 50px;
        }

        .footer-brand h3 {
            font-size: 2rem;
            color: #D40511;
            margin-bottom: 20px;
        }

        .footer-brand p {
            line-height: 1.8;
            color: #ccc;
            margin-bottom: 25px;
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: #333;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: #D40511;
            transform: translateY(-3px);
        }

        .footer-section h4 {
            font-size: 1.3rem;
            margin-bottom: 25px;
            color: #FFCC00;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 12px;
        }

        .footer-section ul li a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-section ul li a:hover {
            color: #FFCC00;
        }

        .footer-bottom {
            border-top: 1px solid #333;
            padding-top: 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: #999;
        }

        .footer-links {
            display: flex;
            gap: 30px;
        }

        .footer-links a {
            color: #999;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: #FFCC00;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .tracking-form {
                flex-direction: column;
            }

            .footer-top {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .footer-bottom {
                flex-direction: column;
                gap: 20px;
            }
            
            .chat-widget {
                width: 300px !important;
            }
            
            .chat-widget.expanded {
                width: 300px !important;
            }
        }

        /* Loading Animation */
        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid #f3f3f3;
            border-top: 3px solid #D40511;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Chat Widget Styles */
        .chat-widget {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 350px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 30px rgba(0,0,0,0.2);
            z-index: 9999;
            overflow: hidden;
            transition: all 0.3s ease;
            max-height: 600px;
        }
        
        .chat-widget.collapsed {
            height: 60px;
            width: 250px;
        }
        
        .chat-widget.expanded {
            height: 500px;
            width: 350px;
        }
        
        .chat-header {
            background: #D40511;
            color: white;
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
        }
        
        .chat-header-left {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .chat-avatar {
            width: 30px;
            height: 30px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #D40511;
            font-weight: bold;
        }
        
        .chat-title h3 {
            font-size: 16px;
            margin: 0;
        }
        
        .chat-title p {
            font-size: 12px;
            margin: 0;
            opacity: 0.8;
        }
        
        .chat-toggle {
            background: none;
            border: none;
            color: white;
            cursor: pointer;
            font-size: 18px;
        }
        
        .chat-body {
            height: calc(100% - 130px);
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .chat-message {
            max-width: 80%;
            padding: 12px 15px;
            border-radius: 15px;
            font-size: 14px;
            line-height: 1.5;
            position: relative;
        }
        
        .chat-message.agent {
            background: #f0f0f0;
            align-self: flex-start;
            border-bottom-left-radius: 5px;
        }
        
        .chat-message.user {
            background: #D40511;
            color: white;
            align-self: flex-end;
            border-bottom-right-radius: 5px;
        }
        
        .chat-time {
            font-size: 10px;
            color: #999;
            margin-top: 5px;
            display: block;
        }
        
        .chat-message.agent .chat-time {
            text-align: left;
        }
        
        .chat-message.user .chat-time {
            text-align: right;
            color: rgba(255,255,255,0.7);
        }
        
        .chat-options {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 10px;
        }
        
        .chat-option {
            background: #f8f9fa;
            border: 1px solid #ddd;
            border-radius: 20px;
            padding: 8px 15px;
            font-size: 13px;
            cursor: pointer;
            transition: all 0.2s;
        }
        
        .chat-option:hover {
            background: #FFCC00;
            border-color: #FFCC00;
        }
        
        .chat-footer {
            padding: 15px;
            border-top: 1px solid #eee;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .chat-input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 25px;
            font-size: 14px;
        }
        
        .chat-input:focus {
            outline: none;
            border-color: #D40511;
        }
        
        .chat-send {
            background: #D40511;
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.2s;
        }
        
        .chat-send:hover {
            background: #b8040e;
            transform: scale(1.05);
        }
        
        .typing-indicator {
            display: flex;
            align-items: center;
            gap: 3px;
            padding: 10px 15px;
            background: #f0f0f0;
            border-radius: 15px;
            width: fit-content;
            margin-top: 5px;
        }
        
        .typing-dot {
            width: 8px;
            height: 8px;
            background: #999;
            border-radius: 50%;
            animation: typingAnimation 1.5s infinite ease-in-out;
        }
        
        .typing-dot:nth-child(1) {
            animation-delay: 0s;
        }
        
        .typing-dot:nth-child(2) {
            animation-delay: 0.3s;
        }
        
        .typing-dot:nth-child(3) {
            animation-delay: 0.6s;
        }
        
        @keyframes typingAnimation {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-5px);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="top-bar">
            📞 Customer Service: 1-800-CALL-DHL | 🌍 Available in 220+ Countries | 🚚 Free Pickup Available
        </div>
        <div class="nav-container">
            <a href="#" class="logo">DHL</a>
            <nav>
                <ul class="nav-menu">
                    <li><a href="#services">Ship Now</a></li>
                    <li><a href="#track">Track</a></li>
                    <li><a href="#about">Solutions</a></li>
                    <li><a href="#support">Support</a></li>
                    <li><a href="#locations">Locations</a></li>
                </ul>
            </nav>
            <div class="nav-actions">
                <a href="#login" class="login-btn">MyDHL+</a>
                <a href="#track" class="btn-track">Track Package</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-container">
            <h1>Excellence. Simply delivered.</h1>
            <p>The world's leading logistics company connecting 220+ countries and territories</p>
            
            <div class="tracking-section" id="track">
                <h2>Track Your Shipment</h2>
                <div class="tracking-tabs">
                    <button class="tab-btn active">Track by Number</button>
                    <button class="tab-btn">Track by Reference</button>
                    <button class="tab-btn">Bulk Track</button>
                </div>
                <form class="tracking-form" id="trackingForm">
                    <input type="text" class="tracking-input" id="trackingInput" placeholder="Enter tracking number (e.g., 1234567890)" required>
                    <button type="submit" class="btn-primary">
                        <span id="trackBtnText">Track Now</span>
                        <span id="trackBtnLoading" class="loading" style="display: none;"></span>
                    </button>
                </form>
                <div class="sample-tracking">
                    <strong>Sample tracking numbers:</strong><br>
                    📦 DHL1234567890 (In Transit) | 📦 DHL0987654321 (Delivered) | 📦 DHL1122334455 (Out for Delivery)
                </div>
            </div>
        </div>
    </section>

    <!-- Live Tracking Section -->
    <section class="live-tracking">
        <div class="live-container">
            <h2>🔴 Live Shipment Updates</h2>
            <div class="tracking-cards">
                <div class="tracking-card">
                    <div class="tracking-number">📦 DHL8765432109</div>
                    <div class="tracking-status">
                        <div class="status-dot"></div>
                        <strong>Out for Delivery</strong>
                    </div>
                    <div class="tracking-details">
                        <strong>From:</strong> Mumbai, India → <strong>To:</strong> New York, USA<br>
                        <strong>Last Update:</strong> 2 minutes ago<br>
                        <strong>Expected:</strong> Today by 6:00 PM<br>
                        <strong>Driver:</strong> Mike Johnson (#4521)
                    </div>
                </div>
                
                <div class="tracking-card">
                    <div class="tracking-number">📦 DHL5544332211</div>
                    <div class="tracking-status">
                        <div class="status-dot"></div>
                        <strong>In Transit</strong>
                    </div>
                    <div class="tracking-details">
                        <strong>From:</strong> London, UK → <strong>To:</strong> Dubai, UAE<br>
                        <strong>Last Update:</strong> 5 minutes ago<br>
                        <strong>Expected:</strong> Tomorrow by 2:00 PM<br>
                        <strong>Location:</strong> Frankfurt Hub
                    </div>
                </div>
                
                <div class="tracking-card">
                    <div class="tracking-number">📦 DHL9988776655</div>
                    <div class="tracking-status">
                        <div class="status-dot" style="background: #28a745;"></div>
                        <strong>Delivered ✅</strong>
                    </div>
                    <div class="tracking-details">
                        <strong>From:</strong> Tokyo, Japan → <strong>To:</strong> Sydney, Australia<br>
                        <strong>Delivered:</strong> 1 hour ago<br>
                        <strong>Signed by:</strong> Sarah Wilson<br>
                        <strong>Delivery Time:</strong> 2 days, 14 hours
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <div class="services-container">
            <h2>Our Premium Services</h2>
            <p class="services-subtitle">Choose from our comprehensive range of logistics solutions designed for businesses and individuals worldwide</p>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">🚀</div>
                    <h3>DHL Express Worldwide</h3>
                    <p>Fastest international express delivery service with door-to-door delivery in 1-3 business days to 220+ destinations.</p>
                    <div class="service-price">Starting from $45.99</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">📦</div>
                    <h3>DHL Parcel International</h3>
                    <p>Cost-effective solution for non-urgent international shipments with delivery in 3-7 business days.</p>
                    <div class="service-price">Starting from $19.99</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">🏢</div>
                    <h3>DHL Supply Chain</h3>
                    <p>End-to-end supply chain management solutions including warehousing, distribution, and fulfillment services.</p>
                    <div class="service-price">Custom Pricing</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">✈️</div>
                    <h3>DHL Global Forwarding</h3>
                    <p>Air and ocean freight solutions for large volume shipments with competitive rates and reliable transit times.</p>
                    <div class="service-price">Quote on Request</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">🛒</div>
                    <h3>DHL eCommerce</h3>
                    <p>Specialized e-commerce logistics solutions for online retailers including last-mile delivery and returns management.</p>
                    <div class="service-price">Starting from $8.99</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">🌍</div>
                    <h3>DHL Same Day</h3>
                    <p>Ultra-fast same-day delivery service for urgent shipments within major cities worldwide.</p>
                    <div class="service-price">Starting from $89.99</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
        <div class="stats-container">
            <div class="stat-item">
                <h3>220+</h3>
                <p>Countries & Territories Served</p>
            </div>
            <div class="stat-item">
                <h3>1.8B</h3>
                <p>Shipments Delivered Annually</p>
            </div>
            <div class="stat-item">
                <h3>550K+</h3>
                <p>Dedicated Employees Worldwide</p>
            </div>
            <div class="stat-item">
                <h3>99.1%</h3>
                <p>On-Time Delivery Rate</p>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="testimonials">
        <div class="testimonials-container">
            <h2>What Our Customers Say</h2>
            <div class="testimonials-grid">
                <div class="testimonial-card">
                    <p class="testimonial-text">DHL has been our logistics partner for over 5 years. Their reliability and speed are unmatched. We've never had a single delayed shipment!</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">AS</div>
                        <div class="author-info">
                            <h4>Arjun Sharma</h4>
                            <p>CEO, TechCorp India</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <p class="testimonial-text">The tracking system is incredible! I can see exactly where my package is at any moment. Customer service is also top-notch.</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">MJ</div>
                        <div class="author-info">
                            <h4>Maria Johnson</h4>
                            <p>Small Business Owner, USA</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <p class="testimonial-text">DHL Express saved our business during the pandemic. When others couldn't deliver, DHL was there. Truly the world's best logistics company!</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">LW</div>
                        <div class="author-info">
                            <h4>Li Wei</h4>
                            <p>Import/Export Manager, China</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer" id="contact">
        <div class="footer-container">
            <div class="footer-top">
                <div class="footer-brand">
                    <h3>DHL</h3>
                    <p>DHL is the global market leader in the logistics industry. We specialize in international express, road and air transport, contract logistics and international mail services.</p>
                    <div class="social-links">
                        <a href="#">📘</a>
                        <a href="#">🐦</a>
                        <a href="#">📷</a>
                        <a href="#">💼</a>
                        <a href="#">📺</a>
                    </div>
                </div>
                <div class="footer-section">
                    <h4>Services</h4>
                    <ul>
                        <li><a href="#">Express Delivery</a></li>
                        <li><a href="#">Parcel & Package</a></li>
                        <li><a href="#">Freight Transport</a></li>
                        <li><a href="#">Supply Chain</a></li>
                        <li><a href="#">eCommerce</a></li>
                        <li><a href="#">Same Day Delivery</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Support</h4>
                    <ul>
                        <li><a href="#">Track & Trace</a></li>
                        <li><a href="#">Customer Service</a></li>
                        <li><a href="#">Shipping Guide</a></li>
                        <li><a href="#">Rate & Transit Times</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Contact Us</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Company</h4>
                    <ul>
                        <li><a href="#">About DHL</a></li>
                        <li><a href="#">Careers</a></li>
                        <li><a href="#">Press Center</a></li>
                        <li><a href="#">Investor Relations</a></li>
                        <li><a href="#">Sustainability</a></li>
                        <li><a href="#">Innovation</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Quick Links</h4>
                    <ul>
                        <li><a href="#">Find Locations</a></li>
                        <li><a href="#">Schedule Pickup</a></li>
                        <li><a href="#">Get Quote</a></li>
                        <li><a href="#">Open Account</a></li>
                        <li><a href="#">Mobile App</a></li>
                        <li><a href="#">Developer API</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2024 DHL International GmbH. All rights reserved.</p>
                <div class="footer-links">
                    <a href="#">Privacy Policy</a>
                    <a href="#">Terms of Use</a>
                    <a href="#">Cookie Policy</a>
                    <a href="#">Legal Notice</a>
                </div>
            </div>
        </div>
    </footer>
    
    <!-- Chat Widget -->
    <div class="chat-widget collapsed" id="chatWidget">
        <div class="chat-header" id="chatHeader">
            <div class="chat-header-left">
                <div class="chat-avatar">D</div>
                <div class="chat-title">
                    <h3>DHL Support</h3>
                    <p id="chatStatus">Online</p>
                </div>
            </div>
            <button class="chat-toggle" id="chatToggle">▲</button>
        </div>
        <div class="chat-body" id="chatBody" style="display: none;">
            <!-- Messages will be added here dynamically -->
        </div>
        <div class="chat-footer" id="chatFooter" style="display: none;">
            <input type="text" class="chat-input" id="chatInput" placeholder="Type your message..." disabled>
            <button class="chat-send" id="chatSend" disabled>➤</button>
        </div>
    </div>

    <script>
        // Realistic tracking data
        const trackingData = {
            'DHL1234567890': {
                status: 'In Transit',
                from: 'New Delhi, India',
                to: 'Los Angeles, USA',
                currentLocation: 'Dubai Hub, UAE',
                expectedDelivery: 'Tomorrow by 3:00 PM',
                updates: [
                    { time: '2 hours ago', location: 'Dubai Hub, UAE', status: 'Departed facility' },
                    { time: '8 hours ago', location: 'Mumbai, India', status: 'Arrived at facility' },
                    { time: '12 hours ago', location: 'New Delhi, India', status: 'Picked up' }
                ]
            },
            'DHL0987654321': {
                status: 'Delivered',
                from: 'London, UK',
                to: 'New York, USA',
                deliveredTo: 'John Smith',
                deliveryTime: '2 hours ago',
                updates: [
                    { time: '2 hours ago', location: 'New York, USA', status: 'Delivered - Signed by John Smith' },
                    { time: '4 hours ago', location: 'New York, USA', status: 'Out for delivery' },
                    { time: '1 day ago', location: 'Cincinnati Hub, USA', status: 'Departed facility' }
                ]
            },
            'DHL1122334455': {
                status: 'Out for Delivery',
                from: 'Tokyo, Japan',
                to: 'Sydney, Australia',
                driver: 'Sarah Wilson (#7823)',
                expectedDelivery: 'Today by 5:00 PM',
                updates: [
                    { time: '30 minutes ago', location: 'Sydney, Australia', status: 'Out for delivery' },
                    { time: '3 hours ago', location: 'Sydney Hub, Australia', status: 'Arrived at delivery facility' },
                    { time: '1 day ago', location: 'Tokyo, Japan', status: 'Departed origin' }
                ]
            }
        };

        // Enhanced tracking form functionality
        document.getElementById('trackingForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const trackingNumber = document.getElementById('trackingInput').value.trim();
            const trackBtn = document.getElementById('trackBtnText');
            const loadingSpinner = document.getElementById('trackBtnLoading');
            
            if (!trackingNumber) {
                alert('⚠️ Please enter a tracking number');
                return;
            }

            // Show loading state
            trackBtn.style.display = 'none';
            loadingSpinner.style.display = 'inline-block';

            // Simulate API call delay
            setTimeout(() => {
                trackBtn.style.display = 'inline';
                loadingSpinner.style.display = 'none';

                const data = trackingData[trackingNumber.toUpperCase()];
                
                if (data) {
                    let alertMessage = `📦 Tracking Number: ${trackingNumber}\n\n`;
                    alertMessage += `📍 Status: ${data.status}\n`;
                    alertMessage += `🚚 From: ${data.from}\n`;
                    alertMessage += `📍 To: ${data.to}\n`;
                    
                    if (data.status === 'Delivered') {
                        alertMessage += `✅ Delivered to: ${data.deliveredTo}\n`;
                        alertMessage += `⏰ Delivery time: ${data.deliveryTime}\n`;
                    } else if (data.status === 'Out for Delivery') {
                        alertMessage += `🚛 Driver: ${data.driver}\n`;
                        alertMessage += `⏰ Expected: ${data.expectedDelivery}\n`;
                    } else {
                        alertMessage += `📍 Current location: ${data.currentLocation}\n`;
                        alertMessage += `⏰ Expected: ${data.expectedDelivery}\n`;
                    }
                    
                    alertMessage += `\n📋 Recent Updates:\n`;
                    data.updates.forEach(update => {
                        alertMessage += `• ${update.time}: ${update.status} (${update.location})\n`;
                    });
                    
                    alert(alertMessage);
                } else {
                    alert(`❌ Tracking number "${trackingNumber}" not found.\n\n💡 Try these sample numbers:\n• DHL1234567890 (In Transit)\n• DHL0987654321 (Delivered)\n• DHL1122334455 (Out for Delivery)`);
                }
            }, 1500);
        });

        // Tab functionality
        document.querySelectorAll('.tab-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
                this.classList.add('active');
                
                const trackingInput = document.getElementById('trackingInput');
                if (this.textContent === 'Track by Reference') {
                    trackingInput.placeholder = 'Enter reference number (e.g., REF123456)';
                } else if (this.textContent === 'Bulk Track') {
                    trackingInput.placeholder = 'Enter multiple tracking numbers (one per line)';
                } else {
                    trackingInput.placeholder = 'Enter tracking number (e.g., DHL1234567890)';
                }
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Auto-update live tracking times
        setInterval(() => {
            const timeElements = document.querySelectorAll('.tracking-details');
            timeElements.forEach(element => {
                if (element.textContent.includes('minutes ago')) {
                    const currentMinutes = parseInt(element.textContent.match(/(\d+) minutes ago/)[1]);
                    element.innerHTML = element.innerHTML.replace(`${currentMinutes} minutes ago`, `${currentMinutes + 1} minutes ago`);
                }
            });
        }, 60000); // Update every minute

        // Add some interactive effects
        document.querySelectorAll('.service-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.borderLeft = '5px solid #D40511';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.borderLeft = 'none';
            });
        });

        // Simulate real-time notifications
        setTimeout(() => {
            if (Math.random() > 0.7) {
                const notification = document.createElement('div');
                notification.style.cssText = `
                    position: fixed;
                    top: 100px;
                    right: 20px;
                    background: #28a745;
                    color: white;
                    padding: 15px 20px;
                    border-radius: 10px;
                    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
                    z-index: 10000;
                    animation: slideIn 0.5s ease-out;
                `;
                notification.innerHTML = '🎉 Package DHL9988776655 has been delivered to Sydney!';
                document.body.appendChild(notification);
                
                setTimeout(() => {
                    notification.remove();
                }, 5000);
            }
        }, 3000);
        
        // Chat Widget Functionality
        const chatWidget = document.getElementById('chatWidget');
        const chatHeader = document.getElementById('chatHeader');
        const chatToggle = document.getElementById('chatToggle');
        const chatBody = document.getElementById('chatBody');
        const chatFooter = document.getElementById('chatFooter');
        const chatInput = document.getElementById('chatInput');
        const chatSend = document.getElementById('chatSend');
        const chatStatus = document.getElementById('chatStatus');
        
        // Chat responses database
        const chatResponses = {
            'track_package': {
                question: 'How do I track my package?',
                answer: 'You can track your package by entering your tracking number in the tracking box on our homepage. Alternatively, you can use our mobile app or call our customer service at 1-800-CALL-DHL.',
                followUp: ['lost_package', 'delivery_time', 'tracking_not_working']
            },
            'shipping_rates': {
                question: 'What are your shipping rates?',
                answer: 'Our shipping rates depend on the package weight, dimensions, origin, destination, and service type. You can get a quote by using our rate calculator on our website or contacting customer service.',
                followUp: ['service_types', 'customs_duties', 'discount_codes']
            },
            'delivery_time': {
                question: 'How long will my delivery take?',
                answer: 'Delivery times vary based on the service selected and destination. DHL Express typically delivers in 1-3 business days internationally, while DHL Parcel may take 3-7 business days. You can check estimated delivery times using our transit time calculator.',
                followUp: ['track_package', 'delivery_delay', 'express_services']
            },
            'pickup_request': {
                question: 'How do I schedule a pickup?',
                answer: 'You can schedule a pickup through our website by logging into your MyDHL+ account, using our mobile app, or calling customer service at 1-800-CALL-DHL. We offer same-day pickup in most major cities if requested before cut-off times.',
                followUp: ['pickup_cost', 'cancel_pickup', 'business_account']
            },
            'lost_package': {
                question: 'My package is lost. What should I do?',
                answer: 'If your tracking hasn\'t updated for 24-48 hours, please contact our customer service team at 1-800-CALL-DHL with your tracking number. We can initiate a package trace and investigation. For international shipments, please allow up to 72 hours for tracking updates.',
                followUp: ['file_claim', 'package_insurance', 'track_package']
            },
            'customs_duties': {
                question: 'How do customs and duties work?',
                answer: 'International shipments may be subject to customs duties and taxes imposed by the destination country. These fees are typically collected from the recipient upon delivery. DHL can provide customs clearance services, but we cannot predict or guarantee the amount of duties that may apply.',
                followUp: ['customs_paperwork', 'prohibited_items', 'duty_paid_shipping']
            },
            'business_account': {
                question: 'How do I open a business account?',
                answer: 'To open a DHL business account, visit our website and complete the business application form or contact our sales team at 1-800-CALL-DHL. Business accounts offer volume discounts, dedicated support, and simplified shipping processes.',
                followUp: ['account_benefits', 'credit_terms', 'volume_discounts']
            },
            'service_types': {
                question: 'What shipping services do you offer?',
                answer: 'DHL offers a range of services including DHL Express (1-3 day delivery), DHL Parcel International (3-7 days), DHL eCommerce, DHL Global Forwarding (air/ocean freight), DHL Supply Chain, and DHL Same Day for urgent deliveries.',
                followUp: ['express_services', 'shipping_rates', 'service_comparison']
            },
            'packaging_guidelines': {
                question: 'What are your packaging guidelines?',
                answer: 'For safe transit, use sturdy boxes with appropriate cushioning material. Packages should be properly sealed with shipping tape. DHL offers free packaging for Express shipments. Ensure items are properly protected and cannot move within the package. Visit our website for detailed packaging guidelines.',
                followUp: ['packaging_materials', 'weight_limits', 'prohibited_items']
            },
            'delivery_delay': {
                question: 'My delivery is delayed. What\'s happening?',
                answer: 'Delays can occur due to weather, customs clearance, or high volume periods. Check your tracking for the most current status. If your package is significantly delayed beyond the estimated delivery date, please contact our customer service team with your tracking number.',
                followUp: ['track_package', 'file_claim', 'delivery_guarantee']
            },
            'contact_support': {
                question: 'How do I contact customer support?',
                answer: 'You can contact DHL customer support by calling 1-800-CALL-DHL, using the live chat on our website, emailing customer.service@dhl.com, or visiting one of our service points. Our customer service team is available 24/7 for urgent inquiries.',
                followUp: ['business_support', 'complaint_process', 'local_office']
            },
            'tracking_not_working': {
                question: 'My tracking number isn\'t working',
                answer: 'If your tracking number isn\'t working, please verify you\'ve entered it correctly. New shipments may take 24 hours to appear in our system. If you\'ve recently shipped your package, please allow some time for it to be scanned into our network. For immediate assistance, contact customer service.',
                followUp: ['track_package', 'lost_package', 'contact_support']
            },
            'prohibited_items': {
                question: 'What items are prohibited for shipping?',
                answer: 'DHL prohibits shipping dangerous goods, illegal items, live animals, human remains, cash/currency, and certain perishables. Restrictions vary by country. Please check our website for a complete list of prohibited and restricted items before shipping.',
                followUp: ['customs_duties', 'packaging_guidelines', 'dangerous_goods']
            },
            'request_quote': {
                question: 'I need a shipping quote',
                answer: 'I\'d be happy to help you get a shipping quote! Please provide me with the following details and I\'ll calculate the best rates for you.',
                followUp: ['track_package', 'shipping_rates', 'service_types']
            },
        };
        
        // Initialize chat
        let chatOpen = false;
        let currentOptions = ['track_package', 'request_quote', 'shipping_rates', 'delivery_time', 'pickup_request', 'contact_support'];
        
        // Toggle chat open/closed
        chatHeader.addEventListener('click', () => {
            if (chatOpen) {
                closeChat();
            } else {
                openChat();
            }
        });
        
        function openChat() {
            chatWidget.classList.remove('collapsed');
            chatWidget.classList.add('expanded');
            chatBody.style.display = 'flex';
            chatFooter.style.display = 'flex';
            chatToggle.textContent = '▼';
            chatOpen = true;
            
            // If this is the first open, show welcome message
            if (chatBody.children.length === 0) {
                showWelcomeMessage();
            }
        }
        
        function closeChat() {
            chatWidget.classList.remove('expanded');
            chatWidget.classList.add('collapsed');
            chatBody.style.display = 'none';
            chatFooter.style.display = 'none';
            chatToggle.textContent = '▲';
            chatOpen = false;
        }
        
        function showWelcomeMessage() {
            addAgentMessage('👋 Welcome to DHL Customer Support! How can I help you today?');
            setTimeout(() => {
                showOptions(currentOptions);
            }, 500);
        }
        
        function addAgentMessage(text) {
            const message = document.createElement('div');
            message.className = 'chat-message agent';
            message.innerHTML = text;
            
            const time = document.createElement('span');
            time.className = 'chat-time';
            time.textContent = getCurrentTime();
            message.appendChild(time);
            
            chatBody.appendChild(message);
            chatBody.scrollTop = chatBody.scrollHeight;
        }
        
        function addUserMessage(text) {
            const message = document.createElement('div');
            message.className = 'chat-message user';
            message.textContent = text;
            
            const time = document.createElement('span');
            time.className = 'chat-time';
            time.textContent = getCurrentTime();
            message.appendChild(time);
            
            chatBody.appendChild(message);
            chatBody.scrollTop = chatBody.scrollHeight;
        }
        
        function showTypingIndicator() {
            const typing = document.createElement('div');
            typing.className = 'typing-indicator';
            typing.id = 'typingIndicator';
            
            for (let i = 0; i < 3; i++) {
                const dot = document.createElement('div');
                dot.className = 'typing-dot';
                typing.appendChild(dot);
            }
            
            chatBody.appendChild(typing);
            chatBody.scrollTop = chatBody.scrollHeight;
        }
        
        function removeTypingIndicator() {
            const indicator = document.getElementById('typingIndicator');
            if (indicator) {
                indicator.remove();
            }
        }
        
        function showOptions(optionKeys) {
            const optionsContainer = document.createElement('div');
            optionsContainer.className = 'chat-options';
            
            optionKeys.forEach(key => {
                if (chatResponses[key]) {
                    const option = document.createElement('div');
                    option.className = 'chat-option';
                    option.textContent = chatResponses[key].question;
                    option.dataset.key = key;
                    
                    option.addEventListener('click', function() {
                        const selectedKey = this.dataset.key;
                        handleOptionSelect(selectedKey);
                    });
                    
                    optionsContainer.appendChild(option);
                }
            });
            
            const message = document.createElement('div');
            message.className = 'chat-message agent';
            message.appendChild(optionsContainer);
            
            chatBody.appendChild(message);
            chatBody.scrollTop = chatBody.scrollHeight;
        }
        
        function handleOptionSelect(key) {
            if (key === 'request_quote') {
                // Show user question
                addUserMessage(chatResponses[key].question);
                
                // Show typing indicator
                showTypingIndicator();
                
                // Simulate agent typing delay
                setTimeout(() => {
                    removeTypingIndicator();
                    
                    // Show agent response
                    addAgentMessage(chatResponses[key].answer);
                    
                    // Show quote form after a delay
                    setTimeout(() => {
                        showQuoteForm();
                    }, 500);
                }, 1500);
                return;
            }
            if (chatResponses[key]) {
                // Show user question
                addUserMessage(chatResponses[key].question);
                
                // Show typing indicator
                showTypingIndicator();
                
                // Simulate agent typing delay
                setTimeout(() => {
                    removeTypingIndicator();
                    
                    // Show agent response
                    addAgentMessage(chatResponses[key].answer);
                    
                    // Show follow-up options after a delay
                    setTimeout(() => {
                        if (chatResponses[key].followUp && chatResponses[key].followUp.length > 0) {
                            addAgentMessage('Do you have any other questions?');
                            showOptions(chatResponses[key].followUp);
                        } else {
                            showOptions(['track_package', 'shipping_rates', 'delivery_time', 'contact_support']);
                        }
                    }, 1000);
                }, 1500);
            }
        }

        function showQuoteForm() {
            const formHtml = `
                <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; margin: 10px 0;">
                    <h4 style="margin-bottom: 15px; color: #D40511;">📋 Shipping Quote Request</h4>
                    <form id="quoteForm" style="display: flex; flex-direction: column; gap: 12px;">
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px;">
                            <div>
                                <label style="font-size: 12px; color: #666; display: block; margin-bottom: 5px;">From Country</label>
                                <select id="fromCountry" style="width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 5px; font-size: 13px;">
                                    <option value="">Select Country</option>
                                    <option value="US">United States</option>
                                    <option value="UK">United Kingdom</option>
                                    <option value="IN">India</option>
                                    <option value="CN">China</option>
                                    <option value="DE">Germany</option>
                                    <option value="JP">Japan</option>
                                    <option value="AU">Australia</option>
                                    <option value="CA">Canada</option>
                                    <option value="FR">France</option>
                                    <option value="AE">UAE</option>
                                </select>
                            </div>
                            <div>
                                <label style="font-size: 12px; color: #666; display: block; margin-bottom: 5px;">To Country</label>
                                <select id="toCountry" style="width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 5px; font-size: 13px;">
                                    <option value="">Select Country</option>
                                    <option value="US">United States</option>
                                    <option value="UK">United Kingdom</option>
                                    <option value="IN">India</option>
                                    <option value="CN">China</option>
                                    <option value="DE">Germany</option>
                                    <option value="JP">Japan</option>
                                    <option value="AU">Australia</option>
                                    <option value="CA">Canada</option>
                                    <option value="FR">France</option>
                                    <option value="AE">UAE</option>
                                </select>
                            </div>
                        </div>
                        
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px;">
                            <div>
                                <label style="font-size: 12px; color: #666; display: block; margin-bottom: 5px;">Weight (kg)</label>
                                <input type="number" id="weight" placeholder="e.g., 2.5" style="width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 5px; font-size: 13px;" min="0.1" step="0.1">
                            </div>
                            <div>
                                <label style="font-size: 12px; color: #666; display: block; margin-bottom: 5px;">Package Type</label>
                                <select id="packageType" style="width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 5px; font-size: 13px;">
                                    <option value="document">Document</option>
                                    <option value="package">Package</option>
                                    <option value="pallet">Pallet</option>
                                </select>
                            </div>
                        </div>
                        
                        <div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 8px;">
                            <div>
                                <label style="font-size: 12px; color: #666; display: block; margin-bottom: 5px;">Length (cm)</label>
                                <input type="number" id="length" placeholder="30" style="width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 5px; font-size: 13px;" min="1">
                            </div>
                            <div>
                                <label style="font-size: 12px; color: #666; display: block; margin-bottom: 5px;">Width (cm)</label>
                                <input type="number" id="width" placeholder="20" style="width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 5px; font-size: 13px;" min="1">
                            </div>
                            <div>
                                <label style="font-size: 12px; color: #666; display: block; margin-bottom: 5px;">Height (cm)</label>
                                <input type="number" id="height" placeholder="15" style="width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 5px; font-size: 13px;" min="1">
                            </div>
                        </div>
                        
                        <div>
                            <label style="font-size: 12px; color: #666; display: block; margin-bottom: 5px;">Service Type</label>
                            <select id="serviceType" style="width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 5px; font-size: 13px;">
                                <option value="express">DHL Express (1-3 days)</option>
                                <option value="standard">DHL Standard (3-7 days)</option>
                                <option value="economy">DHL Economy (7-14 days)</option>
                            </select>
                        </div>
                        
                        <button type="submit" style="background: #D40511; color: white; padding: 12px; border: none; border-radius: 5px; font-weight: bold; cursor: pointer; margin-top: 10px;">
                            💰 Get Quote
                        </button>
                    </form>
                </div>
            `;
            
            const message = document.createElement('div');
            message.className = 'chat-message agent';
            message.innerHTML = formHtml;
            
            chatBody.appendChild(message);
            chatBody.scrollTop = chatBody.scrollHeight;
            
            // Add form submission handler
            document.getElementById('quoteForm').addEventListener('submit', function(e) {
                e.preventDefault();
                handleQuoteSubmission();
            });
        }

        function handleQuoteSubmission() {
            const fromCountry = document.getElementById('fromCountry').value;
            const toCountry = document.getElementById('toCountry').value;
            const weight = document.getElementById('weight').value;
            const packageType = document.getElementById('packageType').value;
            const length = document.getElementById('length').value;
            const width = document.getElementById('width').value;
            const height = document.getElementById('height').value;
            const serviceType = document.getElementById('serviceType').value;
            
            if (!fromCountry || !toCountry || !weight) {
                addAgentMessage('❌ Please fill in all required fields (From Country, To Country, and Weight).');
                return;
            }
            
            // Show user's request summary
            addUserMessage(`Quote request: ${weight}kg ${packageType} from ${fromCountry} to ${toCountry}`);
            
            // Show typing indicator
            showTypingIndicator();
            
            // Generate dummy quote
            setTimeout(() => {
                removeTypingIndicator();
                generateDummyQuote(fromCountry, toCountry, weight, packageType, serviceType);
            }, 2000);
        }

        function generateDummyQuote(from, to, weight, packageType, serviceType) {
            // Dummy pricing logic
            let basePrice = 25;
            const weightNum = parseFloat(weight);
            
            // Weight-based pricing
            if (weightNum <= 1) basePrice += 15;
            else if (weightNum <= 5) basePrice += 25;
            else if (weightNum <= 10) basePrice += 45;
            else basePrice += 65;
            
            // Distance-based pricing (dummy logic)
            const longDistance = ['US-IN', 'UK-AU', 'CN-US', 'JP-UK', 'IN-US', 'AU-UK'];
            const route = `${from}-${to}`;
            if (longDistance.includes(route) || longDistance.includes(`${to}-${from}`)) {
                basePrice += 30;
            }
            
            // Service type multiplier
            let expressPrice = Math.round(basePrice * 1.8);
            let standardPrice = Math.round(basePrice * 1.2);
            let economyPrice = Math.round(basePrice * 0.8);
            
            // Package type adjustment
            if (packageType === 'pallet') {
                expressPrice += 50;
                standardPrice += 35;
                economyPrice += 20;
            }
            
            const countryNames = {
                'US': 'United States', 'UK': 'United Kingdom', 'IN': 'India', 'CN': 'China',
                'DE': 'Germany', 'JP': 'Japan', 'AU': 'Australia', 'CA': 'Canada',
                'FR': 'France', 'AE': 'UAE'
            };
            
            const quoteHtml = `
                <div style="background: linear-gradient(135deg, #D40511, #FFCC00); padding: 20px; border-radius: 10px; color: white; margin: 10px 0;">
                    <h4 style="margin-bottom: 15px;">📊 Your Shipping Quote</h4>
                    <div style="background: rgba(255,255,255,0.1); padding: 15px; border-radius: 8px; margin-bottom: 15px;">
                        <strong>📦 Shipment Details:</strong><br>
                        📍 From: ${countryNames[from] || from}<br>
                        📍 To: ${countryNames[to] || to}<br>
                        ⚖️ Weight: ${weight} kg<br>
                        📋 Type: ${packageType.charAt(0).toUpperCase() + packageType.slice(1)}
                    </div>
                    
                    <div style="background: rgba(255,255,255,0.9); color: #333; padding: 15px; border-radius: 8px;">
                        <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; padding: 10px; background: #f8f9fa; border-radius: 5px; ${serviceType === 'express' ? 'border: 2px solid #D40511;' : ''}">
                            <div>
                                <strong>🚀 DHL Express</strong><br>
                                <small>1-3 business days</small>
                            </div>
                            <div style="text-align: right;">
                                <strong style="font-size: 18px; color: #D40511;">$${expressPrice}</strong>
                            </div>
                        </div>
                        
                        <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; padding: 10px; background: #f8f9fa; border-radius: 5px; ${serviceType === 'standard' ? 'border: 2px solid #D40511;' : ''}">
                            <div>
                                <strong>📦 DHL Standard</strong><br>
                                <small>3-7 business days</small>
                            </div>
                            <div style="text-align: right;">
                                <strong style="font-size: 18px; color: #D40511;">$${standardPrice}</strong>
                            </div>
                        </div>
                        
                        <div style="display: flex; justify-content: space-between; align-items: center; padding: 10px; background: #f8f9fa; border-radius: 5px; ${serviceType === 'economy' ? 'border: 2px solid #D40511;' : ''}">
                            <div>
                                <strong>💰 DHL Economy</strong><br>
                                <small>7-14 business days</small>
                            </div>
                            <div style="text-align: right;">
                                <strong style="font-size: 18px; color: #D40511;">$${economyPrice}</strong>
                            </div>
                        </div>
                    </div>
                    
                    <div style="margin-top: 15px; font-size: 12px; opacity: 0.9;">
                        ✅ Free packaging included<br>
                        ✅ Door-to-door delivery<br>
                        ✅ Real-time tracking<br>
                        ✅ Insurance up to $100 included<br>
                        📞 Quote valid for 7 days | Ref: DHL${Math.random().toString(36).substr(2, 8).toUpperCase()}
                    </div>
                </div>
            `;
            
            addAgentMessage(quoteHtml);
            
            setTimeout(() => {
                addAgentMessage('Would you like to proceed with booking or do you have any other questions? I can also help you with pickup scheduling or tracking existing shipments.');
                showOptions(['pickup_request', 'track_package', 'service_types', 'contact_support']);
            }, 1000);
        }
        
        function getCurrentTime() {
            const now = new Date();
            let hours = now.getHours();
            const minutes = now.getMinutes().toString().padStart(2, '0');
            const ampm = hours >= 12 ? 'PM' : 'AM';
            
            hours = hours % 12;
            hours = hours ? hours : 12; // Convert 0 to 12
            
            return `${hours}:${minutes} ${ampm}`;
        }
        
        // Simulate agent status changes
        function updateAgentStatus() {
            const statuses = ['Online', 'Online', 'Online', 'Online', 'Typing...'];
            const randomStatus = statuses[Math.floor(Math.random() * statuses.length)];
            chatStatus.textContent = randomStatus;
            
            setTimeout(updateAgentStatus, Math.random() * 10000 + 5000);
        }
        
        // Start status updates
        updateAgentStatus();
        
        // Auto-open chat after a delay
        setTimeout(() => {
            if (!chatOpen) {
                openChat();
            }
        }, 3000);
    </script>
</body>
</html>
