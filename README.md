# Aufq
مشروع ريادة الأعمال أفق للتصاميم والجرافيكس، صُمِم بواسطة وليد مخلف العنزي 
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>أفق للتصاميم والجرافيكس</title>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800;900&display=swap" rel="stylesheet">
<style>
  :root {
    --deep: #010c1e;
    --cyan: #00c8f0;
    --gold: #f0c040;
    --white: #ffffff;
    --muted: rgba(255,255,255,0.6);
    --dim: rgba(255,255,255,0.35);
    --card: rgba(255,255,255,0.04);
    --border: rgba(0,200,240,0.15);
  }
  * { margin:0; padding:0; box-sizing:border-box; }
  html { scroll-behavior:smooth; }
  body {
    font-family:'Tajawal',sans-serif;
    background:var(--deep);
    color:var(--white);
    overflow-x:hidden;
  }
  body::after {
    content:'';
    position:fixed; inset:0;
    background-image:
      linear-gradient(rgba(0,200,240,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,200,240,0.03) 1px, transparent 1px);
    background-size:56px 56px;
    pointer-events:none; z-index:0;
  }

  nav {
    position:fixed; top:0; left:0; right:0; z-index:100;
    padding:14px 48px;
    display:flex; align-items:center; justify-content:space-between;
    background:rgba(1,12,30,0.92);
    backdrop-filter:blur(16px);
    border-bottom:1px solid var(--border);
  }
  .nav-logo { font-size:1.05rem; font-weight:800; color:var(--cyan); }
  .nav-links { display:flex; gap:24px; list-style:none; }
  .nav-links a { color:var(--muted); text-decoration:none; font-size:0.85rem; font-weight:500; transition:color 0.2s; }
  .nav-links a:hover { color:var(--cyan); }

  .wrap { position:relative; z-index:1; max-width:1200px; margin:0 auto; padding:88px 48px; }

  .sec-tag { color:var(--cyan); font-size:0.72rem; font-weight:700; letter-spacing:3px; text-transform:uppercase; opacity:0.75; display:block; margin-bottom:8px; }
  .sec-title { font-size:clamp(1.5rem,2.8vw,2.2rem); font-weight:800; margin-bottom:6px; }
  .sec-title span { color:var(--cyan); }
  .line { width:44px; height:2px; background:var(--cyan); border-radius:2px; margin:12px 0 36px; opacity:0.45; }

  /* COVER */
  #cover {
    min-height:100vh;
    display:flex; flex-direction:column;
    justify-content:center; align-items:center;
    text-align:center; padding:110px 48px 70px;
    position:relative; z-index:1;
    background:radial-gradient(ellipse 65% 55% at 50% 40%, rgba(0,55,140,0.28) 0%, transparent 68%);
  }
  .ksu-badge {
    display:flex; align-items:center; gap:12px;
    background:rgba(255,255,255,0.05);
    border:1px solid var(--border);
    border-radius:10px; padding:12px 22px;
    margin-bottom:36px; font-size:0.88rem; color:var(--muted);
  }
  .ksu-badge strong { color:var(--white); }
  .cover-tag { font-size:0.75rem; font-weight:700; letter-spacing:3px; color:var(--cyan); opacity:0.8; margin-bottom:14px; text-transform:uppercase; }
  .cover-title { font-size:clamp(2.2rem,5vw,3.8rem); font-weight:900; line-height:1.2; margin-bottom:14px; }
  .cover-title span { color:var(--cyan); text-shadow:0 0 28px rgba(0,200,240,0.35); }
  .cover-sub { font-size:0.96rem; color:var(--muted); margin-bottom:44px; line-height:1.75; max-width:520px; }
  .cover-stats { display:flex; gap:44px; justify-content:center; margin-bottom:48px; flex-wrap:wrap; }
  .cstat-n { font-size:1.8rem; font-weight:900; color:var(--cyan); }
  .cstat-l { font-size:0.75rem; color:var(--dim); margin-top:3px; }
  .team-box { display:flex; gap:18px; justify-content:center; flex-wrap:wrap; margin-bottom:36px; }
  .team-card {
    background:var(--card); border:1px solid var(--border);
    border-radius:12px; padding:18px 28px; text-align:center; min-width:210px;
  }
  .team-card .role { font-size:0.68rem; color:var(--cyan); font-weight:700; letter-spacing:2px; margin-bottom:7px; }
  .team-card .name { font-size:0.98rem; font-weight:700; margin-bottom:4px; }
  .team-card .id { font-size:0.78rem; color:var(--dim); }
  .team-card .phone { font-size:0.76rem; color:var(--muted); margin-top:3px; direction:ltr; }
  .meta-row { display:flex; gap:28px; justify-content:center; flex-wrap:wrap; font-size:0.83rem; color:var(--muted); }
  .meta-row span strong { color:var(--white); }
  .btn-down {
    display:inline-block; margin-top:32px;
    background:linear-gradient(135deg, var(--cyan), #0070cc);
    color:var(--white); text-decoration:none;
    padding:11px 30px; border-radius:8px;
    font-family:inherit; font-size:0.92rem; font-weight:700;
    box-shadow:0 0 22px rgba(0,200,240,0.22);
    transition:transform 0.2s, box-shadow 0.2s; border:none; cursor:pointer;
  }
  .btn-down:hover { transform:translateY(-2px); box-shadow:0 0 36px rgba(0,200,240,0.38); }

  .divider { position:relative; z-index:1; height:1px; background:linear-gradient(90deg,transparent,var(--cyan),transparent); opacity:0.11; margin:0 48px; }

  /* TABLE */
  .tbl-wrap { overflow-x:auto; border-radius:10px; border:1px solid var(--border); }
  table { width:100%; border-collapse:collapse; font-size:0.86rem; }
  thead tr { background:rgba(0,200,240,0.09); }
  thead th { padding:13px 16px; color:var(--cyan); font-weight:700; text-align:right; border-bottom:1px solid var(--border); font-size:0.8rem; }
  tbody tr { border-bottom:1px solid rgba(255,255,255,0.04); transition:background 0.15s; }
  tbody tr:hover { background:rgba(0,200,240,0.03); }
  tbody tr:last-child { border-bottom:none; }
  tbody td { padding:11px 16px; color:rgba(255,255,255,0.8); text-align:right; }
  .tot td { background:rgba(0,200,240,0.07); font-weight:800; color:var(--white); }
  .hl td { background:rgba(0,200,240,0.04); }
  .net td { background:rgba(0,200,240,0.1); font-weight:800; }
  .yel { color:var(--gold) !important; font-weight:700; }
  .cyn { color:var(--cyan) !important; font-weight:700; }
  .badge { display:inline-block; padding:3px 9px; border-radius:18px; font-size:0.73rem; font-weight:600; }
  .bh { background:rgba(0,200,240,0.11); color:var(--cyan); }
  .bm { background:rgba(240,192,64,0.11); color:var(--gold); }

  /* CARDS */
  .card { background:var(--card); border:1px solid var(--border); border-radius:12px; padding:24px; transition:border-color 0.3s, transform 0.3s; }
  .card:hover { border-color:rgba(0,200,240,0.32); transform:translateY(-3px); }

  .g2 { display:grid; grid-template-columns:1fr 1fr; gap:20px; }
  .g3 { display:grid; grid-template-columns:1fr 1fr 1fr; gap:18px; }
  .g5 { display:grid; grid-template-columns:repeat(5,1fr); gap:12px; }

  .dot-item { display:flex; gap:11px; align-items:flex-start; margin-bottom:12px; font-size:0.88rem; color:rgba(255,255,255,0.78); line-height:1.6; }
  .dot { width:14px; height:14px; border-radius:50%; border:2px solid var(--cyan); flex-shrink:0; margin-top:3px; background:rgba(0,200,240,0.07); }

  .swot-s { background:rgba(0,200,240,0.04); border:1px solid rgba(0,200,240,0.18); border-radius:12px; padding:24px; }
  .swot-w { background:rgba(255,80,80,0.04); border:1px solid rgba(255,80,80,0.16); border-radius:12px; padding:24px; }
  .swot-s h3 { color:var(--cyan); font-size:0.97rem; margin-bottom:16px; }
  .swot-w h3 { color:#ff6666; font-size:0.97rem; margin-bottom:16px; }
  .si { display:flex; gap:9px; margin-bottom:11px; font-size:0.86rem; color:rgba(255,255,255,0.76); line-height:1.6; }
  .sn { color:var(--cyan); font-weight:800; flex-shrink:0; }
  .swot-w .sn { color:#ff6666; }

  .tabs { display:flex; gap:8px; margin-bottom:22px; flex-wrap:wrap; }
  .tab { padding:6px 16px; border-radius:6px; font-family:inherit; font-size:0.8rem; font-weight:600; cursor:pointer; border:1px solid var(--border); background:transparent; color:var(--dim); transition:all 0.2s; }
  .tab.on, .tab:hover { background:rgba(0,200,240,0.09); border-color:var(--cyan); color:var(--cyan); }
  .op { display:none; }
  .op.on { display:block; }

  .be-c { background:var(--card); border:1px solid var(--border); border-radius:9px; padding:18px 10px; text-align:center; }
  .be-y { font-size:0.7rem; color:var(--dim); margin-bottom:7px; font-weight:600; letter-spacing:1px; }
  .be-u { font-size:1.35rem; font-weight:900; color:var(--cyan); margin-bottom:4px; }
  .be-s { font-size:0.72rem; color:var(--dim); }

  .mix { background:var(--card); border:1px solid var(--border); border-radius:12px; padding:24px; text-align:center; transition:all 0.3s; }
  .mix:hover { border-color:rgba(0,200,240,0.32); transform:translateY(-3px); }
  .mix-i { font-size:2rem; margin-bottom:12px; }
  .mix h3 { color:var(--cyan); font-size:0.97rem; margin-bottom:9px; }
  .mix p { color:var(--muted); font-size:0.85rem; line-height:1.65; }

  footer { position:relative; z-index:1; text-align:center; padding:36px; border-top:1px solid var(--border); color:var(--dim); font-size:0.82rem; }
  footer span { color:var(--cyan); }

  .fade { opacity:0; transform:translateY(16px); transition:opacity 0.5s ease, transform 0.5s ease; }
  .fade.in { opacity:1; transform:translateY(0); }

  @media(max-width:860px){
    nav{padding:12px 18px;}
    .nav-links{gap:12px;font-size:0.77rem;}
    .wrap{padding:70px 18px;}
    .g2,.g3,.g5{grid-template-columns:1fr;}
    .cover-stats{gap:24px;}
  }
</style>
</head>
<body>

<nav>
  <div class="nav-logo">✦ أفق للتصاميم والجرافيكس</div>
  <ul class="nav-links">
    <li><a href="#consumers">المستهلكون</a></li>
    <li><a href="#market">السوق</a></li>
    <li><a href="#competitive">الميزة</a></li>
    <li><a href="#marketing">التسويق</a></li>
    <li><a href="#operational">التشغيل</a></li>
    <li><a href="#financial">المالية</a></li>
  </ul>
</nav>

<!-- COVER -->
<div id="cover">
  <div class="ksu-badge">
    <span>🎓</span>
    <div><strong>جامعة الملك سعود</strong><br>مقرر ريادة الأعمال — الفصل الدراسي الثاني 1447 هـ</div>
  </div>
  <div class="cover-tag">دراسة الجدوى الاقتصادية</div>
  <h1 class="cover-title">أفق<br><span>للتصاميم والجرافيكس</span></h1>
  <p class="cover-sub">مشروع ريادي متخصص في تصميم الهوية البصرية، الشعارات،<br>الإعلانات الرقمية وتغليف المنتجات</p>
  <div class="cover-stats">
    <div class="cstat"><div class="cstat-n">7.25M</div><div class="cstat-l">إيرادات السنة الأولى</div></div>
    <div class="cstat"><div class="cstat-n">6.49M</div><div class="cstat-l">صافي الربح الأول</div></div>
    <div class="cstat"><div class="cstat-n">62,750</div><div class="cstat-l">إجمالي الاستثمار (ريال)</div></div>
    <div class="cstat"><div class="cstat-n">4</div><div class="cstat-l">خدمات رئيسية</div></div>
  </div>
  <div class="team-box">
    <div class="team-card">
      <div class="role">قائد المجموعة</div>
      <div class="name">وليد مخلف العنزي</div>
      <div class="id">446101289</div>
      <div class="phone">0537441043</div>
    </div>
    <div class="team-card">
      <div class="role">عضو المجموعة</div>
      <div class="name">طلال منصور المرشود</div>
      <div class="id">447104819</div>
      <div class="phone">0558980553</div>
    </div>
  </div>
  <div class="meta-row">
    <span>رقم الشعبة: <strong>87515</strong></span>
    <span>إشراف: <strong>د. مشاري الراجح</strong></span>
  </div>
  <a href="#consumers" class="btn-down">استعراض خطة الأعمال ↓</a>
</div>

<div class="divider"></div>

<!-- CONSUMERS -->
<div class="wrap" id="consumers">
  <span class="sec-tag">Consumers</span>
  <h2 class="sec-title"><span>المستهلكون</span></h2>
  <div class="line"></div>
  <div class="g2">
    <div class="card fade">
      <h3 style="color:var(--cyan);font-size:0.97rem;margin-bottom:16px;">من هم؟</h3>
      <div class="dot-item"><div class="dot"></div><div>طلاب، رواد أعمال، شركات ناشئة، مؤسسات صغيرة</div></div>
      <div class="dot-item"><div class="dot"></div><div>السوق يلبي احتياجاتهم جزئياً — يبحثون عن جودة أعلى وسرعة تنفيذ</div></div>
      <div class="dot-item"><div class="dot"></div><div>القدرة الشرائية: <strong style="color:var(--cyan)">معتدلة إلى قوية</strong></div></div>
    </div>
    <div class="card fade">
      <h3 style="color:var(--cyan);font-size:0.97rem;margin-bottom:16px;">التطلعات والمطلوب</h3>
      <div class="dot-item"><div class="dot"></div><div>الجمع بين الجودة والسعر المناسب (النوعية + السعر معاً)</div></div>
      <div class="dot-item"><div class="dot"></div><div>تصاميم أكثر تميزاً وتفاعلاً مع العميل</div></div>
      <div class="dot-item"><div class="dot"></div><div>الشراء عبر الإنترنت أو التواصل المباشر — دفع بنكي أو إلكتروني</div></div>
    </div>
  </div>
</div>

<div class="divider"></div>

<!-- MARKET -->
<div class="wrap" id="market">
  <span class="sec-tag">Market Analysis</span>
  <h2 class="sec-title">تحليل <span>السوق</span></h2>
  <div class="line"></div>
  <div class="tbl-wrap fade" style="margin-bottom:32px;">
    <table>
      <thead><tr><th>المنافس</th><th>المنتجات</th><th>مناطق المشروع</th><th>مناطق التسويق</th><th>السعر</th><th>الجودة</th></tr></thead>
      <tbody>
        <tr><td><strong>زد ديزاين</strong></td><td>شعارات، بوسترات، سوشيال ميديا</td><td>عبر الإنترنت</td><td>عبر الإنترنت</td><td>متوسط</td><td><span class="badge bh">مرتفعة</span></td></tr>
        <tr><td><strong>براند مي</strong></td><td>هويات بصرية</td><td>الرياض - أونلاين</td><td>عبر الإنترنت</td><td>مرتفع</td><td><span class="badge bh">مرتفعة</span></td></tr>
        <tr><td><strong>تصميمي</strong></td><td>تصاميم جاهزة وسريعة</td><td>المملكة العامة</td><td>عبر الإنترنت</td><td>منخفض</td><td><span class="badge bm">متوسطة</span></td></tr>
      </tbody>
    </table>
  </div>
  <h3 style="font-size:1rem;margin-bottom:18px;">السوق المستهدف</h3>
  <div class="g2 fade">
    <div class="card">
      <h4 style="color:var(--cyan);font-size:0.87rem;margin-bottom:14px;">رغبة العملاء</h4>
      <div class="dot-item"><div class="dot"></div><div><strong>ماذا يشترون؟</strong> تصاميم تعبّر عن هويتهم وتزيد ظهورهم</div></div>
      <div class="dot-item"><div class="dot"></div><div><strong>متى؟</strong> عند إطلاق مشاريعهم أو حملاتهم الإعلانية</div></div>
      <div class="dot-item"><div class="dot"></div><div><strong>كيف؟</strong> تحويل بنكي أو دفع إلكتروني</div></div>
      <div class="dot-item"><div class="dot"></div><div><strong>التكرار؟</strong> متوسط إلى مرتفع حسب الحملات</div></div>
    </div>
    <div class="tbl-wrap">
      <table>
        <thead><tr><th>فئة العملاء</th><th>العمر</th><th>القدرة الشرائية</th><th>أسلوب الشراء</th></tr></thead>
        <tbody>
          <tr><td><strong>القطاع الحكومي</strong></td><td>18-35</td><td>معتدلة</td><td>إنترنت</td></tr>
          <tr><td><strong>القطاع الخاص</strong></td><td>25-45</td><td><span class="badge bh">قوية</span></td><td>تعاقد مباشر</td></tr>
          <tr><td><strong>تجار التجزئة</strong></td><td>18-45</td><td>معتدلة</td><td>إنترنت</td></tr>
          <tr><td><strong>تجار الجملة</strong></td><td>18-45</td><td>معتدلة</td><td>إنترنت</td></tr>
          <tr><td><strong>الأفراد</strong></td><td>18-60</td><td><span class="badge bh">قوية</span></td><td>إنترنت</td></tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

<div class="divider"></div>

<!-- COMPETITIVE -->
<div class="wrap" id="competitive">
  <span class="sec-tag">Competitive Advantage</span>
  <h2 class="sec-title">الميزة <span>التنافسية</span></h2>
  <div class="line"></div>
  <div class="g2">
    <div class="swot-s fade">
      <h3>✦ نقاط القوة</h3>
      <div class="si"><div class="dot" style="border-color:var(--cyan);margin-top:3px;flex-shrink:0;width:14px;height:14px;border-radius:50%;border:2px solid var(--cyan);background:rgba(0,200,240,0.07);"></div><div>أسعار مناسبة، تواصل مباشر، تصاميم مخصصة لكل عميل</div></div>
      <div class="si"><span class="sn">1.</span><div><strong>الإبداع والابتكار:</strong> تصاميم فريدة وجذابة تتماشى مع احتياجات العملاء</div></div>
      <div class="si"><span class="sn">2.</span><div><strong>أدوات حديثة:</strong> أحدث برامج التصميم مما يزيد جودة الإنتاج</div></div>
      <div class="si"><span class="sn">3.</span><div><strong>خدمة مميزة:</strong> سرعة الاستجابة ومرونة التعامل مع طلبات العملاء</div></div>
    </div>
    <div class="swot-w fade">
      <h3>✗ نقاط الضعف</h3>
      <div class="si"><div class="dot" style="border-color:#ff6666;margin-top:3px;flex-shrink:0;width:14px;height:14px;border-radius:50%;border:2px solid #ff6666;background:rgba(255,80,80,0.07);"></div><div>فريق صغير في البداية</div></div>
      <div class="si"><span class="sn">1.</span><div><strong>قلة الخبرة السوقية:</strong> صعوبة فهم سلوك العملاء والمنافسين بالكامل</div></div>
      <div class="si"><span class="sn">2.</span><div><strong>اعتماد على الأفراد:</strong> غياب أحد الأعضاء قد يؤثر على الإنتاجية</div></div>
      <div class="si"><span class="sn">3.</span><div><strong>التسويق المحدود:</strong> عدم وجود خطة تسويقية قوية قد يحد من وصول المشروع</div></div>
    </div>
  </div>
</div>

<div class="divider"></div>

<!-- MARKETING -->
<div class="wrap" id="marketing">
  <span class="sec-tag">Marketing Mix</span>
  <h2 class="sec-title">المزيج <span>التسويقي</span></h2>
  <div class="line"></div>
  <div class="g3">
    <div class="mix fade"><div class="mix-i">🎨</div><h3>المنتج</h3><p>تصاميم شعارات، هوية بصرية، إعلانات رقمية، تغليف منتجات</p></div>
    <div class="mix fade"><div class="mix-i">💰</div><h3>السعر</h3><p>من <strong style="color:var(--gold)">100 ريال</strong> للتصميم البسيط حتى <strong style="color:var(--gold)">1500 ريال</strong> للهوية الكاملة</p></div>
    <div class="mix fade"><div class="mix-i">📣</div><h3>الترويج</h3><p>إنستقرام، سناب، X — إعلانات ممولة وعروض خاصة</p></div>
  </div>
</div>

<div class="divider"></div>

<!-- OPERATIONAL -->
<div class="wrap" id="operational">
  <span class="sec-tag">Operational Plan</span>
  <h2 class="sec-title">الخطة <span>التشغيلية</span></h2>
  <div class="line"></div>
  <div class="tabs">
    <button class="tab on" onclick="sw('sales',this)">التنبؤ بالمبيعات</button>
    <button class="tab" onclick="sw('invest',this)">التكاليف الاستثمارية</button>
    <button class="tab" onclick="sw('fixed',this)">التكاليف الثابتة</button>
    <button class="tab" onclick="sw('variable',this)">التكاليف المتغيرة</button>
    <button class="tab" onclick="sw('total',this)">إجمالي التكاليف</button>
  </div>

  <div class="op on" id="op-sales">
    <div class="g2" style="margin-bottom:18px;">
      <div>
        <p style="font-size:0.76rem;color:var(--muted);margin-bottom:10px;">عدد الوحدات المتوقع بيعها</p>
        <div class="tbl-wrap"><table>
          <thead><tr><th>المنتج</th><th>العدد</th><th>س1</th><th>س2</th><th>س3</th><th>س4</th><th>س5</th></tr></thead>
          <tbody>
            <tr><td class="yel">هوية بصرية</td><td class="yel">1,000</td><td>1,000</td><td>1,050</td><td>1,155</td><td>1,294</td><td>1,462</td></tr>
            <tr><td class="yel">شعار</td><td class="yel">3,000</td><td>3,000</td><td>3,150</td><td>3,465</td><td>3,881</td><td>4,385</td></tr>
            <tr><td class="yel">مطبوعات</td><td class="yel">7,000</td><td>7,000</td><td>7,350</td><td>8,085</td><td>9,055</td><td>10,232</td></tr>
            <tr><td class="yel">إعلانات</td><td class="yel">500</td><td>500</td><td>525</td><td>578</td><td>647</td><td>731</td></tr>
            <tr class="tot"><td colspan="2">الإجمالي</td><td>11,500</td><td>12,075</td><td>13,283</td><td>14,876</td><td>16,810</td></tr>
          </tbody>
        </table></div>
      </div>
      <div>
        <p style="font-size:0.76rem;color:var(--muted);margin-bottom:10px;">قيمة المبيعات (ريال)</p>
        <div class="tbl-wrap"><table>
          <thead><tr><th>المنتج</th><th>السعر</th><th>س1</th><th>س2</th><th>س3</th><th>س4</th><th>س5</th></tr></thead>
          <tbody>
            <tr><td>هوية بصرية</td><td class="yel">1,500</td><td>1,500,000</td><td>1,575,000</td><td>1,732,500</td><td>1,940,400</td><td>2,192,652</td></tr>
            <tr><td>شعار</td><td class="yel">350</td><td>1,050,000</td><td>1,102,500</td><td>1,267,875</td><td>1,420,020</td><td>1,604,623</td></tr>
            <tr><td>مطبوعات</td><td class="yel">600</td><td>4,200,000</td><td>4,410,000</td><td>5,071,500</td><td>5,680,080</td><td>6,418,490</td></tr>
            <tr><td>إعلانات</td><td class="yel">1,000</td><td>500,000</td><td>525,000</td><td>603,750</td><td>676,200</td><td>764,106</td></tr>
            <tr class="tot"><td>الإجمالي</td><td class="cyn">3,450</td><td>7,250,000</td><td>7,612,500</td><td>8,675,625</td><td>9,716,700</td><td>10,979,871</td></tr>
          </tbody>
        </table></div>
      </div>
    </div>
  </div>

  <div class="op" id="op-invest">
    <div class="g3">
      <div class="card">
        <h4 style="color:var(--cyan);font-size:0.85rem;margin-bottom:12px;">أ) الآلات والمعدات</h4>
        <div class="tbl-wrap"><table>
          <thead><tr><th>البند</th><th>التكلفة</th></tr></thead>
          <tbody>
            <tr><td class="yel">برامج تصميم</td><td>7,500</td></tr>
            <tr><td class="yel">أجهزة حاسب</td><td>20,000</td></tr>
            <tr><td class="yel">طابعات/سكانر</td><td>3,000</td></tr>
            <tr><td class="yel">أدوات الرسم</td><td>500</td></tr>
            <tr><td class="yel">إنترنت وشبكات</td><td>6,000</td></tr>
            <tr><td class="yel">أدوات مكتبية</td><td>4,000</td></tr>
            <tr class="tot"><td>المجموع</td><td>41,000</td></tr>
          </tbody>
        </table></div>
      </div>
      <div class="card">
        <h4 style="color:var(--cyan);font-size:0.85rem;margin-bottom:12px;">ب) الأثاث والديكور</h4>
        <div class="tbl-wrap"><table>
          <thead><tr><th>البند</th><th>التكلفة</th></tr></thead>
          <tbody>
            <tr><td class="yel">كراسي</td><td>3,500</td></tr>
            <tr><td class="yel">طاولات</td><td>5,000</td></tr>
            <tr><td class="yel">أثاث مكتبي</td><td>1,200</td></tr>
            <tr><td class="yel">ديكورات</td><td>800</td></tr>
            <tr><td class="yel">سيراميك</td><td>1,000</td></tr>
            <tr><td class="yel">دهانات</td><td>450</td></tr>
            <tr><td class="yel">ستائر</td><td>1,000</td></tr>
            <tr><td class="yel">عدد وأدوات</td><td>500</td></tr>
            <tr class="tot"><td>المجموع</td><td>13,450</td></tr>
          </tbody>
        </table></div>
      </div>
      <div class="card">
        <h4 style="color:var(--cyan);font-size:0.85rem;margin-bottom:12px;">ج) تكاليف التأسيس</h4>
        <div class="tbl-wrap"><table>
          <thead><tr><th>البند</th><th>التكلفة</th></tr></thead>
          <tbody>
            <tr><td>رسوم تراخيص</td><td>1,000</td></tr>
            <tr><td>تأسيس الموقع</td><td>1,300</td></tr>
            <tr><td>مصاريف حكومية</td><td>2,000</td></tr>
            <tr><td>مصاريف أخرى</td><td>4,000</td></tr>
            <tr class="tot"><td>المجموع</td><td>8,300</td></tr>
          </tbody>
        </table></div>
        <div style="margin-top:14px;text-align:center;padding:12px;background:rgba(0,200,240,0.06);border-radius:8px;border:1px solid var(--border);">
          <div style="font-size:0.72rem;color:var(--muted);margin-bottom:4px;">إجمالي التكاليف الاستثمارية</div>
          <div style="font-size:1.7rem;font-weight:900;color:var(--cyan);">62,750</div>
          <div style="font-size:0.72rem;color:var(--muted);">ريال سعودي</div>
        </div>
      </div>
    </div>
  </div>

  <div class="op" id="op-fixed">
    <div class="tbl-wrap"><table>
      <thead><tr><th>البيان</th><th>السنة الأولى</th><th>السنة الثانية (8%)</th><th>السنة الثالثة (12%)</th><th>السنة الرابعة (13%)</th><th>السنة الخامسة (14%)</th></tr></thead>
      <tbody>
        <tr><td class="yel">الإيجار</td><td>45,000</td><td>48,600</td><td>54,432</td><td>61,508</td><td>70,119</td></tr>
        <tr><td class="yel">الرواتب</td><td>500,000</td><td>540,000</td><td>604,800</td><td>683,424</td><td>779,103</td></tr>
        <tr><td class="yel">صيانة الآلات</td><td>9,000</td><td>9,720</td><td>10,886</td><td>12,302</td><td>14,024</td></tr>
        <tr><td class="yel">التأمين</td><td>2,000</td><td>2,160</td><td>2,419</td><td>2,734</td><td>3,116</td></tr>
        <tr><td class="yel">مصاريف أخرى</td><td>1,900</td><td>2,052</td><td>2,298</td><td>2,597</td><td>2,961</td></tr>
        <tr><td class="yel">تكاليف ثابتة أخرى</td><td>2,700</td><td>2,916</td><td>3,266</td><td>3,690</td><td>4,207</td></tr>
        <tr class="tot"><td>الإجمالي الثابت</td><td>560,600</td><td>605,448</td><td>678,102</td><td>766,255</td><td>873,531</td></tr>
      </tbody>
    </table></div>
  </div>

  <div class="op" id="op-variable">
    <div class="tbl-wrap"><table>
      <thead><tr><th>البيان</th><th>السنة الأولى</th><th>السنة الثانية (7%)</th><th>السنة الثالثة (10%)</th><th>السنة الرابعة (13%)</th><th>السنة الخامسة (14%)</th></tr></thead>
      <tbody>
        <tr><td class="yel">المواد الخام</td><td>5,000</td><td>5,350</td><td>5,885</td><td>6,650</td><td>7,581</td></tr>
        <tr><td class="yel">الأجور</td><td>20,000</td><td>21,400</td><td>23,540</td><td>26,600</td><td>30,324</td></tr>
        <tr><td class="yel">فواتير الكهرباء والماء</td><td>5,000</td><td>5,350</td><td>5,885</td><td>6,650</td><td>7,581</td></tr>
        <tr><td class="yel">أجور توصيل البضائع</td><td>1,200</td><td>1,284</td><td>1,412</td><td>1,596</td><td>1,819</td></tr>
        <tr><td class="yel">مصاريف أخرى</td><td>1,000</td><td>1,070</td><td>1,177</td><td>1,330</td><td>1,516</td></tr>
        <tr><td class="yel">تكاليف متغيرة أخرى</td><td>2,000</td><td>2,140</td><td>2,354</td><td>2,660</td><td>3,032</td></tr>
        <tr class="tot"><td>الإجمالي المتغير</td><td>34,200</td><td>36,594</td><td>40,253</td><td>45,486</td><td>51,854</td></tr>
      </tbody>
    </table></div>
  </div>

  <div class="op" id="op-total">
    <div class="tbl-wrap"><table>
      <thead><tr><th>البيان</th><th>السنة الأولى</th><th>السنة الثانية</th><th>السنة الثالثة</th><th>السنة الرابعة</th><th>السنة الخامسة</th></tr></thead>
      <tbody>
        <tr><td>التكاليف الاستثمارية</td><td>12,550</td><td>12,550</td><td>12,550</td><td>12,550</td><td>12,550</td></tr>
        <tr><td>إجمالي التشغيلية</td><td>594,800</td><td>642,042</td><td>718,355</td><td>811,741</td><td>925,385</td></tr>
        <tr class="tot"><td>إجمالي التكاليف</td><td>607,350</td><td>654,592</td><td>730,905</td><td>824,291</td><td>937,935</td></tr>
        <tr class="hl"><td>÷ عدد الوحدات</td><td>11,960</td><td>12,679</td><td>14,079</td><td>15,918</td><td>18,155</td></tr>
        <tr class="net"><td><strong>تكلفة الوحدة الواحدة</strong></td><td class="cyn">51</td><td class="cyn">52</td><td class="cyn">52</td><td class="cyn">52</td><td class="cyn">52</td></tr>
      </tbody>
    </table></div>
  </div>
</div>

<div class="divider"></div>

<!-- BREAKEVEN -->
<div class="wrap" id="breakeven">
  <span class="sec-tag">Break-Even Point</span>
  <h2 class="sec-title">نقطة <span>التعادل</span></h2>
  <div class="line"></div>
  <div class="tbl-wrap fade" style="margin-bottom:20px;">
    <table>
      <thead><tr><th>البيان</th><th>السنة الأولى</th><th>السنة الثانية</th><th>السنة الثالثة</th><th>السنة الرابعة</th><th>السنة الخامسة</th></tr></thead>
      <tbody>
        <tr><td>التكاليف الثابتة</td><td>560,600</td><td>605,448</td><td>678,102</td><td>766,255</td><td>873,531</td></tr>
        <tr><td>متوسط سعر البيع</td><td>863</td><td>863</td><td>863</td><td>863</td><td>863</td></tr>
        <tr><td>التكلفة المتغيرة/وحدة</td><td>3</td><td>3</td><td>3</td><td>3</td><td>3</td></tr>
        <tr class="hl"><td><strong>نقطة التعادل (وحدات)</strong></td><td class="cyn">652</td><td class="cyn">704</td><td class="cyn">789</td><td class="cyn">891</td><td class="cyn">1,016</td></tr>
        <tr class="net"><td><strong>نقطة التعادل (ريال)</strong></td><td>562,465</td><td>607,481</td><td>680,357</td><td>768,802</td><td>876,433</td></tr>
      </tbody>
    </table>
  </div>
  <div class="g5">
    <div class="be-c fade"><div class="be-y">السنة الأولى</div><div class="be-u">652</div><div class="be-s">562,465 ريال</div></div>
    <div class="be-c fade"><div class="be-y">السنة الثانية</div><div class="be-u">704</div><div class="be-s">607,481 ريال</div></div>
    <div class="be-c fade"><div class="be-y">السنة الثالثة</div><div class="be-u">789</div><div class="be-s">680,357 ريال</div></div>
    <div class="be-c fade"><div class="be-y">السنة الرابعة</div><div class="be-u">891</div><div class="be-s">768,802 ريال</div></div>
    <div class="be-c fade"><div class="be-y">السنة الخامسة</div><div class="be-u">1,016</div><div class="be-s">876,433 ريال</div></div>
  </div>
</div>

<div class="divider"></div>

<!-- FINANCIAL -->
<div class="wrap" id="financial">
  <span class="sec-tag">Financial Plan</span>
  <h2 class="sec-title">قائمة <span>الدخل</span></h2>
  <div class="line"></div>
  <div class="tbl-wrap fade" style="margin-bottom:24px;">
    <table>
      <thead><tr><th>البيان</th><th>السنة الأولى</th><th>السنة الثانية</th><th>السنة الثالثة</th><th>السنة الرابعة</th><th>السنة الخامسة</th></tr></thead>
      <tbody>
        <tr class="hl"><td><strong>المبيعات (Sales)</strong></td><td><strong>7,250,000</strong></td><td><strong>7,612,500</strong></td><td><strong>8,675,625</strong></td><td><strong>9,716,700</strong></td><td><strong>10,979,871</strong></td></tr>
        <tr><td>يُخصم: التكاليف المتغيرة</td><td>34,200</td><td>36,594</td><td>40,253</td><td>45,486</td><td>51,854</td></tr>
        <tr><td><strong>مجمل ربح التشغيل</strong></td><td>7,215,800</td><td>7,575,906</td><td>8,635,372</td><td>9,671,214</td><td>10,928,017</td></tr>
        <tr><td>يُخصم: التكاليف الثابتة</td><td>560,600</td><td>605,448</td><td>678,102</td><td>766,255</td><td>873,531</td></tr>
        <tr><td><strong>صافي الأرباح قبل الزكاة</strong></td><td>6,655,200</td><td>6,970,458</td><td>7,957,270</td><td>8,904,959</td><td>10,054,486</td></tr>
        <tr><td>مصروف الزكاة 2.5%</td><td>166,380</td><td>174,261</td><td>198,932</td><td>222,624</td><td>251,362</td></tr>
        <tr class="net"><td><strong>صافي الربح (Net Income)</strong></td><td class="cyn">6,488,820</td><td class="cyn">6,796,197</td><td class="cyn">7,758,338</td><td class="cyn">8,682,335</td><td class="cyn">9,803,124</td></tr>
      </tbody>
    </table>
  </div>
  <div class="g3 fade">
    <div class="card" style="text-align:center;background:rgba(0,200,240,0.04);">
      <div style="font-size:0.75rem;color:var(--muted);margin-bottom:5px;">صافي ربح السنة الأولى</div>
      <div style="font-size:1.9rem;font-weight:900;color:var(--cyan);">6.49M</div>
      <div style="font-size:0.72rem;color:var(--muted);">ريال سعودي</div>
    </div>
    <div class="card" style="text-align:center;">
      <div style="font-size:0.75rem;color:var(--muted);margin-bottom:5px;">صافي ربح السنة الخامسة</div>
      <div style="font-size:1.9rem;font-weight:900;color:var(--gold);">9.80M</div>
      <div style="font-size:0.72rem;color:var(--muted);">ريال سعودي</div>
    </div>
    <div class="card" style="text-align:center;background:rgba(240,192,64,0.03);">
      <div style="font-size:0.75rem;color:var(--muted);margin-bottom:5px;">نمو الأرباح (5 سنوات)</div>
      <div style="font-size:1.9rem;font-weight:900;color:var(--gold);">+51%</div>
      <div style="font-size:0.72rem;color:var(--muted);">نسبة النمو التراكمي</div>
    </div>
  </div>
</div>

<footer>
  <div style="font-size:1rem;font-weight:800;color:var(--cyan);margin-bottom:5px;">✦ أفق للتصاميم والجرافيكس</div>
  <div>مقرر ريادة الأعمال — جامعة الملك سعود — الفصل الثاني 1447هـ</div>
  <div style="margin-top:5px;">إشراف: <span>د. مشاري الراجح</span> | الشعبة: <span>87515</span></div>
</footer>

<script>
  function sw(id, btn) {
    document.querySelectorAll('.op').forEach(s => s.classList.remove('on'));
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('on'));
    document.getElementById('op-' + id).classList.add('on');
    btn.classList.add('on');
  }
  const io = new IntersectionObserver(entries => {
    entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('in'); });
  }, { threshold: 0.07 });
  document.querySelectorAll('.fade').forEach(el => io.observe(el));
</script>
</body>
</html>
