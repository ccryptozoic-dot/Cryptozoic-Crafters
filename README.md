[index.html.html](https://github.com/user-attachments/files/28931327/index.html.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cryptozoic Crafters | Design. Build. Deliver.</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  :root {
    --yellow: #F5C518;
    --yellow-dark: #d4a800;
    --black: #111111;
    --gray: #555;
    --light-gray: #f7f7f7;
    --white: #fff;
  }
  html { scroll-behavior: smooth; }
  body { font-family: 'Segoe UI', Arial, sans-serif; color: var(--black); background: var(--white); }

  /* NAV */
  nav {
    position: fixed; top: 0; width: 100%; background: var(--white);
    box-shadow: 0 2px 12px rgba(0,0,0,0.08); z-index: 1000;
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 5%; height: 68px;
  }
  .nav-logo { display: flex; align-items: center; gap: 10px; text-decoration: none; }
  .nav-logo-icon {
    width: 42px; height: 42px; background: var(--yellow); border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-weight: 900; font-size: 18px; color: var(--black); letter-spacing: -1px;
  }
  .nav-logo span { font-size: 17px; font-weight: 700; color: var(--black); }
  .nav-logo span b { color: var(--yellow-dark); }
  .nav-links { display: flex; gap: 32px; list-style: none; }
  .nav-links a { text-decoration: none; color: var(--black); font-size: 14px; font-weight: 500; transition: color 0.2s; }
  .nav-links a:hover { color: var(--yellow-dark); }
  .nav-cta {
    background: var(--yellow); color: var(--black); border: none;
    padding: 10px 22px; border-radius: 6px; font-weight: 700; font-size: 14px;
    cursor: pointer; text-decoration: none; transition: background 0.2s;
  }
  .nav-cta:hover { background: var(--yellow-dark); }
  .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; background: none; border: none; padding: 4px; }
  .hamburger span { width: 24px; height: 2px; background: var(--black); border-radius: 2px; display: block; }

  /* HERO */
  #hero {
    min-height: 100vh; padding: 120px 5% 80px;
    display: flex; align-items: center; justify-content: space-between; gap: 40px;
    background: linear-gradient(135deg, #fffbe6 0%, #fff 60%);
    position: relative; overflow: hidden;
  }
  .hero-blob {
    position: absolute; width: 420px; height: 420px; border-radius: 50%;
    background: var(--yellow); opacity: 0.13; right: -80px; top: 60px; z-index: 0;
  }
  .hero-blob2 {
    position: absolute; width: 180px; height: 180px; border-radius: 50%;
    background: var(--yellow); opacity: 0.18; right: 260px; bottom: 60px; z-index: 0;
  }
  .hero-text { max-width: 560px; z-index: 1; }
  .hero-tag {
    display: inline-block; background: var(--yellow); color: var(--black);
    font-size: 12px; font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase;
    padding: 5px 14px; border-radius: 20px; margin-bottom: 18px;
  }
  .hero-text h1 { font-size: clamp(32px, 5vw, 56px); font-weight: 800; line-height: 1.1; margin-bottom: 18px; }
  .hero-text h1 span { color: var(--yellow-dark); }
  .hero-text p { font-size: 17px; color: var(--gray); line-height: 1.7; margin-bottom: 32px; }
  .hero-btns { display: flex; gap: 14px; flex-wrap: wrap; }
  .btn-primary {
    background: var(--yellow); color: var(--black); padding: 14px 28px;
    border-radius: 8px; font-weight: 700; font-size: 15px; text-decoration: none; transition: background 0.2s;
  }
  .btn-primary:hover { background: var(--yellow-dark); }
  .btn-outline {
    border: 2px solid var(--black); color: var(--black); padding: 12px 28px;
    border-radius: 8px; font-weight: 700; font-size: 15px; text-decoration: none; transition: all 0.2s;
  }
  .btn-outline:hover { background: var(--black); color: var(--white); }
  .hero-stats { display: flex; gap: 36px; margin-top: 40px; flex-wrap: wrap; }
  .hero-stat h3 { font-size: 28px; font-weight: 800; color: var(--yellow-dark); }
  .hero-stat p { font-size: 13px; color: var(--gray); }
  .hero-visual { z-index: 1; }
  .hero-card {
    background: var(--white); border-radius: 16px; box-shadow: 0 8px 40px rgba(0,0,0,0.10);
    padding: 28px; max-width: 320px; border-left: 5px solid var(--yellow);
  }
  .hero-card h4 { font-size: 13px; color: var(--gray); font-weight: 500; margin-bottom: 8px; text-transform: uppercase; letter-spacing: 1px; }
  .hero-card p { font-size: 22px; font-weight: 800; margin-bottom: 18px; }
  .hc-items { display: flex; flex-direction: column; gap: 10px; }
  .hc-item { display: flex; align-items: center; gap: 10px; font-size: 14px; }
  .hc-dot { width: 10px; height: 10px; border-radius: 50%; background: var(--yellow); flex-shrink: 0; }

  /* SECTION COMMONS */
  section { padding: 90px 5%; }
  .section-label {
    display: inline-block; background: var(--yellow); color: var(--black);
    font-size: 11px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase;
    padding: 4px 14px; border-radius: 20px; margin-bottom: 14px;
  }
  .section-title { font-size: clamp(26px, 4vw, 40px); font-weight: 800; margin-bottom: 12px; }
  .section-title span { color: var(--yellow-dark); }
  .section-sub { font-size: 16px; color: var(--gray); max-width: 600px; line-height: 1.7; margin-bottom: 48px; }

  /* ABOUT */
  #about { background: var(--light-gray); }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: center; }
  .about-visual { display: flex; flex-direction: column; gap: 16px; }
  .about-card {
    background: var(--white); border-radius: 12px; padding: 22px;
    box-shadow: 0 2px 16px rgba(0,0,0,0.07); border-left: 4px solid var(--yellow);
  }
  .about-card h4 { font-size: 13px; color: var(--yellow-dark); font-weight: 700; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 6px; }
  .about-card p { font-size: 14px; color: var(--gray); line-height: 1.6; }

  /* SERVICES */
  #services { background: var(--white); }
  .services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 24px; }
  .service-card {
    background: var(--light-gray); border-radius: 14px; padding: 28px;
    transition: transform 0.2s, box-shadow 0.2s; border: 2px solid transparent;
  }
  .service-card:hover { transform: translateY(-6px); box-shadow: 0 12px 32px rgba(0,0,0,0.10); border-color: var(--yellow); }
  .service-icon {
    width: 52px; height: 52px; background: var(--yellow); border-radius: 12px;
    display: flex; align-items: center; justify-content: center; font-size: 24px; margin-bottom: 16px;
  }
  .service-card h3 { font-size: 17px; font-weight: 700; margin-bottom: 10px; }
  .service-card p { font-size: 14px; color: var(--gray); line-height: 1.6; }

  /* CORE SERVICES */
  #core { background: var(--black); color: var(--white); }
  #core .section-title { color: var(--white); }
  #core .section-sub { color: #aaa; }
  .core-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; }
  .core-card {
    border: 1px solid #333; border-radius: 14px; padding: 26px;
    transition: border-color 0.2s, background 0.2s;
  }
  .core-card:hover { border-color: var(--yellow); background: rgba(245,197,24,0.05); }
  .core-card h3 { font-size: 16px; font-weight: 700; color: var(--yellow); margin-bottom: 10px; }
  .core-card ul { list-style: none; display: flex; flex-direction: column; gap: 7px; }
  .core-card ul li { font-size: 13px; color: #bbb; padding-left: 16px; position: relative; line-height: 1.5; }
  .core-card ul li::before { content: '▸'; position: absolute; left: 0; color: var(--yellow); }

  /* PROCESS */
  #process { background: var(--light-gray); }
  .process-steps { display: flex; flex-direction: column; gap: 0; max-width: 700px; }
  .process-step { display: flex; gap: 24px; position: relative; }
  .process-step:not(:last-child)::after {
    content: ''; position: absolute; left: 23px; top: 54px;
    width: 2px; height: calc(100% - 24px); background: var(--yellow); opacity: 0.4;
  }
  .step-num {
    width: 48px; height: 48px; border-radius: 50%; background: var(--yellow);
    display: flex; align-items: center; justify-content: center;
    font-weight: 800; font-size: 16px; flex-shrink: 0; color: var(--black);
  }
  .step-content { padding: 8px 0 40px; }
  .step-content h3 { font-size: 17px; font-weight: 700; margin-bottom: 6px; }
  .step-content p { font-size: 14px; color: var(--gray); line-height: 1.6; }

  /* WHY US */
  #why { background: var(--white); }
  .why-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 20px; }
  .why-card {
    border-radius: 14px; padding: 26px; background: var(--light-gray);
    border-top: 4px solid var(--yellow);
  }
  .why-icon { font-size: 28px; margin-bottom: 12px; }
  .why-card h3 { font-size: 15px; font-weight: 700; margin-bottom: 8px; }
  .why-card p { font-size: 13px; color: var(--gray); line-height: 1.6; }

  /* TEAM */
  #team { background: var(--light-gray); }
  .team-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 24px; }
  .team-card {
    background: var(--white); border-radius: 14px; padding: 28px 20px; text-align: center;
    box-shadow: 0 2px 16px rgba(0,0,0,0.07); transition: transform 0.2s;
  }
  .team-card:hover { transform: translateY(-4px); }
  .team-avatar {
    width: 80px; height: 80px; border-radius: 50%; background: var(--yellow);
    display: flex; align-items: center; justify-content: center;
    font-size: 28px; font-weight: 800; margin: 0 auto 16px; color: var(--black);
    border: 3px solid var(--yellow-dark);
  }
  .team-card h3 { font-size: 16px; font-weight: 700; margin-bottom: 4px; }
  .team-card p { font-size: 13px; color: var(--gray); }

  /* TESTIMONIAL */
  #testimonial { background: var(--yellow); }
  .testimonial-box { max-width: 720px; margin: 0 auto; text-align: center; }
  .testimonial-box blockquote { font-size: clamp(17px, 2.5vw, 22px); font-weight: 600; line-height: 1.6; margin-bottom: 24px; color: var(--black); }
  .testimonial-box .cite { font-size: 14px; font-weight: 700; color: #444; }
  .quote-mark { font-size: 72px; font-weight: 900; line-height: 0.8; color: rgba(0,0,0,0.15); display: block; margin-bottom: 10px; }

  /* CONTACT */
  #contact { background: var(--white); }
  .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start; }
  .contact-info { display: flex; flex-direction: column; gap: 22px; }
  .contact-item { display: flex; align-items: flex-start; gap: 16px; }
  .contact-icon {
    width: 46px; height: 46px; background: var(--yellow); border-radius: 10px;
    display: flex; align-items: center; justify-content: center; font-size: 20px; flex-shrink: 0;
  }
  .contact-item h4 { font-size: 13px; color: var(--gray); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 4px; }
  .contact-item p, .contact-item a { font-size: 15px; font-weight: 600; color: var(--black); text-decoration: none; }
  .contact-item a:hover { color: var(--yellow-dark); }
  .contact-form { display: flex; flex-direction: column; gap: 16px; }
  .contact-form input, .contact-form textarea {
    width: 100%; padding: 14px 16px; border: 1.5px solid #ddd; border-radius: 8px;
    font-size: 14px; font-family: inherit; outline: none; transition: border-color 0.2s;
    background: var(--light-gray);
  }
  .contact-form input:focus, .contact-form textarea:focus { border-color: var(--yellow); background: var(--white); }
  .contact-form textarea { min-height: 130px; resize: vertical; }
  .form-btn {
    background: var(--yellow); color: var(--black); border: none;
    padding: 14px; border-radius: 8px; font-weight: 700; font-size: 15px;
    cursor: pointer; transition: background 0.2s;
  }
  .form-btn:hover { background: var(--yellow-dark); }

  /* FOOTER */
  footer {
    background: var(--black); color: #aaa; text-align: center; padding: 30px 5%;
    font-size: 13px;
  }
  footer span { color: var(--yellow); font-weight: 700; }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    nav { padding: 0 5%; }
    .nav-links, .nav-cta { display: none; }
    .hamburger { display: flex; }
    #hero { flex-direction: column; padding: 100px 5% 60px; }
    .hero-visual { display: none; }
    .about-grid, .contact-grid { grid-template-columns: 1fr; }
    .process-steps { max-width: 100%; }
  }

  /* Mobile nav */
  .mobile-menu {
    display: none; position: fixed; top: 68px; left: 0; width: 100%; background: var(--white);
    padding: 20px 5%; box-shadow: 0 8px 24px rgba(0,0,0,0.12); z-index: 999;
    flex-direction: column; gap: 18px;
  }
  .mobile-menu.open { display: flex; }
  .mobile-menu a { font-size: 16px; font-weight: 600; color: var(--black); text-decoration: none; padding: 8px 0; border-bottom: 1px solid #eee; }
  .mobile-menu a:last-child { border-bottom: none; }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#hero" class="nav-logo">
    <div class="nav-logo-icon">CC</div>
    <span><b>Cryptozoic</b> Crafters</span>
  </a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#process">Process</a></li>
    <li><a href="#team">Team</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Get in Touch</a>
  <button class="hamburger" onclick="toggleMenu()" aria-label="Toggle menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- Mobile Menu -->
<div class="mobile-menu" id="mobileMenu">
  <a href="#about" onclick="closeMenu()">About</a>
  <a href="#services" onclick="closeMenu()">Services</a>
  <a href="#process" onclick="closeMenu()">Process</a>
  <a href="#team" onclick="closeMenu()">Team</a>
  <a href="#contact" onclick="closeMenu()">Contact</a>
</div>

<!-- HERO -->
<section id="hero">
  <div class="hero-blob"></div>
  <div class="hero-blob2"></div>
  <div class="hero-text">
    <div class="hero-tag">Nepal's Engineering Consultants</div>
    <h1>Design. Build. <span>Deliver.</span></h1>
    <p>Bringing practical, sustainable, and cost-effective engineering solutions to life. Nepal's trusted civil engineering & architecture consulting firm.</p>
    <div class="hero-btns">
      <a href="#services" class="btn-primary">Explore Services</a>
      <a href="#contact" class="btn-outline">Contact Us</a>
    </div>
    <div class="hero-stats">
      <div class="hero-stat"><h3>40+</h3><p>Team Members</p></div>
      <div class="hero-stat"><h3>6</h3><p>Core Services</p></div>
      <div class="hero-stat"><h3>100%</h3><p>Client Focused</p></div>
    </div>
  </div>
  <div class="hero-visual">
    <div class="hero-card">
      <h4>What We Do</h4>
      <p>End-to-End Engineering Consulting</p>
      <div class="hc-items">
        <div class="hc-item"><div class="hc-dot"></div>Civil Engineering & Architecture</div>
        <div class="hc-item"><div class="hc-dot"></div>Infrastructure Studies</div>
        <div class="hc-item"><div class="hc-dot"></div>Financial Feasibility</div>
        <div class="hc-item"><div class="hc-dot"></div>Project Management</div>
        <div class="hc-item"><div class="hc-dot"></div>BOQ & Cost Estimation</div>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-label">About Us</div>
  <div class="about-grid">
    <div>
      <h2 class="section-title">Engineering Excellence <span>in Nepal</span></h2>
      <p style="font-size:16px; color:#555; line-height:1.8; margin-bottom:20px;">
        Cryptozoic Crafters is an engineering consulting and research firm based in Nepal, specializing in civil engineering, architecture, infrastructure studies, and financial feasibility assessments.
      </p>
      <p style="font-size:16px; color:#555; line-height:1.8; margin-bottom:20px;">
        As the dedicated consulting arm of Bhimeshwor Group, we combine decades of field-tested expertise with cutting-edge engineering innovation to deliver sustainable, practical, and future-ready solutions.
      </p>
      <p style="font-size:16px; color:#555; line-height:1.8;">
        Our commitment to financial feasibility, innovation, and quality ensures that each project contributes meaningfully to community development and the advancement of the construction industry.
      </p>
    </div>
    <div class="about-visual">
      <div class="about-card">
        <h4>🎯 Our Mission</h4>
        <p>To deliver high-quality engineering services that exceed clients' expectations while actively contributing to the development of thriving communities.</p>
      </div>
      <div class="about-card">
        <h4>🔭 Our Vision</h4>
        <p>To be recognized as a leader in the construction industry, known for unwavering commitment to quality, safety, and innovative solutions.</p>
      </div>
      <div class="about-card">
        <h4>🏢 Our Heritage</h4>
        <p>The specialized consulting wing of Bhimeshwor Group — merging legacy construction wisdom with modern engineering solutions.</p>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="section-label">Our Services</div>
  <h2 class="section-title">What We <span>Offer</span></h2>
  <p class="section-sub">Comprehensive engineering and consulting services tailored to your project needs.</p>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">🏗️</div>
      <h3>Design & Engineering</h3>
      <p>Architectural design, structural engineering, MEP systems, and sustainable design solutions that enhance energy efficiency and environmental responsibility.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">📋</div>
      <h3>Project Management</h3>
      <p>Comprehensive project planning, scheduling, resource allocation, and proactive progress monitoring with effective stakeholder communication.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">💰</div>
      <h3>Estimation & Valuation</h3>
      <p>Accurate cost analyses, BOQ preparation, procurement documents, and value engineering for budget optimization and financial feasibility.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">🔍</div>
      <h3>Project Auditing</h3>
      <p>Comprehensive auditing ensuring compliance with technical standards, regulatory frameworks, and contractual obligations with detailed documentation review.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">📐</div>
      <h3>Technical Drawing</h3>
      <p>CAD drawings, cross-sections, site plans, and as-built documentation with 3D modeling and BIM integration for precise technical deliverables.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">🌱</div>
      <h3>Feasibility Studies</h3>
      <p>Soil stability, hydraulic studies, environmental impact assessments, compliance reporting, and financial feasibility for infrastructure projects.</p>
    </div>
  </div>
</section>

<!-- CORE SERVICES -->
<section id="core">
  <div class="section-label" style="background: var(--yellow); color: #111;">Core Expertise</div>
  <h2 class="section-title">Core <span>Services</span></h2>
  <p class="section-sub">Specialized capabilities that set us apart in Nepal's engineering landscape.</p>
  <div class="core-grid">
    <div class="core-card">
      <h3>Conceptual & Detailed Design</h3>
      <ul>
        <li>Structural, geotechnical and infrastructure layouts</li>
        <li>3D modeling and BIM integration</li>
      </ul>
    </div>
    <div class="core-card">
      <h3>Technical Drawing & Drafting</h3>
      <ul>
        <li>CAD drawings, cross-sections and site plans</li>
        <li>As-built documentation</li>
      </ul>
    </div>
    <div class="core-card">
      <h3>Quantity Estimation & Cost Control</h3>
      <ul>
        <li>Preliminary and detailed cost estimates</li>
        <li>Value engineering for budget optimization</li>
      </ul>
    </div>
    <div class="core-card">
      <h3>Bills of Quantities (BOQ)</h3>
      <ul>
        <li>Itemized BOQs compliant with international standards</li>
        <li>Unit rate analysis and procurement schedules</li>
      </ul>
    </div>
    <div class="core-card">
      <h3>Report Generation & Analysis</h3>
      <ul>
        <li>Feasibility, soil, stability and hydraulic studies</li>
        <li>Environmental impact assessments</li>
      </ul>
    </div>
    <div class="core-card">
      <h3>Turnkey Civil Works Support</h3>
      <ul>
        <li>Project management and site supervision</li>
        <li>Contract administration and claims evaluation</li>
      </ul>
    </div>
  </div>
</section>

<!-- PROCESS -->
<section id="process">
  <div class="section-label">How We Work</div>
  <h2 class="section-title">Our <span>Process</span></h2>
  <p class="section-sub">A proven step-by-step approach that ensures quality and transparency at every stage.</p>
  <div class="process-steps">
    <div class="process-step">
      <div class="step-num">1</div>
      <div class="step-content">
        <h3>Discovery &amp; Briefing</h3>
        <p>Identify project objectives, constraints, and deliverables through detailed client consultation.</p>
      </div>
    </div>
    <div class="process-step">
      <div class="step-num">2</div>
      <div class="step-content">
        <h3>Conceptual Design</h3>
        <p>Develop preliminary layouts, structural concepts, and cost frameworks aligned with your vision.</p>
      </div>
    </div>
    <div class="process-step">
      <div class="step-num">3</div>
      <div class="step-content">
        <h3>Detailed Engineering</h3>
        <p>Finalize all drawings, calculations, and technical specifications to construction-ready standards.</p>
      </div>
    </div>
    <div class="process-step">
      <div class="step-num">4</div>
      <div class="step-content">
        <h3>Estimation &amp; BOQ</h3>
        <p>Produce accurate cost analyses and procurement documents for informed decision-making.</p>
      </div>
    </div>
    <div class="process-step">
      <div class="step-num">5</div>
      <div class="step-content">
        <h3>Reporting &amp; Compliance</h3>
        <p>Generate technical, environmental and safety reports meeting regulatory requirements.</p>
      </div>
    </div>
    <div class="process-step">
      <div class="step-num">6</div>
      <div class="step-content">
        <h3>Handover &amp; Support</h3>
        <p>Assist with tendering, construction oversight, and project close-out for seamless delivery.</p>
      </div>
    </div>
  </div>
</section>

<!-- WHY US -->
<section id="why">
  <div class="section-label">Why Choose Us</div>
  <h2 class="section-title">The <span>Cryptozoic Crafters</span> Advantage</h2>
  <p class="section-sub">Five reasons why clients trust us with their most important projects.</p>
  <div class="why-grid">
    <div class="why-card">
      <div class="why-icon">🎓</div>
      <h3>Technical Expertise</h3>
      <p>Seasoned engineers with multidisciplinary backgrounds covering civil, structural, MEP, and geotechnical domains.</p>
    </div>
    <div class="why-card">
      <div class="why-icon">💡</div>
      <h3>Cost Efficiency</h3>
      <p>Rigorous estimation processes and value engineering ensure projects stay on budget without compromising quality.</p>
    </div>
    <div class="why-card">
      <div class="why-icon">✅</div>
      <h3>Quality Assurance</h3>
      <p>ISO-inspired workflows with peer review at every stage guarantee the highest standards in every deliverable.</p>
    </div>
    <div class="why-card">
      <div class="why-icon">🤝</div>
      <h3>Client-Centered</h3>
      <p>Transparent communication, regular milestone reporting, and genuine partnership throughout every project.</p>
    </div>
    <div class="why-card">
      <div class="why-icon">🌿</div>
      <h3>Innovation & Sustainability</h3>
      <p>Cutting-edge tools, green engineering practices, and BIM integration for future-ready infrastructure.</p>
    </div>
  </div>
</section>

<!-- TEAM -->
<section id="team">
  <div class="section-label">Our Team</div>
  <h2 class="section-title">Meet the <span>Experts</span></h2>
  <p class="section-sub">A dedicated team of highly motivated engineers, architects, and project managers committed to delivering exceptional results.</p>
  <div class="team-grid">
    <div class="team-card">
      <div class="team-avatar">SD</div>
      <h3>Er. Samir Dahal</h3>
      <p>Managing Director</p>
    </div>
    <div class="team-card">
      <div class="team-avatar">SK</div>
      <h3>Er. Sujan Khadka</h3>
      <p>Project Manager</p>
    </div>
    <div class="team-card">
      <div class="team-avatar">ST</div>
      <h3>Er. Sampurna Thapa</h3>
      <p>Lead Engineer</p>
    </div>
    <div class="team-card" style="background: #fffbe6; border: 2px dashed var(--yellow);">
      <div class="team-avatar" style="background: #eee; color: #999;">40+</div>
      <h3>Full Team</h3>
      <p>Structural, Civil, MEP & QS Engineers</p>
    </div>
  </div>
</section>

<!-- TESTIMONIAL -->
<section id="testimonial">
  <div class="testimonial-box">
    <div class="section-label" style="background: rgba(0,0,0,0.12); color: #111;">Testimonial</div>
    <span class="quote-mark">"</span>
    <blockquote>
      Cryptozoic Crafters represents a natural evolution of our journey — where field-tested experience meets modern engineering innovation. Together, we offer a complete spectrum of services combining legacy, learning, and leadership to deliver integrated, sustainable, and future-ready solutions.
    </blockquote>
    <div class="cite">— Sandeep Khadka, Director of Bhimeshwor Group</div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-label">Contact Us</div>
  <h2 class="section-title">Let's Build <span>Together</span></h2>
  <p class="section-sub">We welcome inquiries for new projects and collaborations. Reach out to us today!</p>
  <div class="contact-grid">
    <div class="contact-info">
      <div class="contact-item">
        <div class="contact-icon">📍</div>
        <div>
          <h4>Address</h4>
          <p>Purano Sinamangal-32, Kathmandu, Nepal</p>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📱</div>
        <div>
          <h4>WhatsApp</h4>
          <a href="tel:+9779851402595">+977 9851402595</a><br>
          <a href="tel:+9779840077273">+977 9840077273</a>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">✉️</div>
        <div>
          <h4>Email</h4>
          <a href="mailto:ccryptozoic@gmail.com">ccryptozoic@gmail.com</a>
        </div>
      </div>
    </div>
    <div class="contact-form">
      <input type="text" placeholder="Your Full Name" />
      <input type="email" placeholder="Your Email Address" />
      <input type="text" placeholder="Subject / Project Type" />
      <textarea placeholder="Tell us about your project..."></textarea>
      <button class="form-btn" onclick="alert('Thank you! We will get back to you soon.')">Send Message →</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2025 <span>Cryptozoic Crafters</span> | The Consulting Arm of Bhimeshwor Group | Kathmandu, Nepal</p>
  <p style="margin-top:8px; font-size:12px;">Design. Build. Deliver.</p>
</footer>

<script>
function toggleMenu() {
  document.getElementById('mobileMenu').classList.toggle('open');
}
function closeMenu() {
  document.getElementById('mobileMenu').classList.remove('open');
}
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', function(e) {
    const target = document.querySelector(this.getAttribute('href'));
    if (target) {
      e.preventDefault();
      target.scrollIntoView({ behavior: 'smooth' });
    }
  });
});
</script>
</body>
</html>

