<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JK Hospital | Premium Medical Care</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;600;800&family=Outfit:wght@700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    
    <style>
        :root {
            --primary: #0056b3;
            --secondary: #00d2ff;
            --accent: #ff1e56;
            --mama: #ec4899;
            --surface: #ffffff;
            --bg: #fdfdfe;
            --text-dark: #0f172a;
            --text-muted: #64748b;
            --radius-lg: 24px;
            --radius-sm: 12px;
            --shadow: 0 10px 40px rgba(0, 0, 0, 0.04);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; scroll-behavior: smooth; }
        body { font-family: 'Plus Jakarta Sans', sans-serif; background: var(--bg); color: var(--text-dark); line-height: 1.6; overflow-x: hidden; }
        
        /* --- NAVIGATION --- */
        nav {
            position: sticky; top: 0; background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px); z-index: 1000; padding: 15px 6%;
            display: flex; justify-content: space-between; align-items: center;
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
        }

        .logo { font-family: 'Outfit', sans-serif; font-weight: 900; font-size: 1.6rem; color: var(--primary); letter-spacing: -1px; text-decoration: none;}
        .logo span { color: var(--secondary); }

        .nav-links { display: flex; gap: 30px; list-style: none; align-items: center; }
        .nav-links a { text-decoration: none; color: var(--text-dark); font-weight: 600; font-size: 0.9rem; transition: 0.2s; }
        .nav-links a:hover { color: var(--primary); }

        .btn-booking { background: var(--primary); color: white !important; padding: 10px 24px; border-radius: 50px; box-shadow: 0 4px 15px rgba(0, 86, 179, 0.2); }

        .menu-toggle { display: none; font-size: 1.5rem; cursor: pointer; color: var(--primary); }

        /* --- HERO SECTION --- */
        .hero {
            padding: 60px 6%;
            display: grid; grid-template-columns: 1fr 1fr; gap: 40px; align-items: center;
            background: radial-gradient(circle at 100% 0%, #e0f2ff 0%, #fdfdfe 50%);
        }
        .hero-content h1 { font-family: 'Outfit', sans-serif; font-size: clamp(2.2rem, 5vw, 3.8rem); line-height: 1.1; margin-bottom: 20px; font-weight: 900; }
        .hero-content h1 mark { background: none; color: var(--primary); }
        .hero-content p { font-size: 1.1rem; color: var(--text-muted); margin-bottom: 30px; max-width: 500px; }

        .hero-visual { position: relative; width: 100%; }
        .hero-img { width: 100%; height: auto; border-radius: var(--radius-lg); box-shadow: var(--shadow); object-fit: cover; }
        
        .emergency-float {
            position: absolute; bottom: 20px; left: -10px;
            background: white; padding: 15px 25px; border-radius: var(--radius-sm);
            box-shadow: 0 20px 50px rgba(0,0,0,0.1); border-left: 6px solid var(--accent);
            animation: float 3s ease-in-out infinite;
            z-index: 10;
        }

        /* --- SERVICE MATRIX --- */
        .services-section { padding: 60px 6%; background: #f8fafc; }
        .section-tag { display: inline-block; padding: 5px 15px; background: #e0e7ff; color: var(--primary); border-radius: 50px; font-weight: 800; font-size: 0.75rem; margin-bottom: 15px; }
        
        .matrix { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; margin-top: 40px; }
        .m-card {
            background: var(--surface); padding: 30px; border-radius: var(--radius-lg);
            border: 1px solid rgba(0,0,0,0.03); transition: 0.3s;
        }
        .m-card:hover { transform: translateY(-5px); border-color: var(--secondary); }
        .m-card i { font-size: 2rem; color: var(--primary); margin-bottom: 15px; display: block; }
        .m-card h4 { font-family: 'Outfit', sans-serif; margin-bottom: 10px; }

        /* --- BOOKING CARD --- */
        .booking-container { padding: 60px 6%; }
        .booking-card {
            background: var(--text-dark); border-radius: var(--radius-lg);
            display: grid; grid-template-columns: 1fr 1fr; overflow: hidden;
        }
        .booking-info { padding: 40px; color: white; }
        .booking-form { padding: 40px; background: white; }

        .input-group { margin-bottom: 15px; }
        .input-group label { display: block; font-weight: 700; font-size: 0.8rem; margin-bottom: 5px; color: var(--text-muted); }
        .input-group input, .input-group select {
            width: 100%; padding: 12px; border-radius: 8px; border: 1px solid #ddd;
        }
        .btn-confirm { width: 100%; padding: 15px; background: var(--primary); color: white; border: none; border-radius: 8px; font-weight: 800; cursor: pointer; }

        /* --- RESPONSIVENESS FIXES --- */
        @media (max-width: 968px) {
            nav { padding: 15px 20px; }
            .menu-toggle { display: block; }

            /* Mobile Navigation Menu */
            .nav-links {
                display: none; /* Hidden by default */
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: white;
                flex-direction: column;
                padding: 30px;
                gap: 20px;
                text-align: center;
                border-bottom: 2px solid var(--primary);
                box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            }

            .nav-links.active {
                display: flex; /* Shown when toggled */
            }

            .hero, .booking-card { grid-template-columns: 1fr; text-align: center; }
            .hero-content { order: 2; }
            .hero-visual { order: 1; }
            .hero-content p { margin: 0 auto 30px; }
            
            .emergency-float { 
                position: relative; 
                left: 0; 
                bottom: 0; 
                margin: 20px auto 0; 
                width: fit-content;
                animation: none;
            }

            .booking-info, .booking-form { padding: 30px 20px; }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
    </style>
</head>
<body>

    <nav id="navbar">
        <a href="#" class="logo">JK<span>HOSPITAL</span></a>
        <div class="menu-toggle" id="mobile-menu"><i class="fas fa-bars"></i></div>
        <ul class="nav-links" id="nav-list">
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#appointment" class="btn-booking">Book Now</a></li>
        </ul>
    </nav>

    <section class="hero">
        <div class="hero-content">
            <span class="section-tag">24/7 MEDICAL EXCELLENCE</span>
            <h1>Modern Care, <br><mark>Close to You.</mark></h1>
            <p>JK Hospital Kigamboni (Tuamoyo) provides professional medical services using advanced technology and expert physicians.</p>
            <div style="display: flex; gap: 15px; justify-content: center; flex-wrap: wrap;">
                <a href="#appointment" class="btn-booking" style="padding: 15px 35px;">Schedule Visit</a>
                <a href="https://wa.me/255717739497" target="_blank" style="padding: 15px; font-weight: 700; color: var(--text-dark); text-decoration: none;"><i class="fab fa-whatsapp" style="color: #25d366;"></i> Live Chat</a>
            </div>
        </div>
        <div class="hero-visual">
            <img src="https://images.unsplash.com/photo-1519494026892-80bbd2d6fd0d?auto=format&fit=crop&q=80&w=1000" alt="JK Hospital Facility" class="hero-img">
            <div class="emergency-float">
                <small style="text-transform: uppercase; font-weight: 800; color: var(--text-muted); font-size: 0.65rem;">Ambulance Line</small>
                <p style="font-weight: 900; font-size: 1.2rem; color: var(--accent);">+255 717 739 497</p>
            </div>
        </div>
    </section>

    <section class="services-section" id="services">
        <div style="text-align: center;">
            <span class="section-tag">DEPARTMENTS</span>
            <h2 style="font-family: 'Outfit'; font-size: 2.2rem;">Clinical Excellence Matrix</h2>
        </div>
        <div class="matrix">
            <div class="m-card">
                <i class="fas fa-baby" style="color:var(--mama)"></i>
                <h4>Mama na Mtoto</h4>
                <p>Specialized RCH clinic for pediatric care and vaccines.</p>
            </div>
            <div class="m-card">
                <i class="fas fa-microscope"></i>
                <h4>Lab / Vipimo</h4>
                <p>ISO-standard laboratory for accurate diagnostics.</p>
            </div>
            <div class="m-card">
                <i class="fas fa-tooth"></i>
                <h4>Dental Unit</h4>
                <p>Oral surgery and routine dental maintenance.</p>
            </div>
        </div>
    </section>

    <section class="booking-container" id="appointment">
        <div class="booking-card">
            <div class="booking-info">
                <h2 style="font-family: 'Outfit'; font-size: 2rem; margin-bottom: 20px;">Book a Visit.</h2>
                <p>Accepting NHIF and all major insurance providers at our Tuamoyo facility.</p>
            </div>
            <div class="booking-form">
                <form id="appointmentForm">
                    <div class="input-group">
                        <label>FULL NAME</label>
                        <input type="text" id="name" placeholder="Full Name" required>
                    </div>
                    <div class="input-group">
                        <label>PHONE NUMBER</label>
                        <input type="tel" id="phone" placeholder="0xxxxxxxxx" required>
                    </div>
                    <button type="submit" class="btn-confirm">CONFIRM APPOINTMENT</button>
                </form>
            </div>
        </div>
    </section>

    <script>
        // MOBILE MENU TOGGLE
        const menuToggle = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');

        menuToggle.addEventListener('click', () => {
            navList.classList.toggle('active');
        });

        // Close menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navList.classList.remove('active');
            });
        });

        // FORM ALERT
        document.getElementById('appointmentForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert("Asante! Your request has been sent. We will call you shortly.");
            this.reset();
        });
    </script>
</body>
</html>
