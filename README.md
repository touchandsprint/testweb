<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Warm Ups - Interactive Fitness Game</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #673AB7;
            --secondary: #512DA8;
            --light: #EDE7F6;
            --dark: #343a40;
            --text: #6c757d;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            color: var(--text);
            line-height: 1.6;
        }
        
        /* Header */
        .navbar {
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 999;
            background: rgba(255,255,255,0.95);
            box-shadow: 0 2px 15px rgba(0,0,0,0.1);
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .navbar .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
        }
        
        .logo img {
            height: 40px;
        }
        
        .btn {
            display: inline-block;
            background: var(--primary);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .btn:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(103, 58, 183, 0.2);
        }
        
        /* Hero Section */
        .hero {
            padding: 180px 0 100px;
            background: linear-gradient(135deg, #f5f7fa 0%, #e4e8f0 100%);
            text-align: center;
        }
        
        .hero h1 {
            font-size: 48px;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 18px;
            max-width: 700px;
            margin: 0 auto 40px;
        }
        
        .hero-image {
            max-width: 800px;
            margin: 50px auto 0;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }
        
        .hero-image img {
            width: 100%;
            display: block;
        }
        
        /* Features Section */
        .section {
            padding: 100px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .section-title h2 {
            font-size: 36px;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 15px;
        }
        
        .section-title p {
            max-width: 700px;
            margin: 0 auto;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        /* Different card colors for "Why Choose Warm Ups" section */
        .feature-card.card-1 {
            border-top: 5px solid #B39DDB;
        }
        
        .feature-card.card-2 {
            border-top: 5px solid #7E57C2;
        }
        
        .feature-card.card-3 {
            border-top: 5px solid #5E35B1;
        }
        
        .feature-icon {
            font-size: 40px;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .feature-card h3 {
            font-size: 22px;
            font-weight: 600;
            color: var(--dark);
            margin-bottom: 15px;
        }
        
        /* Bullet points for variation descriptions */
        .variation-content ul {
            padding-left: 20px;
            margin: 15px 0;
        }
        
        .variation-content li {
            margin-bottom: 8px;
        }
        
        /* Variations Section */
        .variation-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }
        
        .variation-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .variation-image {
            height: 200px;
            background: #eee;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #999;
            font-size: 14px;
        }
        
        .variation-content {
            padding: 25px;
        }
        
        .variation-content h3 {
            font-size: 20px;
            font-weight: 600;
            color: var(--dark);
            margin-bottom: 10px;
        }
        
        .variation-content .level {
            display: inline-block;
            padding: 3px 10px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 500;
            margin-bottom: 15px;
        }
        
        .level-beginner {
            background: #e3f9e5;
            color: #28a745;
        }
        
        .level-intermediate {
            background: #fff8e1;
            color: #ffc107;
        }
        
        .level-advanced {
            background: #ffe8e8;
            color: #dc3545;
        }
        
        /* Implementation Guide Section */
        .guide-step {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            margin-bottom: 40px;
        }
        
        .guide-image {
            width: 100%;
            max-width: 400px;
            height: 250px;
            background: #EDE7F6;
            border-radius: 10px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-weight: 500;
        }
        
        .guide-content {
            max-width: 600px;
        }
        
        .guide-content h3 {
            font-size: 24px;
            color: var(--dark);
            margin-bottom: 15px;
        }
        
        .guide-content ul {
            text-align: left;
            padding-left: 20px;
        }
        
        .guide-content li {
            margin-bottom: 8px;
        }
        
        /* CTA Section */
        .cta {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            text-align: center;
            padding: 80px 0;
            border-radius: 10px;
            margin: 50px 0;
        }
        
        .cta h2 {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 20px;
        }
        
        .cta p {
            max-width: 700px;
            margin: 0 auto 30px;
            font-size: 18px;
        }
        
        .btn-light {
            background: white;
            color: var(--primary);
        }
        
        .google-play-badge {
            height: 60px;
        }
        
        /* Footer */
        .footer {
            background: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }
        
        .footer-logo {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 20px;
        }
        
        .footer-links {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .footer-links h3 {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 20px;
        }
        
        .footer-links ul {
            list-style: none;
            padding: 0;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #adb5bd;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #adb5bd;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <nav class="navbar">
        <div class="container">
            <div class="logo">
                <img src="logo-placeholder.png" alt="Warm Ups Logo">
            </div>
            <a href="https://play.google.com/store/apps/details?id=com.ar.touchrace" class="btn">Download Now</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Transform Fitness into Play</h1>
            <p>Warm Ups is a dynamic, device-powered fitness game that brings people together through fun, movement-based challenges. Using just Android smartphones, it transforms any space into an interactive playground — no extra sensors or equipment needed.</p>
            <a href="https://play.google.com/store/apps/details?id=com.ar.touchrace">
                <img src="https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png" alt="Get it on Google Play" class="google-play-badge">
            </a>
            <div class="hero-image">
                <img src="hero-placeholder.jpg" alt="Warm Ups in action">
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="section">
        <div class="container">
            <div class="section-title">
                <h2>Why Choose Warm Ups</h2>
                <p>From beginners to fitness enthusiasts, solo players to big team, the app offers customizable activities designed to aid coordination, and social connection.</p>
            </div>
            <div class="features-grid">
                <div class="feature-card card-1">
                    <div class="feature-icon">🏃</div>
                    <h3>No Equipment Needed</h3>
                    <p>Just use Android smartphones you already own - no special sensors or gear required.</p>
                </div>
                <div class="feature-card card-2">
                    <div class="feature-icon">👥</div>
                    <h3>Team Bonding</h3>
                    <p>Perfect for corporate teams, sports groups, or social gatherings to build connections.</p>
                </div>
                <div class="feature-card card-3">
                    <div class="feature-icon">⚙️</div>
                    <h3>Customizable Activities</h3>
                    <p>Choose from multiple game variations to match your group's fitness level and goals.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Variations Section -->
    <section class="section" style="background: #f8f9fa;">
        <div class="container">
            <div class="section-title">
                <h2>Activity Variations</h2>
                <p>Whether you're looking to energize your morning, break the ice at a gathering, or simply get moving with friends, Warm Ups makes fitness playful and inclusive.</p>
            </div>
            <div class="features-grid">
                <!-- Beginner Variation -->
                <div class="variation-card">
                    <div class="variation-image" style="background: #e3f9e5;">[Tiptoe Walk Image]</div>
                    <div class="variation-content">
                        <h3>Tiptoe Walk</h3>
                        <span class="level level-beginner">Beginner</span>
                        <ul>
                            <li>Walk/run on tiptoes to target devices</li>
                            <li>Improves balance and calf engagement</li>
                            <li>Great for warming up lower body</li>
                            <li>Enhances proprioception</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Intermediate Variation -->
                <div class="variation-card">
                    <div class="variation-image" style="background: #fff8e1;">[Crouch Walk Image]</div>
                    <div class="variation-content">
                        <h3>Crouch Walk</h3>
                        <span class="level level-intermediate">Intermediate</span>
                        <ul>
                            <li>Squat-position locomotion</li>
                            <li>Strengthens quadriceps, glutes, and hamstrings</li>
                            <li>Improves lower body endurance</li>
                            <li>Engages core muscles</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Advanced Variation -->
                <div class="variation-card">
                    <div class="variation-image" style="background: #ffe8e8;">[Blindfolded Partner Image]</div>
                    <div class="variation-content">
                        <h3>Blindfolded Partner</h3>
                        <span class="level level-advanced">Advanced</span>
                        <ul>
                            <li>Verbal-guided navigation</li>
                            <li>Enhances communication skills</li>
                            <li>Builds trust and team bonding</li>
                            <li>Improves spatial awareness</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Implementation Guide Section -->
    <section class="section">
        <div class="container">
            <div class="section-title">
                <h2>Implementation Guide</h2>
                <p>Seamless setup process to get your interactive fitness session started quickly</p>
            </div>
            
            <div class="guide-step">
                <div class="guide-image">[Installation Screenshot]</div>
                <div class="guide-content">
                    <h3>1. Installation</h3>
                    <ul>
                        <li>Download from Google Play Store on all Android devices</li>
                        <li>Minimum Android version 8.0 required</li>
                        <li>Approximately 15MB download size</li>
                    </ul>
                </div>
            </div>
            
            <div class="guide-step">
                <div class="guide-image">[Initialization Screenshot]</div>
                <div class="guide-content">
                    <h3>2. Initialization</h3>
                    <ul>
                        <li>Launch the Warm Ups application</li>
                        <li>Select Single Glow or Two Glow mode</li>
                        <li>Grant necessary permissions (location, Bluetooth)</li>
                    </ul>
                </div>
            </div>
            
            <div class="guide-step">
                <div class="guide-image">[Configuration Screenshot]</div>
                <div class="guide-content">
                    <h3>3. Game Configuration</h3>
                    <ul>
                        <li>Choose between Count-Based or Duration-Based format</li>
                        <li>Count-Based: Set target number of device activations</li>
                        <li>Duration-Based: Set time limit for the session</li>
                        <li>Adjust difficulty settings as needed</li>
                    </ul>
                </div>
            </div>
            
            <div class="guide-step">
                <div class="guide-image">[Network Setup Screenshot]</div>
                <div class="guide-content">
                    <h3>4. Network Setup</h3>
                    <ul>
                        <li>Host device generates unique game code</li>
                        <li>Participants enter code to join session</li>
                        <li>All devices connect via local WiFi or Bluetooth</li>
                        <li>Connection status visible on all devices</li>
                    </ul>
                </div>
            </div>
            
            <div class="guide-step">
                <div class="guide-image">[Device Placement Screenshot]</div>
                <div class="guide-content">
                    <h3>5. Device Placement</h3>
                    <ul>
                        <li>Arrange devices according to selected variation</li>
                        <li>Space devices 2-3 meters apart for optimal play</li>
                        <li>Ensure flat, stable surfaces</li>
                        <li>Consider safety when placing devices</li>
                    </ul>
                </div>
            </div>
            
            <div class="guide-step">
                <div class="guide-image">[Game Execution Screenshot]</div>
                <div class="guide-content">
                    <h3>6. Game Execution</h3>
                    <ul>
                        <li>Host initiates the session</li>
                        <li>Real-time progress visible on all devices</li>
                        <li>Visual and audio feedback for interactions</li>
                        <li>Session summary displayed upon completion</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="section">
        <div class="container">
            <div class="cta">
                <h2>Ready to Transform Your Fitness Routine?</h2>
                <p>Join thousands of users enjoying interactive, social fitness with Warm Ups.</p>
                <a href="https://play.google.com/store/apps/details?id=com.ar.touchrace">
                    <img src="https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png" alt="Get it on Google Play" class="google-play-badge">
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-links">
                <div>
                    <h3>Warm Ups</h3>
                    <p>Transforming fitness and team bonding through interactive challenges.</p>
                </div>
                <div>
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Features</a></li>
                        <li><a href="#">Activities</a></li>
                        <li><a href="#">How It Works</a></li>
                        <li><a href="#">Download</a></li>
                    </ul>
                </div>
                <div>
                    <h3>Company</h3>
                    <ul>
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Terms</a></li>
                        <li><a href="#">Privacy</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 AR Technologies. All rights reserved.</p>
            </div>
        </div>
    </footer>
</body>
</html>
