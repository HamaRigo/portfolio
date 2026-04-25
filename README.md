<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>Mohamed Bouallagui — Software Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg:      #080b10;
  --bg1:     #0d111a;
  --bg2:     #111622;
  --bg3:     #161c2e;
  --border:  rgba(255,255,255,0.06);
  --border2: rgba(255,255,255,0.10);
  --text:    #dde2ec;
  --muted:   #5d6785;
  --muted2:  #8491b0;
  --accent:  #4f6ef7;
  --accent2: #7c3aed;
  --teal:    #0ea5b0;
  --gold:    #d4a44c;
  --rose:    #e05a7a;
  --head:    'Syne', sans-serif;
  --body:    'DM Sans', sans-serif;
  --ease:    cubic-bezier(.22,.68,0,1.2);
  --ease2:   cubic-bezier(.16,1,.3,1);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
html{scroll-behavior:smooth;scrollbar-width:thin;scrollbar-color:#1e2540 var(--bg1);}
::-webkit-scrollbar{width:4px;}
::-webkit-scrollbar-track{background:var(--bg1);}
::-webkit-scrollbar-thumb{background:#1e2540;border-radius:2px;}
body{
  background:var(--bg);color:var(--text);
  font-family:var(--body);font-size:15px;line-height:1.65;
  overflow-x:hidden;cursor:none;
}
a{color:inherit;text-decoration:none;}

body::after{
  content:'';position:fixed;inset:0;z-index:1;pointer-events:none;
  background:
    radial-gradient(ellipse 80% 50% at 50% -10%,rgba(79,110,247,.08) 0%,transparent 60%),
    radial-gradient(ellipse 60% 40% at 100% 80%,rgba(124,58,237,.05) 0%,transparent 50%);
}

/* CURSOR */
#c-dot{position:fixed;width:5px;height:5px;background:#fff;border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:transform .08s;}
#c-ring{position:fixed;width:28px;height:28px;border:1px solid rgba(79,110,247,.6);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:width .25s var(--ease2),height .25s var(--ease2),border-color .25s;}
body.chov #c-ring{width:48px;height:48px;border-color:rgba(79,110,247,.3);}

/* LOADER */
#loader{position:fixed;inset:0;z-index:9990;background:var(--bg);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:28px;transition:opacity .8s var(--ease2),visibility .8s;}
#loader.out{opacity:0;visibility:hidden;}
.ld-mono{font-family:var(--head);font-size:3.5rem;font-weight:800;letter-spacing:-.02em;color:#fff;}
.ld-mono em{font-style:normal;color:var(--accent);}
.ld-bg{width:180px;height:1px;background:rgba(255,255,255,.08);overflow:hidden;}
.ld-bar{height:100%;width:0;background:linear-gradient(90deg,var(--accent),var(--teal));animation:ldFill 2s var(--ease2) forwards;}
.ld-lbl{font-size:.72rem;letter-spacing:.18em;text-transform:uppercase;color:var(--muted);}
@keyframes ldFill{to{width:100%;}}

/* CANVAS */
#ptc{position:fixed;inset:0;z-index:0;pointer-events:none;opacity:.4;}

/* NAV */
nav{
  position:fixed;top:0;left:0;right:0;z-index:500;height:60px;
  display:flex;align-items:center;justify-content:space-between;padding:0 5%;
  background:rgba(8,11,16,.85);backdrop-filter:blur(24px) saturate(160%);
  -webkit-backdrop-filter:blur(24px) saturate(160%);
  border-bottom:1px solid var(--border);
  transform:translateY(-100%);animation:navIn .6s .3s var(--ease2) forwards;
}
@keyframes navIn{to{transform:translateY(0);}}
.nav-logo{font-family:var(--head);font-size:.95rem;font-weight:700;letter-spacing:.02em;}
.nav-logo em{font-style:normal;color:var(--accent);}
.nav-links{list-style:none;display:flex;gap:2.5rem;align-items:center;}
.nav-links a{font-size:.78rem;letter-spacing:.09em;text-transform:uppercase;font-weight:500;color:var(--muted);transition:color .25s;position:relative;padding-bottom:2px;}
.nav-links a::after{content:'';position:absolute;bottom:0;left:0;right:0;height:1px;background:var(--accent);transform:scaleX(0);transform-origin:left;transition:transform .3s var(--ease2);}
.nav-links a:hover{color:var(--text);}
.nav-links a:hover::after{transform:scaleX(1);}
.nav-burger{display:none;flex-direction:column;gap:5px;cursor:pointer;}
.nav-burger span{display:block;width:22px;height:1.5px;background:var(--muted);transition:.3s;}

/* HERO */
#hero{
  min-height:100vh;display:grid;grid-template-columns:1fr 1fr;
  align-items:center;gap:6rem;padding:110px 5% 80px;
  max-width:1200px;margin:0 auto;position:relative;z-index:2;
}
.h-badge{
  display:inline-flex;align-items:center;gap:8px;
  border:1px solid rgba(79,110,247,.25);background:rgba(79,110,247,.06);
  padding:.3rem .9rem;border-radius:2px;
  font-size:.72rem;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--accent);
  margin-bottom:1.5rem;
}
.h-dot{width:6px;height:6px;background:var(--accent);border-radius:50%;box-shadow:0 0 0 0 rgba(79,110,247,.6);animation:hdot 2s ease infinite;}
@keyframes hdot{70%{box-shadow:0 0 0 6px rgba(79,110,247,0);}100%{box-shadow:0 0 0 0 rgba(79,110,247,0);}}
.h-name{
  font-family:var(--head);font-size:clamp(2.8rem,4.5vw,4.2rem);font-weight:800;
  line-height:1.0;letter-spacing:-.03em;
  background:linear-gradient(135deg,#ffffff 30%,#c2c8e8 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  margin-bottom:1.1rem;
}
.h-role{font-size:1rem;color:var(--muted2);font-weight:300;letter-spacing:.01em;max-width:420px;margin-bottom:2.2rem;line-height:1.75;}
.h-role strong{color:var(--text);font-weight:500;}
.h-actions{display:flex;gap:1rem;flex-wrap:wrap;}
.btn{display:inline-flex;align-items:center;gap:8px;padding:.7rem 1.6rem;border-radius:3px;font-family:var(--head);font-size:.82rem;font-weight:600;letter-spacing:.06em;text-transform:uppercase;transition:all .3s var(--ease2);border:none;}
.btn-prim{background:var(--accent);color:#fff;}
.btn-prim:hover{background:#6280f9;transform:translateY(-2px);box-shadow:0 8px 24px rgba(79,110,247,.3);}
.btn-out{background:transparent;color:var(--muted2);border:1px solid var(--border2);}
.btn-out:hover{color:var(--text);border-color:rgba(255,255,255,.2);transform:translateY(-2px);}

.h-card-wrap{display:flex;justify-content:center;align-items:center;position:relative;}
.h-ring{position:absolute;border-radius:50%;border:1px dashed rgba(79,110,247,.18);animation:spinRing 20s linear infinite;pointer-events:none;}
.h-ring:nth-child(1){width:340px;height:340px;}
.h-ring:nth-child(2){width:420px;height:420px;animation-direction:reverse;animation-duration:30s;border-color:rgba(124,58,237,.1);}
@keyframes spinRing{to{transform:rotate(360deg);}}
.h-card{
  width:280px;background:var(--bg2);border:1px solid var(--border2);border-radius:6px;
  padding:2rem 1.5rem;position:relative;z-index:2;
  animation:hFloat 7s ease-in-out infinite;
  box-shadow:0 40px 80px rgba(0,0,0,.5),0 0 0 1px rgba(255,255,255,.04) inset;
}
@keyframes hFloat{0%,100%{transform:translateY(0);}50%{transform:translateY(-12px);}}
.h-card-av{
  width:64px;height:64px;background:linear-gradient(135deg,var(--accent2),var(--accent));
  border-radius:4px;display:flex;align-items:center;justify-content:center;
  font-family:var(--head);font-size:1.4rem;font-weight:800;color:#fff;margin-bottom:1.1rem;
}
.h-card-name{font-family:var(--head);font-size:.95rem;font-weight:700;color:#fff;margin-bottom:.25rem;}
.h-card-role{font-size:.75rem;color:var(--muted);margin-bottom:1.5rem;}
.h-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:.5rem;border-top:1px solid var(--border);padding-top:1.2rem;}
.h-sv{font-family:var(--head);font-size:1.3rem;font-weight:800;color:#fff;}
.h-sl{font-size:.62rem;color:var(--muted);letter-spacing:.05em;margin-top:2px;text-transform:uppercase;}
.h-ctag{
  display:inline-flex;align-items:center;gap:5px;
  background:rgba(79,110,247,.08);border:1px solid rgba(79,110,247,.2);
  padding:.18rem .55rem;border-radius:2px;
  font-size:.65rem;font-weight:600;letter-spacing:.06em;text-transform:uppercase;color:var(--accent);margin-bottom:.8rem;
}

/* MARQUEE */
.marquee{
  position:relative;z-index:2;
  border-top:1px solid var(--border);border-bottom:1px solid var(--border);
  padding:.9rem 0;overflow:hidden;background:var(--bg1);
}
.m-inner{display:flex;gap:0;animation:mScroll 28s linear infinite;}
.m-item{
  display:flex;align-items:center;gap:2.5rem;padding:0 2.5rem;
  font-size:.72rem;letter-spacing:.14em;text-transform:uppercase;
  color:var(--muted);white-space:nowrap;font-weight:500;
}
.m-item::after{content:'';display:block;width:4px;height:4px;background:var(--border2);border-radius:50%;}
@keyframes mScroll{from{transform:translateX(0);}to{transform:translateX(-50%);}}

/* SECTIONS */
section{padding:100px 5%;position:relative;z-index:2;}
.s-inner{max-width:1100px;margin:0 auto;}
.s-label{font-size:.68rem;letter-spacing:.2em;text-transform:uppercase;color:var(--accent);font-weight:600;margin-bottom:.5rem;}
.s-title{font-family:var(--head);font-size:clamp(1.8rem,3vw,2.6rem);font-weight:800;letter-spacing:-.025em;color:#fff;line-height:1.1;margin-bottom:.5rem;}
.s-title span{color:var(--muted2);}
.s-rule{width:32px;height:1px;background:var(--accent);margin:1rem 0 3.5rem;}

/* REVEAL */
.rv{opacity:0;transform:translateY(28px);transition:opacity .8s var(--ease2),transform .8s var(--ease2);}
.rv-l{opacity:0;transform:translateX(-30px);transition:opacity .7s var(--ease2),transform .7s var(--ease2);}
.rv-r{opacity:0;transform:translateX(30px);transition:opacity .7s var(--ease2),transform .7s var(--ease2);}
.rv.in,.rv-l.in,.rv-r.in{opacity:1;transform:none;}

/* SKILLS */
#skills{background:var(--bg1);}
.sk-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.8rem 4rem;margin-bottom:3.5rem;}
.sk-meta{display:flex;justify-content:space-between;margin-bottom:.5rem;}
.sk-name{font-size:.83rem;font-weight:500;color:var(--text);}
.sk-pct{font-size:.75rem;color:var(--muted);font-family:var(--head);}
.sk-track{height:2px;background:rgba(255,255,255,.05);border-radius:1px;overflow:hidden;}
.sk-fill{
  height:100%;width:0;background:linear-gradient(90deg,var(--accent2),var(--accent));
  border-radius:1px;transition:width 1.1s var(--ease2);position:relative;overflow:hidden;
}
.sk-fill::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,.35),transparent);
  transform:translateX(-100%);animation:skShim 1.4s 1s ease forwards;
}
@keyframes skShim{to{transform:translateX(200%);}}
.chips{display:flex;flex-wrap:wrap;gap:.5rem;}
.chip{
  border:1px solid var(--border);background:var(--bg2);
  padding:.3rem .85rem;border-radius:2px;
  font-size:.72rem;font-weight:500;color:var(--muted);letter-spacing:.02em;
  transition:all .25s;
}
.chip:hover{border-color:rgba(79,110,247,.35);color:var(--text);transform:translateY(-3px);}

/* EXPERIENCE */
.tl{max-width:760px;}
.tl-line{position:relative;padding-left:36px;}
.tl-line::before{content:'';position:absolute;left:0;top:8px;bottom:0;width:1px;background:linear-gradient(180deg,var(--accent) 0%,rgba(79,110,247,0) 100%);}
.tl-item{position:relative;margin-bottom:2.8rem;}
.tl-dot{position:absolute;left:-39px;top:8px;width:7px;height:7px;border-radius:50%;background:var(--accent);box-shadow:0 0 0 3px rgba(79,110,247,.15);}
.tl-header{display:flex;align-items:flex-start;justify-content:space-between;gap:1rem;flex-wrap:wrap;margin-bottom:.4rem;}
.tl-role{font-family:var(--head);font-size:.95rem;font-weight:700;color:#fff;}
.tl-period{
  font-size:.7rem;letter-spacing:.08em;text-transform:uppercase;color:var(--gold);font-weight:600;
  background:rgba(212,164,76,.07);border:1px solid rgba(212,164,76,.15);
  padding:.2rem .65rem;border-radius:2px;white-space:nowrap;flex-shrink:0;
}
.tl-org{font-size:.8rem;color:var(--teal);margin-bottom:.8rem;}
.tl-pts{list-style:none;}
.tl-pts li{font-size:.85rem;color:var(--muted2);padding-left:1.1rem;position:relative;margin-bottom:.3rem;}
.tl-pts li::before{content:'—';position:absolute;left:0;color:var(--muted);font-size:.8rem;}
.tl-badges{display:flex;flex-wrap:wrap;gap:.4rem;margin-top:.9rem;}
.badge{font-size:.67rem;letter-spacing:.05em;text-transform:uppercase;font-weight:600;padding:.2rem .6rem;border-radius:2px;}
.bb{background:rgba(79,110,247,.08);color:#7d9aff;border:1px solid rgba(79,110,247,.2);}
.bt{background:rgba(14,165,176,.08);color:var(--teal);border:1px solid rgba(14,165,176,.2);}
.br{background:rgba(224,90,122,.08);color:var(--rose);border:1px solid rgba(224,90,122,.2);}
.bg{background:rgba(212,164,76,.08);color:var(--gold);border:1px solid rgba(212,164,76,.2);}

/* PROJECTS */
#projects{background:var(--bg1);}
.pr-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border);border:1px solid var(--border);border-radius:4px;overflow:hidden;}
.pr-card{
  background:var(--bg1);padding:1.8rem;
  transition:background .3s;
  display:flex;flex-direction:column;gap:.7rem;
  position:relative;overflow:hidden;
}
.pr-card::after{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,var(--accent2),var(--accent),var(--teal));
  transform:scaleX(0);transform-origin:left;transition:transform .4s var(--ease2);
}
.pr-card:hover{background:var(--bg2);}
.pr-card:hover::after{transform:scaleX(1);}
.pr-icon{
  width:36px;height:36px;border-radius:3px;
  display:flex;align-items:center;justify-content:center;
  background:var(--bg3);color:var(--accent);
  font-family:var(--head);font-weight:800;font-size:.7rem;
}
.pr-name{font-family:var(--head);font-size:.9rem;font-weight:700;color:#fff;}
.pr-desc{font-size:.8rem;color:var(--muted2);line-height:1.65;flex:1;}
.pr-stack{display:flex;flex-wrap:wrap;gap:.35rem;}
.pr-tag{
  font-size:.65rem;font-weight:600;letter-spacing:.04em;
  padding:.15rem .5rem;border-radius:2px;
  background:rgba(255,255,255,.04);color:var(--muted);border:1px solid var(--border);
  font-family:var(--head);
}

/* EDUCATION */
.edu-grid{display:grid;grid-template-columns:1fr 1fr;gap:2rem;align-items:start;}
.edu-col{display:flex;flex-direction:column;gap:1px;background:var(--border);border:1px solid var(--border);border-radius:4px;overflow:hidden;}
.edu-card{background:var(--bg1);padding:1.4rem 1.5rem;}
.edu-deg{font-family:var(--head);font-size:.88rem;font-weight:700;color:#fff;margin-bottom:.25rem;}
.edu-school{font-size:.8rem;color:var(--teal);}
.edu-yr{font-size:.72rem;color:var(--muted);margin-top:.2rem;}
.lang-card{display:flex;align-items:center;justify-content:space-between;background:var(--bg1);padding:1.1rem 1.5rem;}
.lang-name{font-size:.85rem;font-weight:500;color:var(--text);}
.lang-lvl{font-size:.66rem;letter-spacing:.1em;text-transform:uppercase;font-weight:700;padding:.2rem .65rem;border-radius:2px;}
.lvl-nat{background:rgba(224,90,122,.07);color:var(--rose);border:1px solid rgba(224,90,122,.2);}
.lvl-pro{background:rgba(79,110,247,.07);color:#7d9aff;border:1px solid rgba(79,110,247,.2);}
.cert-row{display:flex;align-items:center;gap:1rem;background:var(--bg1);padding:1rem 1.5rem;border-top:1px solid var(--border);}
.cert-ico{font-size:.85rem;width:28px;height:28px;display:flex;align-items:center;justify-content:center;background:rgba(212,164,76,.08);border-radius:2px;}
.cert-name{font-size:.8rem;color:var(--text);font-weight:500;}

/* CONTACT */
#contact{background:var(--bg1);}
.ct-grid{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:center;}
.ct-cards{display:flex;flex-direction:column;gap:1px;background:var(--border);border:1px solid var(--border);border-radius:4px;overflow:hidden;}
.ct-card{display:flex;align-items:center;gap:1rem;background:var(--bg1);padding:1rem 1.5rem;transition:background .25s,transform .25s var(--ease2);}
.ct-card:hover{background:var(--bg2);transform:translateX(5px);}
.ct-ico{width:36px;height:36px;border-radius:3px;display:flex;align-items:center;justify-content:center;font-size:.85rem;flex-shrink:0;}
.ct-lbl{font-size:.67rem;color:var(--muted);letter-spacing:.08em;text-transform:uppercase;margin-bottom:.12rem;}
.ct-val{font-size:.85rem;font-weight:500;color:var(--text);}
a.ct-val{color:var(--accent);}
a.ct-val:hover{color:#7d9aff;}

.rpl-wrap{display:flex;align-items:center;justify-content:center;height:320px;position:relative;}
.rpl-av{
  width:96px;height:96px;background:linear-gradient(135deg,var(--accent2),var(--accent));
  border-radius:4px;display:flex;align-items:center;justify-content:center;
  font-family:var(--head);font-size:1.6rem;font-weight:800;color:#fff;
  position:relative;z-index:2;box-shadow:0 0 0 1px rgba(79,110,247,.4);
}
.rpl{position:absolute;border-radius:4px;border:1px solid rgba(79,110,247,.35);animation:rplOut 2.5s ease-out infinite;opacity:0;}
.rpl1{width:140px;height:140px;animation-delay:0s;}
.rpl2{width:200px;height:200px;animation-delay:.7s;border-color:rgba(79,110,247,.2);}
.rpl3{width:270px;height:270px;animation-delay:1.4s;border-color:rgba(79,110,247,.1);}
@keyframes rplOut{0%{transform:scale(.85);opacity:.7;}100%{transform:scale(1.1);opacity:0;}}

footer{text-align:center;padding:2.5rem 5%;border-top:1px solid var(--border);font-size:.73rem;color:var(--muted);letter-spacing:.05em;position:relative;z-index:2;}

@media(max-width:960px){
  #hero{grid-template-columns:1fr;gap:3rem;text-align:center;}
  .h-badge,.h-actions{justify-content:center;}
  .h-role{margin:0 auto 2.2rem;}
  .sk-grid{grid-template-columns:1fr;}
  .pr-grid{grid-template-columns:1fr 1fr;}
  .edu-grid{grid-template-columns:1fr;}
  .ct-grid{grid-template-columns:1fr;}
  .nav-links{display:none;position:absolute;top:60px;left:0;right:0;flex-direction:column;gap:0;background:rgba(8,11,16,.97);border-bottom:1px solid var(--border);}
  .nav-links.open{display:flex;}
  .nav-links a{padding:.85rem 5%;}
  .nav-links a::after{display:none;}
  .nav-burger{display:flex;}
}
@media(max-width:600px){
  section{padding:70px 5%;}
  .pr-grid{grid-template-columns:1fr;}
  .h-ring{display:none;}
}
</style>
</head>
<body>

<div id="c-dot"></div>
<div id="c-ring"></div>

<div id="loader">
  <div class="ld-mono">M<em>B</em></div>
  <div class="ld-bg"><div class="ld-bar"></div></div>
  <div class="ld-lbl">Loading portfolio</div>
</div>

<canvas id="ptc"></canvas>

<nav>
  <a href="#hero" class="nav-logo">Mohamed <em>Bouallagui</em></a>
  <ul class="nav-links" id="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <div class="nav-burger" id="burger" onclick="document.getElementById('nav-links').classList.toggle('open')">
    <span></span><span></span><span></span>
  </div>
</nav>

<section id="hero">
  <div class="rv">
    <div class="h-badge"><span class="h-dot"></span>Available &nbsp;·&nbsp; Doha, Qatar</div>
    <h1 class="h-name">Mohamed<br>Bouallagui</h1>
    <p class="h-role">
      Software Engineer specialising in <strong>Backend Systems, Microservices</strong> and Distributed Architecture. Qatar-based with transferable residence permit.
    </p>
    <div class="h-actions">
      <a href="#contact" class="btn btn-prim">Get in Touch &rarr;</a>
      <a href="#projects" class="btn btn-out">View Work</a>
    </div>
  </div>
  <div class="h-card-wrap rv-r">
    <div class="h-ring"></div>
    <div class="h-ring"></div>
    <div class="h-card">
      <div class="h-ctag">&#9679; Open to Opportunities</div>
      <div class="h-card-av">MB</div>
      <div class="h-card-name">Mohamed Bouallagui</div>
      <div class="h-card-role">Backend &nbsp;·&nbsp; Microservices &nbsp;·&nbsp; DevOps</div>
      <div class="h-stats">
        <div><div class="h-sv">4</div><div class="h-sl">Yrs Exp.</div></div>
        <div><div class="h-sv">35%</div><div class="h-sl">Latency ↓</div></div>
        <div><div class="h-sv">15+</div><div class="h-sl">Services</div></div>
      </div>
    </div>
  </div>
</section>

<div class="marquee">
  <div class="m-inner">
    <span class="m-item">ATB Bank</span><span class="m-item">ISE Consulting</span>
    <span class="m-item">Rigoo Marine</span><span class="m-item">ESPRIT</span>
    <span class="m-item">Spring Boot</span><span class="m-item">Apache Kafka</span>
    <span class="m-item">Kubernetes</span><span class="m-item">Keycloak</span>
    <span class="m-item">PostgreSQL</span><span class="m-item">Docker</span>
    <span class="m-item">OAuth 2.0</span><span class="m-item">TensorFlow</span>
    <span class="m-item">ATB Bank</span><span class="m-item">ISE Consulting</span>
    <span class="m-item">Rigoo Marine</span><span class="m-item">ESPRIT</span>
    <span class="m-item">Spring Boot</span><span class="m-item">Apache Kafka</span>
    <span class="m-item">Kubernetes</span><span class="m-item">Keycloak</span>
    <span class="m-item">PostgreSQL</span><span class="m-item">Docker</span>
    <span class="m-item">OAuth 2.0</span><span class="m-item">TensorFlow</span>
  </div>
</div>

<section id="skills">
  <div class="s-inner">
    <div class="rv">
      <div class="s-label">Expertise</div>
      <h2 class="s-title">Technical <span>Skills</span></h2>
      <div class="s-rule"></div>
    </div>
    <div class="sk-grid">
      <div class="rv"><div class="sk-meta"><span class="sk-name">Java &amp; Spring Boot</span><span class="sk-pct">95%</span></div><div class="sk-track"><div class="sk-fill" data-w="95"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">Microservices Architecture</span><span class="sk-pct">92%</span></div><div class="sk-track"><div class="sk-fill" data-w="92"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">Kafka &amp; Event-Driven Design</span><span class="sk-pct">88%</span></div><div class="sk-track"><div class="sk-fill" data-w="88"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">OAuth 2.0 &nbsp;/&nbsp; Keycloak &nbsp;/&nbsp; JWT</span><span class="sk-pct">90%</span></div><div class="sk-track"><div class="sk-fill" data-w="90"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">Docker &amp; Kubernetes</span><span class="sk-pct">85%</span></div><div class="sk-track"><div class="sk-fill" data-w="85"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">PostgreSQL &nbsp;/&nbsp; MongoDB &nbsp;/&nbsp; Redis</span><span class="sk-pct">87%</span></div><div class="sk-track"><div class="sk-fill" data-w="87"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">Angular &amp; React (TypeScript)</span><span class="sk-pct">80%</span></div><div class="sk-track"><div class="sk-fill" data-w="80"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">CI/CD &amp; GitHub Actions</span><span class="sk-pct">85%</span></div><div class="sk-track"><div class="sk-fill" data-w="85"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">TensorFlow &nbsp;/&nbsp; MLflow &nbsp;/&nbsp; OCR</span><span class="sk-pct">72%</span></div><div class="sk-track"><div class="sk-fill" data-w="72"></div></div></div>
      <div class="rv"><div class="sk-meta"><span class="sk-name">Node.js &nbsp;/&nbsp; Python &nbsp;/&nbsp; Symfony</span><span class="sk-pct">75%</span></div><div class="sk-track"><div class="sk-fill" data-w="75"></div></div></div>
    </div>
    <div class="chips rv">
      <span class="chip">DDD</span><span class="chip">CQRS</span><span class="chip">Event-Driven</span>
      <span class="chip">Spring Cloud</span><span class="chip">RabbitMQ</span><span class="chip">WebSockets</span>
      <span class="chip">Tesseract OCR</span><span class="chip">Anomaly Detection</span><span class="chip">PCI-DSS</span>
      <span class="chip">OpenID Connect</span><span class="chip">RBAC</span><span class="chip">SSO</span>
      <span class="chip">GitHub Actions</span><span class="chip">Microservices Migration</span>
    </div>
  </div>
</section>

<section id="experience">
  <div class="s-inner">
    <div class="rv">
      <div class="s-label">Career</div>
      <h2 class="s-title">Work <span>Experience</span></h2>
      <div class="s-rule"></div>
    </div>
    <div class="tl">
      <div class="tl-line">
        <div class="tl-item rv-l">
          <div class="tl-dot"></div>
          <div class="tl-header">
            <span class="tl-role">Software Engineering Consultant</span>
            <span class="tl-period">Apr 2025 &mdash; Present</span>
          </div>
          <div class="tl-org">Doha, Qatar</div>
          <ul class="tl-pts">
            <li>Reduced API latency by 35% through systematic caching optimisation</li>
            <li>Engineered Kafka event-driven pipelines handling production-scale throughput</li>
            <li>Automated 90% of CI/CD workflows, eliminating manual release toil</li>
            <li>Maintained 99.9% system uptime across all production services</li>
          </ul>
          <div class="tl-badges">
            <span class="badge bb">Kafka</span>
            <span class="badge bt">CI/CD Automation</span>
            <span class="badge bg">99.9% Uptime</span>
            <span class="badge br">Latency &minus;35%</span>
          </div>
        </div>
        <div class="tl-item rv-l" style="transition-delay:.12s">
          <div class="tl-dot"></div>
          <div class="tl-header">
            <span class="tl-role">Full-Stack Engineer &mdash; Banking Platform</span>
            <span class="tl-period">Mar 2024 &mdash; Sep 2024</span>
          </div>
          <div class="tl-org">ATB Bank &nbsp;&middot;&nbsp; PFE / CDD</div>
          <ul class="tl-pts">
            <li>Built OCR fraud-detection pipeline achieving 95% accuracy</li>
            <li>Deployed Keycloak IAM protecting 10,000+ user accounts</li>
            <li>Designed and delivered 15+ Spring Boot microservices</li>
          </ul>
          <div class="tl-badges">
            <span class="badge bb">Spring Boot</span>
            <span class="badge bt">Keycloak IAM</span>
            <span class="badge br">OCR &amp; Fraud Detection</span>
            <span class="badge bg">10K+ Users Secured</span>
          </div>
        </div>
        <div class="tl-item rv-l" style="transition-delay:.24s">
          <div class="tl-dot"></div>
          <div class="tl-header">
            <span class="tl-role">Technical Consultant</span>
            <span class="tl-period">Oct 2020 &mdash; Dec 2023</span>
          </div>
          <div class="tl-org">ISE &nbsp;&middot;&nbsp; 3 Years</div>
          <ul class="tl-pts">
            <li>Delivered 360&deg; digital platform driving +40% user engagement</li>
            <li>Compressed deployment cycles from days to minutes</li>
            <li>Architected JWT-based SSO authentication across the platform</li>
          </ul>
          <div class="tl-badges">
            <span class="badge bb">JWT SSO</span>
            <span class="badge bt">+40% Engagement</span>
            <span class="badge bg">Digital Transformation</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="s-inner">
    <div class="rv">
      <div class="s-label">Portfolio</div>
      <h2 class="s-title">Selected <span>Projects</span></h2>
      <div class="s-rule"></div>
    </div>
    <div class="pr-grid">
      <div class="pr-card rv">
        <div class="pr-icon">RG</div>
        <div class="pr-name">Rigoo Marine Platform</div>
        <p class="pr-desc">Enterprise marine-ops platform: 9 Spring Boot microservices, Kafka event-driven architecture, JWT authentication, and 99.9% uptime design on Kubernetes.</p>
        <div class="pr-stack"><span class="pr-tag">Java</span><span class="pr-tag">Spring Boot</span><span class="pr-tag">Kafka</span><span class="pr-tag">PostgreSQL</span><span class="pr-tag">Docker</span><span class="pr-tag">K8s</span></div>
      </div>
      <div class="pr-card rv" style="transition-delay:.08s">
        <div class="pr-icon">FD</div>
        <div class="pr-name">Fraud Detection MLOps</div>
        <p class="pr-desc">OCR verification processing 1,000+ docs/day. Manual review cut from 10 to 2 minutes. Anomaly detection improved fraud accuracy by 35%. Deploy time: 4 h &rarr; 15 min.</p>
        <div class="pr-stack"><span class="pr-tag">Spring Boot</span><span class="pr-tag">React</span><span class="pr-tag">Tesseract</span><span class="pr-tag">TensorFlow</span><span class="pr-tag">Keycloak</span><span class="pr-tag">Redis</span></div>
      </div>
      <div class="pr-card rv" style="transition-delay:.16s">
        <div class="pr-icon">EM</div>
        <div class="pr-name">Enterprise Messaging Hub</div>
        <p class="pr-desc">Real-time messaging platform supporting 1,000+ concurrent WebSocket connections. Spring Boot backend, Angular frontend, Redis pub/sub for low-latency delivery.</p>
        <div class="pr-stack"><span class="pr-tag">Spring Boot</span><span class="pr-tag">Angular</span><span class="pr-tag">Redis</span><span class="pr-tag">WebSockets</span></div>
      </div>
      <div class="pr-card rv" style="transition-delay:.24s">
        <div class="pr-icon">PI</div>
        <div class="pr-name">Predictive Inventory System</div>
        <p class="pr-desc">Supply-chain analytics with predictive inventory management, delivering actionable insights to operations teams in real time.</p>
        <div class="pr-stack"><span class="pr-tag">Symfony</span><span class="pr-tag">PostgreSQL</span><span class="pr-tag">Angular</span></div>
      </div>
      <div class="pr-card rv" style="transition-delay:.32s">
        <div class="pr-icon">IA</div>
        <div class="pr-name">Enterprise IAM Platform</div>
        <p class="pr-desc">Keycloak-powered identity &amp; access management for 500+ bank employees. Full PCI-DSS compliance via RBAC and OpenID Connect SSO.</p>
        <div class="pr-stack"><span class="pr-tag">Keycloak</span><span class="pr-tag">JWT</span><span class="pr-tag">RBAC</span><span class="pr-tag">PCI-DSS</span></div>
      </div>
      <div class="pr-card rv" style="transition-delay:.40s">
        <div class="pr-icon">DP</div>
        <div class="pr-name">360&deg; Digital Platform</div>
        <p class="pr-desc">Comprehensive digital transformation platform driving +40% user engagement. JWT SSO, automated pipelines, and microservices architecture replacing a legacy monolith.</p>
        <div class="pr-stack"><span class="pr-tag">Java</span><span class="pr-tag">Angular</span><span class="pr-tag">JWT</span><span class="pr-tag">CI/CD</span><span class="pr-tag">Docker</span></div>
      </div>
    </div>
  </div>
</section>

<section id="education">
  <div class="s-inner">
    <div class="rv">
      <div class="s-label">Background</div>
      <h2 class="s-title">Education &amp; <span>Languages</span></h2>
      <div class="s-rule"></div>
    </div>
    <div class="edu-grid">
      <div class="rv-l">
        <div class="edu-col">
          <div class="edu-card">
            <div class="edu-deg">Engineering Degree &mdash; Computer Engineering</div>
            <div class="edu-school">ESPRIT &mdash; &Eacute;cole Sup&eacute;rieure Priv&eacute;e d'Ing&eacute;nierie</div>
            <div class="edu-yr">2024</div>
          </div>
          <div class="edu-card">
            <div class="edu-deg">Bachelor &mdash; Computer Science</div>
            <div class="edu-school">FST Sidi Bouzid</div>
            <div class="edu-yr">2018</div>
          </div>
          <div class="cert-row">
            <div class="cert-ico">&#9749;</div>
            <div class="cert-name">Oracle Certified Associate Java SE 8</div>
          </div>
          <div class="cert-row" style="border-top:none;">
            <div class="cert-ico">&#9745;</div>
            <div class="cert-name">Scrum Foundation Professional Certificate</div>
          </div>
        </div>
      </div>
      <div class="rv-r">
        <div class="edu-col" style="margin-bottom:1.5rem;">
          <div class="lang-card"><span class="lang-name">Arabic</span><span class="lang-lvl lvl-nat">Native</span></div>
          <div class="lang-card"><span class="lang-name">English</span><span class="lang-lvl lvl-pro">Professional</span></div>
          <div class="lang-card"><span class="lang-name">French</span><span class="lang-lvl lvl-pro">Professional</span></div>
        </div>
        <div class="edu-col">
          <div class="edu-card">
            <div style="font-size:.72rem;letter-spacing:.12em;text-transform:uppercase;color:var(--gold);font-weight:600;margin-bottom:.7rem;">Target Sectors</div>
            <div class="chips" style="gap:.4rem;">
              <span class="chip">Banking &amp; Fintech</span>
              <span class="chip">Energy &amp; O&amp;G</span>
              <span class="chip">Government Digital</span>
              <span class="chip">Aviation &amp; Logistics</span>
              <span class="chip">Tech Consulting</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="s-inner">
    <div class="rv">
      <div class="s-label">Contact</div>
      <h2 class="s-title">Get In <span>Touch</span></h2>
      <div class="s-rule"></div>
    </div>
    <div class="ct-grid">
      <div class="ct-cards rv-l">
        <div class="ct-card">
          <div class="ct-ico" style="background:rgba(79,110,247,.08);">@</div>
          <div><div class="ct-lbl">Email</div><a href="mailto:mohamed.bouallagui001@gmail.com" class="ct-val">mohamed.bouallagui001@gmail.com</a></div>
        </div>
        <div class="ct-card">
          <div class="ct-ico" style="background:rgba(14,165,176,.08);">#</div>
          <div><div class="ct-lbl">Phone</div><div class="ct-val">+974 77 704 703</div></div>
        </div>
        <div class="ct-card">
          <div class="ct-ico" style="background:rgba(212,164,76,.08);">&#x2316;</div>
          <div><div class="ct-lbl">Location</div><div class="ct-val">Doha, Qatar</div></div>
        </div>
        <div class="ct-card">
          <div class="ct-ico" style="background:rgba(0,200,100,.06);">&#10003;</div>
          <div><div class="ct-lbl">Visa Status</div><div class="ct-val">Qatar ID &mdash; Transferable Permit</div></div>
        </div>
        <div class="ct-card">
          <div class="ct-ico" style="background:rgba(79,110,247,.08);font-size:.7rem;font-weight:700;">in</div>
          <div><div class="ct-lbl">LinkedIn</div><a href="https://linkedin.com/in/mohamed-bouallagui-mb" target="_blank" class="ct-val">linkedin.com/in/mohamed-bouallagui-mb</a></div>
        </div>
        <div class="ct-card">
          <div class="ct-ico" style="background:rgba(255,255,255,.04);font-size:.7rem;font-weight:700;">gh</div>
          <div><div class="ct-lbl">GitHub</div><a href="https://github.com/HamaRigo" target="_blank" class="ct-val">github.com/HamaRigo</a></div>
        </div>
      </div>
      <div class="rv-r">
        <div class="rpl-wrap">
          <div class="rpl rpl1"></div>
          <div class="rpl rpl2"></div>
          <div class="rpl rpl3"></div>
          <div class="rpl-av">MB</div>
        </div>
      </div>
    </div>
  </div>
</section>

<footer>&copy; 2025 Mohamed Bouallagui &nbsp;&middot;&nbsp; Software Engineer &nbsp;&middot;&nbsp; Doha, Qatar</footer>

<script>
window.addEventListener('load',()=>setTimeout(()=>document.getElementById('loader').classList.add('out'),2200));

const dot=document.getElementById('c-dot'),ring=document.getElementById('c-ring');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;dot.style.left=mx+'px';dot.style.top=my+'px';});
(function ar(){rx+=(mx-rx)*.14;ry+=(my-ry)*.14;ring.style.left=rx+'px';ring.style.top=ry+'px';requestAnimationFrame(ar);})();
document.querySelectorAll('a,button,.btn,.pr-card,.ct-card,.chip').forEach(el=>{
  el.addEventListener('mouseenter',()=>document.body.classList.add('chov'));
  el.addEventListener('mouseleave',()=>document.body.classList.remove('chov'));
});

(function(){
  const c=document.getElementById('ptc'),ctx=c.getContext('2d');
  const COLS=['#4f6ef7','#7c3aed','#0ea5b0'];
  let W,H,pts;
  function resize(){W=c.width=innerWidth;H=c.height=innerHeight;}
  function Pt(){this.x=Math.random()*W;this.y=Math.random()*H;this.vx=(Math.random()-.5)*.35;this.vy=(Math.random()-.5)*.35;this.r=Math.random()*1.5+.5;this.col=COLS[Math.floor(Math.random()*COLS.length)];}
  Pt.prototype.tick=function(){this.x+=this.vx;this.y+=this.vy;if(this.x<0||this.x>W)this.vx*=-1;if(this.y<0||this.y>H)this.vy*=-1;};
  function init(){pts=Array.from({length:70},()=>new Pt());}
  function draw(){
    ctx.clearRect(0,0,W,H);
    pts.forEach(p=>{
      p.tick();
      ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
      ctx.fillStyle=p.col;ctx.globalAlpha=.55;ctx.fill();ctx.globalAlpha=1;
    });
    for(let i=0;i<pts.length;i++)for(let j=i+1;j<pts.length;j++){
      const dx=pts[i].x-pts[j].x,dy=pts[i].y-pts[j].y,d=Math.hypot(dx,dy);
      if(d<120){
        ctx.beginPath();ctx.moveTo(pts[i].x,pts[i].y);ctx.lineTo(pts[j].x,pts[j].y);
        ctx.strokeStyle=pts[i].col;ctx.globalAlpha=(1-d/120)*.12;ctx.lineWidth=.5;ctx.stroke();ctx.globalAlpha=1;
      }
    }
    requestAnimationFrame(draw);
  }
  resize();init();draw();
  window.addEventListener('resize',()=>{resize();init();});
})();

const IO=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.classList.add('in');
      e.target.querySelectorAll('.sk-fill[data-w]').forEach(b=>b.style.width=b.dataset.w+'%');
    }
  });
},{threshold:.1});
document.querySelectorAll('.rv,.rv-l,.rv-r').forEach(el=>IO.observe(el));

const SKO=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting)e.target.style.width=e.target.dataset.w+'%';});
},{threshold:.2});
document.querySelectorAll('.sk-fill[data-w]').forEach(b=>SKO.observe(b));
</script>
</body>
</html>