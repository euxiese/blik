[blik-studio_1.html](https://github.com/user-attachments/files/27136229/blik-studio_1.html)

<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Блик — контент-студия</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --cream: #F5F0E8;
    --cream-dark: #EDE6D6;
    --warm-beige: #D4C4A8;
    --sand: #C4A882;
    --sand-dark: #A8895E;
    --charcoal: #2A2520;
    --mid: #6B5E50;
    --light-mid: #9B8E80;
    --white: #FDFAF5;
    --font-display: 'Cormorant Garamond', Georgia, serif;
    --font-body: 'Jost', sans-serif;
  }

  html { scroll-behavior: smooth; }
  body { background: var(--cream); color: var(--charcoal); font-family: var(--font-body); font-weight: 300; line-height: 1.7; overflow-x: hidden; }
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--cream); }
  ::-webkit-scrollbar-thumb { background: var(--sand); border-radius: 2px; }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.4rem 4rem;
    background: rgba(245,240,232,0.94);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(196,168,130,0.2);
  }
  .nav-logo { font-family: var(--font-display); font-size: 1.6rem; font-weight: 400; letter-spacing: 0.15em; text-transform: uppercase; color: var(--charcoal); text-decoration: none; }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a { font-size: 0.98rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--mid); text-decoration: none; transition: color 0.2s; }
  .nav-links a:hover { color: var(--charcoal); }
  .nav-cta { font-size: 0.98rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--white); background: var(--charcoal); padding: 0.65rem 1.5rem; text-decoration: none; transition: background 0.2s; }
  .nav-cta:hover { background: var(--sand-dark); }

  /* HERO */
  #hero { min-height: 100vh; display: grid; grid-template-columns: 1fr 1fr; padding-top: 72px; }
  .hero-left { display: flex; flex-direction: column; justify-content: center; padding: 5rem 4rem 5rem 4rem; }
  .hero-label { font-size: 0.94rem; letter-spacing: 0.22em; text-transform: uppercase; color: var(--sand-dark); margin-bottom: 2rem; display: flex; align-items: center; gap: 1rem; }
  .hero-label::before { content: ''; display: block; width: 2rem; height: 1px; background: var(--sand-dark); }
  .hero-title { font-family: var(--font-display); font-size: clamp(3.5rem, 5vw, 5.8rem); font-weight: 300; line-height: 1.05; color: var(--charcoal); margin-bottom: 2rem; }
  .hero-title em { font-style: italic; color: var(--sand-dark); }
  .hero-sub { font-size: 1.22rem; font-weight: 300; color: var(--mid); max-width: 38ch; margin-bottom: 3rem; line-height: 1.85; }
  .hero-actions { display: flex; gap: 1.2rem; align-items: center; }
  .btn-primary { display: inline-block; font-family: var(--font-body); font-size: 0.97rem; font-weight: 400; letter-spacing: 0.14em; text-transform: uppercase; color: var(--white); background: var(--charcoal); padding: 1rem 2.2rem; text-decoration: none; transition: background 0.25s, transform 0.2s; }
  .btn-primary:hover { background: var(--sand-dark); transform: translateY(-1px); }
  .btn-secondary { display: inline-block; font-size: 0.97rem; font-weight: 400; letter-spacing: 0.14em; text-transform: uppercase; color: var(--mid); text-decoration: none; border-bottom: 1px solid var(--warm-beige); padding-bottom: 2px; transition: color 0.2s, border-color 0.2s; }
  .btn-secondary:hover { color: var(--charcoal); border-color: var(--charcoal); }

  .hero-right { position: relative; overflow: hidden; background: var(--charcoal); }
  .hero-right img { width: 100%; height: 100%; object-fit: cover; display: block; opacity: 0.88; }
  .hero-right-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(42,37,32,0.25) 0%, rgba(42,37,32,0.05) 100%);
    pointer-events: none;
  }
  .hero-stats {
    position: absolute; bottom: 0; left: 0; right: 0;
    display: flex;
    background: rgba(245,240,232,0.93);
    backdrop-filter: blur(10px);
    border-top: 1px solid rgba(196,168,130,0.3);
  }
  .stat { flex: 1; text-align: center; padding: 1.4rem 1rem; border-right: 1px solid rgba(196,168,130,0.3); }
  .stat:last-child { border-right: none; }
  .stat-num { font-family: var(--font-display); font-size: 2rem; font-weight: 300; color: var(--charcoal); display: block; line-height: 1; margin-bottom: 0.25rem; }
  .stat-label { font-size: 0.85rem; letter-spacing: 0.14em; text-transform: uppercase; color: var(--light-mid); }

  /* SECTIONS */
  section { padding: 7rem 4rem; }
  .section-label { font-size: 0.87rem; letter-spacing: 0.22em; text-transform: uppercase; color: var(--sand-dark); margin-bottom: 1rem; display: flex; align-items: center; gap: 0.8rem; }
  .section-label::before { content: ''; display: block; width: 1.5rem; height: 1px; background: var(--sand-dark); }
  .section-title { font-family: var(--font-display); font-size: clamp(2.2rem, 3.5vw, 3.5rem); font-weight: 300; line-height: 1.1; color: var(--charcoal); margin-bottom: 1.5rem; }
  .section-title em { font-style: italic; color: var(--sand-dark); }

  /* ABOUT */
  #about { background: var(--white); display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: center; }
  .about-text p { color: var(--mid); margin-bottom: 1.2rem; font-size: 1.19rem; line-height: 1.85; }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }
  .about-card { background: var(--cream); padding: 1.8rem; border-top: 2px solid var(--warm-beige); transition: border-color 0.2s, transform 0.2s; }
  .about-card:hover { border-color: var(--sand-dark); transform: translateY(-2px); }
  .about-card-num { font-family: var(--font-display); font-size: 2.2rem; font-weight: 300; color: var(--warm-beige); line-height: 1; margin-bottom: 0.8rem; }
  .about-card h4 { font-size: 1rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: var(--charcoal); margin-bottom: 0.5rem; }
  .about-card p { font-size: 1.05rem; color: var(--mid); line-height: 1.65; }

  /* STUDIO PHOTOS STRIP */
  #studio-strip { padding: 0; background: var(--charcoal); }
  .strip-grid { display: grid; grid-template-columns: 2fr 1fr 1fr; height: 480px; }
  .strip-item { overflow: hidden; position: relative; }
  .strip-item img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform 0.6s ease; filter: brightness(0.9); }
  .strip-item:hover img { transform: scale(1.04); filter: brightness(1); }
  .strip-item-label {
    position: absolute; bottom: 1.5rem; left: 1.5rem;
    font-size: 0.87rem; letter-spacing: 0.16em; text-transform: uppercase;
    color: rgba(245,240,232,0.7);
    background: rgba(42,37,32,0.5);
    backdrop-filter: blur(6px);
    padding: 0.35rem 0.8rem;
  }

  /* SERVICES */
  #services { background: var(--cream); }
  .services-header { margin-bottom: 3.5rem; }
  .services-tabs { display: flex; gap: 0.4rem; margin-bottom: 3rem; }
  .tab-btn { font-family: var(--font-body); font-size: 0.95rem; font-weight: 400; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.65rem 1.5rem; border: 1px solid var(--warm-beige); background: transparent; color: var(--mid); cursor: pointer; transition: all 0.2s; }
  .tab-btn.active, .tab-btn:hover { background: var(--charcoal); color: var(--white); border-color: var(--charcoal); }
  .tab-content { display: none; }
  .tab-content.active { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }
  .tab-brands-inner { grid-column: span 3; display: grid; grid-template-columns: repeat(3,1fr); gap: 1.5rem; }

  .service-card { background: var(--white); overflow: hidden; position: relative; transition: transform 0.25s, box-shadow 0.25s; }
  .service-card:hover { transform: translateY(-4px); box-shadow: 0 16px 48px rgba(42,37,32,0.1); }
  .service-card.featured { background: var(--charcoal); }
  .service-card-img { width: 100%; height: 200px; object-fit: cover; display: block; filter: brightness(0.92); transition: filter 0.3s; }
  .service-card:hover .service-card-img { filter: brightness(1); }
  .service-card-body { padding: 1.8rem 1.8rem 2rem; }
  .service-badge { display: inline-block; font-size: 0.83rem; letter-spacing: 0.12em; text-transform: uppercase; background: var(--sand); color: var(--white); padding: 0.25rem 0.65rem; margin-bottom: 0.8rem; }
  .service-card h3 { font-family: var(--font-display); font-size: 1.5rem; font-weight: 400; margin-bottom: 0.7rem; color: var(--charcoal); }
  .service-card.featured h3 { color: var(--cream); }
  .service-card p { font-size: 1.05rem; color: var(--mid); line-height: 1.7; margin-bottom: 1.5rem; }
  .service-card.featured p { color: rgba(212,196,168,0.85); }
  .service-price { font-family: var(--font-display); font-size: 1.5rem; font-weight: 300; color: var(--charcoal); display: block; margin-bottom: 0.2rem; }
  .service-card.featured .service-price { color: var(--cream); }
  .service-price-note { font-size: 0.93rem; color: var(--light-mid); letter-spacing: 0.08em; }
  .service-card.featured .service-price-note { color: var(--warm-beige); opacity: 0.7; }

  /* PACKAGES */
  .package-card { border: 1px solid var(--warm-beige); background: var(--white); overflow: hidden; transition: border-color 0.2s, transform 0.2s; }
  .package-card:hover { border-color: var(--sand-dark); transform: translateY(-3px); }
  .package-card.highlight { border-color: var(--charcoal); background: var(--charcoal); }
  .package-card-img { width: 100%; height: 160px; object-fit: cover; display: block; filter: brightness(0.88); }
  .package-card-body { padding: 1.8rem; }
  .package-name { font-size: 0.93rem; font-weight: 500; letter-spacing: 0.16em; text-transform: uppercase; color: var(--sand-dark); margin-bottom: 0.4rem; }
  .package-card.highlight .package-name { color: var(--warm-beige); }
  .package-price { font-family: var(--font-display); font-size: 2.4rem; font-weight: 300; color: var(--charcoal); line-height: 1; margin-bottom: 0.25rem; }
  .package-card.highlight .package-price { color: var(--cream); }
  .package-price-note { font-size: 0.95rem; color: var(--light-mid); margin-bottom: 1.4rem; }
  .package-card.highlight .package-price-note { color: rgba(212,196,168,0.7); }
  .package-features { list-style: none; margin-bottom: 1.8rem; }
  .package-features li { font-size: 1.05rem; color: var(--mid); padding: 0.45rem 0; border-bottom: 1px solid var(--cream-dark); display: flex; gap: 0.6rem; }
  .package-card.highlight .package-features li { color: rgba(212,196,168,0.85); border-color: rgba(196,168,130,0.15); }
  .package-features li::before { content: '—'; color: var(--sand); font-size: 0.93rem; flex-shrink: 0; margin-top: 2px; }
  .btn-package { display: block; text-align: center; font-size: 0.95rem; font-weight: 400; letter-spacing: 0.12em; text-transform: uppercase; padding: 0.85rem; border: 1px solid var(--charcoal); color: var(--charcoal); text-decoration: none; transition: all 0.2s; }
  .btn-package:hover { background: var(--charcoal); color: var(--white); }
  .package-card.highlight .btn-package { border-color: var(--warm-beige); color: var(--cream); }
  .package-card.highlight .btn-package:hover { background: var(--warm-beige); color: var(--charcoal); }

  /* PROCESS */
  #process { background: var(--cream-dark); }
  .process-steps { display: grid; grid-template-columns: repeat(5, 1fr); gap: 0; margin-top: 4rem; position: relative; }
  .process-steps::before { content: ''; position: absolute; top: 2rem; left: 2rem; right: 2rem; height: 1px; background: var(--warm-beige); z-index: 0; }
  .step { position: relative; z-index: 1; padding: 0 1.2rem; text-align: center; }
  .step-dot { width: 4rem; height: 4rem; border-radius: 50%; background: var(--cream-dark); border: 1px solid var(--warm-beige); display: flex; align-items: center; justify-content: center; margin: 0 auto 1.5rem; font-family: var(--font-display); font-size: 1.3rem; font-weight: 300; color: var(--charcoal); transition: all 0.25s; }
  .step:hover .step-dot { background: var(--charcoal); color: var(--cream); border-color: var(--charcoal); }
  .step h4 { font-size: 0.99rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: var(--charcoal); margin-bottom: 0.6rem; }
  .step p { font-size: 1.02rem; color: var(--mid); line-height: 1.65; }
  .step p em { font-style: normal; font-weight: 500; color: var(--sand-dark); }
  .sla-block { display: grid; grid-template-columns: repeat(3, 1fr); gap: 2px; margin-top: 4rem; background: var(--warm-beige); }
  .sla-item { background: var(--white); padding: 2.2rem; text-align: center; }
  .sla-time { font-family: var(--font-display); font-size: 2.8rem; font-weight: 300; color: var(--charcoal); line-height: 1; display: block; margin-bottom: 0.3rem; }
  .sla-label { font-size: 0.93rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--light-mid); }

  /* PORTFOLIO */
  #portfolio { background: var(--white); }
  .portfolio-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 2.5rem; }
  .portfolio-grid { display: grid; grid-template-columns: repeat(12, 1fr); grid-auto-rows: 260px; gap: 1rem; }
  .portfolio-item { overflow: hidden; position: relative; cursor: pointer; background: var(--cream-dark); }
  .portfolio-item:nth-child(1) { grid-column: span 7; grid-row: span 2; }
  .portfolio-item:nth-child(2) { grid-column: span 5; }
  .portfolio-item:nth-child(3) { grid-column: span 5; }
  .portfolio-item:nth-child(4) { grid-column: span 4; }
  .portfolio-item:nth-child(5) { grid-column: span 4; }
  .portfolio-item:nth-child(6) { grid-column: span 4; }
  .portfolio-item img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform 0.6s ease; filter: brightness(0.9); }
  .portfolio-item:hover img { transform: scale(1.06); filter: brightness(1); }
  .portfolio-overlay { position: absolute; inset: 0; background: linear-gradient(to top, rgba(42,37,32,0.82) 0%, transparent 55%); display: flex; flex-direction: column; justify-content: flex-end; padding: 1.5rem; opacity: 0; transition: opacity 0.3s; }
  .portfolio-item:hover .portfolio-overlay { opacity: 1; }
  .portfolio-overlay h4 { font-family: var(--font-display); font-size: 1.3rem; font-weight: 300; color: var(--cream); margin-bottom: 0.2rem; }
  .portfolio-overlay p { font-size: 0.93rem; letter-spacing: 0.1em; text-transform: uppercase; color: var(--warm-beige); }

  /* EQUIPMENT */
  #equipment { background: var(--charcoal); color: var(--cream); }
  #equipment .section-label { color: var(--warm-beige); }
  #equipment .section-label::before { background: var(--warm-beige); }
  #equipment .section-title { color: var(--cream); }
  #equipment .section-title em { color: var(--sand); }
  .equipment-layout { display: grid; grid-template-columns: 1fr 2fr; gap: 5rem; align-items: start; margin-top: 3rem; }
  .equipment-photo { width: 100%; aspect-ratio: 4/5; object-fit: cover; display: block; opacity: 0.85; }
  .equipment-right { display: flex; flex-direction: column; gap: 2.5rem; }
  .equipment-intro p { font-size: 1.15rem; color: var(--warm-beige); line-height: 1.85; margin-bottom: 0.8rem; }
  .equipment-cols { display: grid; grid-template-columns: repeat(3, 1fr); gap: 2rem; }
  .equipment-col h4 { font-size: 0.87rem; font-weight: 500; letter-spacing: 0.16em; text-transform: uppercase; color: var(--sand); margin-bottom: 1.2rem; padding-bottom: 0.8rem; border-bottom: 1px solid rgba(196,168,130,0.2); }
  .equipment-col ul { list-style: none; }
  .equipment-col li { font-size: 1.05rem; color: var(--warm-beige); padding: 0.45rem 0; border-bottom: 1px solid rgba(196,168,130,0.08); display: flex; align-items: center; gap: 0.6rem; }
  .equipment-col li::before { content: '·'; color: var(--sand); font-size: 1.2rem; line-height: 0; }

  /* BOOKING */
  #booking { background: var(--cream); }
  .booking-layout { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start; }
  .booking-info h3 { font-family: var(--font-display); font-size: 1.15rem; font-weight: 400; color: var(--charcoal); margin-bottom: 1rem; margin-top: 2.2rem; }
  .booking-info h3:first-child { margin-top: 0; }
  .booking-info li { font-size: 1.09rem; color: var(--mid); line-height: 1.75; padding: 0.4rem 0; display: flex; gap: 0.8rem; }
  .booking-info ul { list-style: none; }
  .booking-info li::before { content: '—'; color: var(--sand); flex-shrink: 0; }
  .booking-form { background: var(--white); padding: 3rem; }
  .booking-form h3 { font-family: var(--font-display); font-size: 1.9rem; font-weight: 300; color: var(--charcoal); margin-bottom: 2rem; }
  .form-group { margin-bottom: 1.4rem; }
  .form-group label { display: block; font-size: 0.87rem; font-weight: 500; letter-spacing: 0.13em; text-transform: uppercase; color: var(--mid); margin-bottom: 0.5rem; }
  .form-group input, .form-group select, .form-group textarea { width: 100%; background: var(--cream); border: 1px solid var(--warm-beige); padding: 0.9rem 1rem; font-family: var(--font-body); font-size: 1.11rem; font-weight: 300; color: var(--charcoal); outline: none; transition: border-color 0.2s; appearance: none; }
  .form-group input:focus, .form-group select:focus, .form-group textarea:focus { border-color: var(--sand-dark); }
  .form-group textarea { height: 96px; resize: vertical; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .form-note { font-size: 0.95rem; color: var(--light-mid); margin-bottom: 1.4rem; line-height: 1.65; }
  .btn-submit { width: 100%; background: var(--charcoal); color: var(--white); border: none; padding: 1.1rem; font-family: var(--font-body); font-size: 0.97rem; font-weight: 400; letter-spacing: 0.16em; text-transform: uppercase; cursor: pointer; transition: background 0.2s; }
  .btn-submit:hover { background: var(--sand-dark); }

  /* CONTACTS */
  #contacts { background: var(--cream-dark); padding: 6rem 4rem; }
  .contacts-layout { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 3rem; margin-top: 3rem; }
  .contact-block h4 { font-size: 0.87rem; font-weight: 500; letter-spacing: 0.16em; text-transform: uppercase; color: var(--sand-dark); margin-bottom: 1rem; padding-bottom: 0.8rem; border-bottom: 1px solid var(--warm-beige); }
  .contact-block p, .contact-block a { font-size: 1.13rem; color: var(--mid); text-decoration: none; display: block; line-height: 1.85; transition: color 0.2s; }
  .contact-block a:hover { color: var(--charcoal); }
  .map-block { grid-column: span 2; overflow: hidden; }
  .map-block iframe { width: 100%; height: 220px; border: none; display: block; filter: sepia(20%) contrast(0.9); }

  /* FOOTER */
  footer { background: var(--charcoal); padding: 2rem 4rem; display: flex; align-items: center; justify-content: space-between; }
  .footer-logo { font-family: var(--font-display); font-size: 1.2rem; font-weight: 300; letter-spacing: 0.2em; text-transform: uppercase; color: var(--cream); }
  .footer-copy { font-size: 0.91rem; letter-spacing: 0.08em; color: var(--light-mid); }
  .footer-social { display: flex; gap: 1.5rem; }
  .footer-social a { font-size: 0.93rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--warm-beige); text-decoration: none; transition: color 0.2s; }
  .footer-social a:hover { color: var(--cream); }

  /* FADE IN */
  .fade-in { opacity: 0; transform: translateY(20px); transition: opacity 0.65s ease, transform 0.65s ease; }
  .fade-in.visible { opacity: 1; transform: translateY(0); }

  /* RESPONSIVE */
  @media (max-width: 1024px) {
    nav { padding: 1.2rem 2rem; }
    section { padding: 5rem 2rem; }
    #hero { grid-template-columns: 1fr; }
    .hero-right { height: 60vw; }
    .hero-left { padding: 5rem 2rem 3rem; }
    #about { grid-template-columns: 1fr; gap: 3rem; }
    .strip-grid { grid-template-columns: 1fr 1fr; height: 320px; }
    .strip-item:last-child { display: none; }
    .tab-content.active, .tab-brands-inner { grid-template-columns: 1fr 1fr; }
    .process-steps { grid-template-columns: 1fr 1fr; gap: 2rem; }
    .process-steps::before { display: none; }
    .sla-block { grid-template-columns: 1fr; }
    .portfolio-grid { grid-template-columns: 1fr 1fr; grid-auto-rows: 220px; }
    .portfolio-item { grid-column: span 1 !important; grid-row: span 1 !important; }
    .equipment-layout { grid-template-columns: 1fr; gap: 2.5rem; }
    .equipment-photo { aspect-ratio: 16/7; }
    .booking-layout { grid-template-columns: 1fr; gap: 3rem; }
    .contacts-layout { grid-template-columns: 1fr 1fr; }
    .map-block { grid-column: span 2; }
    footer { flex-direction: column; gap: 1rem; text-align: center; }
    #contacts { padding: 4rem 2rem; }
    .form-row { grid-template-columns: 1fr; }
  }
  @media (max-width: 640px) {
    nav { padding: 1rem 1.2rem; }
    .nav-links { display: none; }
    section { padding: 4rem 1.2rem; }
    .hero-left { padding: 4rem 1.2rem 2rem; }
    .about-grid { grid-template-columns: 1fr; }
    .strip-grid { grid-template-columns: 1fr; height: 260px; }
    .tab-content.active, .tab-brands-inner, .equipment-cols, .contacts-layout { grid-template-columns: 1fr; }
    .map-block { grid-column: span 1; }
    .portfolio-grid { grid-auto-rows: 180px; }
    #contacts { padding: 3rem 1.2rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#hero" class="nav-logo">Блик</a>
  <ul class="nav-links">
    <li><a href="#about">Студия</a></li>
    <li><a href="#services">Услуги</a></li>
    <li><a href="#process">Процесс</a></li>
    <li><a href="#portfolio">Портфолио</a></li>
    <li><a href="#contacts">Контакты</a></li>
  </ul>
  <a href="#booking" class="nav-cta">Забронировать</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <span class="hero-label">Контент-студия · Барнаул</span>
    <h1 class="hero-title">Визуал,<br>который<br><em>продаёт</em></h1>
    <p class="hero-sub">Каталожная и предметная съёмка, карточки для маркетплейсов, Reels и бизнес-портреты — всё под ключ, без лишней суеты.</p>
    <div class="hero-actions">
      <a href="#booking" class="btn-primary">Забронировать съёмку</a>
      <a href="#services" class="btn-secondary">Смотреть услуги</a>
    </div>
  </div>
  <div class="hero-right">
    <!-- Unsplash: studio light setup by Alex Mertz -->
    <img src="https://images.unsplash.com/photo-1542038784456-1ea8e935640e?w=1200&q=85&fit=crop&crop=center" alt="Съёмочная студия" loading="eager">
    <div class="hero-right-overlay"></div>
    <div class="hero-stats">
      <div class="stat"><span class="stat-num">T+1</span><span class="stat-label">Исходники</span></div>
      <div class="stat"><span class="stat-num">T+3</span><span class="stat-label">Готовые фото</span></div>
      <div class="stat"><span class="stat-num">T+7</span><span class="stat-label">Reels и видео</span></div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-text fade-in">
    <span class="section-label">О студии</span>
    <h2 class="section-title">Студия,<br>где всё <em>уже готово</em></h2>
    <p>Мы — контент-студия полного цикла с фокусом на бренды, маркетплейсы и товарный контент. Берём на себя всё: от брифа и раскадровки до готовых файлов.</p>
    <p>Вы фокусируетесь на результате, а не на организации.</p>
    <p>Работаем по прозрачным пакетам и фиксированным срокам. Без сюрпризов.</p>
  </div>
  <div class="about-grid fade-in">
    <div class="about-card">
      <div class="about-card-num">01</div>
      <h4>Фокус на МП</h4>
      <p>Знаем требования WB, Ozon, Яндекс.Маркет. Снимаем в соответствии со стандартами площадок.</p>
    </div>
    <div class="about-card">
      <div class="about-card-num">02</div>
      <h4>Всё под одной крышей</h4>
      <p>Студия + фото/видео команда + монтаж + стилист/визажист опционно.</p>
    </div>
    <div class="about-card">
      <div class="about-card-num">03</div>
      <h4>Экономия времени</h4>
      <p>Бриф → раскадровка → согласование визуала. Площадка готовится под ваш запрос.</p>
    </div>
    <div class="about-card">
      <div class="about-card-num">04</div>
      <h4>SLA и онлайн-бронь</h4>
      <p>Фиксируем сроки, работаем с предоплатой. Прозрачные условия для каждого клиента.</p>
    </div>
  </div>
</section>

<!-- STUDIO PHOTO STRIP -->
<div id="studio-strip">
  <div class="strip-grid">
    <div class="strip-item">
      <img src="https://images.unsplash.com/photo-1598300042247-d088f8ab3a91?w=1200&q=85&fit=crop&crop=center" alt="Студия — общий план" loading="lazy">
      <span class="strip-item-label">Съёмочный зал</span>
    </div>
    <div class="strip-item">
      <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=700&q=85&fit=crop&crop=center" alt="Предметная зона" loading="lazy">
      <span class="strip-item-label">Предметная зона</span>
    </div>
    <div class="strip-item">
      <img src="https://images.unsplash.com/photo-1471341971476-ae15ff5dd4ea?w=700&q=85&fit=crop&crop=center" alt="Световое оборудование" loading="lazy">
      <span class="strip-item-label">Свет и техника</span>
    </div>
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="services-header fade-in">
    <span class="section-label">Услуги и цены</span>
    <h2 class="section-title">Выберите <em>формат</em></h2>
  </div>

  <div class="services-tabs">
    <button class="tab-btn active" onclick="switchTab(this,'rent')">Аренда студии</button>
    <button class="tab-btn" onclick="switchTab(this,'brands')">Для брендов</button>
    <button class="tab-btn" onclick="switchTab(this,'mp')">Для маркетплейсов</button>
  </div>

  <!-- RENT -->
  <div class="tab-content active" id="tab-rent">
    <div class="service-card fade-in">
      <img class="service-card-img" src="https://images.unsplash.com/photo-1609645879126-44e7e2aa4624?w=800&q=80&fit=crop&crop=center" alt="Зал с циклорамой" loading="lazy">
      <div class="service-card-body">
        <h3>Зал с циклорамой</h3>
        <p>Полноценная съёмочная площадка с интерьерным уголком. 3 импульсных источника + базовые насадки включены в стоимость.</p>
        <span class="service-price">1 800 ₽</span>
        <span class="service-price-note">в час · стартовая цена</span>
      </div>
    </div>
    <div class="service-card fade-in">
      <img class="service-card-img" src="https://images.unsplash.com/photo-1540575467063-178a50c2df87?w=800&q=80&fit=crop&crop=top" alt="Пространство студии" loading="lazy">
      <div class="service-card-body">
        <h3>Пространство студии</h3>
        <p>Уютная атмосфера, продуманные зоны и освещение — всё создано так, чтобы вы могли сосредоточиться на съёмке, а не на технических мелочах.</p>
        <span class="service-price">Онлайн-бронь</span>
        <span class="service-price-note">с предоплатой</span>
      </div>
    </div>
    <div class="service-card fade-in">
      <img class="service-card-img" src="https://images.unsplash.com/photo-1520549233664-03f65c1d1327?w=800&q=80&fit=crop&crop=center" alt="Абонемент" loading="lazy">
      <div class="service-card-body">
        <h3>Абонемент 10 часов</h3>
        <p>Пакет для фотографов и регулярных клиентов. Срок действия 30 дней. Приоритетные слоты и гибкое бронирование.</p>
        <span class="service-price">−10%</span>
        <span class="service-price-note">от стоимости аренды</span>
      </div>
    </div>
  </div>

  <!-- BRANDS -->
  <div class="tab-content" id="tab-brands">
    <div class="tab-brands-inner">
      <div class="package-card fade-in">
        <img class="package-card-img" src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?w=600&q=80&fit=crop&crop=center" alt="S пакет" loading="lazy">
        <div class="package-card-body">
          <div class="package-name">S — Mini</div>
          <div class="package-price">~25 000 ₽</div>
          <div class="package-price-note">4 часа съёмки</div>
          <ul class="package-features">
            <li>До 50 фото + 4–5 Reels</li>
            <li>Базовый реквизит</li>
            <li>Раскадровка включена</li>
            <li>Исходники T+1</li>
          </ul>
          <a href="#booking" class="btn-package">Выбрать</a>
        </div>
      </div>
      <div class="package-card highlight fade-in">
        <img class="package-card-img" src="https://images.unsplash.com/photo-1531746020798-e6953c6e8e04?w=600&q=80&fit=crop&crop=center" alt="M пакет" loading="lazy" style="opacity:0.7;">
        <div class="package-card-body">
          <div class="package-name">M — Standard</div>
          <div class="package-price">~38 000 ₽</div>
          <div class="package-price-note">6 часов + визаж</div>
          <ul class="package-features">
            <li>До 80 фото + 8 Reels</li>
            <li>Визаж (1 образ)</li>
            <li>Расширенный реквизит</li>
            <li>Фото готовы за 2–3 дня</li>
          </ul>
          <a href="#booking" class="btn-package">Выбрать</a>
        </div>
      </div>
      <div class="package-card fade-in">
        <img class="package-card-img" src="https://images.unsplash.com/photo-1487412720507-e7ab37603c6f?w=600&q=80&fit=crop&crop=center" alt="L пакет" loading="lazy">
        <div class="package-card-body">
          <div class="package-name">L — Pro</div>
          <div class="package-price">~60 000 ₽</div>
          <div class="package-price-note">8 часов, полный пакет</div>
          <ul class="package-features">
            <li>До 120 фото + 12 Reels</li>
            <li>Бренд-ролик 30–45 сек</li>
            <li>Визаж + стилист</li>
            <li>Продвинутый свет</li>
          </ul>
          <a href="#booking" class="btn-package">Выбрать</a>
        </div>
      </div>
    </div>
  </div>

  <!-- MP -->
  <div class="tab-content" id="tab-mp">
    <div class="service-card fade-in">
      <img class="service-card-img" src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=800&q=80&fit=crop&crop=center" alt="1 ракурс товара" loading="lazy">
      <div class="service-card-body">
        <h3>1 ракурс товара</h3>
        <p>Предметная съёмка на белом, сером или чёрном фоне. Обтравка и тени по ТЗ маркетплейса.</p>
        <span class="service-price">500–700 ₽</span>
        <span class="service-price-note">за кадр, с ретушью</span>
      </div>
    </div>
    <div class="service-card featured fade-in">
      <img class="service-card-img" src="https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?w=800&q=80&fit=crop&crop=center" alt="7 ракурсов SKU" loading="lazy" style="opacity:0.75;">
      <div class="service-card-body">
        <span class="service-badge">Популярный</span>
        <h3>7 ракурсов / SKU</h3>
        <p>Полный набор карточки: главное фото + дополнительные ракурсы в едином стиле. Скидка за объём.</p>
        <span class="service-price">3 200–4 200 ₽</span>
        <span class="service-price-note">за товарную позицию</span>
      </div>
    </div>
    <div class="service-card fade-in">
      <img class="service-card-img" src="https://images.unsplash.com/photo-1611162617213-7d7a39e9b1d7?w=800&q=80&fit=crop&crop=center" alt="Видео карточка" loading="lazy">
      <div class="service-card-body">
        <h3>Видео-карточка / UGC</h3>
        <p>Короткий клип 15–30 сек для карточки товара. Пакеты: 5, 10 или 20 роликов.</p>
        <span class="service-price">1 500–3 000 ₽</span>
        <span class="service-price-note">за ролик</span>
      </div>
    </div>
  </div>
</section>

<!-- PROCESS -->
<section id="process">
  <div class="fade-in">
    <span class="section-label">Как мы работаем</span>
    <h2 class="section-title">От заявки до <em>готового файла</em></h2>
  </div>
  <div class="process-steps">
    <div class="step fade-in">
      <div class="step-dot">1</div>
      <h4>Заявка</h4>
      <p>Пишете в мессенджер или заполняете форму на сайте</p>
    </div>
    <div class="step fade-in">
      <div class="step-dot">2</div>
      <h4>Бриф</h4>
      <p>Совместно с менеджером заполняете бриф — понимаем, что <em>вам</em> нужно</p>
    </div>
    <div class="step fade-in">
      <div class="step-dot">3</div>
      <h4>Предоплата</h4>
      <p>Вносите 50% — дата и время закреплены за вами</p>
    </div>
    <div class="step fade-in">
      <div class="step-dot">4</div>
      <h4>Съёмка</h4>
      <p>Площадка готова под ваш запрос. Приходите — начинаем сразу</p>
    </div>
    <div class="step fade-in">
      <div class="step-dot">5</div>
      <h4>Сдача</h4>
      <p>Файлы в облако. Правки — за наш счёт при ошибке студии</p>
    </div>
  </div>
  <div class="sla-block fade-in">
    <div class="sla-item"><span class="sla-time">T+1</span><span class="sla-label">Исходники</span></div>
    <div class="sla-item"><span class="sla-time">T+2–3</span><span class="sla-label">Готовые фотографии</span></div>
    <div class="sla-item"><span class="sla-time">T+5–7</span><span class="sla-label">Reels и видео</span></div>
  </div>
</section>

<!-- PORTFOLIO -->
<section id="portfolio">
  <div class="portfolio-header fade-in">
    <div>
      <span class="section-label">Портфолио</span>
      <h2 class="section-title">Кейсы <em>студии</em></h2>
    </div>
    <a href="#booking" class="btn-secondary">Обсудить проект</a>
  </div>
  <div class="portfolio-grid">
    <div class="portfolio-item fade-in">
      <img src="https://images.unsplash.com/photo-1558769132-cb1aea458c5e?w=1400&q=85&fit=crop&crop=center" alt="Каталог одежды" loading="lazy">
      <div class="portfolio-overlay"><h4>Каталог одежды</h4><p>120 SKU · WB · 2 дня</p></div>
    </div>
    <div class="portfolio-item fade-in">
      <img src="https://images.unsplash.com/photo-1596462502278-27bfdc403348?w=800&q=85&fit=crop&crop=center" alt="Бьюти-бренд" loading="lazy">
      <div class="portfolio-overlay"><h4>Бьюти-бренд</h4><p>Предметка + Reels</p></div>
    </div>
    <div class="portfolio-item fade-in">
      <img src="https://images.unsplash.com/photo-1515562141207-7a88fb7ce338?w=800&q=85&fit=crop&crop=center" alt="Ювелирный каталог" loading="lazy">
      <div class="portfolio-overlay"><h4>Ювелирный каталог</h4><p>60 SKU · Ozon</p></div>
    </div>
    <div class="portfolio-item fade-in">
      <img src="https://images.unsplash.com/photo-1493663284031-b7e3aefcae8e?w=800&q=85&fit=crop&crop=center" alt="Декор для дома" loading="lazy">
      <div class="portfolio-overlay"><h4>Декор для дома</h4><p>Лайфстайл + каталог</p></div>
    </div>
    <div class="portfolio-item fade-in">
      <img src="https://images.unsplash.com/photo-1487530811176-3780de880c2d?w=800&q=85&fit=crop&crop=center" alt="Флористика" loading="lazy">
      <div class="portfolio-overlay"><h4>Сезонная кампания</h4><p>8 марта · Reels + фото</p></div>
    </div>
    <div class="portfolio-item fade-in">
      <img src="https://images.unsplash.com/photo-1582750433449-648ed127bb54?w=800&q=85&fit=crop&crop=center" alt="Бизнес-портрет" loading="lazy">
      <div class="portfolio-overlay"><h4>Бизнес-портреты</h4><p>Имиджевая съёмка + Reels</p></div>
    </div>
  </div>
</section>

<!-- EQUIPMENT -->
<section id="equipment">
  <span class="section-label">Оборудование</span>
  <h2 class="section-title">Инфраструктура<br><em>под любую задачу</em></h2>
  <div class="equipment-layout fade-in">
    <div>
      <img class="equipment-photo" src="https://images.unsplash.com/photo-1554048612-b6a482bc67e5?w=800&q=85&fit=crop&crop=center" alt="Световое оборудование студии" loading="lazy">
    </div>
    <div class="equipment-right">
      <div class="equipment-intro">
        <p>Мы адаптивны к любому виду контента — предметная съёмка, каталог, портрет, Reels, бизнес-видео.</p>
        <p>Стараемся сделать так, чтобы вы остались довольны результатом и захотели вернуться.</p>
      </div>
      <div class="equipment-cols">
        <div class="equipment-col">
          <h4>Свет</h4>
          <ul>
            <li>3 импульсных источника</li>
            <li>Октабокс</li>
            <li>Стрип-боксы</li>
            <li>Рефлекторы</li>
            <li>Постоянный свет</li>
            <li>Флаги белый/чёрный</li>
          </ul>
        </div>
        <div class="equipment-col">
          <h4>Площадка</h4>
          <ul>
            <li>Циклорама</li>
            <li>Предметная зона</li>
            <li>Интерьерный уголок</li>
            <li>Стойки на колёсах</li>
            <li>Синхронизаторы</li>
            <li>Гримёрная</li>
          </ul>
        </div>
        <div class="equipment-col">
          <h4>Фоны</h4>
          <ul>
            <li>Белый</li>
            <li>Серый</li>
            <li>Чёрный</li>
            <li>Текстурные фоны</li>
            <li>Подиумы и подставки</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- BOOKING -->
<section id="booking">
  <div class="booking-layout">
    <div class="booking-info fade-in">
      <span class="section-label">Бронирование</span>
      <h2 class="section-title">Запишитесь<br><em>онлайн</em></h2>
      <h3>Как проходит бронирование</h3>
      <ul>
        <li>Заполните форму или напишите в Telegram / WhatsApp</li>
        <li>Мы свяжемся в течение 2 часов и уточним детали</li>
        <li>Совместно с менеджером заполняете бриф — понимаем, что вам нужно</li>
        <li>Вносите предоплату 50% — дата закреплена</li>
      </ul>
      <h3>Правила студии</h3>
      <ul>
        <li>Бронь без предоплаты не удерживается</li>
        <li>1 перенос бесплатно при уведомлении ≥24 ч</li>
        <li>Опоздание более 15 мин включается в слот</li>
        <li>Не пришли без предупреждения — предоплата удерживается</li>
      </ul>
      <h3>Контакты</h3>
      <ul>
        <li>Telegram: @blik_studio</li>
        <li>WhatsApp: +7 929 499-32-34</li>
        <li>Барнаул, Загородная 129, 2 этаж, офис 1</li>
      </ul>
    </div>
    <div class="booking-form fade-in">
      <h3>Оставить заявку</h3>
      <div class="form-row">
        <div class="form-group">
          <label>Имя</label>
          <input type="text" placeholder="Как к вам обращаться">
        </div>
        <div class="form-group">
          <label>Телефон / Telegram</label>
          <input type="text" placeholder="+7 или @username">
        </div>
      </div>
      <div class="form-group">
        <label>Тип съёмки</label>
        <select>
          <option value="">Выберите формат</option>
          <option>Аренда студии</option>
          <option>Контент-день для бренда S</option>
          <option>Контент-день для бренда M</option>
          <option>Контент-день для бренда L</option>
          <option>Каталожная / МП (покадрово)</option>
          <option>Бизнес-портрет</option>
          <option>Другое</option>
        </select>
      </div>
      <div class="form-row">
        <div class="form-group">
          <label>Желаемая дата</label>
          <input type="date">
        </div>
        <div class="form-group">
          <label>Количество SKU / часов</label>
          <input type="text" placeholder="Примерно">
        </div>
      </div>
      <div class="form-group">
        <label>Комментарий</label>
        <textarea placeholder="Ниша, товар, особые пожелания..."></textarea>
      </div>
      <p class="form-note">Мы свяжемся с вами в течение 2 часов в рабочее время. Отправляя форму, вы соглашаетесь с правилами студии.</p>
      <button class="btn-submit" type="button">Отправить заявку</button>
    </div>
  </div>
</section>

<!-- CONTACTS -->
<section id="contacts">
  <span class="section-label">Контакты</span>
  <h2 class="section-title fade-in">Найдите <em>нас</em></h2>
  <div class="contacts-layout">
    <div class="contact-block fade-in">
      <h4>Адрес</h4>
      <p>Барнаул</p>
      <p>Загородная, 129</p>
      <p>2 этаж, офис 1</p>
      <p style="margin-top:0.8rem;font-size:0.75rem;color:var(--light-mid);">Пн–Пт: 9:00–21:00<br>Сб–Вс: 10:00–20:00</p>
    </div>
    <div class="contact-block fade-in">
      <h4>Связь</h4>
      <a href="https://t.me/blik_studio">Telegram: @blik_studio</a>
      <a href="tel:+79294993234">+7 929 499-32-34</a>
      <p style="margin-top:0.5rem;font-size:0.75rem;color:var(--light-mid);">Макс. время ответа — 2 часа</p>
    </div>
    <div class="contact-block fade-in">
      <h4>Соцсети</h4>
      <a href="#">Instagram</a>
      <a href="#">ВКонтакте</a>
      <a href="#">Telegram-канал</a>
      <a href="#">MAX</a>
    </div>
    <div class="map-block fade-in">
      <iframe
        src="https://yandex.ru/map-widget/v1/?ll=83.704541%2C53.345614&z=15&pt=83.704541,53.345614,pm2rdm"
        allowfullscreen>
      </iframe>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <span class="footer-logo">Блик</span>
  <span class="footer-copy">© 2025 Контент-студия Блик · Барнаул</span>
  <div class="footer-social">
    <a href="#">IG</a>
    <a href="#">VK</a>
    <a href="#">TG</a>
  </div>
</footer>

<script>
  function switchTab(btn, tab) {
    document.querySelectorAll('.tab-content').forEach(el => el.classList.remove('active'));
    document.querySelectorAll('.tab-btn').forEach(el => el.classList.remove('active'));
    document.getElementById('tab-' + tab).classList.add('active');
    btn.classList.add('active');
  }

  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.08 });

  document.querySelectorAll('.fade-in').forEach((el, i) => {
    el.style.transitionDelay = (i % 5 * 0.08) + 's';
    observer.observe(el);
  });
</script>
</body>
</html>
