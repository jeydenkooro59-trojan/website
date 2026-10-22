<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Northstar | Dark Mode</title>
  <style>
    :root {
      --bg: #07111f;
      --bg-2: #0d1728;
      --panel: #111d2d;
      --panel-2: #16263d;
      --card: #0f1b2d;
      --card-2: #101c30;
      --text: #edf6ff;
      --muted: #9bb0c9;
      --primary: #7dd3fc;
      --primary-2: #4f9cff;
      --accent: #7c3aed;
      --success: #34d399;
      --border: rgba(255, 255, 255, 0.08);
      --shadow: 0 20px 40px rgba(2, 6, 23, 0.45);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: linear-gradient(180deg, var(--bg) 0%, var(--bg-2) 100%);
      color: var(--text);
      line-height: 1.6;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .container {
      width: min(1120px, calc(100% - 2rem));
      margin: 0 auto;
    }

    .section {
      padding: 5.5rem 0;
    }

    .section-header {
      text-align: center;
      margin-bottom: 3rem;
    }

    .section-header h2 {
      font-size: clamp(2rem, 4vw, 2.8rem);
      margin-bottom: 0.75rem;
      color: var(--text);
      letter-spacing: -0.04em;
    }

    .section-header p {
      max-width: 640px;
      margin: 0 auto;
      color: var(--muted);
      font-size: 1.05rem;
    }

    .btn {
      display: inline-block;
      padding: 0.9rem 1.5rem;
      border-radius: 12px;
      border: none;
      cursor: pointer;
      font-weight: 700;
      transition: transform 0.25s ease, box-shadow 0.25s ease, opacity 0.25s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--primary-2), var(--primary));
      color: #081521;
      box-shadow: 0 12px 24px rgba(79, 156, 255, 0.35);
    }

    .btn-secondary {
      background: transparent;
      border: 1px solid var(--border);
      color: var(--text);
    }

    .btn-secondary:hover {
      background: rgba(255, 255, 255, 0.03);
    }

    /* Header */
    header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(7, 17, 31, 0.75);
      border-bottom: 1px solid var(--border);
      backdrop-filter: blur(10px);
    }

    .nav {
      min-height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
    }

    .logo {
      font-size: 1.55rem;
      font-weight: 800;
      letter-spacing: 0.06em;
      color: var(--text);
    }

    .logo span {
      color: var(--primary);
    }

    nav {
      display: flex;
      align-items: center;
      gap: 1.6rem;
      flex-wrap: wrap;
    }

    nav a {
      color: var(--muted);
      transition: color 0.2s ease;
      font-weight: 500;
    }

    nav a:hover {
      color: var(--text);
    }

    .nav-actions {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      flex-wrap: wrap;
    }

    /* Hero */
    .hero {
      background:
        radial-gradient(circle at top right, rgba(124, 58, 237, 0.2), transparent 26%),
        radial-gradient(circle at bottom left, rgba(79, 156, 255, 0.18), transparent 28%),
        linear-gradient(180deg, rgba(9, 16, 28, 1) 0%, rgba(15, 26, 39, 1) 100%);
      padding: 6rem 0 5rem;
      border-bottom: 1px solid var(--border);
    }

    .hero-inner {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 2.5rem;
      align-items: center;
    }

    .eyebrow {
      display: inline-block;
      padding: 0.45rem 0.9rem;
      border-radius: 999px;
      background: rgba(125, 211, 252, 0.08);
      border: 1px solid rgba(125, 211, 252, 0.18);
      color: var(--primary);
      font-size: 0.78rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      font-weight: 700;
      margin-bottom: 1.2rem;
    }

    .hero h1 {
      font-size: clamp(2.8rem, 5vw, 4.3rem);
      line-height: 1.08;
      letter-spacing: -0.05em;
      margin-bottom: 1rem;
    }

    .hero p {
      color: var(--muted);
      font-size: 1.08rem;
      max-width: 580px;
      margin-bottom: 2rem;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      margin-bottom: 2rem;
    }

    .hero-stats {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
    }

    .stat {
      min-width: 120px;
    }

    .stat strong {
      display: block;
      font-size: 1.8rem;
      color: var(--text);
      margin-bottom: 0.2rem;
    }

    .stat span {
      color: var(--muted);
      font-size: 0.94rem;
    }

    .hero-card {
      background: linear-gradient(180deg, rgba(17, 29, 45, 0.95), rgba(12, 20, 31, 0.95));
      border: 1px solid var(--border);
      border-radius: 28px;
      padding: 2rem;
      box-shadow: var(--shadow);
    }

    .mini-panel {
      background: rgba(124, 58, 237, 0.12);
      border: 1px solid rgba(124, 58, 237, 0.2);
      border-radius: 20px;
      padding: 1.2rem;
      margin-bottom: 1rem;
    }

    .mini-panel h3 {
      color: var(--muted);
      font-size: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      margin-bottom: 0.6rem;
    }

    .metric {
      font-size: 2.5rem;
      font-weight: 800;
      color: var(--text);
      letter-spacing: -0.04em;
    }

    .mini-list {
      display: flex;
      flex-direction: column;
      gap: 0.85rem;
    }

    .mini-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0.9rem 1rem;
      border-radius: 14px;
      background: rgba(255, 255, 255, 0.02);
      border: 1px solid var(--border);
      color: var(--muted);
    }

    .mini-item strong {
      color: var(--text);
    }

    .dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: var(--success);
      box-shadow: 0 0 0 5px rgba(52, 211, 153, 0.18);
      display: inline-block;
    }

    /* Services */
    .services-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1.8rem;
    }

    .service-card {
      background: linear-gradient(180deg, rgba(17, 28, 41, 0.9), rgba(13, 20, 31, 0.9));
      border: 1px solid var(--border);
      border-radius: 22px;
      padding: 2rem;
      box-shadow: var(--shadow);
      transition: transform 0.25s ease, border-color 0.25s ease;
    }

    .service-card:hover {
      transform: translateY(-4px);
      border-color: rgba(125, 211, 252, 0.35);
    }

    .icon {
      width: 60px;
      height: 60px;
      border-radius: 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 800;
      margin-bottom: 1.1rem;
      color: var(--bg);
      background: linear-gradient(135deg, var(--primary), #dbeafe);
    }

    .service-card h3 {
      margin-bottom: 0.7rem;
      color: var(--text);
      font-size: 1.3rem;
    }

    .service-card p {
      color: var(--muted);
    }

    /* About */
    .about-wrap {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2.2rem;
      align-items: center;
    }

    .about-box {
      background: linear-gradient(135deg, #101d2d, #111827);
      border: 1px solid var(--border);
      border-radius: 26px;
      padding: 2rem;
      box-shadow: var(--shadow);
    }

    .about-box h3 {
      font-size: 2rem;
      margin-bottom: 1rem;
      color: var(--text);
    }

    .about-box p {
      color: var(--muted);
      margin-bottom: 1.5rem;
    }

    .check-list {
      list-style: none;
      display: grid;
      gap: 0.9rem;
    }

    .check-list li {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      color: var(--text);
    }

    .check {
      width: 22px;
      height: 22px;
      border-radius: 50%;
      background: var(--success);
      color: #04140f;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-size: 0.8rem;
      font-weight: 800;
    }

    .about-panel {
      background: linear-gradient(180deg, rgba(17, 28, 41, 0.9), rgba(14, 21, 31, 0.9));
      border: 1px solid var(--border);
      border-radius: 26px;
      padding: 2rem;
      box-shadow: var(--shadow);
    }

    .about-panel h3 {
      margin-bottom: 1rem;
      color: var(--text);
      font-size: 1.2rem;
    }

    .progress-item {
      margin-bottom: 1.2rem;
    }

    .progress-top {
      display: flex;
      justify-content: space-between;
      margin-bottom: 0.5rem;
      color: var(--text);
      font-weight: 600;
    }

    .progress-bar {
      width: 100%;
      height: 10px;
      background: rgba(255, 255, 255, 0.06);
      border-radius: 999px;
      overflow: hidden;
    }

    .progress-fill {
      height: 100%;
      border-radius: inherit;
      background: linear-gradient(135deg, var(--primary), var(--accent));
    }

    /* Testimonials */
    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1.8rem;
    }

    .testimonial {
      background: linear-gradient(180deg, rgba(17, 28, 41, 0.9), rgba(12, 20, 31, 0.9));
      border: 1px solid var(--border);
      border-radius: 22px;
      padding: 2rem;
      box-shadow: var(--shadow);
    }

    .stars {
      font-size: 1.1rem;
      margin-bottom: 1rem;
      color: #fbbf24;
      letter-spacing: 0.12em;
    }

    .testimonial p {
      color: var(--muted);
      margin-bottom: 1.4rem;
    }

    .person {
      display: flex;
      align-items: center;
      gap: 0.85rem;
    }

    .avatar {
      width: 46px;
      height: 46px;
      border-radius: 50%;
      background: linear-gradient(135deg, #93c5fd, #bfdbfe);
      color: #06131f;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 800;
    }

    .person h4 {
      color: var(--text);
      font-size: 1rem;
    }

    .person span {
      color: var(--muted);
      font-size: 0.84rem;
    }

    /* CTA */
    .cta {
      background: linear-gradient(135deg, #0d1728 0%, #13233d 100%);
      border: 1px solid var(--border);
      border-radius: 28px;
      padding: 3rem 2rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1.5rem;
      box-shadow: var(--shadow);
    }

    .cta h2 {
      font-size: clamp(2rem, 3vw, 2.7rem);
      margin-bottom: 0.45rem;
      letter-spacing: -0.04em;
    }

    .cta p {
      color: var(--muted);
    }

    /* Footer */
    footer {
      background: #050d18;
      border-top: 1px solid var(--border);
      padding: 2rem 0;
      margin-top: 5rem;
    }

    .footer-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .footer-links {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      color: var(--muted);
    }

    .footer-links a:hover {
      color: var(--text);
    }

    @media (max-width: 900px) {
      .hero-inner,
      .about-wrap,
      .services-grid,
      .testimonials-grid {
        grid-template-columns: 1fr;
      }

      .nav {
        flex-wrap: wrap;
        padding: 1rem 0;
      }

      nav {
        justify-content: center;
        width: 100%;
      }

      .cta {
        flex-direction: column;
        text-align: center;
      }
    }

    @media (max-width: 640px) {
      .hero {
        padding-top: 4.5rem;
      }

      .btn {
        width: 100%;
        text-align: center;
      }

      .hero-actions,
      .nav-actions {
        flex-direction: column;
        align-items: stretch;
      }

      .nav-actions {
        width: 100%;
      }
    }
  </style>
</head>
<body>

  <header>
    <div class="container nav">
      <div class="logo">NORTH<span>STAR</span></div>

      <nav>
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#about">About</a>
        <a href="#testimonials">Testimonials</a>
        <a href="#contact">Contact</a>
      </nav>

      <div class="nav-actions">
        <button class="btn btn-secondary" type="button" onclick="showMessage()">Log In</button>
        <button class="btn btn-primary" type="button" onclick="showMessage()">Book a Call</button>
      </div>
    </div>
  </header>

  <section class="hero" id="home">
    <div class="container hero-inner">
      <div>
        <div class="eyebrow">Trusted growth partner</div>
        <h1>Build smarter. Grow faster. Scale with confidence.</h1>
        <p>
          We help modern businesses simplify operations, sharpen strategy, and create sustainable
          momentum through measurable execution.
        </p>

        <div class="hero-actions">
          <button class="btn btn-primary" type="button" onclick="showMessage()">Get Started</button>
          <button class="btn btn-secondary" type="button" onclick="showMessage()">Talk to an Expert</button>
        </div>

        <div class="hero-stats">
          <div class="stat">
            <strong>320%</strong>
            <span>Average ROI</span>
          </div>
          <div class="stat">
            <strong>150+</strong>
            <span>Businesses helped</span>
          </div>
          <div class="stat">
            <strong>12 yrs</strong>
            <span>Industry experience</span>
          </div>
        </div>
      </div>

      <div class="hero-card">
        <div class="mini-panel">
          <h3>Revenue Growth</h3>
          <div class="metric">+$2.4M</div>
        </div>

        <div class="mini-list">
          <div class="mini-item">
            <span>Qualified leads</span>
            <strong>+48%</strong>
          </div>
          <div class="mini-item">
            <span>Conversion rate</span>
            <strong>+31%</strong>
          </div>
          <div class="mini-item">
            <span>Client retention</span>
            <strong>96%</strong>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="services">
    <div class="container">
      <div class="section-header">
        <h2>Business services built for performance</h2>
        <p>
          We combine strategic guidance, operational clarity, and practical execution so your team can
          focus on what matters most: growth.
        </p>
      </div>

      <div class="services-grid">
        <div class="service-card">
          <div class="icon">01</div>
          <h3>Strategy Consulting</h3>
          <p>
            Align your business goals, market position, and long-term roadmap with a clear plan for action.
          </p>
        </div>

        <div class="service-card">
          <div class="icon">02</div>
          <h3>Marketing Systems</h3>
          <p>
            Improve acquisition, retention, and conversion with performance-driven campaigns and smarter funnels.
          </p>
        </div>

        <div class="service-card">
          <div class="icon">03</div>
          <h3>Operational Excellence</h3>
          <p>
            Remove bottlenecks, streamline workflows, and create the systems needed to scale smoothly and reliably.
          </p>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="about">
    <div class="container about-wrap">
      <div class="about-box">
        <h3>We turn complexity into clarity.</h3>
        <p>
          From planning to execution, we help businesses focus on sustainable growth with measurable
          systems that improve confidence, efficiency, and outcomes.
        </p>

        <ul class="check-list">
          <li><span class="check">✓</span> Strategic guidance built around your goals</li>
          <li><span class="check">✓</span> Clear communication and measurable milestones</li>
          <li><span class="check">✓</span> Practical execution for long-term business health</li>
        </ul>
      </div>

      <div class="about-panel">
        <h3>Performance Snapshot</h3>

        <div class="progress-item">
          <div class="progress-top">
            <span>Growth planning</span>
            <span>92%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 92%;"></div>
          </div>
        </div>

        <div class="progress-item">
          <div class="progress-top">
            <span>Customer acquisition</span>
            <span>86%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 86%;"></div>
          </div>
        </div>

        <div class="progress-item">
          <div class="progress-top">
            <span>Operational efficiency</span>
            <span>94%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 94%;"></div>
          </div>
        </div>

        <div class="progress-item">
          <div class="progress-top">
            <span>Retention strategy</span>
            <span>89%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 89%;"></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="testimonials">
    <div class="container">
      <div class="section-header">
        <h2>What our clients say</h2>
        <p>
          Trusted by founders, executives, and teams that need clarity, momentum, and measurable results.
        </p>
      </div>

      <div class="testimonials-grid">
        <div class="testimonial">
          <div class="stars">★★★★★</div>
          <p>
            “Their strategic approach gave us clarity on where to focus and how to scale without unnecessary complexity.”
          </p>
          <div class="person">
            <div class="avatar">AM</div>
            <div>
              <h4>Alicia Moore</h4>
              <span>COO, Meridian Labs</span>
            </div>
          </div>
        </div>

        <div class="testimonial">
          <div class="stars">★★★★★</div>
          <p>
            “The team identified our biggest bottlenecks and helped us improve both performance and client experience.”
          </p>
          <div class="person">
            <div class="avatar">JT</div>
            <div>
              <h4>James Taylor</h4>
              <span>Founder, Summit Works</span>
            </div>
          </div>
        </div>

        <div class="testimonial">
          <div class="stars">★★★★★</div>
          <p>
            “Their guidance helped us refine our offer, increase pipeline quality, and improve retention across the board.”
          </p>
          <div class="person">
            <div class="avatar">LR</div>
            <div>
              <h4>Leah Reed</h4>
              <span>VP Growth, Harbor & Co.</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="contact">
    <div class="container">
      <div class="cta">
        <div>
          <h2>Ready to grow smarter?</h2>
          <p>Let’s build a strategy that creates momentum and delivers measurable results.</p>
        </div>

        <button class="btn btn-primary" type="button" onclick="showMessage()">Schedule a Consultation</button>
      </div>
    </div>
  </section>

  <footer>
    <div class="container footer-inner">
      <div class="logo">NORTH<span>STAR</span></div>
      <div class="footer-links">
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </div>
      <div>© 2026 Northstar Business Solutions</div>
    </div>
  </footer>

  <script>
    function showMessage() {
      alert("Thanks for your interest. We’ll be in touch soon.");
    }
  </script>
</body>
</html># website