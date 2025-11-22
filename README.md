<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Discover your life path, destiny, and personality numbers with our comprehensive numerology calculator. Learn the ancient wisdom of numbers and how they shape your life.">
    <meta name="keywords" content="numerology, life path number, destiny number, soul urge, personality number, birth date numerology, name numerology">
    <title>Numerology Calculator - Discover Your Numbers</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #6a5acd;
            --primary-dark: #5a4abc;
            --secondary-color: #9370db;
            --accent-color: #dda0dd;
            --text-color: #333;
            --light-text: #fff;
            --bg-color: #f9f9f9;
            --card-bg: #ffffff;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --radius: 10px;
            --scale-factor: 1;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            transform: scale(var(--scale-factor));
            transform-origin: top center;
            width: 100vw;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--light-text);
            padding: calc(2rem * var(--scale-factor)) 0;
            text-align: center;
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 L100,0 L100,100 Z" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: cover;
        }

        h1 {
            font-size: calc(2.5rem * var(--scale-factor));
            margin-bottom: calc(0.5rem * var(--scale-factor));
            position: relative;
        }

        .subtitle {
            font-size: calc(1.2rem * var(--scale-factor));
            opacity: 0.9;
            position: relative;
        }

        main {
            padding: calc(2rem * var(--scale-factor)) 0;
        }

        .page {
            display: none;
        }

        .page.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .welcome-section {
            text-align: center;
            padding: calc(3rem * var(--scale-factor)) 0;
        }

        .welcome-section h2 {
            color: var(--primary-color);
            margin-bottom: calc(1rem * var(--scale-factor));
            font-size: calc(2.2rem * var(--scale-factor));
        }

        .welcome-section p {
            max-width: 800px;
            margin: 0 auto calc(2rem * var(--scale-factor));
            font-size: calc(1.1rem * var(--scale-factor));
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: calc(2rem * var(--scale-factor));
            margin: calc(3rem * var(--scale-factor)) 0;
        }

        .feature-card {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: calc(2rem * var(--scale-factor));
            box-shadow: var(--shadow);
            text-align: center;
            transition: transform 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
        }

        .feature-card i {
            font-size: calc(2.5rem * var(--scale-factor));
            color: var(--primary-color);
            margin-bottom: calc(1rem * var(--scale-factor));
        }

        .feature-card h3 {
            margin-bottom: calc(1rem * var(--scale-factor));
            color: var(--primary-color);
            font-size: calc(1.3rem * var(--scale-factor));
        }

        .feature-card p {
            font-size: calc(1rem * var(--scale-factor));
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--light-text);
            padding: calc(15px * var(--scale-factor)) calc(30px * var(--scale-factor));
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: calc(1.1rem * var(--scale-factor));
            margin-top: calc(1rem * var(--scale-factor));
            transition: all 0.3s ease;
            box-shadow: var(--shadow);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }

        .calculator-section {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: calc(2rem * var(--scale-factor));
            box-shadow: var(--shadow);
            margin-bottom: calc(2rem * var(--scale-factor));
        }

        .calculator-section h2 {
            font-size: calc(1.8rem * var(--scale-factor));
            margin-bottom: calc(1rem * var(--scale-factor));
            color: var(--primary-color);
        }

        .calculator-section p {
            font-size: calc(1rem * var(--scale-factor));
            margin-bottom: calc(1.5rem * var(--scale-factor));
        }

        .form-group {
            margin-bottom: calc(1.5rem * var(--scale-factor));
        }

        label {
            display: block;
            margin-bottom: calc(0.5rem * var(--scale-factor));
            font-weight: 600;
            font-size: calc(1rem * var(--scale-factor));
        }

        input, select {
            width: 100%;
            padding: calc(12px * var(--scale-factor));
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: calc(1rem * var(--scale-factor));
            transition: border 0.3s;
        }

        input:focus, select:focus {
            border-color: var(--primary-color);
            outline: none;
        }

        button {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--light-text);
            border: none;
            padding: calc(12px * var(--scale-factor)) calc(24px * var(--scale-factor));
            border-radius: 5px;
            font-size: calc(1rem * var(--scale-factor));
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        button i {
            margin-right: calc(8px * var(--scale-factor));
        }

        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }

        .button-secondary {
            background: linear-gradient(135deg, #6c757d, #868e96);
        }

        .results-section {
            display: none;
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: calc(2rem * var(--scale-factor));
            box-shadow: var(--shadow);
            margin-bottom: calc(2rem * var(--scale-factor));
        }

        .results-section.active {
            display: block;
        }

        .results-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: calc(1.5rem * var(--scale-factor));
            flex-wrap: wrap;
            gap: calc(1rem * var(--scale-factor));
        }

        .results-header h2 {
            font-size: calc(1.8rem * var(--scale-factor));
            color: var(--primary-color);
        }

        .number-cards {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: calc(1.5rem * var(--scale-factor));
            margin-bottom: calc(2rem * var(--scale-factor));
        }

        .number-card {
            background: linear-gradient(135deg, var(--secondary-color), var(--accent-color));
            color: var(--light-text);
            border-radius: var(--radius);
            padding: calc(1.5rem * var(--scale-factor));
            text-align: center;
            transition: transform 0.3s;
            position: relative;
            overflow: hidden;
        }

        .number-card:hover {
            transform: translateY(-5px);
        }

        .number-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: rgba(255, 255, 255, 0.5);
        }

        .number-value {
            font-size: calc(3rem * var(--scale-factor));
            font-weight: 700;
            margin: calc(1rem * var(--scale-factor)) 0;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        .number-title {
            font-size: calc(1.5rem * var(--scale-factor));
            margin-bottom: calc(0.5rem * var(--scale-factor));
        }

        .number-description {
            font-size: calc(1rem * var(--scale-factor));
            line-height: 1.5;
        }

        .detailed-results {
            background-color: #f8f9fa;
            border-radius: var(--radius);
            padding: calc(1.5rem * var(--scale-factor));
            margin-top: calc(1.5rem * var(--scale-factor));
        }

        .detailed-results h3 {
            color: var(--primary-color);
            margin-bottom: calc(1rem * var(--scale-factor));
            border-bottom: 2px solid var(--accent-color);
            padding-bottom: calc(0.5rem * var(--scale-factor));
            font-size: calc(1.3rem * var(--scale-factor));
        }

        .info-section {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: calc(2rem * var(--scale-factor));
            box-shadow: var(--shadow);
            margin-bottom: calc(2rem * var(--scale-factor));
        }

        .info-section h2 {
            color: var(--primary-color);
            margin-bottom: calc(1rem * var(--scale-factor));
            border-bottom: 2px solid var(--accent-color);
            padding-bottom: calc(0.5rem * var(--scale-factor));
            font-size: calc(1.8rem * var(--scale-factor));
        }

        .info-section p {
            font-size: calc(1rem * var(--scale-factor));
            margin-bottom: calc(1rem * var(--scale-factor));
        }

        .tab-container {
            margin-top: calc(1.5rem * var(--scale-factor));
        }

        .tabs {
            display: flex;
            border-bottom: 1px solid #ddd;
            margin-bottom: calc(1.5rem * var(--scale-factor));
            flex-wrap: wrap;
        }

        .tab {
            padding: calc(12px * var(--scale-factor)) calc(20px * var(--scale-factor));
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: all 0.3s;
            font-weight: 600;
            font-size: calc(1rem * var(--scale-factor));
        }

        .tab.active {
            border-bottom: 3px solid var(--primary-color);
            color: var(--primary-color);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        .number-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: calc(1.5rem * var(--scale-factor));
            margin-top: calc(1.5rem * var(--scale-factor));
        }

        .number-item {
            background-color: #f5f5f5;
            border-radius: 8px;
            padding: calc(1.5rem * var(--scale-factor));
            border-left: 4px solid var(--primary-color);
            transition: transform 0.3s;
        }

        .number-item:hover {
            transform: translateY(-3px);
        }

        .number-item h3 {
            color: var(--primary-color);
            margin-bottom: calc(0.5rem * var(--scale-factor));
            display: flex;
            align-items: center;
            font-size: calc(1.2rem * var(--scale-factor));
        }

        .number-item h3 span {
            background: var(--primary-color);
            color: white;
            width: calc(30px * var(--scale-factor));
            height: calc(30px * var(--scale-factor));
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            margin-right: calc(10px * var(--scale-factor));
            font-size: calc(0.9rem * var(--scale-factor));
        }

        .number-item p {
            font-size: calc(0.95rem * var(--scale-factor));
            margin-bottom: calc(0.5rem * var(--scale-factor));
        }

        .ads-section {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: calc(2rem * var(--scale-factor));
            box-shadow: var(--shadow);
            margin-bottom: calc(2rem * var(--scale-factor));
            text-align: center;
        }

        .ads-section h2 {
            font-size: calc(1.5rem * var(--scale-factor));
            margin-bottom: calc(1rem * var(--scale-factor));
        }

        .ads-section p {
            font-size: calc(1rem * var(--scale-factor));
            margin-bottom: calc(1rem * var(--scale-factor));
        }

        .ad-placeholder {
            background-color: #f0f0f0;
            height: calc(250px * var(--scale-factor));
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px dashed #ccc;
            border-radius: 5px;
            margin: calc(1rem * var(--scale-factor)) 0;
        }

        footer {
            background-color: var(--primary-color);
            color: var(--light-text);
            text-align: center;
            padding: calc(1.5rem * var(--scale-factor)) 0;
            margin-top: calc(2rem * var(--scale-factor));
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: calc(1rem * var(--scale-factor));
        }

        .footer-links {
            display: flex;
            gap: calc(1.5rem * var(--scale-factor));
            flex-wrap: wrap;
            justify-content: center;
        }

        .footer-links a {
            color: var(--light-text);
            text-decoration: none;
            transition: opacity 0.3s;
            font-size: calc(0.95rem * var(--scale-factor));
        }

        .footer-links a:hover {
            opacity: 0.8;
        }

        .navigation {
            display: flex;
            justify-content: center;
            gap: calc(1rem * var(--scale-factor));
            margin: calc(2rem * var(--scale-factor)) 0;
            flex-wrap: wrap;
        }

        .nav-button {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: calc(10px * var(--scale-factor)) calc(20px * var(--scale-factor));
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
            font-size: calc(1rem * var(--scale-factor));
        }

        .nav-button:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
        }

        .tooltip {
            position: relative;
            display: inline-block;
            border-bottom: 1px dotted var(--primary-color);
            cursor: help;
            margin-left: calc(5px * var(--scale-factor));
        }

        .tooltip .tooltiptext {
            visibility: hidden;
            width: calc(200px * var(--scale-factor));
            background-color: var(--primary-color);
            color: #fff;
            text-align: center;
            border-radius: 6px;
            padding: calc(10px * var(--scale-factor));
            position: absolute;
            z-index: 1;
            bottom: 125%;
            left: 50%;
            margin-left: calc(-100px * var(--scale-factor));
            opacity: 0;
            transition: opacity 0.3s;
            font-size: calc(0.9rem * var(--scale-factor));
            font-weight: normal;
        }

        .tooltip:hover .tooltiptext {
            visibility: visible;
            opacity: 1;
        }

        .calculation-steps {
            background: #f8f9fa;
            border-radius: 8px;
            padding: calc(1rem * var(--scale-factor));
            margin-top: calc(1rem * var(--scale-factor));
            font-size: calc(0.9rem * var(--scale-factor));
        }

        .calculation-steps h4 {
            margin-bottom: calc(0.5rem * var(--scale-factor));
            color: var(--primary-color);
            font-size: calc(1rem * var(--scale-factor));
        }

        .calculation-steps p {
            font-size: calc(0.9rem * var(--scale-factor));
            margin-bottom: calc(0.5rem * var(--scale-factor));
        }

        .save-results {
            display: flex;
            gap: calc(1rem * var(--scale-factor));
            margin-top: calc(1.5rem * var(--scale-factor));
            flex-wrap: wrap;
        }

        /* Responsive scaling */
        @media (max-width: 1200px) {
            :root {
                --scale-factor: 0.95;
            }
        }

        @media (max-width: 992px) {
            :root {
                --scale-factor: 0.9;
            }
        }

        @media (max-width: 768px) {
            :root {
                --scale-factor: 0.85;
            }
            
            .number-grid, .number-cards {
                grid-template-columns: 1fr;
            }
            
            .tabs {
                flex-direction: column;
            }
            
            .tab {
                border-bottom: 1px solid #ddd;
                border-left: 3px solid transparent;
            }
            
            .tab.active {
                border-left: 3px solid var(--primary-color);
                border-bottom: 1px solid #ddd;
            }
        }

        @media (max-width: 576px) {
            :root {
                --scale-factor: 0.8;
            }
            
            .container {
                padding: 0 15px;
            }
        }

        @media (max-width: 400px) {
            :root {
                --scale-factor: 0.75;
            }
        }

        /* Scale controls */
        .scale-controls {
            position: fixed;
            bottom: 20px;
            right: 20px;
            display: flex;
            gap: 10px;
            z-index: 100;
        }

        .scale-btn {
            background: var(--primary-color);
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-weight: bold;
            font-size: 18px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }

        .scale-btn:hover {
            background: var(--primary-dark);
        }
    </style>
</head>
<body>
    <div class="scale-controls">
        <button class="scale-btn" id="zoom-out">-</button>
        <button class="scale-btn" id="zoom-in">+</button>
    </div>

    <header>
        <div class="container">
            <h1><i class="fas fa-star-of-life"></i> Numerology Calculator</h1>
            <p class="subtitle">Discover the hidden meanings behind your name and birth date</p>
        </div>
    </header>

    <main class="container">
        <!-- Welcome Page -->
        <section id="welcome-page" class="page active">
            <div class="welcome-section">
                <h2>Welcome to Numerology Calculator</h2>
                <p>Numerology is an ancient metaphysical science that explores the mystical relationship between numbers and events in our lives. Discover your unique numbers and what they reveal about your personality, life purpose, and future potential.</p>
                
                <div class="features">
                    <div class="feature-card">
                        <i class="fas fa-calculator"></i>
                        <h3>Calculate Your Numbers</h3>
                        <p>Discover your Life Path, Destiny, Soul Urge, and other important numbers based on your name and birth date.</p>
                    </div>
                    <div class="feature-card">
                        <i class="fas fa-book-open"></i>
                        <h3>Detailed Interpretations</h3>
                        <p>Get comprehensive explanations of what each number means for your personality and life journey.</p>
                    </div>
                    <div class="feature-card">
                        <i class="fas fa-history"></i>
                        <h3>Learn Numerology</h3>
                        <p>Explore the history and methods behind numerology to better understand this ancient practice.</p>
                    </div>
                </div>
                
                <a href="#" class="cta-button" id="get-started-btn">
                    <i class="fas fa-play-circle"></i> Get Started Now
                </a>
            </div>

            <div class="ads-section">
                <h2>Support Our Site</h2>
                <p>Please consider disabling your ad blocker to support our free numerology service.</p>
                <div class="ad-placeholder">
                    <!-- AdSense Ad Unit -->
                    <!-- Replace with your AdSense code -->
                    <p>AdSense Ad Unit (320x250)</p>
                </div>
            </div>
        </section>

        <!-- Calculator Page -->
        <section id="calculator-page" class="page">
            <div class="calculator-section">
                <h2>Calculate Your Numerology Numbers</h2>
                <p>Enter your full name (as per birth certificate) and birth date to discover your complete numerology profile.</p>
                
                <form id="numerology-form">
                    <div class="form-group">
                        <label for="full-name">Full Name <span class="tooltip">?
                            <span class="tooltiptext">Enter your full birth name for accurate calculations</span>
                        </span></label>
                        <input type="text" id="full-name" placeholder="Enter your full name" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="birth-date">Birth Date</label>
                        <input type="date" id="birth-date" required>
                    </div>
                    
                    <button type="submit"><i class="fas fa-calculator"></i> Calculate My Numbers</button>
                </form>
            </div>

            <div class="ads-section">
                <div class="ad-placeholder">
                    <!-- AdSense Ad Unit -->
                    <!-- Replace with your AdSense code -->
                    <p>AdSense Ad Unit (728x90)</p>
                </div>
            </div>

            <div class="navigation">
                <button class="nav-button" id="back-to-welcome"><i class="fas fa-arrow-left"></i> Back to Home</button>
            </div>
        </section>

        <!-- Results Page -->
        <section id="results-page" class="page">
            <div class="results-section active">
                <div class="results-header">
                    <h2>Your Numerology Profile</h2>
                    <div>
                        <button id="calculate-again" class="button-secondary"><i class="fas fa-redo"></i> Calculate Again</button>
                    </div>
                </div>
                
                <div class="number-cards">
                    <div class="number-card">
                        <h3 class="number-title">Life Path Number</h3>
                        <div class="number-value" id="life-path-number">7</div>
                        <p class="number-description" id="life-path-description">Your Life Path Number reveals your life's purpose and the challenges you'll face.</p>
                    </div>
                    
                    <div class="number-card">
                        <h3 class="number-title">Destiny Number</h3>
                        <div class="number-value" id="destiny-number">5</div>
                        <p class="number-description" id="destiny-description">Your Destiny Number indicates your natural talents and abilities.</p>
                    </div>
                    
                    <div class="number-card">
                        <h3 class="number-title">Soul Urge Number</h3>
                        <div class="number-value" id="soul-urge-number">3</div>
                        <p class="number-description" id="soul-urge-description">Your Soul Urge Number reveals your inner desires and motivations.</p>
                    </div>

                    <div class="number-card">
                        <h3 class="number-title">Personality Number</h3>
                        <div class="number-value" id="personality-number">8</div>
                        <p class="number-description" id="personality-description">Your Personality Number shows how others perceive you.</p>
                    </div>
                </div>

                <div class="detailed-results">
                    <h3><i class="fas fa-info-circle"></i> Detailed Interpretation</h3>
                    <div id="detailed-interpretation">
                        <p>Your complete numerology profile reveals a fascinating picture of your life's purpose, talents, and challenges. Based on your numbers, you have a unique combination of traits that shape your personality and destiny.</p>
                        
                        <div class="calculation-steps">
                            <h4>How your numbers were calculated:</h4>
                            <p><strong>Life Path Number:</strong> Derived from your birth date by reducing day, month, and year to single digits and summing them.</p>
                            <p><strong>Destiny Number:</strong> Calculated from your full birth name using the Pythagorean numerology system.</p>
                            <p><strong>Soul Urge Number:</strong> Based on the vowels in your name, representing your inner desires.</p>
                            <p><strong>Personality Number:</strong> Derived from the consonants in your name, showing how others see you.</p>
                        </div>
                    </div>
                </div>

                <div class="save-results">
                    <button id="print-results"><i class="fas fa-print"></i> Print Results</button>
                    <button id="save-pdf" class="button-secondary"><i class="fas fa-file-pdf"></i> Save as PDF</button>
                </div>
            </div>

            <div class="navigation">
                <button class="nav-button" id="back-to-calculator"><i class="fas fa-arrow-left"></i> Back to Calculator</button>
                <button class="nav-button" id="learn-more-btn">Learn More About Numerology</button>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <p>&copy; 2023 Numerology Calculator. All rights reserved.</p>
                <p>This tool is for entertainment and self-discovery purposes only.</p>
                <div class="footer-links">
                    <a href="#">Privacy Policy</a>
                    <a href="#">Terms of Service</a>
                    <a href="#">Contact Us</a>
                    <a href="#">About Numerology</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Auto-scaling functionality
            let scaleFactor = 1;
            const root = document.documentElement;
            
            // Function to update scale
            function updateScale() {
                root.style.setProperty('--scale-factor', scaleFactor);
            }
            
            // Zoom in/out controls
            document.getElementById('zoom-in').addEventListener('click', function() {
                if (scaleFactor < 1.5) {
                    scaleFactor += 0.1;
                    updateScale();
                }
            });
            
            document.getElementById('zoom-out').addEventListener('click', function() {
                if (scaleFactor > 0.5) {
                    scaleFactor -= 0.1;
                    updateScale();
                }
            });
            
            // Auto-scale based on screen size
            function autoScale() {
                const width = window.innerWidth;
                
                if (width < 400) {
                    scaleFactor = 0.75;
                } else if (width < 576) {
                    scaleFactor = 0.8;
                } else if (width < 768) {
                    scaleFactor = 0.85;
                } else if (width < 992) {
                    scaleFactor = 0.9;
                } else if (width < 1200) {
                    scaleFactor = 0.95;
                } else {
                    scaleFactor = 1;
                }
                
                updateScale();
            }
            
            // Initial auto-scale
            autoScale();
            
            // Update on resize
            window.addEventListener('resize', autoScale);
            
            // Page navigation elements
            const pages = document.querySelectorAll('.page');
            const getStartedBtn = document.getElementById('get-started-btn');
            const backToWelcomeBtn = document.getElementById('back-to-welcome');
            const backToCalculatorBtn = document.getElementById('back-to-calculator');
            const learnMoreBtn = document.getElementById('learn-more-btn');
            
            // Form and calculation elements
            const form = document.getElementById('numerology-form');
            const calculateAgainBtn = document.getElementById('calculate-again');
            const printBtn = document.getElementById('print-results');
            const savePdfBtn = document.getElementById('save-pdf');
            
            // Page navigation functions
            function showPage(pageId) {
                pages.forEach(page => {
                    page.classList.remove('active');
                });
                document.getElementById(pageId).classList.add('active');
                window.scrollTo(0, 0);
            }
            
            // Navigation event listeners
            getStartedBtn.addEventListener('click', function(e) {
                e.preventDefault();
                showPage('calculator-page');
            });
            
            backToWelcomeBtn.addEventListener('click', function() {
                showPage('welcome-page');
            });
            
            backToCalculatorBtn.addEventListener('click', function() {
                showPage('calculator-page');
            });
            
            learnMoreBtn.addEventListener('click', function() {
                // In a complete implementation, this would show the learn page
                alert('Learn More page would be implemented here');
            });
            
            // Numerology number descriptions
            const numberDescriptions = {
                1: "You are a natural leader with strong individuality and determination. Your path involves learning independence and pioneering new directions. You have the potential to achieve great things through your initiative and originality.",
                2: "You are cooperative and diplomatic, with a natural ability to create harmony. Your path involves partnership and learning balance. Your sensitivity and intuition make you an excellent mediator and team player.",
                3: "You are creative and expressive, with a gift for communication. Your path involves self-expression and bringing joy to others. Your optimism and enthusiasm inspire those around you.",
                4: "You are practical and disciplined, with a strong sense of responsibility. Your path involves building solid foundations and creating stability. Your reliability and hard work ensure long-term success.",
                5: "You are adventurous and freedom-loving, with a versatile nature. Your path involves embracing change and experiencing life fully. Your adaptability and curiosity lead to diverse experiences.",
                6: "You are nurturing and responsible, with a strong sense of service. Your path involves creating harmony and caring for others. Your compassion and reliability make you a pillar of your community.",
                7: "You are analytical and spiritual, with a deep inner wisdom. Your path involves seeking truth and understanding life's mysteries. Your intuition and perceptiveness give you unique insights.",
                8: "You are ambitious and authoritative, with strong business sense. Your path involves mastering material power and achieving success. Your organizational skills and determination lead to accomplishment.",
                9: "You are compassionate and idealistic, with a global perspective. Your path involves humanitarian service and universal love. Your generosity and vision inspire positive change."
            };
            
            // Calculate life path number from birth date
            function calculateLifePathNumber(birthDate) {
                const date = new Date(birthDate);
                const day = date.getDate();
                const month = date.getMonth() + 1; // Months are 0-indexed
                const year = date.getFullYear();
                
                // Reduce each component to a single digit
                const dayReduced = reduceToSingleDigit(day);
                const monthReduced = reduceToSingleDigit(month);
                const yearReduced = reduceToSingleDigit(year);
                
                // Sum and reduce again
                const sum = dayReduced + monthReduced + yearReduced;
                return reduceToSingleDigit(sum);
            }
            
            // Calculate destiny number from name
            function calculateDestinyNumber(name) {
                // Pythagorean numerology chart
                const numerologyChart = {
                    'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5, 'f': 6, 'g': 7, 'h': 8, 'i': 9,
                    'j': 1, 'k': 2, 'l': 3, 'm': 4, 'n': 5, 'o': 6, 'p': 7, 'q': 8, 'r': 9,
                    's': 1, 't': 2, 'u': 3, 'v': 4, 'w': 5, 'x': 6, 'y': 7, 'z': 8
                };
                
                let sum = 0;
                
                // Remove spaces and convert to lowercase
                const cleanName = name.replace(/\s+/g, '').toLowerCase();
                
                // Calculate sum of all letters
                for (let i = 0; i < cleanName.length; i++) {
                    const char = cleanName[i];
                    if (numerologyChart[char]) {
                        sum += numerologyChart[char];
                    }
                }
                
                // Reduce to single digit
                return reduceToSingleDigit(sum);
            }
            
            // Calculate soul urge number (vowels in name)
            function calculateSoulUrgeNumber(name) {
                const vowels = ['a', 'e', 'i', 'o', 'u'];
                const numerologyChart = {
                    'a': 1, 'e': 5, 'i': 9, 'o': 6, 'u': 3
                };
                
                let sum = 0;
                const cleanName = name.toLowerCase();
                
                // Calculate sum of vowels
                for (let i = 0; i < cleanName.length; i++) {
                    const char = cleanName[i];
                    if (vowels.includes(char) && numerologyChart[char]) {
                        sum += numerologyChart[char];
                    }
                }
                
                // Reduce to single digit
                return reduceToSingleDigit(sum);
            }
            
            // Calculate personality number (consonants in name)
            function calculatePersonalityNumber(name) {
                const vowels = ['a', 'e', 'i', 'o', 'u'];
                const numerologyChart = {
                    'b': 2, 'c': 3, 'd': 4, 'f': 6, 'g': 7, 'h': 8, 'j': 1, 'k': 2, 'l': 3,
                    'm': 4, 'n': 5, 'p': 7, 'q': 8, 'r': 9, 's': 1, 't': 2, 'v': 4, 'w': 5,
                    'x': 6, 'y': 7, 'z': 8
                };
                
                let sum = 0;
                const cleanName = name.toLowerCase();
                
                // Calculate sum of consonants
                for (let i = 0; i < cleanName.length; i++) {
                    const char = cleanName[i];
                    if (!vowels.includes(char) && numerologyChart[char]) {
                        sum += numerologyChart[char];
                    }
                }
                
                // Reduce to single digit
                return reduceToSingleDigit(sum);
            }
            
            // Helper function to reduce numbers to single digit
            function reduceToSingleDigit(num) {
                while (num > 9) {
                    let sum = 0;
                    const digits = num.toString().split('');
                    for (let digit of digits) {
                        sum += parseInt(digit);
                    }
                    num = sum;
                }
                return num;
            }
            
            // Form submission handler
            form.addEventListener('submit', function(e) {
                e.preventDefault();
                
                const fullName = document.getElementById('full-name').value;
                const birthDate = document.getElementById('birth-date').value;
                
                if (!fullName || !birthDate) {
                    alert('Please enter both your name and birth date.');
                    return;
                }
                
                // Calculate numbers
                const lifePathNumber = calculateLifePathNumber(birthDate);
                const destinyNumber = calculateDestinyNumber(fullName);
                const soulUrgeNumber = calculateSoulUrgeNumber(fullName);
                const personalityNumber = calculatePersonalityNumber(fullName);
                
                // Update results
                document.getElementById('life-path-number').textContent = lifePathNumber;
                document.getElementById('destiny-number').textContent = destinyNumber;
                document.getElementById('soul-urge-number').textContent = soulUrgeNumber;
                document.getElementById('personality-number').textContent = personalityNumber;
                
                document.getElementById('life-path-description').textContent = numberDescriptions[lifePathNumber] || "Your Life Path Number reveals your life's purpose and the challenges you'll face.";
                document.getElementById('destiny-description').textContent = numberDescriptions[destinyNumber] || "Your Destiny Number indicates your natural talents and abilities.";
                document.getElementById('soul-urge-description').textContent = numberDescriptions[soulUrgeNumber] || "Your Soul Urge Number reveals your inner desires and motivations.";
                document.getElementById('personality-description').textContent = numberDescriptions[personalityNumber] || "Your Personality Number shows how others perceive you.";
                
                // Update detailed interpretation
                const detailedElement = document.getElementById('detailed-interpretation');
                detailedElement.innerHTML = `
                    <p>Your complete numerology profile reveals a fascinating picture of your life's purpose, talents, and challenges. Based on your numbers, you have a unique combination of traits that shape your personality and destiny.</p>
                    <p><strong>Life Path ${lifePathNumber}:</strong> ${numberDescriptions[lifePathNumber]}</p>
                    <p><strong>Destiny ${destinyNumber}:</strong> ${numberDescriptions[destinyNumber]}</p>
                    <p><strong>Soul Urge ${soulUrgeNumber}:</strong> ${numberDescriptions[soulUrgeNumber]}</p>
                    <p><strong>Personality ${personalityNumber}:</strong> ${numberDescriptions[personalityNumber]}</p>
                    
                    <div class="calculation-steps">
                        <h4>How your numbers were calculated:</h4>
                        <p><strong>Life Path Number (${lifePathNumber}):</strong> Derived from your birth date (${birthDate}) by reducing day, month, and year to single digits and summing them.</p>
                        <p><strong>Destiny Number (${destinyNumber}):</strong> Calculated from your full birth name (${fullName}) using the Pythagorean numerology system.</p>
                        <p><strong>Soul Urge Number (${soulUrgeNumber}):</strong> Based on the vowels in your name, representing your inner desires.</p>
                        <p><strong>Personality Number (${personalityNumber}):</strong> Derived from the consonants in your name, showing how others see you.</p>
                    </div>
                `;
                
                // Show results page
                showPage('results-page');
            });
            
            // Calculate again button
            calculateAgainBtn.addEventListener('click', function() {
                showPage('calculator-page');
                form.reset();
                document.getElementById('full-name').focus();
            });
            
            // Print results button
            printBtn.addEventListener('click', function() {
                window.print();
            });
            
            // Save as PDF button (placeholder functionality)
            savePdfBtn.addEventListener('click', function() {
                alert('PDF export functionality would be implemented with a library like jsPDF in a production environment.');
            });
        });
    </script>
</body>
</html>
