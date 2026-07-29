<!doctype html>
<html lang="en">
  <head>

    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Arena Animation — GTB Nagar, Delhi</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />

   
    <link
      href="https://fonts.googleapis.com/css2?family=Anton&family=JetBrains+Mono:wght@400;500;600&family=Inter:wght@400;500;600;700;800&display=swap"
      rel="stylesheet"
    />

    <style>
   
    
      :root {
        --ink: #0b0f0c;
        --ink-soft: #141813;
        --ink-line: #262c26;
        --paper: #f2efe4;
        --paper-dim: #e7e3d4;
        --chroma: #3dff7a;
        --chroma-dim: #1f8f4a;
        --amber: #ff8a3d;
        --text-hi: #f4f5f1;
        --text-dim: #9da79e;
        --text-ink-dim: #5c6960;
      }
 * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }

    
      html {
        scroll-behavior: smooth;
      }

      
      body {
        font-family: "Inter", Arial, sans-serif;
        background: var(--ink);
        color: var(--text-hi);
        line-height: 1.55;
        -webkit-font-smoothing: antialiased;
      }


      img {
        max-width: 100%;
        display: block;
      }

      
      a {
        text-decoration: none;
        color: inherit;
      }


      ul {
        list-style: none;
      }

    
      .container-wrapper {
        padding: 0 6vw;
      }


      .heading-display {
        font-family: "Anton", sans-serif;
        text-transform: uppercase;
        letter-spacing: 0.5px;
        margin-bottom: 20px;
      }

    
      .text-monospace {
        font-family: "JetBrains Mono", monospace;
      }

      section {
        padding: 100px 6vw;
        position: relative;
      }

      ::selection {
        background: var(--chroma);
        color: var(--ink);
      }

      :focus-visible {
        outline: 2px solid var(--chroma);
        outline-offset: 3px;
      }

    

      .scrubber {
     
        position: sticky;
        top: 0;
        z-index: 100;
        background: var(--ink);
        border-bottom: 1px solid var(--ink-line);
        display: flex;
        align-items: center;
        gap: 14px;
        padding: 10px 6vw;
        font-size: 11px;
      }

      .scrubber .timecode-label {
        color: var(--chroma);
        white-space: nowrap;
      }

    
      .scrubber .timeline-track {
        position: relative;
        flex: 1;
        height: 2px;
        background: var(--ink-line);
      }

    
      .scrubber .timeline-track .timeline-fill {
        position: absolute;
        left: 0;
        top: 0;
        height: 100%;
        width: 6%;
        background: var(--chroma);
      }

    
      .scrubber .timeline-track .timeline-head {
        position: absolute;
        top: 50%;
        left: 6%;
        transform: translate(-50%, -50%);
        width: 10px;
        height: 10px;
        border-radius: 50%;
        background: var(--chroma);
        box-shadow: 0 0 0 4px rgba(61, 255, 122, 0.15);
      }

    
      .scrubber .timeline-marks {
        position: absolute;
        inset: 0;
        display: flex;
        justify-content: space-between;
        align-items: center;
      }

      .scrubber .timeline-marks span {
        width: 1px;
        height: 6px;
        background: var(--ink-line);
      }

        .scrubber .clip-name {
        color: var(--text-dim);
        white-space: nowrap;
        min-width: 110px;
        text-align: right;
      }

   
      nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 26px 6vw 18px;
      }

   
      .logo-container {
        display: flex;
        align-items: baseline;
        gap: 8px;
      }

      
      .logo-container .brand-mark {
        color: var(--chroma);
        font-size: 22px;
      }

      
      .logo-text {
        font-size: 20px;
        letter-spacing: 1px;
      }

      
      .logo-text small {
        display: block;
        font-family: "JetBrains Mono", monospace;
        font-size: 9px;
        letter-spacing: 3px;
        color: var(--text-dim);
        font-weight: 400;
        text-transform: none;
      }

      
      .navigation-links {
        display: flex;
        gap: 36px;
        font-size: 13px;
        letter-spacing: 1.5px;
        text-transform: uppercase;
      
      }

      
      .navigation-links a {
        color: var(--text-dim);
        transition: color 0.2s;
        position: relative;
      }

      
      .navigation-links a:hover,
      .navigation-links a.active {
        color: var(--text-hi);
      }

      
      .navigation-links a.active::after {
        content: "";
        position: absolute;
        left: 0;
        right: 0;
        bottom: -6px;
        height: 2px;
        background: var(--chroma);
      }

      
      .phone-call-button {
        border: 1px solid var(--ink-line);
        color: var(--text-hi);
        padding: 11px 20px;
        font-size: 13px;
        letter-spacing: 0.5px;
        border-radius: 2px;
        transition: all 0.2s;
      }

      
      .phone-call-button:hover {
        border-color: var(--chroma);
        color: var(--chroma);
      }

      .hero-section {
        padding-top: 70px;
        padding-bottom: 60px;
      }

      
      .hero-layout-grid {
        display: grid;
        grid-template-columns: 1.5fr 1fr;
        gap: 60px;
        align-items: end;
      
      }

   

         .recording-dot {
        width: 8px;
        height: 8px;
        border-radius: 50%;
        background: var(--amber);
        animation: blink-animation 1.6s infinite;
      }

      
      @media (prefers-reduced-motion: reduce) {
        .recording-dot {
          animation: none;
        }
      }

      
      @keyframes blink-animation {
        0%,
        100% {
          opacity: 1;
        }
        50% {
          opacity: 0.25;
        }
      }

      h1.primary-headline {
        font-size: clamp(46px, 6.4vw, 92px);
        line-height: 0.94;
        color: var(--text-hi);
      }

      h1.primary-headline .accent-text {
        color: var(--chroma);
      }

      .hero-subtitle {
        margin-top: 26px;
        max-width: 480px;
        color: var(--text-dim);
        font-size: 16px;
      }

      .hero-statistics-line {
        margin-top: 8px;
        font-size: 16px;
        color: var(--text-hi);
      }

      .hero-statistics-line b {
        color: var(--chroma);
        font-family: "JetBrains Mono", monospace;
        font-weight: 600;
      }

      .hero-call-to-actions {
        display: flex;
        gap: 14px;
        margin-top: 34px;
        flex-wrap: wrap;
      }

      .button-solid {
        background: var(--chroma);
        color: var(--ink);
        padding: 15px 28px;
        font-weight: 700;
        font-size: 14px;
        letter-spacing: 0.5px;
        border-radius: 2px;
        display: inline-flex;
        align-items: center;
        gap: 8px;
        transition: transform 0.15s ease;
      }

      .button-solid:hover {
        transform: translateY(-2px);
      }

      .button-ghost {
        border: 1px solid var(--ink-line);
        color: var(--text-hi);
        padding: 15px 26px;
        font-size: 14px;
        letter-spacing: 0.5px;
        border-radius: 2px;
        transition:
          border-color 0.2s,
          color 0.2s;
      }

      .button-ghost:hover {
        border-color: var(--chroma);
        color: var(--chroma);
      }

      .enquiry-form-card {
        background: var(--ink-soft);
        border: 1px solid var(--ink-line);
        border-radius: 3px;
        padding: 0;
        overflow: hidden;
      }

      .enquiry-form-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 16px 22px;
        border-bottom: 1px solid var(--ink-line);
        font-family: "JetBrains Mono", monospace;
        font-size: 11px;
        letter-spacing: 1.5px;
        color: var(--text-dim);
      }

      .enquiry-form-header .recording-status {
        color: var(--chroma);
        display: flex;
        align-items: center;
        gap: 6px;
      }

      .enquiry-form-header .recording-status::before {
        content: "";
        width: 6px;
        height: 6px;
        border-radius: 50%;
        background: var(--chroma);
      }

      .enquiry-form-card form {
        padding: 22px;
      }

      .enquiry-form-card label {
        display: block;
        font-family: "JetBrains Mono", monospace;
        font-size: 10px;
        letter-spacing: 1.5px;
        color: var(--text-dim);
        text-transform: uppercase;
        margin-bottom: 6px;
        margin-top: 16px;
      }

      .enquiry-form-card label:first-of-type {
        margin-top: 0;
      } 

      .enquiry-form-card select {
        width: 100%;
        padding: 12px 12px;
        border: 1px solid var(--ink-line);
        border-radius: 2px;
        font-size: 14px;
        color: var(--text-hi);
        background: var(--ink);
        font-family: "Inter", sans-serif;
      }

      .enquiry-form-card input:focus,
      .enquiry-form-card select:focus {
        border-color: var(--chroma);
      }

      .enquiry-form-card input::placeholder {
        color: #566058;
      }

      .enquiry-form-card button {
        width: 100%;
        background: var(--chroma);
        color: var(--ink);
        border: none;
        padding: 15px;
        font-weight: 700;
        font-size: 13px;
        letter-spacing: 1.5px;
        border-radius: 2px;
        cursor: pointer;
        margin-top: 22px;
        transition: filter 0.15s;
      }

      .enquiry-form-card button:hover {
        filter: brightness(1.08);
      }

      .section-header {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        margin-bottom: 50px;
        gap: 20px;
        flex-wrap: wrap;
      }

   

      .section-heading {
        font-size: clamp(30px, 3.6vw, 46px);
        color: var(--text-hi);
      }

  

      .paper-theme {
        background: var(--paper);
        color: var(--ink);
      }

      .paper-theme .text-dim {
        color: var(--text-ink-dim);
      }

      .paper-theme .section-heading {
        color: var(--ink);
      }

   

      .programs-card-grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 1px;
        background: var(--ink-line);
        border: 1px solid var(--ink-line);
      }

      .program-card {
        background: var(--ink);
        padding: 36px 32px 40px;
        position: relative;
        overflow: hidden;
        border: 1px solid var(--ink-line);
        transition: border-color 0.3s ease;
        text-align: left;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: flex-start;
        min-height: 320px;
      
      }
       
      .program-card:hover {
        border-color: var(--chroma);
      }

      .program-card--tall {
        min-height: 380px;
      }

      .program-card-background {
        position: absolute;
        inset: 0;
        background-size: cover;
        background-position: center;
        filter: brightness(0.55) saturate(1.1);
        z-index: 0;
        transition:
          filter 0.4s ease,
          transform 0.4s ease;
      }

      .program-card:hover .program-card-background {
        filter: brightness(0.7) saturate(1.2);
        transform: scale(1.05);
      }

      .program-card .frame-number,
      .program-card h4,
      .program-card p,
      .program-card .sprocket-hole {
        position: relative;
        z-index: 1;
      }



      .program-card h4 {
        font-size: 20px;
        margin: 6px 0 10px;
        color: var(--text-hi);
        text-shadow: 0 1px 8px rgba(0, 0, 0, 0.6);
        line-height: 1.25;
      }

      .program-card p {
        font-size: 14px;
        color: var(--text-dim);
        text-shadow: 0 1px 6px rgba(0, 0, 0, 0.5);
        line-height: 1.6;
      }

      .program-card .sprocket-hole {
        position: absolute;
        top: 32px;
        right: 30px;
        width: 8px;
        height: 8px;
        border-radius: 50%;
        border: 1px solid var(--ink-line);
        box-shadow: 0 0 4px rgba(0, 0, 0, 0.4);
      }

      .recruiters-logo-grid {
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        align-items: center;
        justify-items: center;
        row-gap: 56px;
        column-gap: 32px;
      }
      .recruiter-logo-wrapper {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
      }

      .recruiter-logo-wrapper img {
        max-width: 140px;
        max-height: 60px;
        width: auto;
        height: auto;
        object-fit: contain;
      }

      .events-card-grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 32px 28px;
        text-align: center;
      }

      .event-item {
        display: flex;
        flex-direction: column;
        gap: 0;
      }

      .event-item img {
        width: 100%;
        aspect-ratio: 16/10;
        object-fit: cover;
        display: block;
        border-radius: 0;
      }

      .event-item h2 {
        font-size: 18px;
        font-weight: 700;
        color: var(--text-hi);
        margin-top: 18px;
        margin-bottom: 10px;
        line-height: 1.3;
      }

      .event-item p {
        font-size: 13.5px;
        color: var(--text-dim);
        line-height: 1.65;
        margin: 0;
      }

      .alumni-testimonial-card {
        border: 1px solid var(--ink-line);
        border-radius: 4px;
        padding: 40px;
        display: flex;
        gap: 36px;
        align-items: center;
        max-width: 880px;
        margin: 0 auto;
      }

      .alumni-play-thumb {
        width: 130px;
        height: 130px;
        flex-shrink: 0;
        border-radius: 3px;
        position: relative;
        background: linear-gradient(135deg, var(--ink-soft), var(--ink));
        border: 1px solid var(--ink-line);
        display: flex;
        align-items: center;
        justify-content: center;
      }

      .alumni-play-thumb::before {
        content: "\25B6";
        color: var(--chroma);
        font-size: 22px;
      }

      .alumni-testimonial-card h4 {
        font-size: 18px;
      }

      .alumni-testimonial-card .alumni-role {
        font-family: "JetBrains Mono", monospace;
        font-size: 11px;
        color: var(--chroma);
        letter-spacing: 1px;
        margin: 6px 0 14px;
        text-transform: uppercase;
      }

      .alumni-testimonial-card p.alumni-quote {
        font-size: 15px;
        color: var(--text-dim);
      }

      .alumni-navigation {
        display: flex;
        justify-content: center;
        gap: 10px;
        margin-top: 26px;
      }

      .alumni-navigation button {
        width: 36px;
        height: 36px;
        border-radius: 50%;
        border: 1px solid var(--ink-line);
        background: transparent;
        color: var(--text-hi);
        cursor: pointer;
        transition: border-color 0.2s;
      }

      .alumni-navigation button:hover {
        border-color: var(--chroma);
        color: var(--chroma);
      }

      .branch-location-grid {
        display: grid;
        grid-template-columns: 0.9fr 1.1fr;
        gap: 50px;
        align-items: start;
      }

      .branch-info-block h3 {
        font-size: 22px;
        margin-bottom: 16px;
        letter-spacing: 0.5px;
        color: var(--ink);
      }

      .branch-info-block p {
        font-size: 14.5px;
        color: var(--text-ink-dim);
        margin-bottom: 10px;
      }

      .branch-info-block .branch-phone {
        font-family: "JetBrains Mono", monospace;
        font-weight: 600;
        color: var(--ink);
        margin-bottom: 22px;
        font-size: 14px;
      }

      .map-embed-container {
        width: 100%;
        height: 320px;
        border-radius: 3px;
        overflow: hidden;
        border: 1px solid var(--ink-line);
        filter: grayscale(0.3) contrast(1.05);
      }

      .map-embed-container iframe {
        width: 100%;
        height: 100%;
        border: 0;
      }

      
      .final-call-to-action {
        text-align: center;
        padding: 130px 6vw 100px;
      }


      .final-call-to-action h2 {
        font-size: clamp(38px, 6vw, 76px);
        line-height: 1.02;
        color: var(--text-hi);
      }

      .final-call-to-action h2 .accent-text {
        color: var(--chroma);
      }

      .final-call-to-action .cta-button-group {
        margin-top: 40px;
        display: flex;
        justify-content: center;
        gap: 16px;
        flex-wrap: wrap;
      }

      
      footer {
        border-top: 1px solid var(--ink-line);
        padding: 26px 6vw;
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-size: 12px;
        color: var(--text-dim);
        font-family: "JetBrains Mono", monospace;
        flex-wrap: wrap; 
        gap: 10px;
      }

      footer a {
        color: var(--chroma);
      }

      .reveal {
        opacity: 1;
      }
@media (max-width: 900px) {
        .hero-layout-grid {
          grid-template-columns: 1fr;
        }

        .programs-card-grid {
          grid-template-columns: repeat(2, 1fr);
        }

        .events-card-grid {
          grid-template-columns: repeat(2, 1fr);
        }

        .recruiters-logo-grid {
          grid-template-columns: repeat(3, 1fr);
        }

        .branch-location-grid {
          grid-template-columns: 1fr;
        }

        .navigation-links {
          display: none;
        }

        .alumni-testimonial-card {
          flex-direction: column;
          text-align: center;
        }

        .scrubber .clip-name {
          display: none;
        }

        section {
          padding: 70px 6vw;
        }
      }

      @media (max-width: 560px) {
        .recruiters-logo-grid {
          grid-template-columns: repeat(2, 1fr);
          row-gap: 40px;
        }
      }
    </style>
  </head>
  <body>
    <nav>
      <div class="logo-container">
        <span class="brand-mark"></span>
        <img
          src="images/arena-animation.webp"
          height="70px"
          alt="Arena Animation logo"
        />
      </div>

      <ul class="navigation-links">
        <li><a href="#" class="active">Home</a></li>
        <mnu><a href="programs">Courses</a></mnu>
        <li><a href="#events">Gallery</a></li>
        <li><a href="#recruiters">Recruiters</a></li>
        <li><a href="#branches">Contact</a></li>
      </ul>

      <a href="tel:9811398844" class="phone-call-button text-monospace"
        >9811 398 844</a
      >
    </nav>

    <section class="hero-section">
      <div class="hero-layout-grid">
        <div class="hero-text-content">
          <div class="eyebrow-container">
            <span class="recording-dot"></span>
            
          </div>

          <h1 class="primary-headline heading-display">
            Your career<br />is still in<br /><span class="accent-text"
              >rough cut.</span
            >
          </h1>

          <p class="hero-subtitle">
            Animation, VFX, game design and UI/UX — taught the way studios
            actually work, from first storyboard to final render.
          </p>

\          <p class="hero-statistics-line">
            About <b>5.2L</b> animators &amp; game designers will be hired
            across India's animation, VFX and digital sector.
          </p>

          <div class="hero-call-to-actions">
            <a href="tel:9811398844" class="button-solid"
              >Call 9811 398 844 →</a
            >
            <a href="#enquiry" class="button-ghost">Apply now</a>
          </div>
        </div>

        <div class="enquiry-form-card" id="enquiry">
          <div class="enquiry-form-header">
            <span>ENQUIRY / TAKE 01</span>
            <span class="recording-status">recording</span>
          </div>

          <form>
            <label for="enquiry-name">Name</label>
            <input
              id="enquiry-name"
              type="text"
              placeholder="Your full name"
              required
            />

            <label for="enquiry-phone">Contact number</label>
            <input
              id="enquiry-phone"
              type="tel"
              placeholder="10-digit mobile number"
              required
            />

            <label for="enquiry-course">Course</label>
            <select id="enquiry-course">
              <option>Animation &amp; VFX</option>
              <option>VFX Course</option>
              <option>Game Design Course</option>
              <option>Advance UI/UX Design</option>
            </select>

            <label for="enquiry-location">Location</label>
            <select id="enquiry-location">
              <option>Delhi NCR</option>
              <option>Outside Delhi NCR</option>
            </select>

            <button type="submit">Get a callback</button>
          </form>
        </div>
      </div>
    </section>

    <section id="programs">
      <div class="section-header reveal">
        <div>
        
          <h2 class="section-heading heading-display">What you'll train in</h2>
    
      <div class="programs-card-grid">
        <div class="program-card reveal">
          <div
            class="program-card-background"
            style="
              background-image: url(&quot;images/amateurs-waterfall-5229807_1920.jpg&quot;);
            "
          ></div>
          <span class="sprocket-hole"></span>
          
          <h4>Animation &amp; VFX</h4>
          <p>
            2D and 3D animation built around a real production pipeline — from
            keyframes to a portfolio reel studios recognise.
          </p>
        </div>

        <div class="program-card program-card--tall reveal">
          <div
            class="program-card-background"
            style="
              background-image: url(&quot;images/heckimg-tree-7619791_1920.jpg&quot;);
            "
          ></div>
          <span class="sprocket-hole"></span>
       
          <h4>VFX Course</h4>
          <p>
            Compositing, simulation and blockbuster-grade effects work, taught
            on the same tools feature-film studios run.
          </p>
        </div>

        <div class="program-card reveal">
          <div
            class="program-card-background"
            style="
              background-image: url(&quot;images/ylvers-the-ugly-swamp-433688_1920.jpg&quot;);
            "
          ></div>
          <span class="sprocket-hole"></span>
    
          <h4>Game Design</h4>
          <p>
            Concept to publish — mechanics, level design and the pipeline behind
            shipping a playable game.
          </p>
        </div>

        <div class="program-card reveal">
          <div
            class="program-card-background"
            style="
              background-image: url(&quot;images/himmelstraeume-flower-7543035_1920.jpg&quot;);
            "
          ></div>
          <span class="sprocket-hole"></span>
         
          <h4>Advance UI/UX Design</h4>
          <p>
            Graphic and web design fundamentals built into interface systems you
            can defend in a design review.
          </p>
        </div>
      </div>
    </section>

    <section id="recruiters" class="paper-theme">
      <div class="section-header reveal">
        <div>
        
          <h2 class="section-heading heading-display">Our top recruiters</h2>
        </div>
    
      </div>

      <!-- Recruiter logo grid -->
      <div class="recruiters-logo-grid">
        <div class="recruiter-logo-wrapper">
          <img src="images/aje.png" alt="Aaj Tak"/>
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/sony.png" alt="Sony" />
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/zeenew.png" alt="Zee News" />
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/Dharma.webp" alt="Dharma Productions" />
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/air.png" alt="Air Asia" />
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/Colors_TV.webp" alt="Colors Viacom18" />
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/star.png" alt="Starbucks" />
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/time.png" alt="Times Network" />
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/dlf.png" alt="DLF" />
        </div>
        <div class="recruiter-logo-wrapper">
          <img src="images/zara.png" alt="Zara" />
        </div>
      </div>
    </section>

    <section id="events">
      <div class="section-header reveal">
        <div>
          <span class="section-index">03 / Events</span>
          <h2 class="section-heading heading-display">Studen happenings</h2>
        </div>
    
      </div>

      <div class="events-card-grid">
        <!-- Event 1 -->
        <div class="event-item reveal">
          <img
            src="https://picsum.photos/seed/event1/600/375"
            alt="Industry Workshop"
            loading="lazy"
          />
          <h2>Industry Workshop</h2>
          <p>
            A full-day masterclass led by senior artists from DNEG and
            Framestore — covering compositing, look development and the
            realities of a production pipeline.
          </p>
        </div>

       <div class="event-item reveal">
          <img
            src="https://picsum.photos/seed/event2/600/375"
            alt="Student Film Festival"
            loading="lazy"
          />
          <h2>Student Film Festival</h2>
          <p>
            Our annual showcase where final-year students premiere their short
            films in front of industry jurors and recruiters.
          </p>
        </div>

        <div class="event-item reveal">
          <img
            src="https://picsum.photos/seed/event3/600/375"
            alt="Studio Tour — Red Chillies"
            loading="lazy"
          />
          <h2>Studio Tour</h2>
          <p>
            Behind-the-scenes visit to Red Chillies VFX studio — students
            observed a live compositing session and interacted with the
            production team.
          </p>
        </div>

        <div class="event-item reveal">
          <img
            src="https://picsum.photos/seed/event4/600/375"
            alt="Portfolio Review Day"
            loading="lazy"
          />
          <h2>Portfolio Review Day</h2>
          <p>
            One-on-one feedback sessions with art directors from top studios.
            Each student left with a clear roadmap to improve their demo reel.
          </p>
        </div>
      </div>
    </section>

    <section class="paper-theme" style="text-align: center">
      <div
        class="section-header reveal"
        style="
          justify-content: center;
          text-align: center;
          flex-direction: column;
          align-items: center;
        "
      >
        <span class="section-index">04 / Alumni</span>
        <h2 class="section-heading heading-display">Playback</h2>
      </div>

      <div class="alumni-testimonial-card reveal">
        <div class="alumni-play-thumb"></div>
        <div>
          <h4>Dhruv Modi</h4>
          <div class="alumni-role">Game design graduate</div>
          <p class="alumni-quote">
            &ldquo;Arena Animation played an important role in building my
            career — my faculty backed me every step of the way.&rdquo;
          </p>
        </div>
      </div>

      <div class="alumni-navigation">
        <button aria-label="Previous">&lsaquo;</button>
        <button aria-label="Next">&rsaquo;</button>
      </div>
    </section>

    <section class="paper-theme" id="branches">
      <div class="section-header reveal">
        <div>
          <span class="section-index">05 / Visit</span>
          <h2 class="section-heading heading-display">North DU campus</h2>
        </div>
      </div>

      <div class="branch-location-grid">
        <!-- Address block -->
        <div class="branch-info-block reveal">
          <h3>GTB Nagar, Delhi</h3>
          <p>
            38, 1st floor, Kingsway Camp, near GTB Nagar Metro Station Gate No.
            1, above Kapoor Abhushan, GTB Nagar, Delhi.
          </p>
          <p class="branch-phone">9811 398 844 &middot; 7827 437 052</p>
          <a
            href="tel:9811398844"
            class="button-ghost"
            style="color: var(--ink); border-color: var(--ink-line)"
          >
            Call this campus &rarr;
          </a>
        </div>

        <div class="map-embed-container reveal">
          <iframe
            src="https://www.google.com/maps?q=GTB+Nagar+Metro+Station+Delhi&output=embed"
            loading="lazy"
            allowfullscreen
          >
          </iframe>
        </div>
      </div>
    </section>

    <section class="final-call-to-action">
      <span class="section-index reveal">06 / Cut to</span>
      <h2 class="reveal heading-display">
        Ready for a career<br />you'd actually
        <span class="accent-text">watch back.</span>
      </h2>
      <div class="cta-button-group reveal">
        <a href="tel:9811398844" class="button-solid">Call 9811 398 844</a>
        <a href="#enquiry" class="button-ghost">Apply now</a>
      </div>
    </section>

    <footer></footer>
  </body>
</html>
