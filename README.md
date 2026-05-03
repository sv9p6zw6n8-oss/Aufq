# Aufq
مشروع ريادة الأعمال أفق للتصاميم والجرافيكس، صُمِم بواسطة وليد مخلف العنزي 
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>خطة الأعمال - مشروع التصميم الإبداعي</title>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800;900&display=swap" rel="stylesheet">
<style>
  :root {
    --blue-deep: #020d1f;
    --blue-mid: #041530;
    --blue-accent: #0a2a5e;
    --cyan: #00d4ff;
    --cyan-dim: #0099cc;
    --cyan-glow: rgba(0,212,255,0.15);
    --gold: #f0c040;
    --white: #ffffff;
    --text-light: rgba(255,255,255,0.85);
    --text-dim: rgba(255,255,255,0.55);
    --card-bg: rgba(255,255,255,0.04);
    --card-border: rgba(0,212,255,0.18);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Tajawal', sans-serif;
    background: var(--blue-deep);
    color: var(--white);
    overflow-x: hidden;
  }

  /* ─── ANIMATED BACKGROUND ─── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 80% 20%, rgba(0,80,180,0.35) 0%, transparent 60%),
      radial-gradient(ellipse 60% 50% at 10% 80%, rgba(0,40,120,0.4) 0%, transparent 55%),
      radial-gradient(ellipse 40% 40% at 50% 50%, rgba(0,180,255,0.06) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  /* ─── GRID OVERLAY ─── */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,255,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* ─── NAV ─── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 18px 48px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(2,13,31,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--card-border);
  }

  .nav-logo {
    font-size: 1.3rem;
    font-weight: 800;
    color: var(--cyan);
    letter-spacing: 1px;
    text-shadow: 0 0 20px rgba(0,212,255,0.5);
  }

  .nav-links {
    display: flex;
    gap: 32px;
    list-style: none;
  }

  .nav-links a {
    color: var(--text-light);
    text-decoration: none;
    font-size: 0.95rem;
    font-weight: 500;
    transition: color 0.3s;
    position: relative;
  }

  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -4px; right: 0;
    width: 0; height: 2px;
    background: var(--cyan);
    transition: width 0.3s;
  }

  .nav-links a:hover { color: var(--cyan); }
  .nav-links a:hover::after { width: 100%; }

  /* ─── SECTIONS SHARED ─── */
  section {
    position: relative;
    z-index: 1;
    padding: 100px 64px;
    max-width: 1300px;
    margin: 0 auto;
  }

  /* ─── HERO ─── */
  #hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding-top: 120px;
    max-width: 100%;
    padding-inline: 48px;
  }

  .hero-globe {
    position: absolute;
    left: 5%;
    top: 50%;
    transform: translateY(-50%);
    width: 380px;
    height: 380px;
    opacity: 0.18;
    pointer-events: none;
  }

  .hero-globe svg { width: 100%; height: 100%; }

  .hero-tag {
    display: inline-block;
    background: var(--cyan-glow);
    border: 1px solid var(--cyan);
    color: var(--cyan);
    font-size: 0.85rem;
    font-weight: 600;
    padding: 6px 20px;
    border-radius: 50px;
    letter-spacing: 2px;
    margin-bottom: 28px;
    animation: fadeDown 0.8s ease both;
  }

  .hero-title {
    font-size: clamp(2.8rem, 6vw, 5rem);
    font-weight: 900;
    line-height: 1.15;
    margin-bottom: 20px;
    animation: fadeDown 0.9s ease 0.1s both;
  }

  .hero-title span {
    color: var(--cyan);
    text-shadow: 0 0 40px rgba(0,212,255,0.5);
  }

  .hero-sub {
    font-size: 1.15rem;
    color: var(--text-dim);
    max-width: 600px;
    line-height: 1.8;
    margin-bottom: 48px;
    animation: fadeDown 1s ease 0.2s both;
  }

  .hero-btns {
    display: flex;
    gap: 16px;
    justify-content: center;
    animation: fadeDown 1s ease 0.3s both;
  }

  .btn-primary {
    background: linear-gradient(135deg, var(--cyan), #0070cc);
    color: var(--white);
    border: none;
    padding: 14px 36px;
    border-radius: 8px;
    font-family: inherit;
    font-size: 1rem;
    font-weight: 700;
    cursor: pointer;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 0 30px rgba(0,212,255,0.3);
    text-decoration: none;
  }

  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 0 50px rgba(0,212,255,0.5);
  }

  .btn-outline {
    background: transparent;
    color: var(--cyan);
    border: 1px solid var(--cyan);
    padding: 14px 36px;
    border-radius: 8px;
    font-family: inherit;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
    text-decoration: none;
  }

  .btn-outline:hover {
    background: var(--cyan-glow);
    transform: translateY(-2px);
  }

  .hero-stats {
    display: flex;
    gap: 60px;
    margin-top: 72px;
    animation: fadeUp 1s ease 0.5s both;
  }

  .stat {
    text-align: center;
  }

  .stat-num {
    font-size: 2.2rem;
    font-weight: 900;
    color: var(--cyan);
    text-shadow: 0 0 20px rgba(0,212,255,0.4);
  }

  .stat-label {
    font-size: 0.85rem;
    color: var(--text-dim);
    margin-top: 4px;
  }

  /* ─── SECTION HEADER ─── */
  .sec-header {
    text-align: center;
    margin-bottom: 60px;
  }

  .sec-tag {
    display: inline-block;
    color: var(--cyan);
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 14px;
    opacity: 0.8;
  }

  .sec-title {
    font-size: clamp(1.8rem, 3.5vw, 2.8rem);
    font-weight: 800;
    margin-bottom: 14px;
  }

  .sec-title span { color: var(--cyan); }

  .sec-line {
    width: 60px;
    height: 3px;
    background: linear-gradient(90deg, var(--cyan), transparent);
    margin: 16px auto 0;
    border-radius: 2px;
  }

  /* ─── CARDS ─── */
  .card {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: 16px;
    padding: 32px;
    backdrop-filter: blur(10px);
    transition: border-color 0.3s, transform 0.3s, box-shadow 0.3s;
  }

  .card:hover {
    border-color: rgba(0,212,255,0.45);
    transform: translateY(-4px);
    box-shadow: 0 20px 60px rgba(0,212,255,0.1);
  }

  /* ─── CONSUMERS ─── */
  #consumers .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 32px;
  }

  .consumer-card {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: 16px;
    padding: 36px;
    backdrop-filter: blur(10px);
  }

  .consumer-card h3 {
    color: var(--cyan);
    font-size: 1.2rem;
    margin-bottom: 20px;
    font-weight: 700;
    border-bottom: 1px solid var(--card-border);
    padding-bottom: 14px;
  }

  .dot-item {
    display: flex;
    align-items: flex-start;
    gap: 14px;
    margin-bottom: 18px;
    color: var(--text-light);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  .dot {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    border: 2px solid var(--cyan);
    flex-shrink: 0;
    margin-top: 3px;
    background: rgba(0,212,255,0.08);
  }

  /* ─── MARKET ANALYSIS ─── */
  .table-wrap {
    overflow-x: auto;
    border-radius: 16px;
    border: 1px solid var(--card-border);
  }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.9rem;
  }

  thead tr {
    background: rgba(0,212,255,0.12);
  }

  thead th {
    padding: 16px 20px;
    color: var(--cyan);
    font-weight: 700;
    text-align: right;
    border-bottom: 1px solid var(--card-border);
    font-size: 0.88rem;
    letter-spacing: 0.5px;
  }

  tbody tr {
    border-bottom: 1px solid rgba(255,255,255,0.05);
    transition: background 0.2s;
  }

  tbody tr:hover { background: rgba(0,212,255,0.04); }
  tbody tr:last-child { border-bottom: none; }

  tbody td {
    padding: 14px 20px;
    color: var(--text-light);
    text-align: right;
    vertical-align: middle;
  }

  .badge {
    display: inline-block;
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 0.78rem;
    font-weight: 600;
  }

  .badge-high { background: rgba(0,212,255,0.15); color: var(--cyan); }
  .badge-mid { background: rgba(240,192,64,0.15); color: var(--gold); }
  .badge-low { background: rgba(255,255,255,0.08); color: var(--text-dim); }

  /* ─── SWOT ─── */
  .swot-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }

  .swot-card {
    border-radius: 16px;
    padding: 32px;
    border: 1px solid;
  }

  .swot-card.strength {
    background: rgba(0,212,255,0.06);
    border-color: rgba(0,212,255,0.25);
  }

  .swot-card.weakness {
    background: rgba(255,80,80,0.06);
    border-color: rgba(255,80,80,0.2);
  }

  .swot-card h3 {
    font-size: 1.1rem;
    font-weight: 800;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .swot-card.strength h3 { color: var(--cyan); }
  .swot-card.weakness h3 { color: #ff6666; }

  .swot-item {
    display: flex;
    gap: 10px;
    margin-bottom: 14px;
    font-size: 0.9rem;
    color: var(--text-light);
    line-height: 1.65;
  }

  .swot-num {
    color: var(--cyan);
    font-weight: 800;
    flex-shrink: 0;
    font-size: 0.85rem;
  }

  .swot-card.weakness .swot-num { color: #ff6666; }

  /* ─── MARKETING MIX ─── */
  .mix-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }

  .mix-card {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: 16px;
    padding: 32px;
    text-align: center;
    transition: all 0.3s;
  }

  .mix-card:hover {
    border-color: rgba(0,212,255,0.4);
    transform: translateY(-4px);
    box-shadow: 0 16px 48px rgba(0,212,255,0.1);
  }

  .mix-icon {
    font-size: 2.5rem;
    margin-bottom: 16px;
  }

  .mix-card h3 {
    color: var(--cyan);
    font-size: 1.1rem;
    font-weight: 700;
    margin-bottom: 12px;
  }

  .mix-card p {
    color: var(--text-dim);
    font-size: 0.9rem;
    line-height: 1.7;
  }

  /* ─── FINANCIAL TABLES ─── */
  .fin-highlight td:first-child {
    font-weight: 800;
    color: var(--cyan);
  }

  .total-row td {
    background: rgba(0,212,255,0.08);
    font-weight: 800;
    color: var(--white);
  }

  .yellow-cell { color: var(--gold) !important; font-weight: 700; }

  /* ─── BREAKEVEN ─── */
  .breakeven-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 16px;
    margin-top: 32px;
  }

  .be-card {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: 12px;
    padding: 24px 16px;
    text-align: center;
    transition: all 0.3s;
  }

  .be-card:hover {
    border-color: rgba(0,212,255,0.4);
    transform: translateY(-3px);
  }

  .be-year {
    font-size: 0.8rem;
    color: var(--text-dim);
    margin-bottom: 10px;
    font-weight: 600;
    letter-spacing: 1px;
  }

  .be-units {
    font-size: 1.5rem;
    font-weight: 900;
    color: var(--cyan);
    margin-bottom: 6px;
  }

  .be-sar {
    font-size: 0.8rem;
    color: var(--text-dim);
  }

  /* ─── INCOME STATEMENT ─── */
  .income-highlight { background: rgba(0,212,255,0.06) !important; }
  .income-net { background: rgba(0,212,255,0.12) !important; }

  /* ─── FOOTER ─── */
  footer {
    position: relative;
    z-index: 1;
    text-align: center;
    padding: 48px;
    border-top: 1px solid var(--card-border);
    color: var(--text-dim);
    font-size: 0.9rem;
  }

  footer span { color: var(--cyan); }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse-glow {
    0%, 100% { box-shadow: 0 0 20px rgba(0,212,255,0.2); }
    50% { box-shadow: 0 0 40px rgba(0,212,255,0.5); }
  }

  .glow-pulse { animation: pulse-glow 3s ease-in-out infinite; }

  /* ─── DIVIDER ─── */
  .divider {
    position: relative;
    z-index: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--cyan), transparent);
    opacity: 0.2;
    margin: 0 64px;
  }

  /* ─── TARGET MARKET TABLE ─── */
  .target-wrap {
    display: grid;
    grid-template-columns: 1fr 1.4fr;
    gap: 32px;
    align-items: start;
  }

  /* ─── OPERATIONAL TABLE ─── */
  .op-tabs {
    display: flex;
    gap: 12px;
    margin-bottom: 32px;
    flex-wrap: wrap;
  }

  .op-tab {
    padding: 8px 22px;
    border-radius: 6px;
    font-family: inherit;
    font-size: 0.88rem;
    font-weight: 600;
    cursor: pointer;
    border: 1px solid var(--card-border);
    background: transparent;
    color: var(--text-dim);
    transition: all 0.2s;
  }

  .op-tab.active, .op-tab:hover {
    background: rgba(0,212,255,0.12);
    border-color: var(--cyan);
    color: var(--cyan);
  }

  .op-section { display: none; }
  .op-section.active { display: block; }

  /* scrollbar */
  ::-webkit-scrollbar { width: 6px; height: 6px; }
  ::-webkit-scrollbar-track { background: var(--blue-deep); }
  ::-webkit-scrollbar-thumb { background: rgba(0,212,255,0.3); border-radius: 3px; }

  @media (max-width: 900px) {
    nav { padding: 14px 20px; }
    .nav-links { gap: 16px; font-size: 0.85rem; }
    section { padding: 80px 24px; }
    #consumers .grid-2 { grid-template-columns: 1fr; }
    .swot-grid { grid-template-columns: 1fr; }
    .mix-grid { grid-template-columns: 1fr 1fr; }
    .breakeven-grid { grid-template-columns: repeat(3, 1fr); }
    .target-wrap { grid-template-columns: 1fr; }
    .hero-stats { gap: 32px; flex-wrap: wrap; justify-content: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">✦ مشروع التصميم الإبداعي</div>
  <ul class="nav-links">
    <li><a href="#consumers">المستهلكون</a></li>
    <li><a href="#market">تحليل السوق</a></li>
    <li><a href="#competitive">الميزة التنافسية</a></li>
    <li><a href="#marketing">التسويق</a></li>
    <li><a href="#operational">التشغيل</a></li>
    <li><a href="#financial">المالية</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero" style="max-width:100%; padding-top:120px;">
  <!-- Globe decoration -->
  <div class="hero-globe">
    <svg viewBox="0 0 400 400" fill="none" xmlns="http://www.w3.org/2000/svg">
      <circle cx="200" cy="200" r="180" stroke="#00d4ff" stroke-width="1.5"/>
      <ellipse cx="200" cy="200" rx="100" ry="180" stroke="#00d4ff" stroke-width="1"/>
      <ellipse cx="200" cy="200" rx="180" ry="80" stroke="#00d4ff" stroke-width="1"/>
      <ellipse cx="200" cy="200" rx="180" ry="30" stroke="#00d4ff" stroke-width="0.5"/>
      <line x1="200" y1="20" x2="200" y2="380" stroke="#00d4ff" stroke-width="1"/>
      <line x1="20" y1="200" x2="380" y2="200" stroke="#00d4ff" stroke-width="1"/>
      <circle cx="200" cy="80" r="5" fill="#00d4ff"/>
      <circle cx="320" cy="160" r="4" fill="#00d4ff"/>
      <circle cx="140" cy="300" r="3" fill="#00d4ff"/>
      <line x1="200" y1="80" x2="320" y2="160" stroke="#00d4ff" stroke-width="0.8" opacity="0.6"/>
      <line x1="320" y1="160" x2="140" y2="300" stroke="#00d4ff" stroke-width="0.8" opacity="0.6"/>
    </svg>
  </div>

  <div class="hero-tag">خطة الأعمال الريادية</div>
  <h1 class="hero-title">مشروع <span>التصميم</span><br>الإبداعي</h1>
  <p class="hero-sub">خدمات تصميم احترافية تشمل الهوية البصرية، الشعارات، الإعلانات الرقمية وتغليف المنتجات بأسعار تنافسية.</p>
  <div class="hero-btns">
    <a href="#financial" class="btn-primary">عرض الخطة المالية</a>
    <a href="#consumers" class="btn-outline">استعراض المشروع</a>
  </div>

  <div class="hero-stats">
    <div class="stat">
      <div class="stat-num">7.25M</div>
      <div class="stat-label">إيرادات السنة الأولى (ريال)</div>
    </div>
    <div class="stat">
      <div class="stat-num">6.49M</div>
      <div class="stat-label">صافي الربح الأول</div>
    </div>
    <div class="stat">
      <div class="stat-num">4</div>
      <div class="stat-label">خدمات رئيسية</div>
    </div>
    <div class="stat">
      <div class="stat-num">62,750</div>
      <div class="stat-label">إجمالي الاستثمار (ريال)</div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CONSUMERS -->
<section id="consumers">
  <div class="sec-header">
    <div class="sec-tag">Consumers</div>
    <h2 class="sec-title"><span>المستهلكون</span></h2>
    <div class="sec-line"></div>
  </div>

  <div class="grid-2">
    <div class="consumer-card">
      <h3>🎯 من هم؟</h3>
      <div class="dot-item">
        <div class="dot"></div>
        <div>طلاب، رواد أعمال، شركات ناشئة، مؤسسات صغيرة</div>
      </div>
      <div class="dot-item">
        <div class="dot"></div>
        <div>يبحثون عن جودة أعلى وسرعة تنفيذ — السوق يقدم لهم ما يلبي احتياجاتهم جزئياً فقط</div>
      </div>
      <div class="dot-item">
        <div class="dot"></div>
        <div>القدرة الشرائية: <strong style="color:var(--cyan)">معتدلة إلى قوية</strong></div>
      </div>
    </div>

    <div class="consumer-card">
      <h3>💡 التطلعات والمطلوب</h3>
      <div class="dot-item">
        <div class="dot"></div>
        <div>التطلعات: الجمع بين الجودة والسعر المناسب (النوعية + السعر معاً)</div>
      </div>
      <div class="dot-item">
        <div class="dot"></div>
        <div>يحتاجون تصاميم أكثر تميزاً وتفاعلاً مع العميل</div>
      </div>
      <div class="dot-item">
        <div class="dot"></div>
        <div>يشترون عبر الإنترنت أو التواصل المباشر، يدفعون بتحويل بنكي أو دفع إلكتروني</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- MARKET ANALYSIS -->
<section id="market">
  <div class="sec-header">
    <div class="sec-tag">Market Analysis</div>
    <h2 class="sec-title">تحليل <span>السوق</span></h2>
    <div class="sec-line"></div>
  </div>

  <div class="table-wrap">
    <table>
      <thead>
        <tr>
          <th>الجودة</th>
          <th>السعر</th>
          <th>مناطق التسويق</th>
          <th>مناطق المشروع</th>
          <th>المنتجات</th>
          <th>المنافس</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><span class="badge badge-high">مرتفعة</span></td>
          <td>متوسط</td>
          <td>عبر الإنترنت</td>
          <td>عبر الإنترنت</td>
          <td>شعارات، بوسترات، تصاميم سوشيال ميديا</td>
          <td><strong>زد ديزاين</strong></td>
        </tr>
        <tr>
          <td><span class="badge badge-high">مرتفعة</span></td>
          <td>مرتفع</td>
          <td>عبر الإنترنت</td>
          <td>الرياض - أونلاين</td>
          <td>هويات بصرية</td>
          <td><strong>براند مي</strong></td>
        </tr>
        <tr>
          <td><span class="badge badge-mid">متوسطة</span></td>
          <td>منخفض</td>
          <td>عبر الإنترنت</td>
          <td>المملكة العامة</td>
          <td>تصاميم جاهزة وخدمات سريعة</td>
          <td><strong>تصميمي</strong></td>
        </tr>
      </tbody>
    </table>
  </div>
</section>

<div class="divider"></div>

<!-- TARGET MARKET -->
<section id="target">
  <div class="sec-header">
    <div class="sec-tag">Target Market</div>
    <h2 class="sec-title">تقسيم <span>السوق المستهدف</span></h2>
    <div class="sec-line"></div>
  </div>

  <div class="target-wrap">
    <div class="card">
      <h3 style="color:var(--cyan); margin-bottom:20px; font-size:1.05rem;">رغبة العملاء</h3>
      <div class="dot-item"><div class="dot"></div><div><strong>ما يشترون؟</strong> — تصاميم حديثة تعبّر عن هويتهم وتزيد ظهورهم</div></div>
      <div class="dot-item"><div class="dot"></div><div><strong>متى؟</strong> — عند إطلاق مشاريعهم أو حملاتهم الإعلانية</div></div>
      <div class="dot-item"><div class="dot"></div><div><strong>أين؟</strong> — عبر المنصات الإلكترونية أو التواصل المباشر</div></div>
      <div class="dot-item"><div class="dot"></div><div><strong>كيف؟</strong> — تحويل بنكي أو دفع إلكتروني</div></div>
      <div class="dot-item"><div class="dot"></div><div><strong>تكرار الشراء؟</strong> — متوسط إلى مرتفع حسب الحملات</div></div>
    </div>

    <div class="card" style="padding:0; overflow:hidden;">
      <table>
        <thead>
          <tr>
            <th>المستوى التعليمي</th>
            <th>أسلوب الشراء</th>
            <th>القدرة الشرائية</th>
            <th>العمر</th>
            <th>فئة العملاء</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>جامعي</td>
            <td>عبر الإنترنت</td>
            <td>معتدلة</td>
            <td>18-35</td>
            <td><strong>القطاع الحكومي</strong></td>
          </tr>
          <tr>
            <td>جامعي</td>
            <td>بالتعاقد المباشر</td>
            <td><span class="badge badge-high">قوية</span></td>
            <td>25-45</td>
            <td><strong>القطاع الخاص</strong></td>
          </tr>
          <tr>
            <td>جامعي</td>
            <td>عبر الإنترنت</td>
            <td>معتدلة</td>
            <td>18-45</td>
            <td><strong>تجار التجزئة</strong></td>
          </tr>
          <tr>
            <td>جامعي</td>
            <td>عبر الإنترنت</td>
            <td>معتدلة</td>
            <td>18-45</td>
            <td><strong>تجار الجملة</strong></td>
          </tr>
          <tr>
            <td>جامعي</td>
            <td>عبر الإنترنت</td>
            <td><span class="badge badge-high">قوية</span></td>
            <td>18-60</td>
            <td><strong>الأفراد</strong></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- COMPETITIVE ADVANTAGE -->
<section id="competitive">
  <div class="sec-header">
    <div class="sec-tag">Competitive Advantage</div>
    <h2 class="sec-title">الميزة <span>التنافسية</span></h2>
    <div class="sec-line"></div>
  </div>

  <div class="swot-grid">
    <div class="swot-card strength">
      <h3>✦ نقاط القوة</h3>
      <div class="swot-item">
        <div class="dot" style="border-color:var(--cyan); margin-top:4px;"></div>
        <div>أسعار مناسبة، تواصل مباشر، تصاميم مخصصة لكل عميل</div>
      </div>
      <div class="swot-item">
        <span class="swot-num">1.</span>
        <div><strong>الإبداع والابتكار:</strong> قدرة الفريق على تقديم تصاميم فريدة وجذابة تتماشى مع احتياجات العملاء</div>
      </div>
      <div class="swot-item">
        <span class="swot-num">2.</span>
        <div><strong>أدوات حديثة:</strong> استخدام أحدث برامج التصميم والجرافيكس مما يزيد من جودة الإنتاج</div>
      </div>
      <div class="swot-item">
        <span class="swot-num">3.</span>
        <div><strong>خدمة عملاء مميزة:</strong> سرعة الاستجابة ومرونة التعامل مع طلبات العملاء المختلفة</div>
      </div>
    </div>

    <div class="swot-card weakness">
      <h3 style="color:#ff6666;">✗ نقاط الضعف</h3>
      <div class="swot-item">
        <div class="dot" style="border-color:#ff6666; margin-top:4px;"></div>
        <div>فريق صغير في البداية</div>
      </div>
      <div class="swot-item">
        <span class="swot-num" style="color:#ff6666;">1.</span>
        <div><strong>قلة الخبرة السوقية:</strong> كفريق جديد قد يكون صعباً فهم سلوك العملاء والمنافسين بالكامل</div>
      </div>
      <div class="swot-item">
        <span class="swot-num" style="color:#ff6666;">2.</span>
        <div><strong>اعتماد محدود على الأفراد:</strong> غياب أحد الأعضاء قد يؤثر على الإنتاجية</div>
      </div>
      <div class="swot-item">
        <span class="swot-num" style="color:#ff6666;">3.</span>
        <div><strong>التسويق المحدود:</strong> عدم وجود خطة تسويقية قوية قد يحد من وصول المشروع</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- MARKETING MIX -->
<section id="marketing">
  <div class="sec-header">
    <div class="sec-tag">Marketing Mix</div>
    <h2 class="sec-title">المزيج <span>التسويقي</span></h2>
    <div class="sec-line"></div>
  </div>

  <div class="mix-grid">
    <div class="mix-card glow-pulse">
      <div class="mix-icon">🎨</div>
      <h3>المنتج</h3>
      <p>تصاميم شعارات، هوية بصرية، إعلانات رقمية، تغليف منتجات</p>
    </div>
    <div class="mix-card">
      <div class="mix-icon">💰</div>
      <h3>السعر</h3>
      <p>أسعار تنافسية من <strong style="color:var(--gold)">100 ريال</strong> للتصميم البسيط وتصل إلى <strong style="color:var(--gold)">1500 ريال</strong> للهوية الكاملة</p>
    </div>
    <div class="mix-card">
      <div class="mix-icon">📣</div>
      <h3>الترويج</h3>
      <p>عبر وسائل التواصل (إنستقرام، سناب، X)، إعلانات ممولة وعروض خاصة</p>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- OPERATIONAL PLAN -->
<section id="operational">
  <div class="sec-header">
    <div class="sec-tag">Operational Plan</div>
    <h2 class="sec-title">الخطة <span>التشغيلية</span></h2>
    <div class="sec-line"></div>
  </div>

  <div class="op-tabs">
    <button class="op-tab active" onclick="showOp('sales')">التنبؤ بالمبيعات</button>
    <button class="op-tab" onclick="showOp('invest')">التكاليف الاستثمارية</button>
    <button class="op-tab" onclick="showOp('fixed')">التكاليف الثابتة</button>
    <button class="op-tab" onclick="showOp('variable')">التكاليف المتغيرة</button>
    <button class="op-tab" onclick="showOp('total')">إجمالي التكاليف</button>
  </div>

  <!-- Sales Forecast -->
  <div class="op-section active" id="op-sales">
    <div style="display:grid; grid-template-columns:1fr 1fr; gap:24px; margin-bottom:24px;">
      <div class="card">
        <h3 style="color:var(--cyan); margin-bottom:16px; font-size:1rem;">عدد الوحدات المتوقع بيعها</h3>
        <div class="table-wrap">
          <table>
            <thead><tr><th>المنتج</th><th>العدد</th><th>س1</th><th>س2</th><th>س3</th><th>س4</th><th>س5</th></tr></thead>
            <tbody>
              <tr><td class="yellow-cell">تصميم هوية بصرية</td><td class="yellow-cell">1000</td><td>1000</td><td>1050</td><td>1155</td><td>1294</td><td>1462</td></tr>
              <tr><td class="yellow-cell">تصميم شعار</td><td class="yellow-cell">3000</td><td>3000</td><td>3150</td><td>3465</td><td>3881</td><td>4385</td></tr>
              <tr><td class="yellow-cell">تصميم مطبوعات</td><td class="yellow-cell">7000</td><td>7000</td><td>7350</td><td>8085</td><td>9055</td><td>10232</td></tr>
              <tr><td class="yellow-cell">تصميم إعلانات</td><td class="yellow-cell">500</td><td>500</td><td>525</td><td>578</td><td>647</td><td>731</td></tr>
              <tr class="total-row"><td colspan="2">الإجمالي</td><td>11500</td><td>12075</td><td>13283</td><td>14876</td><td>16810</td></tr>
              <tr><td colspan="2" style="color:var(--text-dim)">نسبة النمو</td><td>—</td><td style="color:var(--gold)">5%</td><td style="color:var(--gold)">10%</td><td style="color:var(--gold)">12%</td><td style="color:var(--gold)">13%</td></tr>
            </tbody>
          </table>
        </div>
      </div>
      <div class="card">
        <h3 style="color:var(--cyan); margin-bottom:16px; font-size:1rem;">قيمة المبيعات (ريال)</h3>
        <div class="table-wrap">
          <table>
            <thead><tr><th>المنتج</th><th>السعر</th><th>س1</th><th>س2</th><th>س3</th><th>س4</th><th>س5</th></tr></thead>
            <tbody>
              <tr><td>هوية بصرية</td><td class="yellow-cell">1500</td><td>1,500,000</td><td>1,575,000</td><td>1,732,500</td><td>1,940,400</td><td>2,192,652</td></tr>
              <tr><td>شعار</td><td class="yellow-cell">350</td><td>1,050,000</td><td>1,102,500</td><td>1,267,875</td><td>1,420,020</td><td>1,604,623</td></tr>
              <tr><td>مطبوعات</td><td class="yellow-cell">600</td><td>4,200,000</td><td>4,410,000</td><td>5,071,500</td><td>5,680,080</td><td>6,418,490</td></tr>
              <tr><td>إعلانات</td><td class="yellow-cell">1000</td><td>500,000</td><td>525,000</td><td>603,750</td><td>676,200</td><td>764,106</td></tr>
              <tr class="total-row"><td>الإجمالي</td><td style="color:var(--cyan)">3450</td><td>7,250,000</td><td>7,612,500</td><td>8,675,625</td><td>9,716,700</td><td>10,979,871</td></tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>

  <!-- Investment Costs -->
  <div class="op-section" id="op-invest">
    <div style="display:grid; grid-template-columns:1fr 1fr 1fr; gap:24px;">
      <div class="card">
        <h3 style="color:var(--cyan); margin-bottom:16px; font-size:0.95rem;">أ) الآلات والمعدات</h3>
        <div class="table-wrap">
          <table>
            <thead><tr><th>البند</th><th>التكلفة</th></tr></thead>
            <tbody>
              <tr><td class="yellow-cell">برامج تصميم</td><td>7,500</td></tr>
              <tr><td class="yellow-cell">أجهزة حاسب</td><td>20,000</td></tr>
              <tr><td class="yellow-cell">طابعات/سكانر</td><td>3,000</td></tr>
              <tr><td class="yellow-cell">أدوات الرسم</td><td>500</td></tr>
              <tr><td class="yellow-cell">إنترنت وشبكات</td><td>6,000</td></tr>
              <tr><td class="yellow-cell">أدوات مكتبية</td><td>4,000</td></tr>
              <tr class="total-row"><td>المجموع</td><td>41,000</td></tr>
            </tbody>
          </table>
        </div>
      </div>
      <div class="card">
        <h3 style="color:var(--cyan); margin-bottom:16px; font-size:0.95rem;">ب) الأثاث والديكور</h3>
        <div class="table-wrap">
          <table>
            <thead><tr><th>البند</th><th>التكلفة</th></tr></thead>
            <tbody>
              <tr><td class="yellow-cell">كراسي</td><td>3,500</td></tr>
              <tr><td class="yellow-cell">طاولات</td><td>5,000</td></tr>
              <tr><td class="yellow-cell">أثاث مكتبي</td><td>1,200</td></tr>
              <tr><td class="yellow-cell">ديكورات</td><td>800</td></tr>
              <tr><td class="yellow-cell">سيراميك</td><td>1,000</td></tr>
              <tr><td class="yellow-cell">دهانات</td><td>450</td></tr>
              <tr><td class="yellow-cell">ستائر</td><td>1,000</td></tr>
              <tr><td class="yellow-cell">عدد وأدوات</td><td>500</td></tr>
              <tr class="total-row"><td>المجموع</td><td>13,450</td></tr>
            </tbody>
          </table>
        </div>
      </div>
      <div class="card">
        <h3 style="color:var(--cyan); margin-bottom:16px; font-size:0.95rem;">ج) تكاليف التأسيس</h3>
        <div class="table-wrap">
          <table>
            <thead><tr><th>البند</th><th>التكلفة</th></tr></thead>
            <tbody>
              <tr><td>رسوم تراخيص</td><td>1,000</td></tr>
              <tr><td>تأسيس الموقع</td><td>1,300</td></tr>
              <tr><td>مصاريف حكومية</td><td>2,000</td></tr>
              <tr><td>مصاريف أخرى</td><td>4,000</td></tr>
              <tr class="total-row"><td>المجموع</td><td>8,300</td></tr>
            </tbody>
          </table>
        </div>
        <div style="margin-top:20px; background:rgba(0,212,255,0.08); border:1px solid var(--card-border); border-radius:10px; padding:16px; text-align:center;">
          <div style="font-size:0.8rem; color:var(--text-dim); margin-bottom:6px;">إجمالي التكاليف الاستثمارية</div>
          <div style="font-size:2rem; font-weight:900; color:var(--cyan);">62,750</div>
          <div style="font-size:0.8rem; color:var(--text-dim);">ريال سعودي</div>
        </div>
      </div>
    </div>
  </div>

  <!-- Fixed Costs -->
  <div class="op-section" id="op-fixed">
    <div class="table-wrap">
      <table>
        <thead>
          <tr>
            <th>البيان</th>
            <th>السنة الأولى</th>
            <th>السنة الثانية (8%)</th>
            <th>السنة الثالثة (12%)</th>
            <th>السنة الرابعة (13%)</th>
            <th>السنة الخامسة (14%)</th>
          </tr>
        </thead>
        <tbody>
          <tr><td class="yellow-cell">الإيجار</td><td>45,000</td><td>48,600</td><td>54,432</td><td>61,508</td><td>70,119</td></tr>
          <tr><td class="yellow-cell">الرواتب</td><td>500,000</td><td>540,000</td><td>604,800</td><td>683,424</td><td>779,103</td></tr>
          <tr><td class="yellow-cell">صيانة الآلات</td><td>9,000</td><td>9,720</td><td>10,886</td><td>12,302</td><td>14,024</td></tr>
          <tr><td class="yellow-cell">التأمين</td><td>2,000</td><td>2,160</td><td>2,419</td><td>2,734</td><td>3,116</td></tr>
          <tr><td class="yellow-cell">مصاريف أخرى</td><td>1,900</td><td>2,052</td><td>2,298</td><td>2,597</td><td>2,961</td></tr>
          <tr><td class="yellow-cell">تكاليف ثابتة أخرى</td><td>2,700</td><td>2,916</td><td>3,266</td><td>3,690</td><td>4,207</td></tr>
          <tr class="total-row"><td>إجمالي التكلفة الثابتة</td><td>560,600</td><td>605,448</td><td>678,102</td><td>766,255</td><td>873,531</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Variable Costs -->
  <div class="op-section" id="op-variable">
    <div class="table-wrap">
      <table>
        <thead>
          <tr>
            <th>البيان</th>
            <th>السنة الأولى</th>
            <th>السنة الثانية (7%)</th>
            <th>السنة الثالثة (10%)</th>
            <th>السنة الرابعة (13%)</th>
            <th>السنة الخامسة (14%)</th>
          </tr>
        </thead>
        <tbody>
          <tr><td class="yellow-cell">المواد الخام</td><td>5,000</td><td>5,350</td><td>5,885</td><td>6,650</td><td>7,581</td></tr>
          <tr><td class="yellow-cell">الأجور</td><td>20,000</td><td>21,400</td><td>23,540</td><td>26,600</td><td>30,324</td></tr>
          <tr><td class="yellow-cell">فواتير الكهرباء والماء</td><td>5,000</td><td>5,350</td><td>5,885</td><td>6,650</td><td>7,581</td></tr>
          <tr><td class="yellow-cell">أجور توصيل البضائع</td><td>1,200</td><td>1,284</td><td>1,412</td><td>1,596</td><td>1,819</td></tr>
          <tr><td class="yellow-cell">مصاريف أخرى</td><td>1,000</td><td>1,070</td><td>1,177</td><td>1,330</td><td>1,516</td></tr>
          <tr><td class="yellow-cell">تكاليف متغيرة أخرى</td><td>2,000</td><td>2,140</td><td>2,354</td><td>2,660</td><td>3,032</td></tr>
          <tr class="total-row"><td>إجمالي التكلفة المتغيرة</td><td>34,200</td><td>36,594</td><td>40,253</td><td>45,486</td><td>51,854</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Total Costs -->
  <div class="op-section" id="op-total">
    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>البيان</th><th>السنة الأولى</th><th>السنة الثانية</th><th>السنة الثالثة</th><th>السنة الرابعة</th><th>السنة الخامسة</th></tr>
        </thead>
        <tbody>
          <tr><td>التكاليف الاستثمارية</td><td>12,550</td><td>12,550</td><td>12,550</td><td>12,550</td><td>12,550</td></tr>
          <tr><td>إجمالي التشغيلية (ثابتة + متغيرة)</td><td>594,800</td><td>642,042</td><td>718,355</td><td>811,741</td><td>925,385</td></tr>
          <tr class="total-row"><td>إجمالي التكاليف</td><td>607,350</td><td>654,592</td><td>730,905</td><td>824,291</td><td>937,935</td></tr>
          <tr class="income-highlight"><td>÷ عدد الوحدات</td><td>11,960</td><td>12,679</td><td>14,079</td><td>15,918</td><td>18,155</td></tr>
          <tr class="income-net"><td><strong>تكلفة الوحدة الواحدة</strong></td><td><strong style="color:var(--cyan)">51</strong></td><td><strong style="color:var(--cyan)">52</strong></td><td><strong style="color:var(--cyan)">52</strong></td><td><strong style="color:var(--cyan)">52</strong></td><td><strong style="color:var(--cyan)">52</strong></td></tr>
        </tbody>
      </table>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- BREAKEVEN -->
<section id="breakeven">
  <div class="sec-header">
    <div class="sec-tag">Break-Even Point</div>
    <h2 class="sec-title">نقطة <span>التعادل</span></h2>
    <div class="sec-line"></div>
  </div>

  <div class="table-wrap" style="margin-bottom:32px;">
    <table>
      <thead>
        <tr><th>البيان</th><th>السنة الأولى</th><th>السنة الثانية</th><th>السنة الثالثة</th><th>السنة الرابعة</th><th>السنة الخامسة</th></tr>
      </thead>
      <tbody>
        <tr><td>التكاليف الثابتة</td><td>560,600</td><td>605,448</td><td>678,102</td><td>766,255</td><td>873,531</td></tr>
        <tr><td>متوسط سعر بيع المنتجات</td><td>863</td><td>863</td><td>863</td><td>863</td><td>863</td></tr>
        <tr><td>التكلفة المتغيرة للوحدة</td><td>3</td><td>3</td><td>3</td><td>3</td><td>3</td></tr>
        <tr class="income-highlight"><td><strong>نقطة التعادل بالوحدات</strong></td><td><strong style="color:var(--cyan)">652</strong></td><td><strong style="color:var(--cyan)">704</strong></td><td><strong style="color:var(--cyan)">789</strong></td><td><strong style="color:var(--cyan)">891</strong></td><td><strong style="color:var(--cyan)">1,016</strong></td></tr>
        <tr class="income-net"><td><strong>نقطة التعادل بالريال</strong></td><td><strong>562,465</strong></td><td><strong>607,481</strong></td><td><strong>680,357</strong></td><td><strong>768,802</strong></td><td><strong>876,433</strong></td></tr>
      </tbody>
    </table>
  </div>

  <div class="breakeven-grid">
    <div class="be-card"><div class="be-year">السنة الأولى</div><div class="be-units">652</div><div class="be-sar">562,465 ريال</div></div>
    <div class="be-card"><div class="be-year">السنة الثانية</div><div class="be-units">704</div><div class="be-sar">607,481 ريال</div></div>
    <div class="be-card"><div class="be-year">السنة الثالثة</div><div class="be-units">789</div><div class="be-sar">680,357 ريال</div></div>
    <div class="be-card"><div class="be-year">السنة الرابعة</div><div class="be-units">891</div><div class="be-sar">768,802 ريال</div></div>
    <div class="be-card"><div class="be-year">السنة الخامسة</div><div class="be-units">1,016</div><div class="be-sar">876,433 ريال</div></div>
  </div>
</section>

<div class="divider"></div>

<!-- FINANCIAL PLAN -->
<section id="financial">
  <div class="sec-header">
    <div class="sec-tag">Financial Plan</div>
    <h2 class="sec-title">الخطة <span>المالية</span> — قائمة الدخل</h2>
    <div class="sec-line"></div>
  </div>

  <div class="table-wrap">
    <table>
      <thead>
        <tr>
          <th>البيان</th>
          <th>السنة الأولى</th>
          <th>السنة الثانية</th>
          <th>السنة الثالثة</th>
          <th>السنة الرابعة</th>
          <th>السنة الخامسة</th>
        </tr>
      </thead>
      <tbody>
        <tr class="income-highlight">
          <td><strong>المبيعات (Sales)</strong></td>
          <td><strong>7,250,000</strong></td>
          <td><strong>7,612,500</strong></td>
          <td><strong>8,675,625</strong></td>
          <td><strong>9,716,700</strong></td>
          <td><strong>10,979,871</strong></td>
        </tr>
        <tr>
          <td>يُخصم: التكاليف المتغيرة</td>
          <td>34,200</td><td>36,594</td><td>40,253</td><td>45,486</td><td>51,854</td>
        </tr>
        <tr>
          <td><strong>مجمل ربح التشغيل (Gross Operating Profit)</strong></td>
          <td>7,215,800</td><td>7,575,906</td><td>8,635,372</td><td>9,671,214</td><td>10,928,017</td>
        </tr>
        <tr>
          <td>يُخصم: التكاليف الثابتة</td>
          <td>560,600</td><td>605,448</td><td>678,102</td><td>766,255</td><td>873,531</td>
        </tr>
        <tr>
          <td><strong>صافي الأرباح قبل الزكاة</strong></td>
          <td>6,655,200</td><td>6,970,458</td><td>7,957,270</td><td>8,904,959</td><td>10,054,486</td>
        </tr>
        <tr>
          <td>مصروف الزكاة 2.5%</td>
          <td>166,380</td><td>174,261</td><td>198,932</td><td>222,624</td><td>251,362</td>
        </tr>
        <tr class="income-net">
          <td><strong>صافي الربح (Net Income)</strong></td>
          <td><strong style="color:var(--cyan); font-size:1.05rem;">6,488,820</strong></td>
          <td><strong style="color:var(--cyan);">6,796,197</strong></td>
          <td><strong style="color:var(--cyan);">7,758,338</strong></td>
          <td><strong style="color:var(--cyan);">8,682,335</strong></td>
          <td><strong style="color:var(--cyan);">9,803,124</strong></td>
        </tr>
      </tbody>
    </table>
  </div>

  <!-- Summary Cards -->
  <div style="display:grid; grid-template-columns:repeat(3,1fr); gap:24px; margin-top:40px;">
    <div class="card" style="text-align:center; background:rgba(0,212,255,0.06);">
      <div style="font-size:0.85rem; color:var(--text-dim); margin-bottom:8px;">صافي ربح السنة الأولى</div>
      <div style="font-size:2.2rem; font-weight:900; color:var(--cyan);">6.49M</div>
      <div style="font-size:0.8rem; color:var(--text-dim);">ريال سعودي</div>
    </div>
    <div class="card" style="text-align:center;">
      <div style="font-size:0.85rem; color:var(--text-dim); margin-bottom:8px;">صافي ربح السنة الخامسة</div>
      <div style="font-size:2.2rem; font-weight:900; color:var(--gold);">9.80M</div>
      <div style="font-size:0.8rem; color:var(--text-dim);">ريال سعودي</div>
    </div>
    <div class="card" style="text-align:center; background:rgba(240,192,64,0.05);">
      <div style="font-size:0.85rem; color:var(--text-dim); margin-bottom:8px;">نمو الأرباح (5 سنوات)</div>
      <div style="font-size:2.2rem; font-weight:900; color:var(--gold);">+51%</div>
      <div style="font-size:0.8rem; color:var(--text-dim);">نسبة النمو التراكمي</div>
    </div>
  </div>
</section>

<footer>
  <div style="font-size:1.3rem; font-weight:800; color:var(--cyan); margin-bottom:8px;">✦ مشروع التصميم الإبداعي</div>
  <div>خطة أعمال ريادية — <span>جميع الأرقام بالريال السعودي</span></div>
</footer>

<script>
  function showOp(id) {
    document.querySelectorAll('.op-section').forEach(s => s.classList.remove('active'));
    document.querySelectorAll('.op-tab').forEach(t => t.classList.remove('active'));
    document.getElementById('op-' + id).classList.add('active');
    event.target.classList.add('active');
  }

  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.08 });

  document.querySelectorAll('.card, .swot-card, .mix-card, .be-card, .consumer-card, .table-wrap').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(24px)';
    el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
