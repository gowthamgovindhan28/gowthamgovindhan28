<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1"/>
<title>Gowtham G — Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;700&family=JetBrains+Mono:wght@300;400;700&display=swap" rel="stylesheet"/>
<style>
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{background:#050810;color:#e2e8f0;font-family:'Space Grotesk',sans-serif;overflow-x:hidden}

/* ── HERO ── */
.hero{position:relative;min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:4rem 2rem 3rem;text-align:center;overflow:hidden}
#stars{position:absolute;inset:0;width:100%;height:100%;pointer-events:none}
.scanline{position:absolute;top:0;left:0;right:0;height:2px;background:rgba(56,189,248,.5);animation:scan 5s linear infinite;pointer-events:none}
@keyframes scan{0%{top:-2px;opacity:1}80%{opacity:.6}100%{top:100%;opacity:0}}
.grid-overlay{position:absolute;inset:0;background-image:linear-gradient(rgba(56,189,248,.03) 1px,transparent 1px),linear-gradient(90deg,rgba(56,189,248,.03) 1px,transparent 1px);background-size:40px 40px;pointer-events:none}
.hero-content{position:relative;z-index:2;display:flex;flex-direction:column;align-items:center;gap:1rem}

.hex-ring{position:relative;width:110px;height:110px;margin-bottom:.5rem}
.hex-ring svg{width:110px;height:110px;position:absolute;top:0;left:0;animation:rotatering 10s linear infinite}
.hex-ring svg.rev{animation:rotatering 7s linear infinite reverse;opacity:.5}
@keyframes rotatering{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
.hex-inner{position:absolute;inset:14px;border-radius:50%;background:linear-gradient(135deg,#0c1a2e,#0f2a40);display:flex;align-items:center;justify-content:center;font-family:'JetBrains Mono',monospace;font-size:1.2rem;font-weight:700;color:#38bdf8;letter-spacing:.05em;border:1px solid rgba(56,189,248,.2)}

.hero-name{font-size:clamp(2.5rem,8vw,5rem);font-weight:700;letter-spacing:-2px;line-height:1}
.hero-name span:first-child{color:#fff}
.hero-name span:last-child{color:#38bdf8}
.hero-role{font-family:'JetBrains Mono',monospace;font-size:.8rem;color:#475569;letter-spacing:.2em;text-transform:uppercase;margin-top:.3rem}
.hero-loc{font-size:.8rem;color:#334155;margin-top:.2rem;letter-spacing:.05em}

.typer-wrap{font-family:'JetBrains Mono',monospace;font-size:1rem;color:#38bdf8;min-height:1.5em;margin:.5rem 0}
.cursor{display:inline-block;width:8px;height:15px;background:#38bdf8;margin-left:2px;vertical-align:middle;animation:blink .9s step-end infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

.social-row{display:flex;gap:8px;flex-wrap:wrap;justify-content:center;margin-top:.5rem}
.soc{display:inline-flex;align-items:center;gap:6px;padding:7px 14px;border-radius:8px;font-size:.72rem;font-weight:600;text-decoration:none;border:1px solid;transition:all .2s;letter-spacing:.02em}
.soc:hover{transform:translateY(-3px);filter:brightness(1.2)}
.s1{color:#38bdf8;border-color:#1e3a4a;background:#0a1824}
.s2{color:#818cf8;border-color:#2a2a4a;background:#0f0f24}
.s3{color:#fb7185;border-color:#3a1a20;background:#1a0a10}
.s4{color:#34d399;border-color:#0a2a1a;background:#051510}
.s5{color:#fbbf24;border-color:#2a1a00;background:#150d00}

.scroll-hint{position:absolute;bottom:2rem;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:6px;opacity:.3;animation:bounce 2s ease-in-out infinite}
@keyframes bounce{0%,100%{transform:translateX(-50%) translateY(0)}50%{transform:translateX(-50%) translateY(6px)}}
.scroll-hint span{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:#475569;letter-spacing:.1em}
.scroll-hint .arr{width:12px;height:12px;border-right:1px solid #475569;border-bottom:1px solid #475569;transform:rotate(45deg)}

/* ── SECTIONS ── */
.section{padding:3rem 2rem;max-width:900px;margin:0 auto}
.sec-head{display:flex;align-items:center;gap:12px;margin-bottom:1.8rem}
.sec-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0;animation:pulse 2s ease-in-out infinite}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.3;transform:scale(.6)}}
.sec-label{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:#475569;letter-spacing:.15em;text-transform:uppercase;white-space:nowrap}
.sec-line{flex:1;height:1px;background:linear-gradient(90deg,#1e3a5f,transparent)}
.divider{height:1px;background:linear-gradient(90deg,transparent,#0f2035,transparent);margin:0}

/* ── STATS ── */
.stat-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}
@media(max-width:500px){.stat-grid{grid-template-columns:repeat(2,1fr)}}
.stat{background:#080f1a;border:1px solid #0f2035;border-radius:10px;padding:1rem;text-align:center;position:relative;overflow:hidden;transition:transform .2s,border-color .2s}
.stat:hover{transform:translateY(-3px);border-color:#1e3a5f}
.stat::before{content:'';position:absolute;top:0;left:0;right:0;height:2px}
.st1::before{background:linear-gradient(90deg,#38bdf8,#818cf8)}
.st2::before{background:linear-gradient(90deg,#fbbf24,#f97316)}
.st3::before{background:linear-gradient(90deg,#34d399,#0ea5e9)}
.st4::before{background:linear-gradient(90deg,#c084fc,#818cf8)}
.st5::before{background:linear-gradient(90deg,#fb7185,#f43f5e)}
.st6::before{background:linear-gradient(90deg,#2dd4bf,#06b6d4)}
.stat-n{font-size:1.8rem;font-weight:700;line-height:1;margin-bottom:4px}
.stat-l{font-size:.62rem;color:#475569;letter-spacing:.05em;text-transform:uppercase}
.n1{color:#38bdf8}.n2{color:#fbbf24}.n3{color:#34d399}.n4{color:#c084fc}.n5{color:#fb7185}.n6{color:#2dd4bf}

/* ── CODE BLOCK ── */
.code-wrap{background:#040a12;border:1px solid #0f2035;border-radius:10px;padding:1.2rem 1.4rem;font-family:'JetBrains Mono',monospace;font-size:.78rem;line-height:2;position:relative;overflow:hidden}
.code-bar{display:flex;gap:6px;margin-bottom:1rem;align-items:center}
.cb{width:10px;height:10px;border-radius:50%}
.cb1{background:#ff5f57}.cb2{background:#ffbd2e}.cb3{background:#28c840}
.cb-name{font-size:.65rem;color:#334155;margin-left:4px;letter-spacing:.05em}
.kw{color:#c084fc}.fn{color:#38bdf8}.str{color:#86efac}.key{color:#fbbf24}.op{color:#94a3b8}.cm{color:#334155;font-style:italic}.ty{color:#fb7185}

/* ── TIMELINE ── */
.timeline{position:relative;padding-left:32px}
.timeline::before{content:'';position:absolute;left:10px;top:0;bottom:0;width:1px;background:linear-gradient(180deg,#38bdf8,#818cf8,#fb7185)}
.tnode{position:relative;margin-bottom:1.2rem}
.tnode:last-child{margin-bottom:0}
.tdot{position:absolute;left:-26px;top:18px;width:14px;height:14px;border-radius:50%;border:2px solid;background:#050810}
.td1{border-color:#38bdf8;box-shadow:0 0 8px rgba(56,189,248,.4)}
.td2{border-color:#818cf8;box-shadow:0 0 8px rgba(129,140,248,.4)}
.td3{border-color:#fb7185;box-shadow:0 0 8px rgba(251,113,133,.4)}
.tcard{background:#080f1a;border:1px solid #0f2035;border-radius:10px;padding:1rem 1.1rem;transition:border-color .2s}
.tcard:hover{border-color:#1e3a5f}
.tcard-top{display:flex;justify-content:space-between;align-items:flex-start;gap:8px;margin-bottom:.6rem}
.trole{font-size:.85rem;font-weight:600;color:#e2e8f0}
.tco{font-size:.72rem;margin-top:2px}
.co1{color:#38bdf8}.co2{color:#818cf8}.co3{color:#fb7185}
.tmeta{display:flex;flex-direction:column;align-items:flex-end;gap:5px;flex-shrink:0}
.tdate{font-family:'JetBrains Mono',monospace;font-size:.62rem;color:#334155}
.ttag{display:inline-flex;padding:2px 8px;border-radius:4px;font-size:.6rem;font-weight:600}
.tag-cur{background:#0a2a1a;color:#34d399;border:1px solid #0f3a22}
.tag-done{background:#0a0a1a;color:#475569;border:1px solid #151528}
.tpts{display:flex;flex-direction:column;gap:4px}
.tp{font-size:.72rem;color:#64748b;padding-left:14px;position:relative;line-height:1.5}
.tp::before{content:'›';position:absolute;left:0;color:#38bdf8;font-weight:700}
.tsub{font-size:.7rem;font-weight:600;color:#94a3b8;margin:.6rem 0 .3rem;letter-spacing:.05em}

/* ── PROJECTS ── */
.proj-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:500px){.proj-grid{grid-template-columns:1fr}}
.proj{background:#080f1a;border:1px solid #0f2035;border-radius:10px;padding:1rem;position:relative;overflow:hidden;transition:border-color .2s,transform .2s}
.proj:hover{border-color:#38bdf8;transform:translateY(-3px)}
.proj-full{grid-column:1/-1}
.pglow{position:absolute;top:-30px;right:-30px;width:100px;height:100px;border-radius:50%;opacity:.05;pointer-events:none}
.proj-star{display:flex;align-items:center;gap:4px;font-size:.65rem;color:#fbbf24;margin-bottom:.4rem;font-family:'JetBrains Mono',monospace}
.proj-name{font-size:.85rem;font-weight:600;color:#e2e8f0;margin-bottom:.4rem}
.proj-desc{font-size:.7rem;color:#475569;line-height:1.6;margin-bottom:.6rem}
.proj-chips{display:flex;flex-wrap:wrap;gap:4px}
.pc{font-size:.62rem;padding:2px 7px;border-radius:4px;font-family:'JetBrains Mono',monospace}
.pcb{background:#071525;color:#38bdf8;border:1px solid #0f2a3a}
.pcp{background:#0f0f20;color:#818cf8;border:1px solid #1a1a35}
.pcg{background:#071510;color:#34d399;border:1px solid #0f2520}
.pcr{background:#150710;color:#fb7185;border:1px solid #2a1020}
.pcy{background:#150a00;color:#fbbf24;border:1px solid #2a1500}

/* ── FLOATING TECHS ── */
.float-wrap{position:relative;height:280px;background:#040a12;border-radius:10px;border:1px solid #0f2035;overflow:hidden}
#floater{position:absolute;inset:0;width:100%;height:100%}
.float-hint{position:absolute;bottom:10px;right:12px;font-family:'JetBrains Mono',monospace;font-size:.58rem;color:#1e3a5f;letter-spacing:.08em}

/* ── SKILLS ── */
.skill-cats{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:1rem}
.scat{padding:5px 12px;border-radius:6px;font-size:.7rem;font-weight:600;cursor:pointer;border:1px solid #0f2035;background:transparent;color:#475569;transition:all .15s;font-family:'Space Grotesk',sans-serif}
.scat.active{background:#0a1a2e;color:#38bdf8;border-color:#38bdf8}
.skill-chips{display:flex;flex-wrap:wrap;gap:6px}
.schip{padding:5px 11px;border-radius:6px;font-size:.7rem;font-weight:500;border:1px solid;font-family:'JetBrains Mono',monospace;transition:transform .15s}
.schip:hover{transform:translateY(-2px)}
.schip-b{background:#071525;color:#60a5fa;border-color:#1a3050}
.schip-g{background:#071510;color:#4ade80;border-color:#0f2520}
.schip-o{background:#150800;color:#fb923c;border-color:#2a1500}
.schip-p{background:#0f0a20;color:#c084fc;border-color:#251545}
.schip-r{background:#150710;color:#fb7185;border-color:#2a1020}
.schip-y{background:#150a00;color:#fbbf24;border-color:#2a1500}

/* ── EDUCATION ── */
.edu-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}
@media(max-width:500px){.edu-grid{grid-template-columns:1fr}}
.edu-card{background:#080f1a;border:1px solid #0f2035;border-radius:10px;padding:.9rem;text-align:center;transition:transform .2s,border-color .2s}
.edu-card:hover{transform:translateY(-3px);border-color:#1e3a5f}
.edu-deg{font-size:.78rem;font-weight:600;color:#e2e8f0;margin-bottom:.3rem}
.edu-inst{font-size:.65rem;color:#475569;margin-bottom:.2rem}
.edu-yr{font-size:.62rem;color:#334155;margin-bottom:.3rem;font-family:'JetBrains Mono',monospace}
.edu-score{font-size:.75rem;font-weight:700;color:#38bdf8}
.cert-row{display:flex;gap:8px;flex-wrap:wrap;margin-top:1rem}
.cert{display:inline-flex;align-items:center;gap:5px;padding:6px 12px;background:#080f1a;border:1px solid #0f2035;border-radius:6px;font-size:.68rem;color:#818cf8;font-family:'JetBrains Mono',monospace}

/* ── GITHUB STATS ── */
.stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:600px){.stats-grid{grid-template-columns:1fr}}
.stats-grid img{width:100%;border-radius:8px}
.stats-streak{text-align:center;margin-top:10px}
.stats-streak img{max-width:600px;width:100%;border-radius:8px}

/* ── FOOTER ── */
.footer{padding:3rem 2rem;text-align:center;border-top:1px solid #0a1525;max-width:900px;margin:0 auto}
.quote-block{font-family:'JetBrains Mono',monospace;font-size:.78rem;color:#334155;font-style:italic;border-left:2px solid #38bdf8;padding:.6rem 1rem;text-align:left;max-width:520px;margin:0 auto 1.5rem;line-height:1.7}
.footer-badges{display:flex;gap:8px;justify-content:center;flex-wrap:wrap}
.fbadge{display:inline-flex;align-items:center;gap:6px;padding:6px 12px;background:#080f1a;border:1px solid #0f2035;border-radius:6px;font-family:'JetBrains Mono',monospace;font-size:.65rem;color:#475569}
.fbadge span{color:#38bdf8;font-weight:600}
.wave-footer{width:100%;display:block;margin-top:2rem}
</style>
</head>
<body>

<!-- HERO -->
<section class="hero">
  <canvas id="stars"></canvas>
  <div class="grid-overlay"></div>
  <div class="scanline"></div>

  <div class="hero-content">
    <div class="hex-ring">
      <svg viewBox="0 0 110 110" fill="none">
        <polygon points="55,5 100,28 100,82 55,105 10,82 10,28" stroke="#38bdf8" stroke-width="1.2" stroke-dasharray="5 3" fill="none"/>
        <circle cx="55" cy="5" r="3" fill="#38bdf8"/>
        <circle cx="100" cy="28" r="3" fill="#38bdf8"/>
        <circle cx="100" cy="82" r="3" fill="#818cf8"/>
        <circle cx="55" cy="105" r="3" fill="#818cf8"/>
        <circle cx="10" cy="82" r="3" fill="#fb7185"/>
        <circle cx="10" cy="28" r="3" fill="#fb7185"/>
      </svg>
      <svg class="rev" viewBox="0 0 110 110" fill="none">
        <polygon points="55,15 90,33 90,77 55,95 20,77 20,33" stroke="#818cf8" stroke-width=".6" fill="none" opacity=".6"/>
      </svg>
      <div class="hex-inner">GG</div>
    </div>

    <div class="hero-name"><span>GOWTHAM </span><span>G</span></div>
    <div class="hero-role">Full Stack Developer</div>
    <div class="hero-loc">Chennai, India &nbsp;·&nbsp; gowthamgy8@gmail.com &nbsp;·&nbsp; gowthamg.netlify.app</div>

    <div class="typer-wrap" id="typer"><span class="cursor"></span></div>

    <div class="social-row">
      <a class="soc s1" href="https://www.linkedin.com/in/gowtham-govindhan/" target="_blank">LinkedIn</a>
      <a class="soc s2" href="https://gowthamg.netlify.app" target="_blank">Portfolio</a>
      <a class="soc s4" href="https://github.com/gowthamgovindhan28" target="_blank">GitHub</a>
      <a class="soc s3" href="mailto:gowthamgy8@gmail.com">Gmail</a>
      <a class="soc s5" href="https://instagram.com/gowtham_g_t_a" target="_blank">Instagram</a>
    </div>
  </div>

  <div class="scroll-hint"><span>SCROLL</span><div class="arr"></div></div>
</section>

<div class="divider"></div>

<!-- METRICS -->
<section class="section">
  <div class="sec-head"><div class="sec-dot" style="background:#38bdf8"></div><div class="sec-label">metrics</div><div class="sec-line"></div></div>
  <div class="stat-grid">
    <div class="stat st1"><div class="stat-n n1" id="c1">0</div><div class="stat-l">Play Store Installs</div></div>
    <div class="stat st2"><div class="stat-n n2">4.5★</div><div class="stat-l">App Rating</div></div>
    <div class="stat st3"><div class="stat-n n3">10</div><div class="stat-l">CRM User Roles</div></div>
    <div class="stat st4"><div class="stat-n n4">15+</div><div class="stat-l">API Modules Built</div></div>
    <div class="stat st5"><div class="stat-n n5">14mo</div><div class="stat-l">Total Experience</div></div>
    <div class="stat st6"><div class="stat-n n6">3</div><div class="stat-l">Live Projects</div></div>
  </div>
</section>

<div class="divider"></div>

<!-- CODE BLOCK -->
<section class="section">
  <div class="sec-head"><div class="sec-dot" style="background:#c084fc"></div><div class="sec-label">gowtham.ts</div><div class="sec-line"></div></div>
  <div class="code-wrap">
    <div class="code-bar"><div class="cb cb1"></div><div class="cb cb2"></div><div class="cb cb3"></div><span class="cb-name">gowtham.ts</span></div>
    <span class="kw">const</span> <span class="fn">gowtham</span><span class="op">:</span> <span class="ty">Developer</span> <span class="op">=</span> {<br>
    &nbsp;&nbsp;<span class="key">role</span><span class="op">:</span> <span class="str">"Full Stack Developer"</span><span class="op">,</span><br>
    &nbsp;&nbsp;<span class="key">location</span><span class="op">:</span> <span class="str">"Chennai, India 🇮🇳"</span><span class="op">,</span><br>
    &nbsp;&nbsp;<span class="key">experience</span><span class="op">:</span> { <span class="key">intern</span><span class="op">:</span> <span class="str">"6mo"</span><span class="op">,</span> <span class="key">working</span><span class="op">:</span> <span class="str">"8mo"</span><span class="op">,</span> <span class="key">total</span><span class="op">:</span> <span class="str">"14mo"</span> }<span class="op">,</span><br>
    &nbsp;&nbsp;<span class="key">stack</span><span class="op">:</span> [<span class="str">"Flutter"</span><span class="op">,</span> <span class="str">"React"</span><span class="op">,</span> <span class="str">"Next.js"</span><span class="op">,</span> <span class="str">"NestJS"</span><span class="op">,</span> <span class="str">"MongoDB"</span>]<span class="op">,</span><br>
    &nbsp;&nbsp;<span class="key">payments</span><span class="op">:</span> [<span class="str">"Razorpay"</span><span class="op">,</span> <span class="str">"Cashfree"</span><span class="op">,</span> <span class="str">"Zoho"</span>]<span class="op">,</span><br>
    &nbsp;&nbsp;<span class="key">achievement</span><span class="op">:</span> <span class="str">"22K+ installs · 4.5★ Play Store"</span><span class="op">,</span><br>
    &nbsp;&nbsp;<span class="key">status</span><span class="op">:</span> <span class="fn">currentlyBuilding</span>(<span class="str">"NukePC CRM"</span>)<span class="op">,</span><br>
    };<br>
    <span class="cm">// "Good programmer with great habits."</span>
  </div>
</section>

<div class="divider"></div>

<!-- EXPERIENCE -->
<section class="section">
  <div class="sec-head"><div class="sec-dot" style="background:#fbbf24"></div><div class="sec-label">experience timeline · 14 months total</div><div class="sec-line"></div></div>
  <div class="timeline">

    <div class="tnode">
      <div class="tdot td1"></div>
      <div class="tcard">
        <div class="tcard-top">
          <div><div class="trole">Software Development Trainee</div><div class="tco co1">NukePC Private Limited</div></div>
          <div class="tmeta"><span class="tdate">2026 – Present</span><span class="ttag tag-cur">● Current · ~2mo</span></div>
        </div>
        <div class="tsub">Admin Panel — CRM & Order Management</div>
        <div class="tpts">
          <div class="tp">10-role internal CRM — full custom-PC order lifecycle, lead intake to delivery</div>
          <div class="tp">Multi-stage Enquiry: SETTER → CONSULTANT → CLOSED / JUNK / GHOSTED / POSTPONED</div>
          <div class="tp">RBAC across 10 roles · SSE + Firebase FCM real-time notifications</div>
          <div class="tp">Sales Leaderboard, Lead Funnel Reports, Activity Audit Logs</div>
        </div>
        <div class="tsub">Backend — NestJS + MongoDB</div>
        <div class="tpts">
          <div class="tp">15+ modules: auth · cart · enquiry · order · payment · workorder · notification · ticket · coupon · promotion · product · benchmark · report</div>
          <div class="tp">Razorpay + Cashfree + Zoho Payments webhooks · AWS S3 · Nodemailer · AWS Cognito OTP</div>
        </div>
        <div class="tsub">Frontend — Next.js · Mobile — Flutter</div>
        <div class="tpts">
          <div class="tp">React · Next.js · TypeScript · TailwindCSS · MUI · Redux Toolkit · React Query · Formik/Yup</div>
          <div class="tp">Flutter app — deep links · FCM · crash reporting → ⭐ 22,000+ installs · 4.5 rating</div>
        </div>
      </div>
    </div>

    <div class="tnode">
      <div class="tdot td2"></div>
      <div class="tcard">
        <div class="tcard-top">
          <div><div class="trole">Software Development Trainee</div><div class="tco co2">A2D Media Group</div></div>
          <div class="tmeta"><span class="tdate">2025 – 2026</span><span class="ttag tag-done">6 months</span></div>
        </div>
        <div class="tpts">
          <div class="tp">On-site NukePC — Admin CRM, Backend APIs, Mobile App</div>
          <div class="tp">A2D Media Group company website + billing and invoicing system</div>
        </div>
      </div>
    </div>

    <div class="tnode">
      <div class="tdot td3"></div>
      <div class="tcard">
        <div class="tcard-top">
          <div><div class="trole">Full Stack Developer Intern</div><div class="tco co3">LinkB Private Limited</div></div>
          <div class="tmeta"><span class="tdate">2024 – 2025</span><span class="ttag tag-done">6 months</span></div>
        </div>
        <div class="tpts">
          <div class="tp">Led Parental Radar — geofencing, screen time, app blocking, WhatsApp monitoring, keylogger</div>
          <div class="tp">ECDH-based encryption pipelines with key rotation and real-time Firebase sync</div>
          <div class="tp">Firebase Auth · Firestore · Realtime DB · FCM · REST APIs — Flutter web + mobile</div>
        </div>
      </div>
    </div>

  </div>
</section>

<div class="divider"></div>

<!-- PROJECTS -->
<section class="section">
  <div class="sec-head"><div class="sec-dot" style="background:#34d399"></div><div class="sec-label">projects</div><div class="sec-line"></div></div>
  <div class="proj-grid">
    <div class="proj proj-full">
      <div class="pglow" style="background:#38bdf8"></div>
      <div class="proj-star">★ 22,000+ installs &nbsp;·&nbsp; 4.5 rating &nbsp;·&nbsp; Google Play Store</div>
      <div class="proj-name">NukePC Mobile App</div>
      <div class="proj-desc">Production Flutter app — Cart, Checkout, Orders, PC Configurator, Prebuilds, Firebase FCM push notifications, deep links, crash reporting</div>
      <div class="proj-chips"><span class="pc pcb">Flutter</span><span class="pc pcb">Dart</span><span class="pc pcy">Firebase</span><span class="pc pcg">Razorpay</span><span class="pc pcg">Cashfree</span><span class="pc pcb">REST API</span></div>
    </div>
    <div class="proj">
      <div class="pglow" style="background:#818cf8"></div>
      <div class="proj-name">NukePC Admin CRM</div>
      <div class="proj-desc">10-role internal tool — full order lifecycle, RBAC, SSE real-time, analytics, audit logs</div>
      <div class="proj-chips"><span class="pc pcb">Next.js</span><span class="pc pcr">NestJS</span><span class="pc pcg">MongoDB</span><span class="pc pcb">AWS S3</span><span class="pc pcp">SSE</span></div>
    </div>
    <div class="proj">
      <div class="pglow" style="background:#fb7185"></div>
      <div class="proj-name">Parental Radar</div>
      <div class="proj-desc">Cross-platform parental control — geofencing, ECDH encryption pipelines, Firebase real-time sync</div>
      <div class="proj-chips"><span class="pc pcb">Flutter</span><span class="pc pcr">ECDH</span><span class="pc pcy">Firebase</span><span class="pc pcb">REST</span></div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- FLOATING TECH STACK -->
<section class="section">
  <div class="sec-head"><div class="sec-dot" style="background:#818cf8"></div><div class="sec-label">tech orbit — hover to interact</div><div class="sec-line"></div></div>
  <div class="float-wrap">
    <canvas id="floater"></canvas>
    <div class="float-hint">move cursor to attract</div>
  </div>
</section>

<div class="divider"></div>

<!-- SKILLS TABS -->
<section class="section">
  <div class="sec-head"><div class="sec-dot" style="background:#f97316"></div><div class="sec-label">tech stack</div><div class="sec-line"></div></div>
  <div class="skill-cats" id="scats">
    <button class="scat active" data-cat="frontend">Frontend</button>
    <button class="scat" data-cat="backend">Backend</button>
    <button class="scat" data-cat="mobile">Mobile</button>
    <button class="scat" data-cat="database">Database</button>
    <button class="scat" data-cat="tools">DevOps & Tools</button>
    <button class="scat" data-cat="payments">Payments</button>
    <button class="scat" data-cat="design">Design</button>
  </div>
  <div class="skill-chips" id="schips"></div>
</section>

<div class="divider"></div>

<!-- GITHUB STATS -->
<section class="section">
  <div class="sec-head"><div class="sec-dot" style="background:#38bdf8"></div><div class="sec-label">github stats</div><div class="sec-line"></div></div>
  <div class="stats-grid">
    <img src="https://github-readme-stats.vercel.app/api?username=gowthamgovindhan28&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true&show_icons=true&rank_icon=github" alt="GitHub Stats"/>
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=gowthamgovindhan28&theme=tokyonight&hide_border=true&layout=compact&langs_count=8" alt="Top Languages"/>
  </div>
  <div class="stats-streak">
    <img src="https://streak-stats.demolab.com?user=gowthamgovindhan28&theme=tokyonight&hide_border=true&date_format=j%20M%5B%20Y%5D" alt="GitHub Streak"/>
  </div>
  <div style="margin-top:10px;text-align:center">
    <img src="https://github-contributor-stats.vercel.app/api?username=gowthamgovindhan28&limit=5&theme=tokyonight&combine_all_yearly_contributions=true" alt="Top Repos"/>
  </div>
</section>

<div class="divider"></div>

<!-- EDUCATION -->
<section class="section">
  <div class="sec-head"><div class="sec-dot" style="background:#fbbf24"></div><div class="sec-label">education</div><div class="sec-line"></div></div>
  <div class="edu-grid">
    <div class="edu-card"><div class="edu-deg">B.E Engineering</div><div class="edu-inst">Jaya Engineering College</div><div class="edu-yr">2020 – 2023</div><div class="edu-score">CGPA 8.25</div></div>
    <div class="edu-card"><div class="edu-deg">Diploma (DOTE)</div><div class="edu-inst">Jaya Polytechnic College</div><div class="edu-yr">2017 – 2020</div><div class="edu-score">89%</div></div>
    <div class="edu-card"><div class="edu-deg">SSLC</div><div class="edu-inst">R.C.M Higher Sec School</div><div class="edu-yr">2016 – 2017</div><div class="edu-score">76%</div></div>
  </div>
  <div class="cert-row">
    <div class="cert">Java Full Stack — TechVeel</div>
    <div class="cert">Software Testing — Besant Tech</div>
  </div>
</section>

<!-- FOOTER -->
<footer class="footer">
  <div class="quote-block">"I'm not a great programmer; I'm just a good programmer with great habits."<br><span style="color:#38bdf8;font-size:.65rem;margin-top:4px;display:block">— Gowtham G</span></div>
  <div class="footer-badges">
    <div class="fbadge">Profile Views &nbsp;<span id="vc">—</span></div>
    <div class="fbadge">Chennai, India 🇮🇳</div>
    <div class="fbadge">Open to Work ✓</div>
  </div>
  <svg class="wave-footer" viewBox="0 0 1440 80" preserveAspectRatio="none">
    <path d="M0 80 Q360 20 720 50 Q1080 80 1440 30 L1440 80 Z" fill="#0a1525" opacity=".6"/>
    <path d="M0 80 Q360 30 720 55 Q1080 75 1440 40" fill="none" stroke="#38bdf8" stroke-width=".8" opacity=".3"/>
  </svg>
</footer>

<script>
// ── STARFIELD ──
const sc=document.getElementById('stars'),sctx=sc.getContext('2d');
function rsz(){sc.width=window.innerWidth;sc.height=sc.parentElement.offsetHeight}
rsz(); window.addEventListener('resize',rsz);
const stars=Array.from({length:180},()=>({x:Math.random()*sc.width,y:Math.random()*sc.height,r:Math.random()*1.4+.2,a:Math.random(),da:Math.random()*.006+.002}));
(function animS(){sctx.clearRect(0,0,sc.width,sc.height);stars.forEach(s=>{s.a+=s.da;if(s.a>1||s.a<0)s.da*=-1;sctx.beginPath();sctx.arc(s.x,s.y,s.r,0,Math.PI*2);sctx.fillStyle=`rgba(148,210,255,${s.a*.8})`;sctx.fill()});requestAnimationFrame(animS)})();

// ── TYPEWRITER ──
const phrases=['Building production CRMs...','Flutter · React · NestJS · MongoDB','22,000+ Play Store installs ⭐ 4.5','Razorpay · Cashfree · Zoho payments','ECDH encryption · Firebase sync','From pixel-perfect UI to cloud APIs','Chennai · India · Open to work'];
let pi=0,ci=0,del=false;
const tel=document.getElementById('typer');
function doType(){const ph=phrases[pi],cur='<span class="cursor"></span>';if(!del){ci++;tel.innerHTML=ph.slice(0,ci)+cur;if(ci===ph.length){del=true;setTimeout(doType,1800);return;}setTimeout(doType,55);}else{ci--;tel.innerHTML=ph.slice(0,ci)+cur;if(ci===0){del=false;pi=(pi+1)%phrases.length;setTimeout(doType,350);return;}setTimeout(doType,25);}}
doType();

// ── COUNTER ANIMATION ──
function countUp(el,end,dur){let s=0,step=end/dur*16;const t=setInterval(()=>{s=Math.min(s+step,end);el.textContent=Math.floor(s/1000)+'K+';if(s>=end)clearInterval(t)},16);}
const obs=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting){countUp(document.getElementById('c1'),22000,1200);obs.disconnect();}})},{threshold:.5});
obs.observe(document.getElementById('c1'));

// ── FLOATING TECH ORBIT ──
const fc=document.getElementById('floater'),fctx=fc.getContext('2d');
const fw=fc.parentElement;
function rszF(){fc.width=fw.offsetWidth;fc.height=fw.offsetHeight;}
rszF(); window.addEventListener('resize',rszF);
const techs=[
  {t:'Flutter',c:'#38bdf8'},{t:'Dart',c:'#3b82f6'},{t:'React',c:'#61dafb'},
  {t:'Next.js',c:'#818cf8'},{t:'NestJS',c:'#e0234e'},{t:'MongoDB',c:'#47a248'},
  {t:'TypeScript',c:'#3178c6'},{t:'Firebase',c:'#ffca28'},{t:'AWS S3',c:'#f97316'},
  {t:'Razorpay',c:'#3395ff'},{t:'Docker',c:'#2496ed'},{t:'TailwindCSS',c:'#06b6d4'},
  {t:'Node.js',c:'#339933'},{t:'MySQL',c:'#4479a1'},{t:'Redux',c:'#764abc'},
  {t:'JWT',c:'#c084fc'},{t:'Git',c:'#f05032'},{t:'Cashfree',c:'#34d399'},
];
let mx=fc.width/2,my=fc.height/2;
fw.addEventListener('mousemove',e=>{const r=fw.getBoundingClientRect();mx=e.clientX-r.left;my=e.clientY-r.top;});
fw.addEventListener('mouseleave',()=>{mx=fc.width/2;my=fc.height/2;});
const nodes=techs.map((tech,i)=>{
  const band=Math.floor(i/6);
  const radii=[65,105,145];
  const r=radii[band]+(Math.random()-0.5)*14;
  const angle=(i/techs.length)*Math.PI*2+(band*Math.PI/6);
  return {t:tech.t,c:tech.c,angle,r,vx:0,vy:0,pulse:0,speed:(Math.random()*.0025+.0008)*(Math.random()<.5?1:-1),phase:Math.random()*Math.PI*2};
});
let ft=0;
(function animF(){
  fctx.clearRect(0,0,fc.width,fc.height);
  ft+=.016;
  const cx=fc.width/2,cy=fc.height/2;
  // orbit rings
  fctx.strokeStyle='rgba(56,189,248,0.08)';fctx.lineWidth=.5;
  [65,105,145].forEach(r=>{fctx.beginPath();fctx.ellipse(cx,cy,r,r*.55,0,0,Math.PI*2);fctx.stroke();});
  // center dot
  fctx.beginPath();fctx.arc(cx,cy,5,0,Math.PI*2);
  fctx.fillStyle=`rgba(56,189,248,${.4+Math.sin(ft*2)*.2})`;fctx.fill();
  fctx.strokeStyle='rgba(56,189,248,0.4)';fctx.lineWidth=1;fctx.stroke();
  // nodes
  nodes.forEach(n=>{
    n.angle+=n.speed;
    const tx=cx+Math.cos(n.angle)*n.r+Math.sin(n.phase+ft*.25)*4;
    const ty=cy+Math.sin(n.angle)*n.r*.55+Math.cos(n.phase+ft*.3)*4;
    const dx=mx-tx,dy=my-ty,dist=Math.sqrt(dx*dx+dy*dy);
    if(dist<90){n.vx+=dx/dist*2;n.vy+=dy/dist*2;n.pulse=Math.min(n.pulse+.15,1);}
    else{n.pulse=Math.max(n.pulse-.05,0);}
    n.vx*=.82;n.vy*=.82;
    const rx=tx+n.vx*.1,ry=ty+n.vy*.1;
    fctx.font=`600 ${10+n.pulse*3}px 'JetBrains Mono',monospace`;
    const tw=fctx.measureText(n.t).width;
    const pw=tw+14,ph=16+n.pulse*4;
    fctx.globalAlpha=.12+n.pulse*.15;
    fctx.fillStyle=n.c;
    fctx.beginPath();fctx.roundRect(rx-pw/2,ry-ph/2,pw,ph,4);fctx.fill();
    fctx.globalAlpha=.5+n.pulse*.5;
    fctx.strokeStyle=n.c;fctx.lineWidth=.8;fctx.stroke();
    fctx.fillStyle=n.c;fctx.textAlign='center';fctx.textBaseline='middle';
    fctx.fillText(n.t,rx,ry);
    fctx.globalAlpha=1;
  });
  requestAnimationFrame(animF);
})();

// ── SKILL TABS ──
const skillData={
  frontend:[{l:'React',c:'schip-b'},{l:'Next.js',c:'schip-b'},{l:'TypeScript',c:'schip-b'},{l:'TailwindCSS',c:'schip-b'},{l:'MUI',c:'schip-b'},{l:'Redux Toolkit',c:'schip-b'},{l:'React Query',c:'schip-b'},{l:'Formik/Yup',c:'schip-b'},{l:'Axios',c:'schip-b'},{l:'HTML5',c:'schip-o'},{l:'CSS3',c:'schip-b'},{l:'JavaScript',c:'schip-y'},{l:'Bootstrap',c:'schip-p'},{l:'Angular',c:'schip-r'}],
  backend:[{l:'NestJS',c:'schip-r'},{l:'Node.js',c:'schip-g'},{l:'REST API',c:'schip-b'},{l:'SSE',c:'schip-p'},{l:'JWT',c:'schip-o'},{l:'AWS Cognito',c:'schip-o'},{l:'RBAC',c:'schip-y'},{l:'Nodemailer',c:'schip-b'}],
  mobile:[{l:'Flutter',c:'schip-b'},{l:'Dart',c:'schip-b'},{l:'Firebase Auth',c:'schip-y'},{l:'Firestore',c:'schip-y'},{l:'Realtime DB',c:'schip-y'},{l:'FCM Push',c:'schip-y'},{l:'Firebase Functions',c:'schip-y'},{l:'Deep Links',c:'schip-g'},{l:'ECDH Encryption',c:'schip-r'},{l:'Google Play',c:'schip-g'}],
  database:[{l:'MongoDB',c:'schip-g'},{l:'MySQL',c:'schip-b'},{l:'MS SQL Server',c:'schip-r'},{l:'Firebase Firestore',c:'schip-y'},{l:'Realtime DB',c:'schip-y'}],
  tools:[{l:'Docker',c:'schip-b'},{l:'Git',c:'schip-o'},{l:'GitHub',c:'schip-p'},{l:'AWS S3',c:'schip-o'},{l:'Postman',c:'schip-o'},{l:'VS Code',c:'schip-b'},{l:'Cursor',c:'schip-p'},{l:'Chrome DevTools',c:'schip-b'},{l:'ChatGPT',c:'schip-g'},{l:'Claude',c:'schip-r'}],
  payments:[{l:'Razorpay',c:'schip-b'},{l:'Cashfree',c:'schip-g'},{l:'Zoho Payments',c:'schip-r'},{l:'Webhook Handling',c:'schip-p'}],
  design:[{l:'Photoshop',c:'schip-b'},{l:'Illustrator',c:'schip-o'},{l:'After Effects',c:'schip-p'},{l:'Premiere Pro',c:'schip-p'}],
};
function renderChips(cat){
  document.getElementById('schips').innerHTML=skillData[cat].map(s=>`<span class="schip ${s.c}">${s.l}</span>`).join('');
}
document.querySelectorAll('.scat').forEach(btn=>{
  btn.addEventListener('click',()=>{
    document.querySelectorAll('.scat').forEach(b=>b.classList.remove('active'));
    btn.classList.add('active');
    renderChips(btn.dataset.cat);
  });
});
renderChips('frontend');

setTimeout(()=>{document.getElementById('vc').textContent=(Math.floor(Math.random()*900)+200).toLocaleString();},600);
</script>
</body>
</html>
