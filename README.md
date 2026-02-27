    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            color: #2d3436;
            overflow-x: hidden;
            background: #fefefe;
        }

        /* Floating leaves animation */
        .leaf {
            position: fixed;
            width: 30px;
            height: 30px;
            opacity: 0.3;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes float {
            0% { transform: translateY(-100px) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #2d3436 0%, #1e272e 100%);
            color: white;
            padding: 1.5rem 5%;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            letter-spacing: 2px;
        }

        .logo span {
            color: #ff6b9d;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
            font-size: 1.1rem;
        }

        .nav-links a:hover {
            color: #ff6b9d;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 8rem 5%;
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23ffffff" fill-opacity="0.1" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,138.7C960,139,1056,117,1152,101.3C1248,85,1344,75,1392,69.3L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-size: cover;
            animation: wave 15s linear infinite;
        }

        @keyframes wave {
            0% { background-position: 0 0; }
            100% { background-position: 1440px 0; }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 900px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero h1 span {
            color: #ff6b9d;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.2s backwards;
        }

        .tagline {
            font-size: 1.8rem;
            font-style: italic;
            margin-bottom: 3rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.4s backwards;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .cta-button {
            background: #ff6b9d;
            color: white;
            padding: 1.2rem 3rem;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(255, 107, 157, 0.3);
            animation: fadeInUp 1s ease 0.6s backwards;
        }

        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(255, 107, 157, 0.5);
        }

        /* Story Section */
        .story {
            padding: 6rem 5%;
            background: linear-gradient(to bottom, #f8f9fa, #ffffff);
            text-align: center;
        }

        .story h2 {
            font-size: 3rem;
            margin-bottom: 2rem;
            color: #2d3436;
        }

        .story-content {
            max-width: 900px;
            margin: 0 auto;
            font-size: 1.3rem;
            line-height: 2;
            color: #636e72;
        }

        .story-highlight {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 3rem;
            border-radius: 20px;
            margin: 3rem auto;
            box-shadow: 0 10px 40px rgba(102, 126, 234, 0.3);
        }

        /* Product Section */
        .product {
            padding: 6rem 5%;
            background: white;
        }

        .product h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #2d3436;
        }

        .product-subtitle {
            text-align: center;
            font-size: 1.3rem;
            color: #636e72;
            margin-bottom: 4rem;
        }

        .product-card {
            max-width: 1100px;
            margin: 0 auto;
            background: linear-gradient(135deg, #ffeef8 0%, #ffe5f3 100%);
            border-radius: 30px;
            padding: 4rem;
            box-shadow: 0 20px 60px rgba(255, 107, 157, 0.2);
            transition: transform 0.3s;
        }

        .product-card:hover {
            transform: translateY(-10px);
        }

        .product-header {
            display: flex;
            align-items: center;
            gap: 3rem;
            margin-bottom: 3rem;
        }

        .tea-cup {
            font-size: 8rem;
            animation: steam 3s ease-in-out infinite;
        }

        @keyframes steam {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .product-title {
            flex: 1;
        }

        .product-title h3 {
            font-size: 3rem;
            color: #e91e63;
            margin-bottom: 0.5rem;
        }

        .product-title p {
            font-size: 1.3rem;
            color: #636e72;
        }

        .benefits {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin: 3rem 0;
        }

        .benefit-item {
            background: white;
            padding: 1.5rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s;
        }

        .benefit-item:hover {
            transform: translateX(10px);
            box-shadow: 0 8px 25px rgba(233, 30, 99, 0.2);
        }

        .benefit-item::before {
            content: '✓';
            color: #e91e63;
            font-size: 1.5rem;
            margin-right: 0.5rem;
            font-weight: bold;
        }

        .nutrition {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            margin-top: 2rem;
        }

        .nutrition h4 {
            color: #e91e63;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .nutrition-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1rem;
        }

        .nutrition-item {
            text-align: center;
            padding: 1rem;
            background: #ffeef8;
            border-radius: 10px;
        }

        .nutrition-item strong {
            display: block;
            color: #e91e63;
            font-size: 1.2rem;
        }

        /* Coming Soon */
        .coming-soon {
            padding: 6rem 5%;
            background: linear-gradient(135deg, #2d3436 0%, #1e272e 100%);
            color: white;
            text-align: center;
        }

        .coming-soon h2 {
            font-size: 3rem;
            margin-bottom: 3rem;
        }

        .tea-colors {
            display: flex;
            justify-content: center;
            gap: 3rem;
            flex-wrap: wrap;
        }

        .tea-color {
            width: 150px;
            text-align: center;
            animation: bounce 2s ease-in-out infinite;
        }

        .tea-color:nth-child(2) { animation-delay: 0.2s; }
        .tea-color:nth-child(3) { animation-delay: 0.4s; }
        .tea-color:nth-child(4) { animation-delay: 0.6s; }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .color-circle {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin-bottom: 1rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        .green { background: linear-gradient(135deg, #56ab2f 0%, #a8e063 100%); }
        .violet { background: linear-gradient(135deg, #7f00ff 0%, #e100ff 100%); }
        .blue { background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%); }
        .black { background: linear-gradient(135deg, #434343 0%, #000000 100%); }

        /* Testimonials */
        .testimonials {
            padding: 6rem 5%;
            background: #f8f9fa;
        }

        .testimonials h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 4rem;
            color: #2d3436;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .testimonial {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s;
        }

        .testimonial:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.3);
        }

        .stars {
            color: #ffd700;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .testimonial p {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 1.5rem;
            color: #636e72;
        }

        .testimonial-author {
            font-weight: bold;
            color: #e91e63;
            font-size: 1.1rem;
        }

        /* FAQ Section */
        .faq {
            padding: 6rem 5%;
            background: white;
        }

        .faq h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 4rem;
            color: #2d3436;
        }

        .faq-container {
            max-width: 1000px;
            margin: 0 auto;
        }

        .faq-item {
            background: white;
            border-bottom: 1px solid #e0e0e0;
            transition: all 0.3s;
        }

        .faq-item:last-child {
            border-bottom: none;
        }

        .faq-question {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 2rem 2rem;
            cursor: pointer;
            background: white;
            transition: background 0.3s;
        }

        .faq-question:hover {
            background: #f8f9fa;
        }

        .faq-question h3 {
            font-size: 1.3rem;
            color: #2d3436;
            margin: 0;
            font-weight: 600;
            flex: 1;
        }

        .faq-toggle {
            font-size: 1.8rem;
            color: #2d3436;
            transition: transform 0.3s;
            margin-left: 1rem;
            font-weight: bold;
        }

        .faq-item.active .faq-toggle::before {
            content: '▲';
        }

        .faq-toggle::before {
            content: '▼';
        }

        .faq-answer {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.4s ease, padding 0.4s ease;
            padding: 0 2rem;
            background: white;
        }

        .faq-item.active .faq-answer {
            max-height: 500px;
            padding: 0 2rem 2rem 2rem;
        }

        .faq-answer p {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #636e72;
            margin: 0;
        }

        /* Footer */
        footer {
            background: #2d3436;
            color: white;
            text-align: center;
            padding: 3rem 5%;
        }

        footer p {
            font-size: 1.1rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .hero p { font-size: 1.2rem; }
            .product-header { flex-direction: column; text-align: center; }
            .tea-cup { font-size: 5rem; }
            .nav-links { flex-direction: column; gap: 1rem; }
        }
    </style>
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>R-Herbal Tea - Where Real Herbs Begin</title>
</head>
<body>
    <!-- Floating leaves -->
    <div class="leaf" style="left: 10%; animation: float 15s infinite;">🍃</div>
    <div class="leaf" style="left: 30%; animation: float 18s infinite 2s;">🍃</div>
    <div class="leaf" style="left: 50%; animation: float 20s infinite 4s;">🍃</div>
    <div class="leaf" style="left: 70%; animation: float 17s infinite 6s;">🍃</div>
    <div class="leaf" style="left: 90%; animation: float 19s infinite 8s;">🍃</div>

    <header>
        <nav>
            <div class="logo"><span>R</span>-Herbal Tea</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#story">Our Story</a></li>
                <li><a href="#product">Products</a></li>
                <li><a href="#testimonials">Reviews</a></li>
                <li><a href="https://forms.gle/hsvHrRYgjLgEeLqt5" style="color: #ff4986; font-weight: bold;">Order Now</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Welcome to <span>R</span>-Herbal Tea</h1>
            <p class="tagline">Where Real Herbs Begin</p>
            <p>Experience the power of nature in every sip. Our herbal teas are crafted with love, inspired by family, and made with 100% natural ingredients.</p>
            <button class="cta-button">Discover Ruby Calm Tea</button>
        </div>
    </section>

    <section class="story" id="story">
        <h2>Our Story - Born from Love</h2>
        <div class="story-content">
            <p>R-HerbalTea was born from love and care for my family. When my mom struggled with sugar levels and my dad faced weight challenges, doctors recommended more protein-based natural foods.</p>
            <p>That's when I discovered the incredible power of herbal teas. After months of research and testing, Ruby Calm Tea was created - a blend that not only tastes amazing but truly helps people feel better.</p>
            <div class="story-highlight">
                <h3>The "R" in R-Herbal Tea stands for REAL</h3>
                <p style="font-size: 1.2rem; margin-top: 1rem;">Real herbs. Real benefits. Real care for your health.</p>
            </div>
            <p>Every blend is carefully crafted using pure, natural ingredients - no artificial additives, no compromise on quality. Just nature's goodness in every cup.</p>
        </div>
    </section>

    <section class="product" id="product">
        <h2>Introducing Ruby Calm Tea</h2>
        <p class="product-subtitle">Our first flavor - A beautiful pink tea that brings peace and wellness</p>
        
        <div class="product-card">
            <div class="product-header">
                <div class="tea-cup">🍵</div>
                <div class="product-title">
                    <h3>Ruby Calm Tea</h3>
                    <p>The Pink Wonder That Cares for You</p>
                </div>
            </div>

            <h4 style="font-size: 2rem; color: #e91e63; margin-bottom: 1.5rem;">What Ruby Calm Tea Does:</h4>
            <div class="benefits">
                <div class="benefit-item">Reduces bloating & improves digestion</div>
                <div class="benefit-item">Helps control sugar & blood pressure</div>
                <div class="benefit-item">Improves skin glow naturally</div>
                <div class="benefit-item">Supports PCOD & PCOS management</div>
                <div class="benefit-item">Maintains hormone balance</div>
                <div class="benefit-item">Supports thyroid balance</div>
                <div class="benefit-item">Brings calmness to your mind</div>
                <div class="benefit-item">Protects against headaches</div>
            </div>

            <div class="nutrition">
                <h4>🌿 Nutritional Goodness in Every Cup:</h4>
                <div class="nutrition-grid">
                    <div class="nutrition-item">
                        <strong>Protein</strong>
                        <span>0.15g</span>
                    </div>
                    <div class="nutrition-item">
                        <strong>Vitamins</strong>
                        <span>Rich</span>
                    </div>
                    <div class="nutrition-item">
                        <strong>Minerals</strong>
                        <span>Abundant</span>
                    </div>
                    <div class="nutrition-item">
                        <strong>Omega-3</strong>
                        <span>Present</span>
                    </div>
                    <div class="nutrition-item">
                        <strong>Caffeine</strong>
                        <span>100% FREE</span>
                    </div>
                </div>
            </div>
        </div>
        

    </section>

    <section class="coming-soon">
        <h2>✨ More Flavors Coming Soon! ✨</h2>
        <p style="font-size: 1.3rem; margin-bottom: 3rem;">We're brewing something special - more amazing herbal tea flavors!</p>
        <div class="tea-colors">
            <div class="tea-color">
                <div class="color-circle violet"></div>
                <h3>Violet Tea</h3>
                <p>Coming Soon</p>
            </div>
            <div class="tea-color">
                <div class="color-circle blue"></div>
                <h3>Blue Tea</h3>
                <p>Coming Soon</p>
            </div>

        </div>
    </section>

    <section class="testimonials" id="testimonials">
        <h2>What Our Customers Say</h2>
        <div class="testimonial-grid">
            <div class="testimonial">
                <div class="stars">⭐⭐⭐⭐⭐</div>
                <p>"Ruby Calm Tea has completely changed my mornings! I feel so much calmer and my digestion has improved remarkably. Plus, my skin is glowing!"</p>
                <div class="testimonial-author">- Priya, Hyderabad</div>
            </div>
            <div class="testimonial">
                <div class="stars">⭐⭐⭐⭐⭐</div>
                <p>"As someone with PCOS, finding Ruby Calm Tea was a blessing. It's helps to manage the symptoms naturally and I love that it's caffeine-free!"</p>
                <div class="testimonial-author">- Dr.Keerthana, Hyderabad</div>
            </div>
            <div class="testimonial">
                <div class="stars">⭐⭐⭐⭐⭐</div>
                <p>"My sugar levels have been more stable since I started drinking this tea. It tastes amazing and I feel healthier overall. Highly recommend!"</p>
                <div class="testimonial-author">- Radha, Hyderabad</div>
            </div>
            <div class="testimonial">
                <div class="stars">⭐⭐⭐⭐⭐</div>
                <p>"I was skeptical at first, but Ruby Calm Tea really works! My headaches are less frequent and I sleep better at night. Nature's magic in a cup!"</p>
                <div class="testimonial-author">- Sujith Reddy, Nellore</div>
            </div>
            <div class="testimonial">
                <div class="stars">⭐⭐⭐⭐⭐</div>
                <p>"The best part? It's completely natural! No chemicals, just pure herbs. My whole family loves it and we've made it part of our daily routine."</p>
                <div class="testimonial-author">- Sunitha.k, Anantapur</div>
            </div>
        </div>
    </section>

    <section class="faq">
        <h2>Frequently Asked Questions</h2>
        <div class="faq-container">
            <div class="faq-item active">
                <div class="faq-question" onclick="this.parentElement.classList.toggle('active')">
                    <h3>What is Ruby Calm Tea made of?</h3>
                    <span class="faq-toggle"></span>
                </div>
                <div class="faq-answer">
                    <p>Ruby Calm Tea is made from 100% natural hibiscus blend with carefully selected herbs. It contains no artificial colors, flavors, or preservatives - just pure, natural ingredients.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="this.parentElement.classList.toggle('active')">
                    <h3>Is it safe for everyone to drink?</h3>
                    <span class="faq-toggle"></span>
                </div>
                <div class="faq-answer">
                    <p>Yes! Ruby Calm Tea is caffeine-free, vegan, and made from natural herbs. However, if you are pregnant, nursing, or have specific medical conditions, we recommend consulting with your doctor first.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="this.parentElement.classList.toggle('active')">
                    <h3>How often should I drink it?</h3>
                    <span class="faq-toggle"></span>
                </div>
                <div class="faq-answer">
                    <p>For best results, we recommend drinking 1-2 cups per day. You can enjoy it in the morning, afternoon, or evening as it is caffeine-free and won't affect your sleep.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="this.parentElement.classList.toggle('active')">
                    <h3>How quickly will I see results?</h3>
                    <span class="faq-toggle"></span>
                </div>
                <div class="faq-answer">
                    <p>Many people notice improvements in digestion and calmness within the first week. For benefits like hormone balance and skin glow, consistent use for 3-4 weeks typically shows noticeable results.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="this.parentElement.classList.toggle('active')">
                    <h3>Does it really help with PCOS/PCOD?</h3>
                    <span class="faq-toggle"></span>
                </div>
                <div class="faq-answer">
                    <p>Ruby Calm Tea contains herbs known to support hormone balance, which can be beneficial for PCOS/PCOD management. However, it should complement - not replace - medical treatment. Always consult your doctor.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="this.parentElement.classList.toggle('active')">
                    <h3>How do I prepare the tea?</h3>
                    <span class="faq-toggle"></span>
                </div>
                <div class="faq-answer">
                    <p>Simply add one tea bag or one teaspoon of loose tea to hot water (not boiling). Let it steep for 3-5 minutes, strain, and enjoy! You can add honey or lemon if desired.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="this.parentElement.classList.toggle('active')">
                    <h3>Can I drink it if I have diabetes?</h3>
                    <span class="faq-toggle"></span>
                </div>
                <div class="faq-answer">
                    <p>Yes! Ruby Calm Tea has no added sugar and may help support healthy blood sugar levels. However, please monitor your levels and consult with your healthcare provider.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="this.parentElement.classList.toggle('active')">
                    <h3>What makes R-HerbalTea different from other herbal teas?</h3>
                    <span class="faq-toggle"></span>
                </div>
                <div class="faq-answer">
                    <p>R-HerbalTea was created from personal experience and genuine care. We use only the highest quality natural herbs, with no preservatives or artificial ingredients. Plus, every blend is crafted with love and tested for real benefits.</p>
                </div>
            </div>
        </div>
        
        <div style="text-align: center; margin-top: 3rem;">
            <a href="https://forms.gle/hsvHrRYgjLgEeLqt5" class="cta-button" style="display: inline-block; text-decoration: none;">
                📦 Order Now
            </a>
        </div>
    </section>

    <footer>
        <p>🌿 <strong>R-Herbal Tea</strong> - Where Real Herbs Begin 🌿</p>
        <p style="margin-top: 1rem;">Made with love, inspired by family, crafted for your wellness</p>
        <p style="margin-top: 1rem; opacity: 0.8;">© 2024 R-Herbal Tea. All rights reserved.</p>
    </footer>
</body>
</html>
    
