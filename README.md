<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>SodaMC • Survival</title>
  <meta name="description" content="SodaMC Survival - Server Minecraft Việt Nam" />

  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg:#0b0f0a; /* dark green */
      --panel:#0f1410;
      --accent:#8bd46b; /* green */
      --accent-dark:#6db24f;
      --muted:#aeb8a8;
      --glass: rgba(255,255,255,0.04);
      --glass-2: rgba(255,255,255,0.03);
      --rounded:14px;
      --container:1200px;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Inter,system-ui,Arial;background:linear-gradient(180deg,var(--bg),#071007);color:#eaf2e8}

    /* layout */
    header{background:linear-gradient(180deg, rgba(0,0,0,0.25), rgba(0,0,0,0.6)), url('https://i.imgur.com/7yKZQfR.jpg') center/cover no-repeat; padding:28px 18px;}
    .wrap{max-width:var(--container);margin:0 auto;padding:0 20px}

    /* nav */
    nav{display:flex;align-items:center;justify-content:space-between;gap:12px}
    .logo{display:flex;align-items:center;gap:12px}
    .logo .mark{width:48px;height:48px;border-radius:10px;background:linear-gradient(135deg,var(--accent),var(--accent-dark));display:flex;align-items:center;justify-content:center;font-weight:700;color:#062007}
    .sitename{font-weight:700;font-size:20px}
    .nav-links{display:flex;gap:18px;align-items:center}
    .nav-links a{color:var(--muted);text-decoration:none;font-weight:600}
    .btn-join{background:var(--accent);color:#062007;padding:10px 16px;border-radius:10px;font-weight:700;text-decoration:none;box-shadow:0 6px 18px rgba(107,163,86,0.12)}

    /* hero */
    .hero{display:flex;flex-direction:column;align-items:flex-start;padding:50px 0}
    .hero-inner{display:flex;gap:28px;align-items:center}
    .hero-left{max-width:640px}
    .hero h1{font-size:48px;margin:0 0 10px;line-height:1.02}
    .hero p{margin:0 0 18px;color:var(--muted)}
    .hero-cta{display:flex;gap:12px}
    .ipbox{background:var(--glass);padding:10px 14px;border-radius:10px;border:1px solid rgba(255,255,255,0.03);font-weight:700}

    /* features */
    .section{padding:48px 0}
    .title{font-size:28px;color:var(--accent);margin-bottom:18px}
    .grid{display:grid;grid-template-columns:repeat(3,1fr);gap:20px}
    .card{background:linear-gradient(180deg,var(--panel),#0b1210);border-radius:var(--rounded);padding:18px;border:1px solid var(--glass-2);box-shadow:0 6px 18px rgba(0,0,0,0.4)}
    .card h3{margin:0 0 8px;color:#dff4d7}
    .muted{color:var(--muted);font-size:14px}

    /* events / top */
    .events .card{display:flex;flex-direction:column;gap:8px}
    .event-badge{display:inline-block;padding:6px 10px;border-radius:999px;background:rgba(139,212,107,0.12);color:var(--accent-dark);font-weight:700;font-size:13px}

    /* top list */
    .top-list{display:flex;flex-direction:column;gap:12px}
    .player{display:flex;align-items:center;gap:12px;padding:10px;border-radius:10px;background:linear-gradient(90deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02));border:1px solid rgba(255,255,255,0.02)}
    .avatar{width:48px;height:48px;border-radius:8px;background:#001204;display:flex;align-items:center;justify-content:center;color:var(--accent);font-weight:800}
    .player .meta{flex:1}
    .player .meta b{display:block}
    .rank{font-weight:800;color:var(--accent)}

    /* responsive */
    @media (max-width:980px){.grid{grid-template-columns:repeat(2,1fr)}.hero h1{font-size:40px}}
    @media (max-width:700px){.grid{grid-template-columns:1fr}.hero-inner{flex-direction:column;align-items:flex-start}.nav-links{display:none}}

    /* tiny helpers */
    .small{font-size:13px;color:var(--muted)}

  </style>
</head>
<body>

<header>
  <div class="wrap">
    <nav>
      <div class="logo">
        <div class="mark">SD</div>
        <div>
          <div class="sitename">SodaMC</div>
          <div class="small">Survival Server</div>
        </div>
      </div>

      <div class="nav-links">
        <a href="#news">Tin tức</a>
        <a href="#events">Sự kiện</a>
        <a href="#top">BXH</a>
        <a href="#team">Đội ngũ</a>
        <a class="btn-join" href="#join">Tham gia</a>
      </div>
    </nav>

    <div class="hero">
      <div class="hero-inner">
        <div class="hero-left">
          <h1>SodaMC • Survival</h1>
          <p>Trải nghiệm Survival thuần Việt — Kinh tế, Đất đai, Guild, Jobs, Bosss và cộng đồng thân thiện.</p>

          <div class="hero-cta">
            <div class="ipbox">IP: <strong>sodamc.com</strong></div>
            <a class="btn-join" href="#join">Vào Survival</a>
            <a href="#events" style="color:var(--muted);text-decoration:underline">Xem sự kiện</a>
          </div>

          <div style="margin-top:18px;color:var(--muted);font-size:14px">Phiên bản: <strong>1.8 - 1.21+</strong> • Chế độ: <strong>Survival</strong></div>
        </div>

        <div class="hero-right" style="margin-left:auto;min-width:280px;">
          <div class="card" style="padding:18px;">
            <h3>Live: Players Online</h3>
            <div style="font-size:36px;font-weight:800;color:var(--accent);margin-top:6px">128</div>
            <div class="small" style="margin-top:8px">Server ổn định, ping thấp — join ngay để khám phá!</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</header>

<main>
  <div class="wrap">

    <!-- Tin tức -->
    <section id="news" class="section">
      <div class="title">📢 Tin tức mới</div>
      <div class="grid">
        <article class="card">
          <h3>Reset Season 6</h3>
          <div class="small muted">Ngày: 01/01/2026</div>
          <p class="muted">Reset đã hoàn tất — nhiều cấp độ, boss và tính năng mới. Tham gia để nhận quà tân thủ.</p>
        </article>

        <article class="card">
          <h3>Update Boss Rừng</h3>
          <div class="small muted">Ngày: 05/01/2026</div>
          <p class="muted">Boss mới xuất hiện tại rừng tối — hợp tác săn boss để nhận đồ hiếm.</p>
        </article>

        <article class="card">
          <h3>Giftcode SODA</h3>
          <div class="small muted">Ngày: 10/01/2026</div>
          <p class="muted">Nhập mã <b>SODASURVIVAL</b> để nhận kit miễn phí.</p>
        </article>
      </div>
    </section>

    <!-- Events -->
    <section id="events" class="section events">
      <div class="title">🎉 Sự kiện tháng</div>
      <div class="grid">
        <div class="card">
          <span class="event-badge">Đua Top</span>
          <h3>Đua Top Coins</h3>
          <p class="muted">Top 1–3 nhận VIP & coins. Thời gian: 1 tháng.</p>
        </div>
        <div class="card">
          <span class="event-badge">Hàng tuần</span>
          <h3>Săn Boss Biển</h3>
          <p class="muted">Team săn boss nhận vật phẩm giới hạn.</p>
        </div>
        <div class="card">
          <span class="event-badge">Daily</span>
          <h3>Rương Bí Ẩn</h3>
          <p class="muted">Mỗi ngày 10 rương spawn ngẫu nhiên — ai nhanh người đó có.</p>
        </div>
      </div>
    </section>

    <!-- Top players -->
    <section id="top" class="section">
      <div class="title">🏅 Top Survival</div>
      <div class="grid">
        <div class="card">
          <h3>Top Coins</h3>
          <div class="top-list">
            <div class="player"><div class="avatar">1</div><div class="meta"><b>RichKid</b><span class="small muted">250.000 coins</span></div><div class="rank">#1</div></div>
            <div class="player"><div class="avatar">2</div><div class="meta"><b>MinerPro</b><span class="small muted">180.000 coins</span></div><div class="rank">#2</div></div>
            <div class="player"><div class="avatar">3</div><div class="meta"><b>FarmerX</b><span class="small muted">150.000 coins</span></div><div class="rank">#3</div></div>
          </div>
        </div>

        <div class="card">
          <h3>Top Playtime</h3>
          <div class="top-list">
            <div class="player"><div class="avatar">A</div><div class="meta"><b>PlayerA</b><span class="small muted">120 giờ</span></div><div class="rank">#1</div></div>
            <div class="player"><div class="avatar">B</div><div class="meta"><b>PlayerB</b><span class="small muted">98 giờ</span></div><div class="rank">#2</div></div>
            <div class="player"><div class="avatar">C</div><div class="meta"><b>PlayerC</b><span class="small muted">90 giờ</span></div><div class="rank">#3</div></div>
          </div>
        </div>

        <div class="card">
          <h3>Top Boss Kills</h3>
          <div class="top-list">
            <div class="player"><div class="avatar">X</div><div class="meta"><b>KillerX</b><span class="small muted">350 kill</span></div><div class="rank">#1</div></div>
            <div class="player"><div class="avatar">Y</div><div class="meta"><b>DarkBoy</b><span class="small muted">330 kill</span></div><div class="rank">#2</div></div>
            <div class="player"><div class="avatar">Z</div><div class="meta"><b>Z3R0</b><span class="small muted">300 kill</span></div><div class="rank">#3</div></div>
          </div>
        </div>
      </div>
    </section>

    <!-- join detail -->
    <section id="join" class="section">
      <div class="title">🕹 Tham gia ngay</div>
      <div class="grid">
        <div class="card">
          <h3>Thông tin server</h3>
          <p class="muted">IP: <strong>sodamc.com</strong><br>Phiên bản: <strong>1.8 - 1.21+</strong><br>Chế độ: <strong>Survival</strong></p>
          <p class="muted">Plugin: Towny, Jobs, Economy, Bosses, CustomDungeons — hỗ trợ game-play sâu & lâu dài.</p>
        </div>

        <div class="card">
          <h3>Hướng dẫn nhanh</h3>
          <ol class="muted" style="padding-left:18px;margin:8px 0">
            <li>Vào Minecraft → Multiplayer → Add Server</li>
            <li>Nhập IP: <b>sodamc.com</b> → Join</li>
            <li>Hoàn thành tutorial, nhận kit tân thủ</li>
          </ol>
        </div>

        <div class="card">
          <h3>Quy tắc cơ bản</h3>
          <ul class="muted" style="padding-left:18px;margin:8px 0">
            <li>Không gian lận (cheat, X-Ray)</li>
            <li>Tôn trọng người chơi khác</li>
            <li>Không grief khu vực của người khác</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- team -->
    <section id="team" class="section">
      <div class="title">👑 Đội ngũ vận hành</div>
      <div class="grid">
        <div class="card">
          <h3>Haooo (Owner)</h3>
          <p class="muted">Quản lý, phát triển plugin, sự kiện.</p>
        </div>
        <div class="card">
          <h3>Admin Team</h3>
          <p class="muted">Giám sát, xử lý report & bảo trì server.</p>
        </div>
        <div class="card">
          <h3>Mod & Helpers</h3>
          <p class="muted">Hỗ trợ người chơi, guide tân thủ.</p>
        </div>
      </div>
    </section>

  </div>
</main>

<footer style="margin-top:40px;padding:30px 0;background:linear-gradient(180deg,rgba(0,0,0,0.2),rgba(0,0,0,0.35))">
  <div class="wrap small">© 2026 SodaMC • Server Survival • Liên hệ: <strong>Haooo</strong></div>
</footer>

</body>
</html>
