<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Test Bazar — উচ্চমাধ্যমিক পরীক্ষার প্রস্তুতি</title>
<link href="https://fonts.googleapis.com/css2?family=Tiro+Bangla:ital@0;1&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --green: #1a7a4a;
    --green-light: #2aad68;
    --green-pale: #e8f7ef;
    --saffron: #e8730a;
    --saffron-light: #fdf0e4;
    --dark: #0f1a14;
    --mid: #2c4035;
    --text: #1c2e24;
    --muted: #5a7a66;
    --border: #c5dccb;
    --white: #f8fdf9;
    --card-bg: #ffffff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Syne', sans-serif;
    background: var(--white);
    color: var(--text);
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1rem 2rem;
    background: rgba(248,253,249,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
  }

  .logo {
    font-size: 1.4rem; font-weight: 800; color: var(--green);
    letter-spacing: -0.5px;
  }
  .logo span { color: var(--saffron); }

  nav a {
    text-decoration: none; color: var(--mid); font-size: 0.85rem;
    font-weight: 600; margin-left: 1.5rem; transition: color 0.2s;
  }
  nav a:hover { color: var(--green); }

  .nav-cta {
    background: var(--green); color: white !important;
    padding: 0.45rem 1.1rem; border-radius: 6px;
  }
  .nav-cta:hover { background: var(--green-light) !important; color: white !important; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 7rem 2rem 4rem;
    position: relative;
    overflow: hidden;
    background: linear-gradient(160deg, #f0faf4 0%, #fdf6ee 100%);
  }

  .hero::before {
    content: '';
    position: absolute; top: -100px; right: -150px;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(26,122,74,0.08) 0%, transparent 70%);
    border-radius: 50%;
  }

  .hero::after {
    content: '';
    position: absolute; bottom: -80px; left: -100px;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(232,115,10,0.07) 0%, transparent 70%);
    border-radius: 50%;
  }

  .hero-inner {
    max-width: 1100px; margin: 0 auto; width: 100%;
    display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center;
    position: relative; z-index: 1;
  }

  .hero-tag {
    display: inline-block;
    background: var(--green-pale); color: var(--green);
    font-size: 0.75rem; font-weight: 700; letter-spacing: 1px;
    padding: 0.3rem 0.9rem; border-radius: 20px;
    border: 1px solid rgba(26,122,74,0.2);
    margin-bottom: 1.2rem;
    text-transform: uppercase;
    animation: fadeUp 0.6s ease both;
  }

  h1 {
    font-family: 'Tiro Bangla', serif;
    font-size: clamp(2.2rem, 4vw, 3.2rem);
    line-height: 1.25;
    color: var(--dark);
    margin-bottom: 1rem;
    animation: fadeUp 0.6s 0.1s ease both;
  }

  h1 em {
    font-style: normal;
    color: var(--green);
    position: relative;
  }

  h1 em::after {
    content: '';
    position: absolute; bottom: 2px; left: 0; right: 0; height: 3px;
    background: var(--saffron); border-radius: 2px;
    opacity: 0.7;
  }

  .hero-sub {
    font-family: 'Tiro Bangla', serif;
    font-size: 1.05rem; color: var(--muted); line-height: 1.7;
    margin-bottom: 2rem;
    animation: fadeUp 0.6s 0.2s ease both;
  }

  .hero-btns {
    display: flex; gap: 1rem; flex-wrap: wrap;
    animation: fadeUp 0.6s 0.3s ease both;
  }

  .btn-primary {
    background: var(--green); color: white;
    padding: 0.8rem 1.8rem; border-radius: 8px;
    font-size: 0.95rem; font-weight: 700; cursor: pointer;
    border: none; text-decoration: none; display: inline-block;
    transition: all 0.2s; box-shadow: 0 4px 15px rgba(26,122,74,0.3);
    font-family: 'Tiro Bangla', serif;
  }
  .btn-primary:hover { background: var(--green-light); transform: translateY(-2px); box-shadow: 0 6px 20px rgba(26,122,74,0.4); }

  .btn-secondary {
    background: white; color: var(--green);
    padding: 0.8rem 1.8rem; border-radius: 8px;
    font-size: 0.95rem; font-weight: 700; cursor: pointer;
    border: 2px solid var(--green); text-decoration: none; display: inline-block;
    transition: all 0.2s;
    font-family: 'Tiro Bangla', serif;
  }
  .btn-secondary:hover { background: var(--green-pale); transform: translateY(-2px); }

  /* HERO CARD */
  .hero-card {
    background: white;
    border-radius: 16px;
    padding: 1.8rem;
    box-shadow: 0 20px 60px rgba(15,26,20,0.12);
    border: 1px solid var(--border);
    animation: fadeUp 0.6s 0.2s ease both;
  }

  .card-header {
    display: flex; align-items: center; gap: 0.6rem;
    margin-bottom: 1.2rem;
  }
  .card-dot { width: 10px; height: 10px; border-radius: 50%; }

  .quiz-title {
    font-family: 'Tiro Bangla', serif;
    font-size: 1rem; font-weight: 600; color: var(--dark);
    margin-bottom: 1rem;
  }

  .quiz-q {
    background: var(--green-pale);
    border-left: 3px solid var(--green);
    padding: 0.7rem 0.9rem; border-radius: 0 8px 8px 0;
    font-family: 'Tiro Bangla', serif;
    font-size: 0.9rem; color: var(--text); margin-bottom: 0.8rem;
  }

  .quiz-opts { display: flex; flex-direction: column; gap: 0.5rem; }

  .quiz-opt {
    padding: 0.5rem 0.9rem; border-radius: 6px;
    font-family: 'Tiro Bangla', serif;
    font-size: 0.85rem; cursor: pointer;
    border: 1.5px solid var(--border);
    transition: all 0.15s; color: var(--text);
    background: white;
  }
  .quiz-opt:hover { border-color: var(--green); background: var(--green-pale); }
  .quiz-opt.correct { border-color: var(--green); background: var(--green-pale); color: var(--green); font-weight: 600; }
  .quiz-opt.wrong { border-color: #dc3545; background: #fdf0f0; color: #dc3545; }

  .quiz-timer {
    display: flex; align-items: center; justify-content: space-between;
    margin-top: 1rem; font-size: 0.8rem; color: var(--muted);
  }

  .timer-bar {
    flex: 1; height: 4px; background: var(--border); border-radius: 2px; margin: 0 0.7rem;
    overflow: hidden;
  }
  .timer-fill {
    height: 100%; background: var(--green); border-radius: 2px;
    width: 65%; animation: shrink 30s linear infinite;
  }

  /* STATS */
  .stats {
    background: var(--dark); padding: 3rem 2rem;
  }
  .stats-inner {
    max-width: 1100px; margin: 0 auto;
    display: grid; grid-template-columns: repeat(4, 1fr); gap: 2rem; text-align: center;
  }
  .stat-num {
    font-size: 2.2rem; font-weight: 800; color: var(--green-light);
  }
  .stat-label {
    font-family: 'Tiro Bangla', serif;
    font-size: 0.9rem; color: rgba(255,255,255,0.6); margin-top: 0.3rem;
  }

  /* SUBJECTS */
  .subjects { padding: 5rem 2rem; background: white; }
  .section-inner { max-width: 1100px; margin: 0 auto; }

  .section-label {
    font-size: 0.75rem; font-weight: 700; letter-spacing: 2px;
    text-transform: uppercase; color: var(--saffron);
    margin-bottom: 0.5rem;
  }
  h2 {
    font-family: 'Tiro Bangla', serif;
    font-size: clamp(1.6rem, 3vw, 2.2rem); color: var(--dark);
    margin-bottom: 0.5rem;
  }
  .section-sub {
    font-family: 'Tiro Bangla', serif;
    color: var(--muted); font-size: 1rem; margin-bottom: 2.5rem;
  }

  .subjects-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(180px, 1fr)); gap: 1rem;
  }

  .subj-card {
    border: 1.5px solid var(--border); border-radius: 12px;
    padding: 1.2rem 1rem; text-align: center;
    transition: all 0.2s; cursor: pointer;
    background: white;
  }
  .subj-card:hover { border-color: var(--green); background: var(--green-pale); transform: translateY(-3px); box-shadow: 0 8px 25px rgba(26,122,74,0.1); }

  .subj-icon { font-size: 2rem; margin-bottom: 0.6rem; }
  .subj-name {
    font-family: 'Tiro Bangla', serif;
    font-size: 0.95rem; font-weight: 600; color: var(--dark);
  }
  .subj-count { font-size: 0.75rem; color: var(--muted); margin-top: 0.2rem; }

  /* PRICING */
  .pricing { padding: 5rem 2rem; background: linear-gradient(180deg, #f0faf4 0%, white 100%); }

  .pricing-grid {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem;
    max-width: 900px; margin: 0 auto;
  }

  .price-card {
    background: white; border: 1.5px solid var(--border);
    border-radius: 16px; padding: 2rem 1.5rem;
    position: relative; transition: all 0.2s;
  }
  .price-card:hover { box-shadow: 0 12px 40px rgba(15,26,20,0.1); transform: translateY(-4px); }
  .price-card.popular {
    border-color: var(--green);
    box-shadow: 0 8px 30px rgba(26,122,74,0.15);
  }

  .popular-badge {
    position: absolute; top: -12px; left: 50%; transform: translateX(-50%);
    background: var(--green); color: white;
    font-size: 0.7rem; font-weight: 700; padding: 0.25rem 0.9rem;
    border-radius: 20px; letter-spacing: 0.5px; white-space: nowrap;
  }

  .price-plan {
    font-family: 'Tiro Bangla', serif;
    font-size: 1rem; font-weight: 600; color: var(--muted); margin-bottom: 0.5rem;
  }
  .price-amount {
    font-size: 2.5rem; font-weight: 800; color: var(--dark);
    line-height: 1;
  }
  .price-amount span { font-size: 1rem; font-weight: 400; color: var(--muted); }
  .price-divider { border: none; border-top: 1px solid var(--border); margin: 1.2rem 0; }

  .price-feat {
    font-family: 'Tiro Bangla', serif;
    font-size: 0.88rem; color: var(--text); padding: 0.35rem 0;
    display: flex; align-items: center; gap: 0.5rem;
  }
  .price-feat::before { content: "✓"; color: var(--green); font-weight: 700; flex-shrink: 0; }
  .price-feat.no::before { content: "✗"; color: #ccc; }
  .price-feat.no { color: var(--muted); }

  .price-btn {
    width: 100%; margin-top: 1.5rem;
    padding: 0.75rem; border-radius: 8px;
    font-family: 'Tiro Bangla', serif;
    font-size: 0.95rem; font-weight: 600; cursor: pointer;
    border: 2px solid var(--green); transition: all 0.2s;
  }
  .price-btn.filled { background: var(--green); color: white; }
  .price-btn.filled:hover { background: var(--green-light); }
  .price-btn.outline { background: white; color: var(--green); }
  .price-btn.outline:hover { background: var(--green-pale); }

  /* REGISTRATION */
  .register {
    padding: 5rem 2rem;
    background: var(--dark);
  }

  .register-inner {
    max-width: 560px; margin: 0 auto; text-align: center;
  }

  .register h2 { color: white; }
  .register .section-sub { color: rgba(255,255,255,0.5); }

  .form-wrap {
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.1);
    border-radius: 16px; padding: 2rem;
    margin-top: 2rem; text-align: left;
  }

  .form-group { margin-bottom: 1.1rem; }

  label {
    display: block; font-family: 'Tiro Bangla', serif;
    font-size: 0.85rem; color: rgba(255,255,255,0.7);
    margin-bottom: 0.4rem;
  }

  input, select {
    width: 100%; padding: 0.7rem 1rem;
    background: rgba(255,255,255,0.08);
    border: 1.5px solid rgba(255,255,255,0.15);
    border-radius: 8px; color: white;
    font-family: 'Tiro Bangla', serif; font-size: 0.95rem;
    outline: none; transition: border 0.2s;
    -webkit-appearance: none;
  }
  input::placeholder { color: rgba(255,255,255,0.3); }
  input:focus, select:focus { border-color: var(--green-light); }
  select option { background: var(--dark); }

  .submit-btn {
    width: 100%; padding: 0.9rem;
    background: var(--green); color: white;
    border: none; border-radius: 8px;
    font-family: 'Tiro Bangla', serif;
    font-size: 1rem; font-weight: 700;
    cursor: pointer; margin-top: 0.5rem;
    transition: all 0.2s;
    box-shadow: 0 4px 15px rgba(26,122,74,0.4);
  }
  .submit-btn:hover { background: var(--green-light); transform: translateY(-2px); }

  .form-note {
    font-family: 'Tiro Bangla', serif;
    font-size: 0.78rem; color: rgba(255,255,255,0.35);
    text-align: center; margin-top: 0.8rem;
  }

  /* SUCCESS MESSAGE */
  .success-msg {
    display: none;
    background: var(--green-pale); border: 1.5px solid var(--green);
    border-radius: 12px; padding: 1.5rem; text-align: center;
    margin-top: 1rem;
  }
  .success-msg.show { display: block; }
  .success-msg p {
    font-family: 'Tiro Bangla', serif;
    color: var(--green); font-size: 1rem; font-weight: 600;
  }

  /* DEMO MODAL */
  .modal-overlay {
    display: none; position: fixed; inset: 0; z-index: 200;
    background: rgba(15,26,20,0.85); backdrop-filter: blur(4px);
    align-items: center; justify-content: center; padding: 1rem;
  }
  .modal-overlay.open { display: flex; }

  .modal {
    background: white; border-radius: 16px; padding: 2rem;
    max-width: 520px; width: 100%; max-height: 90vh; overflow-y: auto;
    animation: popIn 0.3s ease;
  }

  .modal-header {
    display: flex; justify-content: space-between; align-items: center;
    margin-bottom: 1.5rem;
  }
  .modal-title {
    font-family: 'Tiro Bangla', serif;
    font-size: 1.2rem; font-weight: 600; color: var(--dark);
  }
  .modal-close {
    background: none; border: none; font-size: 1.4rem;
    cursor: pointer; color: var(--muted); line-height: 1;
  }

  .q-num {
    font-size: 0.75rem; font-weight: 700; color: var(--saffron);
    letter-spacing: 1px; text-transform: uppercase; margin-bottom: 0.5rem;
  }
  .q-text {
    font-family: 'Tiro Bangla', serif;
    font-size: 1rem; color: var(--dark); margin-bottom: 1rem; line-height: 1.6;
  }
  .q-opts { display: flex; flex-direction: column; gap: 0.6rem; }
  .q-opt {
    padding: 0.65rem 1rem; border-radius: 8px;
    font-family: 'Tiro Bangla', serif; font-size: 0.9rem;
    border: 1.5px solid var(--border); cursor: pointer;
    transition: all 0.15s; background: white;
  }
  .q-opt:hover:not(.answered) { border-color: var(--green); background: var(--green-pale); }
  .q-opt.correct { border-color: var(--green); background: var(--green-pale); color: var(--green); font-weight: 600; }
  .q-opt.wrong { border-color: #dc3545; background: #fdf0f0; color: #dc3545; }

  .q-nav {
    display: flex; justify-content: space-between; align-items: center;
    margin-top: 1.5rem;
  }
  .q-nav button {
    padding: 0.5rem 1.2rem; border-radius: 6px;
    font-family: 'Tiro Bangla', serif; font-size: 0.9rem;
    cursor: pointer; transition: all 0.15s;
  }
  .btn-next {
    background: var(--green); color: white; border: none;
  }
  .btn-next:hover { background: var(--green-light); }
  .btn-next:disabled { background: var(--border); color: var(--muted); cursor: default; }
  .q-progress { font-size: 0.85rem; color: var(--muted); }

  .result-box {
    display: none; text-align: center; padding: 1rem 0;
  }
  .result-box.show { display: block; }
  .result-score {
    font-size: 3rem; font-weight: 800; color: var(--green);
  }
  .result-text {
    font-family: 'Tiro Bangla', serif;
    font-size: 1.1rem; color: var(--dark); margin-top: 0.5rem;
  }
  .result-sub {
    font-family: 'Tiro Bangla', serif;
    font-size: 0.9rem; color: var(--muted); margin-top: 0.3rem;
  }

  /* FOOTER */
  footer {
    background: var(--dark); border-top: 1px solid rgba(255,255,255,0.08);
    padding: 2rem; text-align: center;
  }
  footer p {
    font-family: 'Tiro Bangla', serif;
    font-size: 0.85rem; color: rgba(255,255,255,0.4);
  }
  footer strong { color: var(--green-light); }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes popIn {
    from { opacity: 0; transform: scale(0.95); }
    to { opacity: 1; transform: scale(1); }
  }
  @keyframes shrink {
    from { width: 100%; }
    to { width: 0%; }
  }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    .hero-inner { grid-template-columns: 1fr; gap: 2rem; }
    .stats-inner { grid-template-columns: repeat(2, 1fr); }
    .pricing-grid { grid-template-columns: 1fr; max-width: 380px; }
    nav .nav-links { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">Test <span>Bazar</span></div>
  <div class="nav-links">
    <a href="#subjects">বিষয়সমূহ</a>
    <a href="#pricing">মূল্য</a>
    <a href="#register">রেজিস্ট্রেশন</a>
    <a href="#register" class="nav-cta">শুরু করুন</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-inner">
    <div class="hero-content">
      <div class="hero-tag">উচ্চমাধ্যমিক ২০২৫–২৬</div>
      <h1>পরীক্ষার প্রস্তুতি নাও <em>সঠিকভাবে</em></h1>
      <p class="hero-sub">Test Bazar — এর সাথে প্রতিদিন practice করো, নিজের অগ্রগতি দেখো, এবং পরীক্ষায় সেরা ফলাফল অর্জন করো।</p>
      <div class="hero-btns">
        <a href="#register" class="btn-primary">এখনই শুরু করো</a>
        <button class="btn-secondary" onclick="openDemo()">Demo Test দাও →</button>
      </div>
    </div>
    <div class="hero-card">
      <div class="card-header">
        <div class="card-dot" style="background:#e74c3c"></div>
        <div class="card-dot" style="background:#f39c12"></div>
        <div class="card-dot" style="background:#2ecc71"></div>
        <span style="font-size:0.8rem;color:var(--muted);margin-left:0.5rem">Physics — Chapter 3</span>
      </div>
      <div class="quiz-title">নমুনা প্রশ্ন</div>
      <div class="quiz-q">আলোর গতি শূন্যস্থানে প্রায় কত?</div>
      <div class="quiz-opts">
        <div class="quiz-opt" onclick="this.classList.add('wrong')">3 × 10⁸ km/s</div>
        <div class="quiz-opt correct">3 × 10⁸ m/s</div>
        <div class="quiz-opt" onclick="this.classList.add('wrong')">3 × 10⁶ m/s</div>
      </div>
      <div class="quiz-timer">
        <span>⏱ ৩০ সেকেন্ড</span>
        <div class="timer-bar"><div class="timer-fill"></div></div>
        <span>প্রশ্ন ১/২০</span>
      </div>
    </div>
  </div>
</section>

<!-- STATS -->
<div class="stats">
  <div class="stats-inner">
    <div><div class="stat-num">৫০০+</div><div class="stat-label">নিবন্ধিত শিক্ষার্থী</div></div>
    <div><div class="stat-num">২০০০+</div><div class="stat-label">MCQ প্রশ্ন</div></div>
    <div><div class="stat-num">৬টি</div><div class="stat-label">বিষয় উপলব্ধ</div></div>
    <div><div class="stat-num">৯৮%</div><div class="stat-label">সন্তুষ্ট শিক্ষার্থী</div></div>
  </div>
</div>

<!-- SUBJECTS -->
<section class="subjects" id="subjects">
  <div class="section-inner">
    <div class="section-label">বিষয়সমূহ</div>
    <h2>যেসব বিষয়ে Test পাবে</h2>
    <p class="section-sub">উচ্চমাধ্যমিক সিলেবাস অনুযায়ী প্রতিটি chapter আলাদাভাবে</p>
    <div class="subjects-grid">
      <div class="subj-card"><div class="subj-icon">⚛️</div><div class="subj-name">পদার্থবিজ্ঞান</div><div class="subj-count">৩৫০+ প্রশ্ন</div></div>
      <div class="subj-card"><div class="subj-icon">🧪</div><div class="subj-name">রসায়ন</div><div class="subj-count">৩২০+ প্রশ্ন</div></div>
      <div class="subj-card"><div class="subj-icon">🧬</div><div class="subj-name">জীববিজ্ঞান</div><div class="subj-count">২৮০+ প্রশ্ন</div></div>
      <div class="subj-card"><div class="subj-icon">📐</div><div class="subj-name">গণিত</div><div class="subj-count">৪০০+ প্রশ্ন</div></div>
      <div class="subj-card"><div class="subj-icon">🌍</div><div class="subj-name">ভূগোল</div><div class="subj-count">২৫০+ প্রশ্ন</div></div>
      <div class="subj-card"><div class="subj-icon">📚</div><div class="subj-name">বাংলা</div><div class="subj-count">২২০+ প্রশ্ন</div></div>
    </div>
  </div>
</section>

<!-- PRICING -->
<section class="pricing" id="pricing">
  <div class="section-inner">
    <div style="text-align:center;margin-bottom:2.5rem">
      <div class="section-label">মূল্য পরিকল্পনা</div>
      <h2>তোমার বাজেট অনুযায়ী বেছে নাও</h2>
      <p class="section-sub">সব plan এ bKash / Nagad এ payment করা যাবে</p>
    </div>
    <div class="pricing-grid">
      <div class="price-card">
        <div class="price-plan">ফ্রি</div>
        <div class="price-amount">৳০</div>
        <hr class="price-divider">
        <div class="price-feat">Demo test (৫ প্রশ্ন)</div>
        <div class="price-feat">Result দেখা</div>
        <div class="price-feat no">Unlimited test</div>
        <div class="price-feat no">Leaderboard</div>
        <div class="price-feat no">Detailed analysis</div>
        <button class="price-btn outline" onclick="openDemo()">Demo দাও</button>
      </div>
      <div class="price-card popular">
        <div class="popular-badge">সবচেয়ে জনপ্রিয়</div>
        <div class="price-plan">মাসিক</div>
        <div class="price-amount">৳৯৯ <span>/ মাস</span></div>
        <hr class="price-divider">
        <div class="price-feat">Unlimited test</div>
        <div class="price-feat">সব বিষয় access</div>
        <div class="price-feat">Detailed result</div>
        <div class="price-feat">Leaderboard</div>
        <div class="price-feat no">Priority support</div>
        <button class="price-btn filled" onclick="document.getElementById('register').scrollIntoView({behavior:'smooth'})">এখনই নাও</button>
      </div>
      <div class="price-card">
        <div class="price-plan">বার্ষিক</div>
        <div class="price-amount">৳৮৯৯ <span>/ বছর</span></div>
        <hr class="price-divider">
        <div class="price-feat">Unlimited test</div>
        <div class="price-feat">সব বিষয় access</div>
        <div class="price-feat">Detailed result</div>
        <div class="price-feat">Leaderboard</div>
        <div class="price-feat">Priority support</div>
        <button class="price-btn outline" onclick="document.getElementById('register').scrollIntoView({behavior:'smooth'})">বার্ষিক নাও</button>
      </div>
    </div>
    <p style="text-align:center;font-family:'Tiro Bangla',serif;font-size:0.85rem;color:var(--muted);margin-top:1.5rem">
      💳 Payment: bKash / Nagad — নম্বর: <strong style="color:var(--green)">01XXXXXXXXXX</strong>
    </p>
  </div>
</section>

<!-- REGISTER -->
<section class="register" id="register">
  <div class="register-inner">
    <div class="section-label" style="color:var(--saffron)">রেজিস্ট্রেশন</div>
    <h2>আজই যোগ দাও</h2>
    <p class="section-sub">Registration করো, payment করো, এবং সাথে সাথে test শুরু করো</p>
    <div class="form-wrap">
      <div id="regForm">
        <div class="form-group">
          <label>পূর্ণ নাম *</label>
          <input type="text" id="name" placeholder="তোমার নাম লেখো">
        </div>
        <div class="form-group">
          <label>Email Address *</label>
          <input type="email" id="email" placeholder="example@gmail.com">
        </div>
        <div class="form-group">
          <label>Mobile নম্বর *</label>
          <input type="tel" id="mobile" placeholder="01XXXXXXXXXX">
        </div>
        <div class="form-group">
          <label>Class *</label>
          <select id="class">
            <option value="">বেছে নাও</option>
            <option>একাদশ শ্রেণি (Class 11)</option>
            <option>দ্বাদশ শ্রেণি (Class 12)</option>
          </select>
        </div>
        <div class="form-group">
          <label>বিভাগ *</label>
          <select id="group">
            <option value="">বেছে নাও</option>
            <option>বিজ্ঞান</option>
            <option>মানবিক</option>
            <option>বাণিজ্য</option>
          </select>
        </div>
        <div class="form-group">
          <label>Plan বেছে নাও *</label>
          <select id="plan">
            <option value="">বেছে নাও</option>
            <option>মাসিক — ৳৯৯</option>
            <option>বার্ষিক — ৳৮৯৯</option>
          </select>
        </div>
        <button class="submit-btn" onclick="submitForm()">Registration করো →</button>
        <p class="form-note">Registration এর পর payment এর নির্দেশনা email এ পাঠানো হবে।</p>
      </div>
      <div class="success-msg" id="successMsg">
        <p>🎉 Registration সফল হয়েছে!</p>
        <p style="font-size:0.85rem;margin-top:0.5rem;color:var(--muted)">Payment এর নির্দেশনা শীঘ্রই তোমার email এ পাঠানো হবে।</p>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p><strong>Test Bazar</strong> — উচ্চমাধ্যমিক পরীক্ষার সেরা প্রস্তুতি</p>
  <p style="margin-top:0.4rem">যোগাযোগ: testbazar@gmail.com | bKash: 01XXXXXXXXXX</p>
</footer>

<!-- DEMO MODAL -->
<div class="modal-overlay" id="demoModal">
  <div class="modal">
    <div class="modal-header">
      <div class="modal-title">Demo Test — পদার্থবিজ্ঞান</div>
      <button class="modal-close" onclick="closeDemo()">✕</button>
    </div>
    <div id="quizArea">
      <div class="q-num" id="qNum">প্রশ্ন ১ / ৫</div>
      <div class="q-text" id="qText"></div>
      <div class="q-opts" id="qOpts"></div>
      <div class="q-nav">
        <div class="q-progress" id="qScore">সঠিক: ০</div>
        <button class="btn-next" id="nextBtn" onclick="nextQ()" disabled>পরবর্তী →</button>
      </div>
    </div>
    <div class="result-box" id="resultBox">
      <div class="result-score" id="finalScore"></div>
      <div class="result-text" id="resultText"></div>
      <div class="result-sub">সম্পূর্ণ access পেতে subscription নাও!</div>
      <button class="btn-primary" style="margin-top:1.2rem" onclick="closeDemo();document.getElementById('register').scrollIntoView({behavior:'smooth'})">Registration করো →</button>
    </div>
  </div>
</div>

<script>
const questions = [
  { q: "নিউটনের গতির দ্বিতীয় সূত্র অনুযায়ী, F = ?", opts: ["ma", "mv", "mg", "m/a"], ans: 0 },
  { q: "তড়িৎ প্রবাহের SI একক কী?", opts: ["ভোল্ট", "অ্যাম্পিয়ার", "ওহম", "ওয়াট"], ans: 1 },
  { q: "আলোর গতি শূন্যস্থানে প্রায় কত m/s?", opts: ["3×10⁶", "3×10⁷", "3×10⁸", "3×10⁹"], ans: 2 },
  { q: "চৌম্বক ক্ষেত্রের SI একক কী?", opts: ["টেসলা", "গাউস", "ওয়েবার", "হেনরি"], ans: 0 },
  { q: "শক্তির SI একক কী?", opts: ["ওয়াট", "জুল", "নিউটন", "পাস্কাল"], ans: 1 }
];

let cur = 0, score = 0, answered = false;

function loadQ() {
  answered = false;
  const q = questions[cur];
  document.getElementById('qNum').textContent = `প্রশ্ন ${cur+1} / ${questions.length}`;
  document.getElementById('qText').textContent = q.q;
  document.getElementById('nextBtn').disabled = true;
  const opts = document.getElementById('qOpts');
  opts.innerHTML = '';
  q.opts.forEach((o, i) => {
    const btn = document.createElement('button');
    btn.className = 'q-opt';
    btn.textContent = o;
    btn.onclick = () => answer(i);
    opts.appendChild(btn);
  });
}

function answer(i) {
  if (answered) return;
  answered = true;
  const q = questions[cur];
  const btns = document.querySelectorAll('.q-opt');
  btns.forEach(b => b.classList.add('answered'));
  btns[q.ans].classList.add('correct');
  if (i !== q.ans) btns[i].classList.add('wrong');
  else score++;
  document.getElementById('qScore').textContent = `সঠিক: ${score}`;
  document.getElementById('nextBtn').disabled = false;
  if (cur === questions.length - 1) document.getElementById('nextBtn').textContent = 'ফলাফল দেখো';
}

function nextQ() {
  cur++;
  if (cur >= questions.length) {
    document.getElementById('quizArea').style.display = 'none';
    const rb = document.getElementById('resultBox');
    rb.classList.add('show');
    document.getElementById('finalScore').textContent = `${score}/${questions.length}`;
    const pct = (score/questions.length)*100;
    document.getElementById('resultText').textContent =
      pct >= 80 ? '🌟 অসাধারণ! তুমি খুব ভালো করেছ!' :
      pct >= 60 ? '👍 ভালো করেছ! আরও practice করো।' :
      '💪 চেষ্টা চালিয়ে যাও! subscription নিলে আরও ভালো হবে।';
  } else { loadQ(); }
}

function openDemo() {
  cur = 0; score = 0;
  document.getElementById('quizArea').style.display = 'block';
  document.getElementById('resultBox').classList.remove('show');
  document.getElementById('qScore').textContent = 'সঠিক: ০';
  loadQ();
  document.getElementById('demoModal').classList.add('open');
}

function closeDemo() {
  document.getElementById('demoModal').classList.remove('open');
}

function submitForm() {
  const name = document.getElementById('name').value.trim();
  const email = document.getElementById('email').value.trim();
  const mobile = document.getElementById('mobile').value.trim();
  const cls = document.getElementById('class').value;
  const grp = document.getElementById('group').value;
  const plan = document.getElementById('plan').value;
  if (!name || !email || !mobile || !cls || !grp || !plan) {
    alert('সব তথ্য পূরণ করো।'); return;
  }
  document.getElementById('regForm').style.display = 'none';
  document.getElementById('successMsg').classList.add('show');
}

document.getElementById('demoModal').addEventListener('click', function(e) {
  if (e.target === this) closeDemo();
});
</script>
</body>
</html>
