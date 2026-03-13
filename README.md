<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dow Zarai Markaz — Agricultural Excellence · Ziarat</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400;1,600&family=DM+Sans:wght@300;400;500;600&family=Noto+Nastaliq+Urdu:wght@400;700&display=swap" rel="stylesheet">
<style>
/* ╔══════════════════════════════════════════════╗
   ║  DESIGN SYSTEM                               ║
   ╚══════════════════════════════════════════════╝ */
:root {
  --void:   #060d07;
  --deep:   #0a1a0c;
  --rich:   #112214;
  --grove:  #1e3d26;
  --fern:   #2d5c38;
  --moss:   #3d7a4c;
  --leaf:   #5a9e6c;
  --sage:   #8dc49a;
  --mist:   #c4dfc9;
  --dew:    #e8f5eb;
  --cream:  #faf8f3;
  --white:  #ffffff;
  --amber:  #c2620a;
  --gold:   #d4860e;
  --gilt:   #e8a830;
  --glow:   #f5c660;
  --max: 1280px;
  --e1: cubic-bezier(0.22,1,0.36,1);
  --e2: cubic-bezier(0.34,1.56,0.64,1);
  --e3: cubic-bezier(0.77,0,0.18,1);
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth;font-size:16px;overflow-x:hidden}
body{
  font-family:'DM Sans',sans-serif;
  background:var(--void);
  color:var(--white);
  overflow-x:hidden;
  -webkit-font-smoothing:antialiased;
  cursor:none;
}
a{text-decoration:none;color:inherit}
img{display:block;max-width:100%}

/* ╔══════════════════════════════════════════════╗
   ║  CUSTOM CURSOR                               ║
   ╚══════════════════════════════════════════════╝ */
.cursor{
  position:fixed;z-index:10000;pointer-events:none;
  top:0;left:0;transform:translate(-50%,-50%);
}
.cursor-dot{
  width:8px;height:8px;border-radius:50%;
  background:var(--gilt);
  transition:transform .1s;
}
.cursor-ring{
  position:fixed;z-index:9999;pointer-events:none;
  top:0;left:0;transform:translate(-50%,-50%);
  width:36px;height:36px;border-radius:50%;
  border:1.5px solid rgba(232,168,48,.45);
  transition:transform .18s var(--e1),width .25s var(--e1),height .25s var(--e1),border-color .25s;
}
.cursor-ring.hover{
  width:56px;height:56px;
  border-color:rgba(232,168,48,.8);
  background:rgba(232,168,48,.06);
}

/* ╔══════════════════════════════════════════════╗
   ║  PRELOADER                                   ║
   ╚══════════════════════════════════════════════╝ */
#preloader{
  position:fixed;inset:0;z-index:9998;
  background:var(--void);
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;gap:20px;
}
.pl-logo{
  font-family:'Cormorant',serif;font-size:2.8rem;font-weight:300;
  color:var(--white);letter-spacing:3px;
  opacity:0;animation:plFade .8s var(--e1) .2s forwards;
}
.pl-sub{
  font-size:.62rem;letter-spacing:5px;text-transform:uppercase;
  color:rgba(255,255,255,.3);
  opacity:0;animation:plFade .8s var(--e1) .5s forwards;
}
.pl-bar{
  width:180px;height:1px;background:rgba(255,255,255,.1);
  position:relative;overflow:hidden;
  opacity:0;animation:plFade .8s var(--e1) .7s forwards;
}
.pl-bar::after{
  content:'';position:absolute;top:0;left:-100%;
  width:100%;height:100%;background:var(--gilt);
  animation:plLoad 1.6s var(--e1) 1s forwards;
}
@keyframes plFade{to{opacity:1}}
@keyframes plLoad{to{left:0}}
#preloader.out{
  animation:plOut .7s var(--e3) forwards;
}
@keyframes plOut{
  to{opacity:0;transform:translateY(-100%)}
}

/* ╔══════════════════════════════════════════════╗
   ║  FLOATING PARTICLES                          ║
   ╚══════════════════════════════════════════════╝ */
.particles{
  position:fixed;inset:0;z-index:1;pointer-events:none;overflow:hidden;
}
.p{
  position:absolute;border-radius:50%;
  background:radial-gradient(circle,rgba(93,158,108,.25),transparent 70%);
  animation:pFloat linear infinite;
}
@keyframes pFloat{
  0%{transform:translateY(100vh) rotate(0deg);opacity:0}
  10%{opacity:1}
  90%{opacity:.4}
  100%{transform:translateY(-120px) rotate(720deg);opacity:0}
}

/* ╔══════════════════════════════════════════════╗
   ║  TOPBAR                                      ║
   ╚══════════════════════════════════════════════╝ */
.topbar{
  position:relative;z-index:100;
  background:rgba(6,13,7,.9);
  border-bottom:1px solid rgba(255,255,255,.05);
  backdrop-filter:blur(10px);
}
.tb{
  max-width:var(--max);margin:0 auto;padding:10px 48px;
  display:flex;justify-content:space-between;align-items:center;
}
.tb-phones{display:flex;gap:32px}
.tb-phone{
  display:flex;align-items:center;gap:8px;
  font-size:.7rem;letter-spacing:.5px;color:rgba(255,255,255,.4);
  transition:color .3s;
}
.tb-phone:hover{color:var(--gilt)}
.tb-phone svg{width:11px;height:11px;fill:currentColor}
.tb-locale{
  font-size:.6rem;letter-spacing:4px;text-transform:uppercase;
  color:rgba(255,255,255,.18);
}

/* ╔══════════════════════════════════════════════╗
   ║  NAVIGATION                                  ║
   ╚══════════════════════════════════════════════╝ */
.nav{
  position:sticky;top:0;z-index:500;
  transition:background .5s,border-color .5s,backdrop-filter .5s;
  border-bottom:1px solid transparent;
}
.nav.scrolled{
  background:rgba(6,13,7,.95);
  border-color:rgba(255,255,255,.06);
  backdrop-filter:blur(24px) saturate(180%);
  box-shadow:0 4px 40px rgba(0,0,0,.4);
}
.nav-inner{
  max-width:var(--max);margin:0 auto;padding:0 48px;
  height:74px;display:flex;align-items:center;
  justify-content:space-between;gap:32px;
}
/* Logo */
.logo{display:flex;align-items:center;gap:14px}
.logo-gem{
  width:44px;height:44px;border-radius:11px;
  background:linear-gradient(145deg,var(--fern),var(--void));
  border:1px solid rgba(93,158,108,.3);
  display:flex;align-items:center;justify-content:center;
  font-size:1.25rem;position:relative;overflow:hidden;
  transition:border-color .3s,transform .3s var(--e2);
}
.logo:hover .logo-gem{border-color:var(--gilt);transform:scale(1.05) rotate(-3deg)}
.logo-gem::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(232,168,48,.1),transparent);
}
.logo-t{display:flex;flex-direction:column;gap:1px}
.logo-en{
  font-family:'Cormorant',serif;font-size:1.05rem;font-weight:500;
  color:var(--white);line-height:1;letter-spacing:.5px;
}
.logo-ur{
  font-family:'Noto Nastaliq Urdu',serif;font-size:.68rem;
  direction:rtl;color:var(--gilt);line-height:1.5;
}
/* Nav links */
.nav-menu{display:flex;list-style:none;align-items:center;gap:2px}
.nav-menu a{
  display:block;padding:9px 16px;
  font-size:.78rem;font-weight:500;letter-spacing:.2px;
  color:rgba(255,255,255,.55);border-radius:8px;
  transition:color .25s,background .25s;position:relative;
}
.nav-menu a:hover{color:var(--white);background:rgba(255,255,255,.06)}
/* Dropdown */
.has-dd{position:relative}
.dd{
  position:absolute;top:calc(100% + 10px);left:50%;
  transform:translateX(-50%) translateY(8px) scale(.96);
  min-width:210px;
  background:rgba(14,26,16,.97);
  border:1px solid rgba(93,158,108,.18);
  border-radius:16px;overflow:hidden;
  box-shadow:0 20px 60px rgba(0,0,0,.6);
  opacity:0;visibility:hidden;pointer-events:none;
  transition:all .25s var(--e2);
  transform-origin:top center;
}
.has-dd:hover .dd{
  opacity:1;visibility:visible;pointer-events:all;
  transform:translateX(-50%) translateY(0) scale(1);
}
.dd a{
  display:flex;align-items:center;gap:11px;
  padding:11px 20px;font-size:.79rem;
  color:rgba(255,255,255,.55);
  border-bottom:1px solid rgba(255,255,255,.05);
  border-radius:0;transition:color .2s,background .2s,padding-left .2s;
}
.dd a:last-child{border:none}
.dd a:hover{color:var(--white);background:rgba(93,158,108,.1);padding-left:26px}
.dd a .di{font-size:.9rem;width:18px;text-align:center}
/* CTA */
.nav-btn{
  display:inline-flex;align-items:center;gap:8px;
  background:linear-gradient(135deg,var(--amber),var(--gold));
  color:var(--white);padding:10px 24px;border-radius:8px;
  font-size:.78rem;font-weight:600;letter-spacing:.3px;
  box-shadow:0 4px 20px rgba(194,98,10,.4);
  transition:transform .25s var(--e2),box-shadow .25s,opacity .25s;
}
.nav-btn:hover{transform:translateY(-2px);box-shadow:0 8px 32px rgba(194,98,10,.5);opacity:.95}

/* ╔══════════════════════════════════════════════╗
   ║  HERO — FULL CINEMATIC                       ║
   ╚══════════════════════════════════════════════╝ */
.hero{
  position:relative;height:100svh;min-height:640px;
  overflow:hidden;background:var(--void);
}
/* Parallax bg */
.hero-bg{
  position:absolute;inset:-10%;
  background-image:url('https://images.unsplash.com/photo-1500937386664-56d1dfef3854?w=2000&q=90');
  background-size:cover;background-position:center;
  transform:scale(1.12);
  animation:heroZoom 18s ease-in-out infinite alternate;
  will-change:transform;
}
@keyframes heroZoom{
  from{transform:scale(1.12) translate(0,0)}
  to{transform:scale(1.05) translate(-1%,1%)}
}
.hero-grad{
  position:absolute;inset:0;
  background:
    linear-gradient(110deg,rgba(6,13,7,.92) 0%,rgba(6,13,7,.65) 50%,rgba(6,13,7,.15) 100%),
    linear-gradient(to top,rgba(6,13,7,.8) 0%,transparent 45%);
}
/* Noise overlay */
.hero-noise{
  position:absolute;inset:0;opacity:.04;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.75' numOctaves='4'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  background-size:200px 200px;
}
/* Side rule line */
.hero-rule{
  position:absolute;left:48px;top:0;bottom:0;
  width:1px;background:linear-gradient(to bottom,transparent,rgba(232,168,48,.3) 20%,rgba(232,168,48,.3) 80%,transparent);
  z-index:2;
}
/* Scroll indicator */
.hero-scroll{
  position:absolute;bottom:40px;left:48px;z-index:4;
  display:flex;align-items:center;gap:14px;
  font-size:.6rem;letter-spacing:3.5px;text-transform:uppercase;
  color:rgba(255,255,255,.3);
  animation:fadeUp .8s var(--e1) 2.8s both;
}
.scroll-line{
  width:40px;height:1px;background:rgba(255,255,255,.2);
  position:relative;overflow:hidden;
}
.scroll-line::after{
  content:'';position:absolute;top:0;left:-100%;
  width:100%;height:100%;background:var(--gilt);
  animation:scrollPulse 2.2s ease-in-out 2.8s infinite;
}
@keyframes scrollPulse{
  0%{left:-100%}50%{left:100%}100%{left:100%}
}
/* Hero content */
.hero-content{
  position:absolute;inset:0;z-index:3;
  display:flex;align-items:center;
  padding:0 80px 0 80px;
}
.hero-text{max-width:780px}
/* Staggered entrance */
.hero-eyebrow{
  display:flex;align-items:center;gap:14px;
  margin-bottom:24px;
  opacity:0;animation:fadeUp .8s var(--e1) 1.8s forwards;
}
.h-line{width:40px;height:1px;background:var(--gilt)}
.h-eyebrow-text{
  font-size:.62rem;letter-spacing:4px;text-transform:uppercase;
  color:rgba(255,255,255,.5);font-weight:500;
}
.hero-headline{
  font-family:'Cormorant',serif;
  font-size:clamp(3.8rem,7.5vw,7rem);
  font-weight:300;color:var(--white);
  line-height:.95;letter-spacing:-1px;
  margin-bottom:20px;
  opacity:0;animation:fadeUp .9s var(--e1) 2s forwards;
}
.hero-headline em{
  font-style:italic;
  background:linear-gradient(135deg,var(--gilt),var(--gold));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
}
.hero-headline .outline{
  -webkit-text-stroke:1px rgba(255,255,255,.25);
  -webkit-text-fill-color:transparent;
}
.hero-urdu{
  font-family:'Noto Nastaliq Urdu',serif;
  font-size:1.15rem;direction:rtl;
  color:rgba(255,255,255,.45);line-height:2.2;
  margin-bottom:22px;
  opacity:0;animation:fadeUp .8s var(--e1) 2.2s forwards;
}
.hero-desc{
  font-size:.92rem;color:rgba(255,255,255,.55);
  line-height:1.9;max-width:460px;margin-bottom:40px;
  opacity:0;animation:fadeUp .8s var(--e1) 2.35s forwards;
}
.hero-actions{
  display:flex;gap:14px;align-items:center;flex-wrap:wrap;
  opacity:0;animation:fadeUp .8s var(--e1) 2.5s forwards;
}
.btn-gold{
  display:inline-flex;align-items:center;gap:10px;
  background:linear-gradient(135deg,var(--amber),var(--gold));
  color:var(--white);padding:15px 34px;border-radius:8px;
  font-size:.84rem;font-weight:600;letter-spacing:.3px;
  box-shadow:0 6px 28px rgba(194,98,10,.45);
  transition:transform .3s var(--e2),box-shadow .3s;
  position:relative;overflow:hidden;
}
.btn-gold::before{
  content:'';position:absolute;top:0;left:-100%;
  width:100%;height:100%;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,.15),transparent);
  transition:left .5s;
}
.btn-gold:hover{transform:translateY(-3px);box-shadow:0 12px 36px rgba(194,98,10,.55)}
.btn-gold:hover::before{left:100%}
.btn-ghost{
  display:inline-flex;align-items:center;gap:8px;
  padding:14px 30px;border-radius:8px;
  border:1px solid rgba(255,255,255,.2);
  color:rgba(255,255,255,.7);font-size:.84rem;font-weight:500;
  background:rgba(255,255,255,.04);backdrop-filter:blur(8px);
  transition:border-color .3s,background .3s,color .3s;
}
.btn-ghost:hover{border-color:rgba(255,255,255,.55);background:rgba(255,255,255,.1);color:var(--white)}
/* Hero right panel — stats */
.hero-stats-panel{
  position:absolute;right:80px;top:50%;transform:translateY(-50%);
  z-index:4;display:flex;flex-direction:column;gap:3px;
  opacity:0;animation:fadeLeft .8s var(--e1) 2.6s forwards;
}
@keyframes fadeLeft{from{opacity:0;transform:translateY(-50%) translateX(20px)}to{opacity:1;transform:translateY(-50%) translateX(0)}}
.hs{
  background:rgba(255,255,255,.04);
  border:1px solid rgba(255,255,255,.07);
  border-radius:12px;padding:20px 24px;min-width:140px;
  backdrop-filter:blur(10px);
  text-align:center;
  transition:background .3s,border-color .3s,transform .3s var(--e2);
}
.hs:hover{background:rgba(255,255,255,.09);border-color:rgba(232,168,48,.3);transform:translateX(-4px)}
.hs-num{
  font-family:'Cormorant',serif;font-size:2.4rem;font-weight:500;
  color:var(--gilt);line-height:1;
  display:flex;justify-content:center;align-items:baseline;gap:2px;
}
.hs-num sup{font-size:1.2rem}
.hs-lbl{
  font-size:.59rem;letter-spacing:2px;text-transform:uppercase;
  color:rgba(255,255,255,.3);margin-top:5px;
}
/* Slide indicators */
.hero-pages{
  position:absolute;bottom:40px;right:80px;z-index:4;
  font-family:'Cormorant',serif;font-size:1.1rem;
  color:rgba(255,255,255,.3);
  opacity:0;animation:fadeUp .8s var(--e1) 2.8s forwards;
}
.hero-pages .curr{color:var(--gilt);font-size:1.5rem}
@keyframes fadeUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}

/* ╔══════════════════════════════════════════════╗
   ║  MARQUEE STRIP                               ║
   ╚══════════════════════════════════════════════╝ */
.marquee-wrap{
  background:var(--grove);
  border-top:1px solid rgba(255,255,255,.06);
  border-bottom:1px solid rgba(255,255,255,.06);
  overflow:hidden;padding:14px 0;
}
.marquee-track{
  display:flex;white-space:nowrap;
  animation:marquee 28s linear infinite;
}
.marquee-track:hover{animation-play-state:paused}
@keyframes marquee{to{transform:translateX(-50%)}}
.m-item{
  display:inline-flex;align-items:center;gap:10px;
  padding:0 32px;
  font-size:.68rem;font-weight:600;letter-spacing:2.5px;
  text-transform:uppercase;color:rgba(255,255,255,.4);
}
.m-sep{color:var(--gilt);font-size:1.2rem}

/* ╔══════════════════════════════════════════════╗
   ║  PRODUCTS — EDITORIAL GRID                   ║
   ╚══════════════════════════════════════════════╝ */
.sec{padding:120px 48px}
.wrap{max-width:var(--max);margin:0 auto}
.sec-dark{background:var(--deep)}
.sec-void{background:var(--void)}
.sec-rich{background:var(--rich)}

/* Section header */
.sechead{margin-bottom:80px}
.sechead-row{
  display:flex;justify-content:space-between;
  align-items:flex-end;gap:32px;
}
.sechead-kicker{
  font-size:.62rem;letter-spacing:4px;text-transform:uppercase;
  color:var(--leaf);margin-bottom:14px;
  display:flex;align-items:center;gap:12px;
}
.kicker-bar{width:32px;height:1px;background:var(--leaf)}
.sechead h2{
  font-family:'Cormorant',serif;
  font-size:clamp(2.4rem,4vw,3.8rem);
  font-weight:300;line-height:1.08;
  color:var(--white);letter-spacing:-.5px;
}
.sechead h2 em{font-style:italic;color:var(--gilt)}
.sechead-link{
  font-size:.75rem;font-weight:600;letter-spacing:2px;
  text-transform:uppercase;color:var(--leaf);
  display:flex;align-items:center;gap:8px;
  transition:color .25s,gap .25s;
  flex-shrink:0;
}
.sechead-link:hover{color:var(--gilt);gap:14px}
.sechead-link::after{content:'→';font-size:.9rem}

/* Products editorial grid */
.prod-editorial{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:2px;
}
.pe{
  position:relative;overflow:hidden;
  background:var(--rich);
  cursor:none;
  aspect-ratio:auto;
}
/* First card bigger */
.pe:first-child{
  grid-row:span 2;
  display:flex;flex-direction:column;
}
.pe-img{
  overflow:hidden;
  flex-shrink:0;
}
.pe:first-child .pe-img{flex:1;min-height:240px}
.pe:not(:first-child) .pe-img{height:200px}
.pe-img img{
  width:100%;height:100%;object-fit:contain;
  background:var(--deep);padding:24px;
  transition:transform .7s var(--e1);
}
.pe:hover .pe-img img{transform:scale(1.08)}
/* Shine */
.pe::after{
  content:'';position:absolute;
  top:-60%;left:-60%;width:30%;height:200%;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,.06),transparent);
  transform:skewX(-18deg);
  transition:left .7s var(--e1);
  pointer-events:none;
  z-index:2;
}
.pe:hover::after{left:160%}
.pe-info{padding:28px 28px 32px}
.pe-badge{
  display:inline-block;margin-bottom:10px;
  font-size:.58rem;font-weight:700;letter-spacing:1.5px;
  text-transform:uppercase;padding:4px 10px;border-radius:4px;
}
.b-gold{background:rgba(232,168,48,.15);color:var(--gilt);border:1px solid rgba(232,168,48,.25)}
.b-green{background:rgba(61,122,76,.2);color:var(--sage);border:1px solid rgba(61,122,76,.3)}
.b-muted{background:rgba(255,255,255,.07);color:rgba(255,255,255,.5);border:1px solid rgba(255,255,255,.1)}
.pe-cat{
  font-size:.6rem;letter-spacing:2.5px;text-transform:uppercase;
  color:var(--leaf);margin-bottom:8px;
}
.pe-name{
  font-family:'Cormorant',serif;
  font-size:1.3rem;font-weight:500;
  color:var(--white);line-height:1.3;margin-bottom:8px;
}
.pe:first-child .pe-name{font-size:1.7rem}
.pe-formula{
  font-size:.72rem;color:rgba(255,255,255,.4);
  margin-bottom:10px;letter-spacing:.3px;
}
.pe-desc{
  font-size:.79rem;color:rgba(255,255,255,.38);
  line-height:1.75;
  display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden;
  margin-bottom:18px;
}
.pe:first-child .pe-desc{-webkit-line-clamp:3}
.pe-foot{
  display:flex;justify-content:space-between;align-items:center;
  padding-top:16px;
  border-top:1px solid rgba(255,255,255,.07);
}
.pe-pack{font-size:.7rem;color:rgba(255,255,255,.28)}
.pe-btn{
  display:inline-flex;align-items:center;gap:6px;
  font-size:.7rem;font-weight:600;letter-spacing:1.5px;
  text-transform:uppercase;color:var(--leaf);
  transition:color .25s,gap .25s;
}
.pe-btn:hover{color:var(--gilt);gap:10px}
.pe-btn::after{content:'→';transition:transform .25s}
.pe-btn:hover::after{transform:translateX(3px)}

/* ╔══════════════════════════════════════════════╗
   ║  WHY US — BENTO GRID                         ║
   ╚══════════════════════════════════════════════╝ */
.bento{
  display:grid;
  grid-template-columns:repeat(12,1fr);
  grid-template-rows:auto;
  gap:16px;
}
.bento-item{
  background:rgba(255,255,255,.03);
  border:1px solid rgba(255,255,255,.07);
  border-radius:20px;padding:40px;
  transition:background .3s,border-color .3s,transform .35s var(--e2);
}
.bento-item:hover{
  background:rgba(255,255,255,.07);
  border-color:rgba(93,158,108,.25);
  transform:translateY(-6px);
}
.bi-1{grid-column:span 4;grid-row:span 2}
.bi-2{grid-column:span 4}
.bi-3{grid-column:span 4}
.bi-4{grid-column:span 5}
.bi-5{grid-column:span 3}
.bi-6{grid-column:span 4}
/* Highlight bento */
.bento-item.accent{
  background:linear-gradient(145deg,var(--grove),var(--fern));
  border-color:rg