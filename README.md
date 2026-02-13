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

        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Plus Jakarta Sans', sans-serif; background: var(--bg); color: var(--text-dark); line-height: 1.6; }
        
        /* --- NAVIGATION --- */
        nav {
            position: sticky; top: 0; background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(20px); z-index: 1000; padding: 12px 6%;
            display: flex; justify-content: space-between; align-items: center;
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
        }
        .logo { font-family: 'Outfit', sans-serif; font-weight: 900; font-size: 1.6rem; color: var(--primary); letter-spacing: -1px; text-decoration: none;}
        .logo span { color: var(--secondary); }

        .nav-links { display: flex; gap: 30px; list-style: none; align-items: center; }
        .nav-links a { text-decoration: none; color: var(--text-dark); font-weight: 600; font-size: 0.9rem; transition: 0.2s; }
        .nav-links a:hover { color: var(--primary); }

        .btn-booking { background: var(--primary); color: white !important; padding: 10px 24px; border-radius: 50px; box-shadow: 0 4px 15px rgba(0, 86, 179, 0.2); }

        /* --- HERO SECTION --- */
        .hero {
            padding: 60px 6%;
            display: grid; grid-template-columns: 1fr 1fr; gap: 40px; align-items: center;
            background: radial-gradient(circle at 100% 0%, #e0f2ff 0%, #fdfdfe 50%);
        }
        .hero-content h1 { font-family: 'Outfit', sans-serif; font-size: 3.8rem; line-height: 1.1; margin-bottom: 20px; font-weight: 900; }
        .hero-content h1 mark { background: none; color: var(--primary); }
        .hero-content p { font-size: 1.1rem; color: var(--text-muted); margin-bottom: 30px; max-width: 500px; }

        .hero-visual { position: relative; }
        .hero-img { width: 100%; border-radius: var(--radius-lg); box-shadow: var(--shadow); }
        
        /* Floating Emergency Card */
        .emergency-float {
            position: absolute; bottom: -20px; left: -20px;
            background: white; padding: 20px; border-radius: var(--radius-sm);
            box-shadow: 0 20px 50px rgba(0,0,0,0.1); border-left: 6px solid var(--accent);
            animation: float 3s ease-in-out infinite;
        }

        /* --- ABOUT SECTION --- */
        .about-wrap { padding: 80px 6%; display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; }
        .about-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
        .stat-box { background: white; padding: 25px; border-radius: var(--radius-sm); border: 1px solid #f1f5f9; text-align: center; box-shadow: var(--shadow); }
        .stat-box h3 { font-size: 2rem; color: var(--primary); margin-bottom: 5px; }

        /* --- SERVICE MATRIX (COMPACT & VISIBLE) --- */
        .services-section { padding: 60px 6%; background: #f8fafc; }
        .section-tag { display: inline-block; padding: 5px 15px; background: #e0e7ff; color: var(--primary); border-radius: 50px; font-weight: 800; font-size: 0.75rem; margin-bottom: 15px; }
        
        .matrix { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 20px; margin-top: 40px; }
        .m-card {
            background: var(--surface); padding: 35px 25px; border-radius: var(--radius-lg);
            border: 1px solid rgba(0,0,0,0.03); transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            text-align: left; position: relative; overflow: hidden;
        }
        .m-card:hover { transform: translateY(-10px); box-shadow: 0 25px 50px rgba(0, 86, 179, 0.08); border-color: var(--secondary); }
        .m-card i { font-size: 2.2rem; color: var(--primary); margin-bottom: 20px; display: block; opacity: 0.9; }
        .m-card h4 { font-family: 'Outfit', sans-serif; font-size: 1.25rem; margin-bottom: 10px; }
        .m-card p { font-size: 0.85rem; color: var(--text-muted); }

        /* Specialist Card Styles */
        .m-card.urgent { border-top: 5px solid var(--accent); }
        .m-card.mama { border-top: 5px solid var(--mama); }
        .m-card.mama i { color: var(--mama); }

        /* --- APPOINTMENT SECTION --- */
        .booking-container { padding: 80px 6%; }
        .booking-card {
            background: var(--text-dark); color: white; border-radius: var(--radius-lg);
            display: grid; grid-template-columns: 1fr 1.2fr; overflow: hidden;
            box-shadow: 0 40px 80px rgba(0,0,0,0.2);
        }
        .booking-info { padding: 60px; background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%); }
        .booking-form { padding: 60px; background: white; color: var(--text-dark); }
        
        .input-group { margin-bottom: 20px; }
        .input-group label { display: block; font-weight: 700; font-size: 0.85rem; margin-bottom: 8px; color: var(--text-muted); }
        .input-group input, .input-group select {
            width: 100%; padding: 14px; border-radius: var(--radius-sm);
            border: 2px solid #f1f5f9; outline: none; transition: 0.3s;
        }
        .input-group input:focus { border-color: var(--primary); }
        
        .btn-confirm {
            width: 100%; padding: 16px; background: var(--primary); color: white;
            border: none; border-radius: var(--radius-sm); font-weight: 800; cursor: pointer;
        }

        /* --- FOOTER --- */
        footer { padding: 60px 6%; background: white; border-top: 1px solid #f1f5f9; }
        .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 40px; }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @media (max-width: 968px) {
            .hero, .about-wrap, .booking-card { grid-template-columns: 1fr; }
            .hero-content h1 { font-size: 2.8rem; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

    <nav>
        <a href="#" class="logo">JK<span>HOSPITAL</span></a>
        <ul class="nav-links">
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#updates">Updates</a></li>
            <li><a href="#appointment" class="btn-booking">Book Now</a></li>
        </ul>
    </nav>

    <section class="hero">
        <div class="hero-content">
            <span class="section-tag">24/7 MEDICAL EXCELLENCE</span>
            <h1>Modern Care, <br><mark>Close to You.</mark></h1>
            <p>JK Hospital Kigamboni (Tuamoyo) provides professional medical services using advanced technology and expert physicians.</p>
            <div style="display: flex; gap: 15px;">
                <a href="#appointment" class="btn-booking" style="padding: 15px 35px;">Schedule Visit</a>
                <a href="https://wa.me/255717739497" style="padding: 15px; font-weight: 700; color: var(--text-dark); text-decoration: none;"><i class="fab fa-whatsapp" style="color: #25d366;"></i> Live Chat</a>
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

    <section class="about-wrap" id="about">
        <div>
            <span class="section-tag">OUR STORY</span>
            <h2 style="font-family: 'Outfit'; font-size: 2.5rem; margin-bottom: 20px;">Dedicated to Kigamboni.</h2>
            <p style="color: var(--text-muted); margin-bottom: 20px;">Founded in August 2023, JK Hospital Co. Ltd operates as a premium private district-level hospital. We bridge the healthcare gap in Tuamoyo by providing reliable, specialized treatment for the whole family.</p>
            <div class="about-stats">
                <div class="stat-box"><h3>24h</h3><p>Operation</p></div>
                <div class="stat-box"><h3>10+</h3><p>Units</p></div>
            </div>
        </div>
        <img src="https://images.unsplash.com/photo-1551076805-e1869033e561?auto=format&fit=crop&q=80&w=800" alt="Medical Team" style="width: 100%; border-radius: var(--radius-lg);">
    </section>

    <section class="services-section" id="services">
        <center>
            <span class="section-tag">DEPARTMENTS</span>
            <h2 style="font-family: 'Outfit'; font-size: 2.5rem;">Clinical Excellence Matrix</h2>
        </center>

        <div class="matrix">
            <div class="m-card urgent">
                <i class="fas fa-truck-medical" style="color: var(--accent);"></i>
                <h4>Ambulance</h4>
                <p>Swift 24/7 emergency response and inter-facility transfers.</p>
            </div>
            <div class="m-card mama">
                <i class="fas fa-baby"></i>
                <h4>Mama na Mtoto</h4>
                <p>Specialized RCH clinic for pediatric care and vaccines.</p>
            </div>
            <div class="m-card mama">
                <i class="fas fa-hospital-user"></i>
                <h4>Maternity</h4>
                <p>Private delivery suites with neonatal monitoring (Huduma ya Kujifungua).</p>
            </div>
            <div class="m-card">
                <i class="fas fa-microscope"></i>
                <h4>Lab / Vipimo</h4>
                <p>ISO-standard laboratory for accurate diagnostics.</p>
            </div>
            <div class="m-card">
                <i class="fas fa-tooth"></i>
                <h4>Dental Unit</h4>
                <p>Oral surgery, scaling, and routine dental maintenance.</p>
            </div>
            <div class="m-card">
                <i class="fas fa-pills"></i>
                <h4>Pharmacy</h4>
                <p>24-hour pharmaceutical access for all prescribed medicines.</p>
            </div>
            <div class="m-card">
                <i class="fas fa-scissors"></i>
                <h4>Surgical Theater</h4>
                <p>Major & minor surgical procedures by specialist surgeons.</p>
            </div>
            <div class="m-card">
                <i class="fas fa-wave-square"></i>
                <h4>Ultrasound</h4>
                <p>High-resolution imaging for maternal and internal health.</p>
            </div>
            <div class="m-card">
                <i class="fas fa-heartbeat"></i>
                <h4>NCD Clinic</h4>
                <p>Expert management for Diabetes and Hypertension.</p>
            </div>
            <div class="m-card">
                <i class="fas fa-user-md"></i>
                <h4>OPD Services</h4>
                <p>General practitioner consultations for all age groups.</p>
            </div>
        </div>
    </section>

    <section class="booking-container" id="appointment">
        <div class="booking-card">
            <div class="booking-info">
                <h2 style="font-family: 'Outfit'; font-size: 2.5rem; margin-bottom: 20px;">Visit Our Specialists.</h2>
                <p style="opacity: 0.8;">Secure your consultation slot today. We accept NHIF, Strategis, Jubilee, and all major insurance providers.</p>
                <div style="margin-top: 40px;">
                    <p><i class="fas fa-map-marker-alt"></i> Tuamoyo Area, Kigamboni, Dar</p>
                    <p><i class="fas fa-clock"></i> Open 24/7</p>
                </div>
            </div>
            <div class="booking-form">
                <form>
                    <div class="input-group">
                        <label>FULL NAME</label>
                        <input type="text" placeholder="e.g. John Doe" required>
                    </div>
                    <div class="input-group">
                        <label>SELECT SERVICE</label>
                        <select>
                            <option>Mama na Mtoto / RCH</option>
                            <option>Dental Appointment</option>
                            <option>Maternity Consultation</option>
                            <option>General Checkup</option>
                        </select>
                    </div>
                    <div class="input-group">
                        <label>PHONE NUMBER</label>
                        <input type="tel" placeholder="0xxxxxxxxx" required>
                    </div>
                    <button class="btn-confirm">CONFIRM APPOINTMENT</button>
                </form>
            </div>
        </div>
    </section>

    <footer>
        <div class="footer-grid">
            <div>
                <a href="#" class="logo">JK<span>HOSPITAL</span></a>
                <p style="color: var(--text-muted); margin-top: 15px;">Redefining the standard of private healthcare in Kigamboni. Quality care you can count on.</p>
            </div>
            <div>
                <h4>Contact</h4>
                <ul style="list-style: none; color: var(--text-muted); font-size: 0.9rem; margin-top: 15px;">
                    <li>Tuamoyo, Kigamboni</li>
                    <li>+255 717 739 497</li>
                </ul>
            </div>
            <div>
                <h4>Social</h4>
                <div style="display: flex; gap: 15px; margin-top: 15px; font-size: 1.2rem; color: var(--primary);">
                    <i class="fab fa-facebook"></i>
                    <i class="fab fa-instagram"></i>
                    <i class="fab fa-whatsapp"></i>
                </div>
            </div>
        </div>
        <hr style="margin: 40px 0; border: none; border-top: 1px solid #f1f5f9;">
        <center style="font-size: 0.8rem; color: var(--text-muted);">&copy; 2026 JK Hospital Company Limited.</center>
    </footer>

</body>
</html>
