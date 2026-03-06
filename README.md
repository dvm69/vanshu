<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>for vanshu 🐚</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400&family=Tenor+Sans&display=swap" rel="stylesheet">
<style>
/* ════════════════════════════════════════
   TULIP COLOR SYSTEM
   Pink tulip:    #F472B6 → #EC4899 → #DB2777
   Purple tulip:  #A78BFA → #8B5CF6 → #7C3AED  
   Blue tulip:    #60A5FA → #3B82F6 → #2563EB
   Lavender:      #C4B5FD → #DDD6FE
   Coral:         #FB7185 → #F43F5E
   Sky:           #BAE6FD → #7DD3FC
   Peach accent:  #FCA5A5 → #FDA4AF
════════════════════════════════════════ */
:root{
  --tp:  #F472B6;  /* tulip pink */
  --tpp: #EC4899;  /* deep tulip pink */
  --tv:  #A78BFA;  /* tulip violet */
  --tb:  #60A5FA;  /* tulip blue */
  --tbb: #3B82F6;  /* deep tulip blue */
  --lav: #C4B5FD;  /* lavender */
  --sky: #BAE6FD;  /* sky */
  --cor: #FB7185;  /* coral */
  --pch: #FDA4AF;  /* peach */
  --mg:  linear-gradient(135deg,#F472B6,#A78BFA,#60A5FA);
  --mg2: linear-gradient(135deg,#60A5FA,#A78BFA,#F472B6);
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-snap-type:y mandatory;overflow-y:scroll;}
body{background:#08041a;color:#fff;font-family:'Tenor Sans',sans-serif;cursor:none;overflow-x:hidden;}

/* ── CURSOR ── */
#cur{position:fixed;width:12px;height:12px;border-radius:50%;pointer-events:none;z-index:99999;
  background:radial-gradient(circle,#F472B6,#A78BFA);
  box-shadow:0 0 10px #F472B6,0 0 20px #A78BFA;
  transition:transform .1s;}
#cur2{position:fixed;width:36px;height:36px;border-radius:50%;border:1.5px solid rgba(196,181,253,.5);pointer-events:none;z-index:99998;transition:all .15s ease;}

/* ── LOADING ── */
#loading{position:fixed;inset:0;z-index:9999;
  background:linear-gradient(135deg,#08041a,#120828,#080c1e);
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:1.5rem;}
.lt{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:1.3rem;
  background:var(--mg);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  letter-spacing:.3em;}
.lbw{width:200px;height:2px;background:rgba(255,255,255,.08);border-radius:2px;overflow:hidden;}
.lb{height:100%;width:0;background:linear-gradient(90deg,#F472B6,#A78BFA,#60A5FA);border-radius:2px;}

/* ── SECTIONS ── */
section{scroll-snap-align:start;scroll-snap-stop:always;height:100vh;position:relative;overflow:hidden;}
#s-memories{height:auto;min-height:100vh;}

/* ── GLOBAL ANIMATED MESH BG per section ── */
.mesh-bg{position:absolute;inset:0;z-index:0;pointer-events:none;}

/* ── GRAIN ── */
.grain{position:fixed;inset:0;z-index:2;pointer-events:none;opacity:.03;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  animation:gr 8s steps(1) infinite;}
@keyframes gr{0%,100%{transform:translate(0,0);}25%{transform:translate(-5%,5%);}50%{transform:translate(5%,-5%);}75%{transform:translate(-3%,3%);}}

/* ══════════════════════════════
   SCENE 1 — INTRO
   Deep indigo with tulip aurora + 3D stars + wave bar
══════════════════════════════ */
#s-intro{display:flex;align-items:center;justify-content:center;flex-direction:column;
  background:radial-gradient(ellipse 100% 80% at 50% 0%,#1a0840 0%,#08041a 60%);}

/* Aurora blobs */
#s-intro .mesh-bg{
  background:
    radial-gradient(ellipse 60% 50% at 15% 25%,rgba(244,114,182,.22) 0%,transparent 60%),
    radial-gradient(ellipse 70% 55% at 85% 70%,rgba(96,165,250,.2) 0%,transparent 58%),
    radial-gradient(ellipse 55% 65% at 50% 50%,rgba(167,139,250,.15) 0%,transparent 55%),
    radial-gradient(ellipse 40% 40% at 75% 20%,rgba(196,181,253,.12) 0%,transparent 50%);
  animation:auroramove 10s ease-in-out infinite alternate;}
@keyframes auroramove{
  0%{transform:translate(0,0) scale(1);}
  33%{transform:translate(2%,3%) scale(1.03);}
  66%{transform:translate(-3%,1%) scale(.97);}
  100%{transform:translate(1%,-2%) scale(1.04);}
}

/* 3D Star canvas */
#star-canvas{position:absolute;inset:0;z-index:1;pointer-events:none;}

/* Wave bar at bottom of intro */
#wave-bar{position:absolute;bottom:0;left:0;right:0;z-index:3;pointer-events:none;}

/* Intro text */
.intro-wrap{position:relative;z-index:10;text-align:center;}
.intro-pre{font-size:.72rem;letter-spacing:.5em;text-transform:uppercase;opacity:0;
  margin-bottom:1.5rem;display:block;transform:translateY(20px);
  background:linear-gradient(90deg,var(--tp),var(--lav));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.intro-name{font-family:'Cormorant Garamond',serif;font-size:clamp(5rem,20vw,13rem);
  font-weight:300;font-style:italic;line-height:.9;display:inline-block;}
.intro-name .ch{display:inline-block;opacity:0;transform:translateY(120px) rotateX(90deg);transform-origin:top center;}
.gname{
  background:linear-gradient(135deg,#F472B6,#C084FC,#818CF8,#60A5FA,#34D399,#C084FC,#F472B6);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  background-size:400%;animation:gs 6s ease infinite;
  filter:drop-shadow(0 0 30px rgba(244,114,182,.4)) drop-shadow(0 0 60px rgba(167,139,250,.3));}
@keyframes gs{0%,100%{background-position:0%;}50%{background-position:100%;}}
.intro-from{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:1.05rem;
  color:rgba(196,181,253,.55);margin-top:2rem;opacity:0;transform:translateY(20px);}
.iscroll{position:absolute;bottom:5rem;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:.7rem;z-index:10;opacity:0;}
.iscroll span{font-size:.6rem;letter-spacing:.4em;text-transform:uppercase;color:rgba(186,230,253,.4);}
.sdot{width:5px;height:5px;border-radius:50%;
  background:var(--tp);box-shadow:0 0 8px var(--tp);animation:sd 1.5s ease-in-out infinite;}
@keyframes sd{0%,100%{opacity:.3;transform:translateY(0);}50%{opacity:1;transform:translateY(8px);}}

/* Floating tulip petals on intro */
.petal{position:absolute;border-radius:50% 0 50% 0;pointer-events:none;
  animation:petalfall linear infinite;opacity:0;}
@keyframes petalfall{
  0%{opacity:0;transform:translateY(-60px) rotate(0deg);}
  5%{opacity:.8;}
  95%{opacity:.5;}
  100%{opacity:0;transform:translateY(110vh) rotate(720deg);}
}

/* ══════════════════════════════
   SCENE 2 — VINYL MEMORIES
   Deep blue-violet with pink tulip accents
══════════════════════════════ */
#s-memories{
  display:flex;flex-direction:column;align-items:center;
  justify-content:flex-start;padding:5rem 1rem 6rem;gap:2.5rem;
  background:
    radial-gradient(ellipse 65% 50% at 10% 20%,rgba(96,165,250,.18) 0%,transparent 55%),
    radial-gradient(ellipse 55% 60% at 90% 80%,rgba(244,114,182,.15) 0%,transparent 50%),
    radial-gradient(ellipse 50% 50% at 50% 50%,rgba(167,139,250,.1) 0%,transparent 60%),
    #060c1e;
}
.mt{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:clamp(1.8rem,5vw,3.5rem);
  text-align:center;opacity:0;transform:translateY(40px);transition:all 1s ease;z-index:10;position:relative;
  background:linear-gradient(135deg,var(--sky),var(--lav),var(--tp));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  filter:drop-shadow(0 0 20px rgba(96,165,250,.3));}
.mt.vis{opacity:1;transform:translateY(0);}
.ms{font-size:.68rem;letter-spacing:.3em;text-transform:uppercase;
  color:var(--lav);text-align:center;opacity:0;transition:all 1s ease .2s;z-index:10;position:relative;}
.ms.vis{opacity:.65;}

.vinyl-row{display:flex;gap:2rem;flex-wrap:wrap;justify-content:center;
  z-index:10;position:relative;perspective:1400px;width:100%;max-width:960px;}

.vunit{display:flex;flex-direction:column;align-items:center;gap:1rem;
  opacity:0;transform:translateY(70px) scale(.85);
  transition:opacity .7s ease,transform .7s cubic-bezier(.175,.885,.32,1.275);
  cursor:none;position:relative;}
.vunit.vis{opacity:1;transform:translateY(0) scale(1);}

.vinyl{width:158px;height:158px;border-radius:50%;position:relative;
  transform-style:preserve-3d;
  transition:transform .6s cubic-bezier(.175,.885,.32,1.275),filter .4s ease;
  filter:drop-shadow(0 16px 32px rgba(0,0,0,.6));}
.vunit:hover .vinyl{transform:rotateY(-28deg) rotateX(10deg) scale(1.12);
  filter:drop-shadow(0 28px 55px rgba(0,0,0,.7)) drop-shadow(0 0 40px var(--vglow));}

/* Grooved record */
.vinyl-face{position:absolute;inset:0;border-radius:50%;overflow:hidden;
  background:
    radial-gradient(circle at 50% 50%,
    #282828 0%,#111 18%,#1c1c1c 19%,#0a0a0a 32%,
    #161616 33%,#090909 46%,#131313 47%,#070707 60%,
    #101010 61%,#050505 74%,#0d0d0d 75%,#030303 100%);}
.vinyl-face::before{content:'';position:absolute;inset:0;border-radius:50%;
  background:repeating-conic-gradient(rgba(255,255,255,.012) 0deg,transparent 1deg,transparent 3deg,rgba(255,255,255,.008) 4deg);
  mix-blend-mode:screen;}
/* Tulip-hued iridescent sheen */
.vinyl-face::after{content:'';position:absolute;inset:0;border-radius:50%;
  background:conic-gradient(
    transparent 0%,
    rgba(244,114,182,.22) 7%,
    rgba(192,132,252,.18) 15%,
    transparent 22%,
    rgba(96,165,250,.2) 32%,
    rgba(52,211,153,.12) 40%,
    transparent 47%,
    rgba(244,114,182,.2) 57%,
    rgba(167,139,250,.18) 67%,
    transparent 73%,
    rgba(186,230,253,.15) 83%,
    transparent 90%,
    rgba(244,114,182,.18) 97%,
    transparent 100%
  );animation:sheen var(--vspeed,3s) linear infinite;}
@keyframes sheen{to{transform:rotate(360deg);}}

.vinyl-label{position:absolute;inset:30%;border-radius:50%;display:flex;
  flex-direction:column;align-items:center;justify-content:center;gap:.12rem;
  z-index:2;border:1px solid rgba(255,255,255,.08);}
.vinyl-label-title{font-size:.35rem;letter-spacing:.1em;text-transform:uppercase;
  color:rgba(255,255,255,.75);text-align:center;line-height:1.5;}
.vinyl-label-artist{font-size:.29rem;color:rgba(255,255,255,.38);text-align:center;}
.vinyl-hole{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  width:11px;height:11px;border-radius:50%;background:#000;z-index:3;
  box-shadow:0 0 0 1px rgba(255,255,255,.1);}

.vunit.playing .vinyl-face{animation:recspin var(--vspeed,3s) linear infinite;}
@keyframes recspin{to{transform:rotate(360deg);}}
.vunit.playing .vinyl-face::after{animation:none;}

/* Pop card */
.vmem{position:absolute;bottom:calc(100% + 8px);left:50%;
  transform:translateX(-50%) translateY(20px) scale(.7);
  opacity:0;pointer-events:none;
  transition:all .5s cubic-bezier(.175,.885,.32,1.275);z-index:50;width:185px;}
.vunit.popped .vmem{transform:translateX(-50%) translateY(-8px) scale(1);opacity:1;pointer-events:all;}
.vmem-card{background:var(--vcardbg);border:1px solid rgba(255,255,255,.18);
  border-radius:22px;padding:1.3rem 1.1rem;text-align:center;
  box-shadow:0 28px 56px rgba(0,0,0,.6),0 0 32px var(--vglow),inset 0 1px 0 rgba(255,255,255,.12);
  position:relative;overflow:hidden;cursor:none;}
.vmem-card::before{content:'';position:absolute;inset:0;border-radius:22px;
  background:linear-gradient(135deg,rgba(255,255,255,.09),transparent 50%);pointer-events:none;}
.vmem-card::after{content:'';position:absolute;bottom:-10px;left:50%;transform:translateX(-50%);
  width:2px;height:14px;background:linear-gradient(to bottom,rgba(255,255,255,.18),transparent);}
.vmem-emoji{font-size:2.2rem;display:block;margin-bottom:.4rem;
  filter:drop-shadow(0 0 12px var(--vglow));animation:vfe 2.5s ease-in-out infinite;}
@keyframes vfe{0%,100%{transform:translateY(0);}50%{transform:translateY(-6px);}}
.vmem-title{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:.86rem;
  margin-bottom:.3rem;line-height:1.3;color:var(--vglow);
  text-shadow:0 0 12px var(--vglow);}
.vmem-hint{font-size:.5rem;letter-spacing:.18em;text-transform:uppercase;color:rgba(255,255,255,.32);}
.vunit-label{font-size:.58rem;letter-spacing:.18em;text-transform:uppercase;
  color:rgba(255,255,255,.28);text-align:center;transition:color .3s,text-shadow .3s;}
.vunit:hover .vunit-label,.vunit.popped .vunit-label{color:var(--vglow);text-shadow:0 0 10px var(--vglow);}

.vparticle{position:absolute;top:50%;left:50%;width:7px;height:7px;border-radius:50%;
  pointer-events:none;z-index:60;animation:vburst var(--vbd,.6s) ease forwards;}
@keyframes vburst{0%{transform:translate(-50%,-50%) translate(0,0) scale(1);opacity:1;}
  100%{transform:translate(-50%,-50%) translate(var(--vbx),var(--vby)) scale(0);opacity:0;}}

/* ══════════════════════════════
   MODAL — full tulip palette
══════════════════════════════ */
#modal{position:fixed;inset:0;z-index:5000;display:flex;align-items:center;
  justify-content:center;padding:2rem;opacity:0;pointer-events:none;transition:opacity .5s ease;}
#modal.open{opacity:1;pointer-events:all;}
.mbk{position:absolute;inset:0;background:rgba(4,2,16,.88);backdrop-filter:blur(32px);}
.mbox{max-width:440px;width:100%;border-radius:36px;padding:2.8rem 2.4rem;
  position:relative;z-index:1;transform:translateY(40px) scale(.9);
  transition:all .5s cubic-bezier(.175,.885,.32,1.275);
  border:1px solid rgba(255,255,255,.14);
  box-shadow:0 60px 120px rgba(0,0,0,.65),0 0 60px var(--mglow,rgba(167,139,250,.2)),
  inset 0 1px 0 rgba(255,255,255,.1);}
#modal.open .mbox{transform:translateY(0) scale(1);}
.micon{font-size:3rem;margin-bottom:1rem;animation:fi 3s ease-in-out infinite;}
@keyframes fi{0%,100%{transform:translateY(0);}50%{transform:translateY(-10px);}}
.mh{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:1.75rem;margin-bottom:1rem;}
.mp{font-size:.9rem;line-height:1.9;color:rgba(255,255,255,.75);font-weight:300;}
.mcb{position:absolute;top:1.4rem;right:1.4rem;width:32px;height:32px;border-radius:50%;
  border:1px solid rgba(255,255,255,.15);background:rgba(255,255,255,.05);
  color:rgba(255,255,255,.55);font-size:.85rem;cursor:none;display:flex;
  align-items:center;justify-content:center;transition:all .2s;}
.mcb:hover{background:rgba(255,255,255,.12);color:#fff;}
.nplay{display:flex;align-items:center;gap:.75rem;margin-top:1.4rem;padding:.75rem .9rem;
  border-radius:14px;background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.08);}
.ndisc{width:34px;height:34px;border-radius:50%;animation:spin 4s linear infinite;flex-shrink:0;}
@keyframes spin{to{transform:rotate(360deg);}}
.ninfo{flex:1;}
.ntrack{font-size:.78rem;color:#fff;}
.nartist{font-size:.62rem;color:rgba(255,255,255,.4);}
.nbar{height:2px;background:rgba(255,255,255,.1);border-radius:2px;margin-top:.45rem;overflow:hidden;}
.nprog{height:100%;width:30%;border-radius:2px;transition:width .1s linear;}

/* ══════════════════════════════
   SCENE 3 — MESSAGES
   Deep blue with pink + blue tulip tones
══════════════════════════════ */
#s-messages{display:flex;flex-direction:column;align-items:center;justify-content:center;
  gap:1.8rem;padding:2rem;
  background:
    radial-gradient(ellipse 60% 50% at 20% 30%,rgba(96,165,250,.16) 0%,transparent 55%),
    radial-gradient(ellipse 55% 55% at 80% 65%,rgba(244,114,182,.14) 0%,transparent 52%),
    radial-gradient(ellipse 45% 45% at 50% 80%,rgba(167,139,250,.1) 0%,transparent 55%),
    #060a1c;}
.mst{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:clamp(1.5rem,4vw,2.6rem);
  text-align:center;opacity:0;transform:translateY(30px);transition:all .8s ease;z-index:10;position:relative;
  background:linear-gradient(135deg,var(--tp),var(--lav),var(--sky));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  filter:drop-shadow(0 0 20px rgba(244,114,182,.3));}
.mst.vis{opacity:1;transform:translateY(0);}

.iphone{width:272px;height:548px;border-radius:44px;
  background:linear-gradient(160deg,#0e1020,#080a18);
  border:1.5px solid rgba(167,139,250,.25);
  box-shadow:0 0 0 .5px rgba(167,139,250,.1),0 50px 100px rgba(0,0,0,.8),
    0 0 80px rgba(167,139,250,.1),inset 0 0 30px rgba(96,165,250,.03);
  position:relative;overflow:hidden;opacity:0;
  transform:translateY(60px) rotateX(15deg);
  transition:all 1s cubic-bezier(.175,.885,.32,1.275);z-index:10;}
.iphone.vis{opacity:1;transform:translateY(0) rotateX(0);}
.iphone::before{content:'';position:absolute;inset:0;border-radius:44px;
  background:linear-gradient(160deg,rgba(167,139,250,.07),transparent 40%);pointer-events:none;z-index:20;}
.intch{width:88px;height:22px;background:#000;border-radius:0 0 14px 14px;margin:0 auto;position:relative;z-index:21;}
.istat{display:flex;justify-content:space-between;padding:.22rem 1.1rem;
  font-size:.52rem;color:rgba(196,181,253,.5);position:relative;z-index:20;}
.ihdr{display:flex;align-items:center;gap:.55rem;padding:.4rem 1rem .55rem;
  border-bottom:1px solid rgba(167,139,250,.1);position:relative;z-index:20;}
.iav{width:30px;height:30px;border-radius:50%;
  background:linear-gradient(135deg,var(--tp),var(--lav),var(--tb));
  display:flex;align-items:center;justify-content:center;font-size:.95rem;}
.inm{font-size:.75rem;font-weight:500;color:#fff;}
.ionl{font-size:.58rem;color:#86efac;}
.imsgs{height:calc(100% - 106px);overflow-y:auto;padding:.7rem .65rem;
  display:flex;flex-direction:column;gap:.4rem;scrollbar-width:none;}
.imsgs::-webkit-scrollbar{display:none;}
.imsg{max-width:80%;padding:.42rem .78rem;border-radius:14px;font-size:.66rem;
  line-height:1.55;opacity:0;transform:translateY(8px);}
.imsg.vis{opacity:1;transform:translateY(0);transition:all .3s ease;}
/* my bubbles — pink-to-violet tulip gradient */
.im{background:linear-gradient(135deg,#9d174d,#6d28d9);align-self:flex-end;
  border-bottom-right-radius:3px;color:rgba(255,255,255,.95);
  box-shadow:0 4px 12px rgba(167,139,250,.25);}
.it{background:rgba(255,255,255,.09);align-self:flex-start;
  border-bottom-left-radius:3px;color:rgba(255,255,255,.88);}
.itime{font-size:.46rem;opacity:.38;text-align:right;margin-top:.2rem;}

.spill{display:flex;align-items:center;gap:.72rem;padding:.75rem 1.7rem;border-radius:50px;
  background:rgba(30,215,96,.07);border:1px solid rgba(30,215,96,.3);
  text-decoration:none;color:#fff;font-size:.8rem;cursor:none;
  opacity:0;transform:translateY(18px);transition:all .6s ease .3s;position:relative;z-index:10;
  box-shadow:0 0 20px rgba(30,215,96,.08);}
.spill.vis{opacity:1;transform:translateY(0);}
.spill:hover{background:rgba(30,215,96,.14);box-shadow:0 0 35px rgba(30,215,96,.18);}
.spdot{width:7px;height:7px;border-radius:50%;background:#1DB954;animation:spd 1.5s ease infinite;}
@keyframes spd{0%,100%{transform:scale(1);}50%{transform:scale(1.6);opacity:.5;}}

/* ══════════════════════════════
   SCENE 4 — SUNSET + BEACH WAVES
   Now with full animated wave system
══════════════════════════════ */
#s-sunset{position:relative;background:#0a0410;}
#sunc{position:absolute;inset:0;width:100%;height:100%;}

/* Beach foam particles */
.foam{position:absolute;border-radius:50%;pointer-events:none;background:rgba(255,255,255,.7);
  animation:foamdrift linear infinite;}
@keyframes foamdrift{
  0%{transform:translateX(0) scale(1);opacity:.8;}
  50%{opacity:.4;}
  100%{transform:translateX(var(--fx,30px)) scale(.2);opacity:0;}
}

.sovt{position:absolute;inset:0;display:flex;flex-direction:column;
  align-items:center;justify-content:flex-end;padding-bottom:8rem;
  text-align:center;z-index:10;
  background:linear-gradient(transparent 35%,rgba(5,2,15,.55) 100%);}
.sunh{font-family:'Cormorant Garamond',serif;font-style:italic;
  font-size:clamp(2rem,7vw,5rem);opacity:0;transform:translateY(30px);transition:all 1s ease;
  background:linear-gradient(135deg,#FDA4AF,#F9A8D4,#FDE68A,#FDA4AF);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  filter:drop-shadow(0 0 30px rgba(249,168,212,.4));}
.sunh.vis{opacity:1;transform:translateY(0);}
.sunp{font-family:'Cormorant Garamond',serif;font-style:italic;
  color:rgba(253,211,175,.6);font-size:1.05rem;margin-top:.8rem;opacity:0;transition:all 1s ease .4s;}
.sunp.vis{opacity:1;}

/* ══════════════════════════════
   SCENE 5 — THE QUESTION
   Full pink-blue tulip bloom
══════════════════════════════ */
#s-question{display:flex;flex-direction:column;align-items:center;
  justify-content:center;padding:3rem 2rem;position:relative;
  background:
    radial-gradient(ellipse 80% 65% at 25% 40%,rgba(244,114,182,.2) 0%,transparent 55%),
    radial-gradient(ellipse 70% 70% at 75% 60%,rgba(96,165,250,.18) 0%,transparent 55%),
    radial-gradient(ellipse 55% 55% at 50% 20%,rgba(167,139,250,.16) 0%,transparent 50%),
    radial-gradient(ellipse 50% 40% at 50% 90%,rgba(251,113,133,.12) 0%,transparent 50%),
    #08041a;}
/* petal rain on question scene */
#q-petals{position:absolute;inset:0;pointer-events:none;z-index:1;overflow:hidden;}

.qfrom{font-size:.68rem;letter-spacing:.4em;text-transform:uppercase;
  color:var(--lav);margin-bottom:2rem;opacity:0;transition:opacity 1s;
  position:relative;z-index:10;}
.qfrom.vis{opacity:.65;}
.qtxt{font-family:'Cormorant Garamond',serif;font-style:italic;
  font-size:clamp(2rem,7vw,4.8rem);text-align:center;max-width:680px;line-height:1.15;
  margin-bottom:1.5rem;opacity:0;transform:translateY(40px);transition:all 1s ease .2s;
  position:relative;z-index:10;}
.qtxt.vis{opacity:1;transform:translateY(0);}
.hl{background:linear-gradient(135deg,#F472B6,#C084FC,#60A5FA,#34D399,#C084FC,#F472B6);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  background-size:300%;animation:gs 5s ease infinite;
  filter:drop-shadow(0 0 25px rgba(244,114,182,.35));}
.qsub{font-family:'Cormorant Garamond',serif;font-style:italic;
  color:rgba(196,181,253,.42);font-size:1rem;margin-bottom:3rem;text-align:center;
  opacity:0;transition:opacity 1s .4s;position:relative;z-index:10;}
.qsub.vis{opacity:1;}
.qbtns{display:flex;gap:1.5rem;align-items:center;flex-wrap:wrap;
  justify-content:center;opacity:0;transition:opacity 1s .6s;position:relative;z-index:10;}
.qbtns.vis{opacity:1;}

.byy{padding:1rem 3rem;border-radius:50px;
  background:linear-gradient(135deg,#ec4899,#a855f7,#3b82f6);
  border:none;color:#fff;font-family:'Cormorant Garamond',serif;font-style:italic;font-size:1.3rem;
  cursor:none;position:relative;overflow:hidden;
  box-shadow:0 8px 30px rgba(168,85,247,.4),0 0 60px rgba(244,114,182,.2);
  transition:all .3s ease;}
.byy::before{content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(255,255,255,.22),transparent);opacity:0;transition:opacity .3s;}
.byy:hover{transform:scale(1.07);
  box-shadow:0 18px 55px rgba(168,85,247,.6),0 0 80px rgba(244,114,182,.35);}
.byy:hover::before{opacity:1;}
/* Pulse ring on yes button */
.byy::after{content:'';position:absolute;inset:-4px;border-radius:54px;
  border:2px solid rgba(244,114,182,.4);animation:btnpulse 2s ease infinite;}
@keyframes btnpulse{0%,100%{transform:scale(1);opacity:.5;}50%{transform:scale(1.06);opacity:0;}}

.bno{padding:.55rem 1.5rem;border-radius:50px;background:rgba(255,255,255,.03);
  border:1px solid rgba(255,255,255,.1);color:rgba(255,255,255,.3);
  font-size:.82rem;cursor:none;position:fixed;transition:all .25s ease;bottom:28%;right:8%;}

/* ── YES SCREEN ── */
#yes-screen{position:fixed;inset:0;z-index:8000;
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  background:
    radial-gradient(ellipse 70% 60% at 30% 40%,rgba(244,114,182,.25) 0%,transparent 55%),
    radial-gradient(ellipse 65% 70% at 70% 60%,rgba(96,165,250,.22) 0%,transparent 55%),
    radial-gradient(ellipse 50% 40% at 50% 15%,rgba(167,139,250,.18) 0%,transparent 50%),
    #08041a;
  opacity:0;pointer-events:none;transition:opacity 1s ease;text-align:center;padding:2rem;}
#yes-screen.open{opacity:1;pointer-events:all;}
#ycvs{position:absolute;inset:0;pointer-events:none;}
.yb{font-size:5rem;animation:ybb .5s ease infinite alternate;position:relative;z-index:2;}
@keyframes ybb{from{transform:scale(1) translateY(0);}to{transform:scale(1.12) translateY(-14px);}}
.yh{font-family:'Cormorant Garamond',serif;font-style:italic;
  font-size:clamp(2.5rem,8vw,5rem);
  background:linear-gradient(135deg,#F472B6,#C084FC,#60A5FA,#34D399,#FDE68A,#F472B6);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  background-size:300%;animation:gs 3s ease infinite;
  margin:1.4rem 0;position:relative;z-index:2;
  filter:drop-shadow(0 0 30px rgba(244,114,182,.5));}
.yp{font-family:'Cormorant Garamond',serif;font-style:italic;
  font-size:1.15rem;color:rgba(196,181,253,.7);max-width:360px;position:relative;z-index:2;}

/* ── RIPPLE ── */
.rpl{position:fixed;border-radius:50%;pointer-events:none;z-index:9990;
  animation:ro .65s ease forwards;}
@keyframes ro{from{width:0;height:0;opacity:.8;transform:translate(-50%,-50%);}
  to{width:120px;height:120px;opacity:0;transform:translate(-50%,-50%);}}
</style>
</head>
<body>

<div id="loading">
  <div class="lt">loading memories...</div>
  <div class="lbw"><div class="lb" id="lbar"></div></div>
</div>

<div class="grain"></div>
<div id="cur"></div>
<div id="cur2"></div>

<!-- ═══════════ SCENE 1 — INTRO ═══════════ -->
<section id="s-intro">
  <div class="mesh-bg"></div>
  <canvas id="star-canvas"></canvas>
  <canvas id="wave-bar" height="120"></canvas>

  <div class="intro-wrap">
    <span class="intro-pre" id="ipre">a little something for</span>
    <div class="intro-name">
      <span class="ch gname">V</span><span class="ch gname">a</span><span class="ch gname">n</span><span class="ch gname">s</span><span class="ch gname">h</span><span class="ch gname">u</span>
    </div>
    <div class="intro-from" id="ifrom">from devam, with the whole ocean 🌊</div>
  </div>
  <div class="iscroll" id="iscrl">
    <span>scroll to remember</span>
    <div class="sdot"></div>
  </div>
</section>

<!-- ═══════════ SCENE 2 — VINYL MEMORIES ═══════════ -->
<section id="s-memories">
  <h2 class="mt" id="mtit">songs that remind me of you</h2>
  <p class="ms" id="msub">spin the records — our memories live inside them</p>

  <div class="vinyl-row">
    <div class="vunit" id="mc0" style="--vglow:#FDE68A;--vcardbg:linear-gradient(135deg,#1a1205,#251a08);--vspeed:3.2s;transition-delay:.05s" onclick="popVinyl('mc0','shell')">
      <div class="vinyl"><div class="vinyl-face">
        <div class="vinyl-label" style="background:radial-gradient(#2a1e06,#16100a);">
          <div class="vinyl-label-title">STARBOY</div><div class="vinyl-label-artist">The Weeknd</div>
        </div><div class="vinyl-hole"></div>
      </div></div>
      <div class="vmem"><div class="vmem-card"><span class="vmem-emoji">🐚</span>
        <div class="vmem-title">the yellow &amp; purple shells</div>
        <div class="vmem-hint">tap again to relive →</div>
      </div></div>
      <div class="vunit-label">Starboy · 2016</div>
    </div>

    <div class="vunit" id="mc1" style="--vglow:#F9A8D4;--vcardbg:linear-gradient(135deg,#1a0818,#260e22);--vspeed:2.8s;transition-delay:.15s" onclick="popVinyl('mc1','lip')">
      <div class="vinyl"><div class="vinyl-face">
        <div class="vinyl-label" style="background:radial-gradient(#28101e,#14080e);">
          <div class="vinyl-label-title">BEAUTY BEHIND<br>THE MADNESS</div><div class="vinyl-label-artist">The Weeknd</div>
        </div><div class="vinyl-hole"></div>
      </div></div>
      <div class="vmem"><div class="vmem-card"><span class="vmem-emoji">💄</span>
        <div class="vmem-title">her signature lipgloss</div>
        <div class="vmem-hint">tap again to relive →</div>
      </div></div>
      <div class="vunit-label">BBTM · 2015</div>
    </div>

    <div class="vunit" id="mc2" style="--vglow:#C4B5FD;--vcardbg:linear-gradient(135deg,#0e0820,#16082e);--vspeed:3.6s;transition-delay:.25s" onclick="popVinyl('mc2','ipod')">
      <div class="vinyl"><div class="vinyl-face">
        <div class="vinyl-label" style="background:radial-gradient(#1a0830,#0c0418);">
          <div class="vinyl-label-title">AFTER HOURS</div><div class="vinyl-label-artist">The Weeknd</div>
        </div><div class="vinyl-hole"></div>
      </div></div>
      <div class="vmem"><div class="vmem-card"><span class="vmem-emoji">🎵</span>
        <div class="vmem-title">one earbud each, always</div>
        <div class="vmem-hint">tap again to relive →</div>
      </div></div>
      <div class="vunit-label">After Hours · 2020</div>
    </div>

    <div class="vunit" id="mc3" style="--vglow:#BAE6FD;--vcardbg:linear-gradient(135deg,#071428,#0a1a32);--vspeed:4s;transition-delay:.35s" onclick="popVinyl('mc3','villa')">
      <div class="vinyl"><div class="vinyl-face">
        <div class="vinyl-label" style="background:radial-gradient(#0a1828,#050e18);">
          <div class="vinyl-label-title">DAWN FM</div><div class="vinyl-label-artist">The Weeknd</div>
        </div><div class="vinyl-hole"></div>
      </div></div>
      <div class="vmem"><div class="vmem-card"><span class="vmem-emoji">🏡</span>
        <div class="vmem-title">our someday villa</div>
        <div class="vmem-hint">tap again to relive →</div>
      </div></div>
      <div class="vunit-label">Dawn FM · 2022</div>
    </div>

    <div class="vunit" id="mc4" style="--vglow:#F472B6;--vcardbg:linear-gradient(135deg,#1a0628,#22083a);--vspeed:3s;transition-delay:.45s" onclick="popVinyl('mc4','phone')">
      <div class="vinyl"><div class="vinyl-face">
        <div class="vinyl-label" style="background:radial-gradient(#1e0628,#0e0214);">
          <div class="vinyl-label-title">KISS LAND</div><div class="vinyl-label-artist">The Weeknd</div>
        </div><div class="vinyl-hole"></div>
      </div></div>
      <div class="vmem"><div class="vmem-card"><span class="vmem-emoji">📱</span>
        <div class="vmem-title">"come over" (we can't)</div>
        <div class="vmem-hint">tap again to relive →</div>
      </div></div>
      <div class="vunit-label">Kiss Land · 2013</div>
    </div>
  </div>
</section>

<!-- ═══════════ SCENE 3 — MESSAGES ═══════════ -->
<section id="s-messages">
  <h2 class="mst" id="mst">things we say at 2am</h2>
  <div class="iphone" id="iph">
    <div class="intch"></div>
    <div class="istat"><span>9:41</span><span>●●●</span></div>
    <div class="ihdr"><div class="iav">🌙</div><div><div class="inm">Vanshu 💜</div><div class="ionl">online</div></div></div>
    <div class="imsgs" id="imsgs">
      <div class="imsg im">come over, i miss you 🥺<div class="itime">11:48 pm</div></div>
      <div class="imsg it">devam it's literally midnight 😭<div class="itime">11:49 pm</div></div>
      <div class="imsg im">i know but still<div class="itime">11:49 pm</div></div>
      <div class="imsg it">what would i even tell my mom 💀<div class="itime">11:50 pm</div></div>
      <div class="imsg im">fresh air at midnight obviously<div class="itime">11:50 pm</div></div>
      <div class="imsg it">you are actually insane 😂<div class="itime">11:51 pm</div></div>
      <div class="imsg it">but like... i miss you too 🫶<div class="itime">11:51 pm</div></div>
      <div class="imsg im">SEE!! told you<div class="itime">11:52 pm</div></div>
      <div class="imsg im">ok fine. tomorrow then<div class="itime">11:52 pm</div></div>
      <div class="imsg it">tomorrow 🌅<div class="itime">11:53 pm</div></div>
      <div class="imsg im">also i made something for you btw<div class="itime">11:54 pm</div></div>
      <div class="imsg it">wait what 🥹<div class="itime">11:55 pm</div></div>
      <div class="imsg im">a playlist. and one other thing 😌<div class="itime">11:55 pm</div></div>
      <div class="imsg it">now i need to know<div class="itime">11:56 pm</div></div>
      <div class="imsg im">keep scrolling 🐚<div class="itime">11:56 pm</div></div>
    </div>
  </div>
  <a href="https://open.spotify.com" target="_blank" class="spill" id="spill">
    <div class="spdot"></div><span>a playlist for vanshu</span>
    <span style="opacity:.35;font-size:.72rem">→</span>
  </a>
</section>

<!-- ═══════════ SCENE 4 — SUNSET + WAVES ═══════════ -->
<section id="s-sunset">
  <canvas id="sunc"></canvas>
  <div class="sovt">
    <h2 class="sunh" id="sunh">that evening at the beach...</h2>
    <p class="sunp" id="sunp">the sky looked like it was painted just for us</p>
  </div>
</section>

<!-- ═══════════ SCENE 5 — THE QUESTION ═══════════ -->
<section id="s-question">
  <div id="q-petals"></div>
  <div class="qfrom" id="qfrom">devam → vanshu</div>
  <div class="qtxt" id="qtxt"><span class="hl">will you go on a date</span><br>with me, vanshu? 🌊</div>
  <div class="qsub" id="qsub">i've been meaning to ask you this for a while now...</div>
  <div class="qbtns" id="qbtns">
    <button class="byy" onclick="sayYes()">yes, obviously 💜</button>
    <button class="bno" id="bno" onmouseover="runAway()" ontouchstart="runAway()">maybe not</button>
  </div>
</section>

<!-- YES SCREEN -->
<div id="yes-screen">
  <canvas id="ycvs"></canvas>
  <div class="yb">🌊💜🌷</div>
  <div class="yh">she said yes!!</div>
  <div class="yp">i knew it, vanshu. i genuinely cannot wait. 🌅</div>
</div>

<!-- MODAL -->
<div id="modal" onclick="cm(event)">
  <div class="mbk"></div>
  <div class="mbox" id="mbox">
    <button class="mcb" onclick="cm()">✕</button>
    <div class="micon" id="micon"></div>
    <div class="mh" id="mh"></div>
    <div class="mp" id="mp"></div>
  </div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
/* ─── LOADING ─── */
const lbar=document.getElementById('lbar');
let lp=0,lInt=setInterval(()=>{lp+=Math.random()*7+2;
  if(lp>=100){lp=100;clearInterval(lInt);setTimeout(()=>{
    const ld=document.getElementById('loading');
    ld.style.transition='opacity .8s';ld.style.opacity='0';
    setTimeout(()=>{ld.style.display='none';runIntro();},800);},200);}
  lbar.style.width=lp+'%';},80);

/* ─── CURSOR ─── */
const cur=document.getElementById('cur'),cur2=document.getElementById('cur2');
let cx=0,cy=0;
document.addEventListener('mousemove',e=>{cx=e.clientX;cy=e.clientY;
  cur.style.left=cx-6+'px';cur.style.top=cy-6+'px';
  setTimeout(()=>{cur2.style.left=cx-18+'px';cur2.style.top=cy-18+'px';},80);});
document.addEventListener('click',e=>{
  // rainbow ripple
  const cols=['rgba(244,114,182,.5)','rgba(167,139,250,.5)','rgba(96,165,250,.5)','rgba(52,211,153,.4)'];
  const r=document.createElement('div');r.className='rpl';
  r.style.cssText=`left:${e.clientX}px;top:${e.clientY}px;border-color:${cols[Math.floor(Math.random()*cols.length)]};`;
  document.body.appendChild(r);pTick();setTimeout(()=>r.remove(),700);});

/* ─── AUDIO ─── */
let actx;
function gac(){if(!actx)actx=new(window.AudioContext||window.webkitAudioContext)();return actx;}
function pTick(f=880,d=.08){try{const a=gac(),o=a.createOscillator(),g=a.createGain();o.connect(g);g.connect(a.destination);o.frequency.value=f;o.type='sine';g.gain.setValueAtTime(.1,a.currentTime);g.gain.exponentialRampToValueAtTime(.001,a.currentTime+d);o.start();o.stop(a.currentTime+d);}catch(e){}}
function pChime(){[523,659,784,1047].forEach((f,i)=>setTimeout(()=>pTick(f,.15),i*110));}
function pWhoosh(){try{const a=gac(),o=a.createOscillator(),g=a.createGain();o.connect(g);g.connect(a.destination);o.type='sawtooth';o.frequency.setValueAtTime(160,a.currentTime);o.frequency.exponentialRampToValueAtTime(60,a.currentTime+.4);g.gain.setValueAtTime(.07,a.currentTime);g.gain.exponentialRampToValueAtTime(.001,a.currentTime+.4);o.start();o.stop(a.currentTime+.45);}catch(e){}}
function pYes(){[523,659,784,1047,1318,1568,2093].forEach((f,i)=>setTimeout(()=>pTick(f,.2),i*85));}

/* ════════════════════════════════
   THREE.JS — 3D STAR FIELD
   Tulip-colored stars orbiting in 3D
════════════════════════════════ */
const starCv=document.getElementById('star-canvas');
const SR=new THREE.WebGLRenderer({canvas:starCv,alpha:true,antialias:true});
SR.setPixelRatio(Math.min(devicePixelRatio,2));
SR.setSize(innerWidth,innerHeight);
const SSc=new THREE.Scene(),SCam=new THREE.PerspectiveCamera(70,innerWidth/innerHeight,.1,1000);
SCam.position.z=35;

// Star particles — tulip hue spectrum
const sGeo=new THREE.BufferGeometry(),sN=1200;
const sPos=new Float32Array(sN*3),sCol=new Float32Array(sN*3),sSz=new Float32Array(sN);
// Tulip palette in linear RGB
const tulipCols=[
  [.96,.44,.71], // #F472B6 tulip pink
  [.78,.54,.98], // #C084FC purple
  [.51,.55,.98], // #818CF8 indigo
  [.38,.65,.98], // #60A5FA blue
  [.77,.71,.99], // #C4B5FD lavender
  [.98,.64,.64], // #FB9090 coral
  [.98,.80,.68], // #FAD4AE peach
  [.73,.88,.99], // #BAE2FC sky
  [1.0,.88,.54], // #FFE08A butter
];
for(let i=0;i<sN;i++){
  const r=15+Math.random()*50,theta=Math.random()*Math.PI*2,phi=Math.acos(2*Math.random()-1);
  sPos[i*3]=r*Math.sin(phi)*Math.cos(theta);
  sPos[i*3+1]=r*Math.sin(phi)*Math.sin(theta);
  sPos[i*3+2]=r*Math.cos(phi)-(Math.random()*20);
  const c=tulipCols[Math.floor(Math.random()*tulipCols.length)];
  sCol[i*3]=c[0];sCol[i*3+1]=c[1];sCol[i*3+2]=c[2];
  sSz[i]=Math.random()*.35+.1;
}
sGeo.setAttribute('position',new THREE.BufferAttribute(sPos,3));
sGeo.setAttribute('color',new THREE.BufferAttribute(sCol,3));
sGeo.setAttribute('size',new THREE.BufferAttribute(sSz,1));
const sMat=new THREE.PointsMaterial({size:.28,vertexColors:true,transparent:true,opacity:.85,sizeAttenuation:true});
const sMesh=new THREE.Points(sGeo,sMat);
SSc.add(sMesh);

// Larger bright star sparkles
const bsGeo=new THREE.BufferGeometry();
const bsN=80,bsPos=new Float32Array(bsN*3),bsCol=new Float32Array(bsN*3);
for(let i=0;i<bsN;i++){
  bsPos[i*3]=(Math.random()-.5)*80;bsPos[i*3+1]=(Math.random()-.5)*80;bsPos[i*3+2]=(Math.random()-.5)*40;
  const c=tulipCols[Math.floor(Math.random()*tulipCols.length)];
  bsCol[i*3]=c[0];bsCol[i*3+1]=c[1];bsCol[i*3+2]=c[2];
}
bsGeo.setAttribute('position',new THREE.BufferAttribute(bsPos,3));
bsGeo.setAttribute('color',new THREE.BufferAttribute(bsCol,3));
const bsMesh=new THREE.Points(bsGeo,new THREE.PointsMaterial({size:.65,vertexColors:true,transparent:true,opacity:.9,sizeAttenuation:true}));
SSc.add(bsMesh);

let smx=0,smy=0;
document.addEventListener('mousemove',e=>{smx=(e.clientX/innerWidth-.5)*2;smy=-(e.clientY/innerHeight-.5)*2;});
(function sgl(){requestAnimationFrame(sgl);
  const t=performance.now()*.0004;
  sMesh.rotation.y=t*.15+smx*.3;sMesh.rotation.x=t*.08+smy*.2;sMesh.rotation.z=t*.05;
  bsMesh.rotation.y=-t*.1+smx*.15;bsMesh.rotation.x=-t*.06+smy*.1;
  // Twinkle — vary opacity
  sMat.opacity=.75+Math.sin(t*3)*.1;
  SR.render(SSc,SCam);})();
window.addEventListener('resize',()=>{SR.setSize(innerWidth,innerHeight);SCam.aspect=innerWidth/innerHeight;SCam.updateProjectionMatrix();});

/* ════════════════════════════════
   INTRO WAVE BAR — animated coloured waves
   (bottom of intro scene)
════════════════════════════════ */
const wbCv=document.getElementById('wave-bar');
const wbCtx=wbCv.getContext('2d');
function rsWb(){wbCv.width=innerWidth;wbCv.height=120;}rsWb();
window.addEventListener('resize',rsWb);
const wbWaves=[
  {color:'rgba(244,114,182,.55)',speed:.8,amp:18,phase:0,y:.55},
  {color:'rgba(167,139,250,.45)',speed:.6,amp:14,phase:1.5,y:.65},
  {color:'rgba(96,165,250,.4)',speed:1.0,amp:10,phase:3.0,y:.75},
  {color:'rgba(196,181,253,.35)',speed:.5,amp:7,phase:4.5,y:.85},
];
let wbt=0;
(function wbl(){
  requestAnimationFrame(wbl);
  wbCtx.clearRect(0,0,wbCv.width,wbCv.height);
  wbWaves.forEach(w=>{
    wbCtx.beginPath();wbCtx.moveTo(0,wbCv.height*w.y);
    for(let x=0;x<wbCv.width;x+=3){
      const y=wbCv.height*w.y+Math.sin(x*.012+wbt*w.speed+w.phase)*w.amp;
      wbCtx.lineTo(x,y);
    }
    wbCtx.lineTo(wbCv.width,wbCv.height);wbCtx.lineTo(0,wbCv.height);wbCtx.closePath();
    wbCtx.fillStyle=w.color;wbCtx.fill();
  });
  wbt+=.016;
})();

/* ════════════════════════════════
   FLOATING PETALS (intro + question)
════════════════════════════════ */
const petalColors=['#F472B6','#C084FC','#60A5FA','#FB7185','#C4B5FD','#BAE6FD','#F9A8D4','#DDD6FE'];
function spawnPetal(container){
  const p=document.createElement('div');p.className='petal';
  const sz=6+Math.random()*12;
  const col=petalColors[Math.floor(Math.random()*petalColors.length)];
  const dur=8+Math.random()*12;
  p.style.cssText=`
    width:${sz}px;height:${sz*.7}px;
    background:${col};
    opacity:${.4+Math.random()*.5};
    left:${Math.random()*100}%;
    top:-30px;
    animation-duration:${dur}s;
    animation-delay:${Math.random()*dur}s;
    box-shadow:0 0 ${sz}px ${col}88;
  `;
  container.appendChild(p);
  setTimeout(()=>p.remove(),(dur+5)*1000);
}
const introSection=document.getElementById('s-intro');
setInterval(()=>spawnPetal(introSection),600);
const qSection=document.getElementById('q-petals');
setInterval(()=>{
  const p=document.createElement('div');p.className='petal';
  const sz=5+Math.random()*10,col=petalColors[Math.floor(Math.random()*petalColors.length)],dur=6+Math.random()*10;
  p.style.cssText=`width:${sz}px;height:${sz*.7}px;background:${col};left:${Math.random()*100}%;top:-20px;animation-duration:${dur}s;animation-delay:${Math.random()*3}s;box-shadow:0 0 ${sz}px ${col}88;`;
  qSection.appendChild(p);setTimeout(()=>p.remove(),(dur+4)*1000);
},400);

/* ════════════════════════════════
   SUNSET CANVAS — rich painted beach
   with crashing wave animation
════════════════════════════════ */
const sc=document.getElementById('sunc');const sctx=sc.getContext('2d');
function rsc(){sc.width=sc.offsetWidth||innerWidth;sc.height=sc.offsetHeight||innerHeight;}rsc();
window.addEventListener('resize',rsc);
let st=0;

// Ocean waves with foam
const oceanWaves=[
  {y:.60,sp:.5,am:12,ph:0,   col:'rgba(244,114,182,.25)',foam:true},
  {y:.63,sp:.4,am:9, ph:1.2, col:'rgba(167,139,250,.2)'},
  {y:.66,sp:.65,am:7,ph:2.4, col:'rgba(96,165,250,.18)'},
  {y:.69,sp:.8,am:5, ph:3.5, col:'rgba(244,114,182,.14)'},
  {y:.72,sp:1.0,am:4,ph:4.7, col:'rgba(167,139,250,.12)'},
  {y:.75,sp:1.2,am:3,ph:5.8, col:'rgba(96,165,250,.1)'},
];
// Crashing wave objects
const crashWaves=[];
function spawnCrash(){
  crashWaves.push({x:Math.random()*(sc.width||innerWidth),y:(sc.height||innerHeight)*.61,life:0,maxLife:80,w:40+Math.random()*80});
}
setInterval(spawnCrash,900);

const ships=[{x:.28,s:2.4},{x:.48,s:2.8},{x:.66,s:2.2},{x:.80,s:1.9}];

function dSun(){
  const W=sc.width||innerWidth,H=sc.height||innerHeight;
  sctx.clearRect(0,0,W,H);

  // Sky — deep violet → rose → tulip pink → golden → peach
  const sky=sctx.createLinearGradient(0,0,0,H*.64);
  sky.addColorStop(0,'#0c0420');
  sky.addColorStop(.1,'#1a0635');
  sky.addColorStop(.28,'#6b1050');
  sky.addColorStop(.45,'#d03070');
  sky.addColorStop(.60,'#f06030');
  sky.addColorStop(.74,'#f8a020');
  sky.addColorStop(.86,'#fdd060');
  sky.addColorStop(1,'#fce8a0');
  sctx.fillStyle=sky;sctx.fillRect(0,0,W,H*.64);

  // Horizontal glowing sun streak
  const sunY=H*.63;
  const sunGl=sctx.createRadialGradient(W/2,sunY,0,W/2,sunY,W*.65);
  sunGl.addColorStop(0,'rgba(255,210,100,.45)');
  sunGl.addColorStop(.3,'rgba(240,100,80,.2)');
  sunGl.addColorStop(.7,'rgba(180,60,180,.08)');
  sunGl.addColorStop(1,'transparent');
  sctx.fillStyle=sunGl;sctx.fillRect(0,H*.2,W,H*.5);

  // Atmospheric pink haze band
  const haze=sctx.createLinearGradient(0,H*.38,0,H*.56);
  haze.addColorStop(0,'transparent');
  haze.addColorStop(.5,'rgba(244,114,182,.12)');
  haze.addColorStop(1,'transparent');
  sctx.fillStyle=haze;sctx.fillRect(0,H*.38,W,H*.2);

  // Ocean base
  const oc=sctx.createLinearGradient(0,H*.60,0,H);
  oc.addColorStop(0,'#8B1550');
  oc.addColorStop(.2,'#5A0E3C');
  oc.addColorStop(.5,'#300828');
  oc.addColorStop(1,'#100510');
  sctx.fillStyle=oc;sctx.fillRect(0,H*.60,W,H*.4);

  // Shimmering reflection columns
  for(let i=0;i<9;i++){
    const cx2=W*(.3+i*.06),sw=8+i*3;
    const col=sctx.createLinearGradient(cx2-sw*3,H*.62,cx2+sw*3,H*.62);
    col.addColorStop(0,'transparent');
    col.addColorStop(.5,`rgba(255,${180-i*12},${120-i*8},${.18-i*.015})`);
    col.addColorStop(1,'transparent');
    sctx.fillStyle=col;
    // ripple each column
    const colH=H*(.35-i*.025);
    sctx.fillRect(cx2-sw*3,H*.63+Math.sin(st*1.2+i)*(2+i*.3),sw*6,colH);
  }

  // Ocean waves — tulip colored
  oceanWaves.forEach(w=>{
    sctx.beginPath();sctx.moveTo(0,H*w.y);
    for(let x=0;x<=W;x+=3){
      const y=H*w.y+Math.sin(x*.016+st*w.sp+w.ph)*w.am;
      sctx.lineTo(x,y);
    }
    sctx.lineTo(W,H);sctx.lineTo(0,H);sctx.closePath();
    sctx.fillStyle=w.col;sctx.fill();

    // Foam tops on first wave
    if(w.foam){
      sctx.beginPath();sctx.moveTo(0,H*w.y);
      for(let x=0;x<=W;x+=3){
        const y=H*w.y+Math.sin(x*.016+st*w.sp+w.ph)*w.am-2;
        sctx.lineTo(x,y);
      }
      sctx.strokeStyle='rgba(255,255,255,.18)';sctx.lineWidth=2;sctx.stroke();
    }
  });

  // Crashing wave splashes
  for(let i=crashWaves.length-1;i>=0;i--){
    const cw=crashWaves[i];
    const prog=cw.life/cw.maxLife;
    const alpha=(prog<.3?prog/.3:1-prog/.7)*0.6;
    if(alpha>0){
      const grad=sctx.createRadialGradient(cw.x,cw.y,0,cw.x,cw.y,cw.w*prog);
      grad.addColorStop(0,`rgba(255,255,255,${alpha})`);
      grad.addColorStop(.5,`rgba(244,114,182,${alpha*.5})`);
      grad.addColorStop(1,'transparent');
      sctx.fillStyle=grad;
      sctx.beginPath();sctx.ellipse(cw.x,cw.y,cw.w*prog,cw.w*prog*.3,0,0,Math.PI*2);
      sctx.fill();
    }
    cw.life++;if(cw.life>cw.maxLife)crashWaves.splice(i,1);
  }

  // Ship silhouettes
  ships.forEach(s=>{
    const sx=W*s.x,sy=H*.60-s.s*4;
    sctx.fillStyle='rgba(5,2,12,.94)';
    sctx.fillRect(sx-s.s*6,sy,s.s*12,s.s*6);
    sctx.fillRect(sx-1,sy-s.s*10,2,s.s*10);
    sctx.fillRect(sx+s.s*4,sy-s.s*7,2,s.s*7);
    // Warm ship light
    sctx.beginPath();sctx.arc(sx,sy-s.s*10,2.5,0,Math.PI*2);
    sctx.fillStyle=`rgba(255,220,150,${.55+Math.sin(st*2+s.x*8)*.3})`;sctx.fill();
    // Pink/violet halo on light
    sctx.beginPath();sctx.arc(sx,sy-s.s*10,6,0,Math.PI*2);
    sctx.fillStyle=`rgba(244,114,182,${.08+Math.sin(st*2+s.x*8)*.04})`;sctx.fill();
  });

  st+=.016;
}
(function sl(){requestAnimationFrame(sl);dSun();})();

/* ════════════════════════════════
   YES — HEART + PETAL CANVAS
════════════════════════════════ */
const yc=document.getElementById('ycvs');const yctx=yc.getContext('2d');
const yhe=[];
function spYH(){yhe.push({x:Math.random()*innerWidth,y:innerHeight+40,
  vy:-(Math.random()*3.5+2),vx:(Math.random()-.5)*3,
  s:Math.random()*30+14,o:1,
  e:['💜','🌸','🐚','✨','🌊','💕','💫','🎀','🌷','🪷','💐','🫧','⭐'][Math.floor(Math.random()*13)]});}
(function yl(){yc.width=innerWidth;yc.height=innerHeight;
  yhe.forEach(h=>{h.y+=h.vy;h.x+=h.vx;h.vy*=.999;h.o-=.0035;
    yctx.globalAlpha=Math.max(0,h.o);yctx.font=h.s+'px serif';yctx.fillText(h.e,h.x,h.y);});
  for(let i=yhe.length-1;i>=0;i--)if(yhe[i].o<=0)yhe.splice(i,1);
  yctx.globalAlpha=1;requestAnimationFrame(yl);})();

/* ─── INTRO ANIMATION ─── */
function runIntro(){
  const pre=document.getElementById('ipre'),chars=document.querySelectorAll('.ch');
  const from=document.getElementById('ifrom'),scrl=document.getElementById('iscrl');
  setTimeout(()=>{pre.style.transition='opacity 1s ease,transform 1s ease';pre.style.opacity='1';pre.style.transform='translateY(0)';},300);
  chars.forEach((c,i)=>{setTimeout(()=>{
    c.style.transition='opacity .6s ease,transform .85s cubic-bezier(.175,.885,.32,1.275)';
    c.style.opacity='1';c.style.transform='translateY(0) rotateX(0)';
    pTick(440+i*55,.06);},700+i*100);});
  setTimeout(()=>{from.style.transition='opacity 1s ease,transform 1s ease';from.style.opacity='1';from.style.transform='translateY(0)';},1700);
  setTimeout(()=>{scrl.style.transition='opacity 1s';scrl.style.opacity='1';},2300);
}

/* ─── SCROLL OBSERVER ─── */
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.classList.add('vis');
      if(e.target.id==='iph')revMsgs();
      if(e.target.id==='sunh')pWhoosh();
    }
  });
},{threshold:.22});
['mtit','msub','mc0','mc1','mc2','mc3','mc4','mst','iph','spill','sunh','sunp','qfrom','qtxt','qsub','qbtns'].forEach(id=>{const el=document.getElementById(id);if(el)obs.observe(el);});

/* ─── VINYL POP ─── */
let activeVinyl=null;
function popVinyl(id,memKey){
  const unit=document.getElementById(id);
  const wasPopped=unit.classList.contains('popped');
  if(activeVinyl&&activeVinyl!==unit)activeVinyl.classList.remove('popped','playing');
  if(wasPopped){unit.classList.remove('popped','playing');activeVinyl=null;openMem(memKey);return;}
  unit.classList.add('popped','playing');activeVinyl=unit;pChime();
  // Particle burst — tulip palette
  const tulipP=['#F472B6','#C084FC','#60A5FA','#34D399','#FDE68A','#FB7185','#BAE6FD','#DDD6FE'];
  for(let i=0;i<18;i++){
    const p=document.createElement('div');p.className='vparticle';
    const ang=Math.random()*360,dist=50+Math.random()*65,rad=ang*Math.PI/180;
    p.style.cssText=`--vbx:${Math.cos(rad)*dist}px;--vby:${Math.sin(rad)*dist}px;--vbd:${.4+Math.random()*.5}s;background:${tulipP[Math.floor(Math.random()*tulipP.length)]};box-shadow:0 0 6px currentColor;`;
    unit.appendChild(p);setTimeout(()=>p.remove(),1000);
  }
}

/* ─── MESSAGES ─── */
let mr=false;
function revMsgs(){
  if(mr)return;mr=true;
  document.querySelectorAll('.imsg').forEach((m,i)=>setTimeout(()=>{m.classList.add('vis');pTick(680,.04);},200+i*380));
}

/* ─── VINYL TILT ─── */
document.querySelectorAll('.vunit').forEach(unit=>{
  unit.addEventListener('mousemove',e=>{
    const r=unit.getBoundingClientRect(),x=(e.clientX-r.left)/r.width-.5,y=(e.clientY-r.top)/r.height-.5;
    const v=unit.querySelector('.vinyl');
    if(v&&!unit.classList.contains('popped'))v.style.transform=`rotateY(${x*32}deg) rotateX(${-y*22}deg) scale(1.1)`;
  });
  unit.addEventListener('mouseleave',()=>{
    const v=unit.querySelector('.vinyl');
    if(v&&!unit.classList.contains('popped'))v.style.transform='';
  });
});

/* ─── MODAL DATA ─── */
const mem={
  shell:{icon:'🐚',title:'the yellow & purple shells',
    bg:'linear-gradient(135deg,#120d04,#1c1608)',tc:'linear-gradient(135deg,#FDE68A,#FCA5A5)',ec:'#FDE68A',
    body:`remember our <em style="color:#FDE68A">first time</em> at the beach? we ran straight to the water and completely ignored that waves don't care about shoes.<br><br>we spent twenty minutes walking the shore, heads down, searching. you were so specific — right shape, right colour, no chips allowed.<br><br>and then you found them. one <em style="color:#FDE68A">yellow</em>. one <em style="color:#DDD6FE">purple</em>. you held them up like actual treasure. you kept both. obviously. and i'd have given you every shell on that beach.`},
  lip:{icon:'💄',title:'her signature lipgloss',
    bg:'linear-gradient(135deg,#180610,#22081a)',tc:'linear-gradient(135deg,#F9A8D4,#FBCFE8)',ec:'#F9A8D4',
    body:`you always have it. always. in your pocket, your bag, somehow materialising from nowhere mid-conversation.<br><br>i've never once seen you without it. it's part of you — the way you reach for it automatically, the way it <em style="color:#F9A8D4">catches the light</em>.<br><br>it's one of those small things i've quietly noticed without meaning to. and now i <em style="color:#F9A8D4">can't not notice it</em>.`},
  ipod:{icon:'🎵',title:'the weeknd, always',
    bg:'linear-gradient(135deg,#0a0618,#14082a)',tc:'linear-gradient(135deg,#C4B5FD,#DDD6FE)',ec:'#C4B5FD',
    body:`it became a whole thing — sharing one earbud each. objectively the most annoying way to listen to music. and somehow <em style="color:#C4B5FD">the only way i want to</em>.<br><br>the weeknd just makes more sense now. tied to specific evenings, specific moments, specific <em style="color:#C4B5FD">you</em>.<br><br>some songs i can't hear without thinking of you now. i'm genuinely not sure that's a problem.`,np:true},
  villa:{icon:'🏡',title:'our someday by the sea',
    bg:'linear-gradient(135deg,#061220,#0a1830)',tc:'linear-gradient(135deg,#BAE6FD,#E0F2FE)',ec:'#BAE6FD',
    body:`we talked about it that evening — what kind of house we'd want someday. right by the shore, obviously. big windows. always the <em style="color:#BAE6FD">sound of the ocean</em>.<br><br>a little garden where we grow things badly. a porch for every sunset. a kitchen that smells like whatever we're learning that week.<br><br>it's a someday dream. but <em style="color:#BAE6FD">somedays are good to have</em>.`},
  phone:{icon:'📱',title:'"come over" (we can\'t)',
    bg:'linear-gradient(135deg,#160424,#200630)',tc:'linear-gradient(135deg,#F472B6,#FBCFE8)',ec:'#F472B6',
    body:`it became a joke and then it stopped being a joke.<br><br><em style="color:#F472B6">"come over"</em> — neither of us can actually go. we both know this. we both say it anyway.<br><br>because there's nowhere to go, it's late, families are home, the world is inconvenient. and we'd still rather be talking to each other than not. that's kind of <em style="color:#F472B6">everything</em>, isn't it.`}
};
let npI;
function openMem(t){
  const d=mem[t],mb=document.getElementById('mbox');
  document.getElementById('micon').textContent=d.icon;
  const mhEl=document.getElementById('mh');
  mhEl.textContent=d.title;mhEl.style.background=d.tc;
  mhEl.style.webkitBackgroundClip='text';mhEl.style.webkitTextFillColor='transparent';mhEl.style.backgroundClip='text';
  document.getElementById('mp').innerHTML=d.body;
  mb.style.background=d.bg;
  mb.style.setProperty('--mglow',d.ec+'44');
  clearInterval(npI);
  if(d.np){
    const np=document.createElement('div');np.className='nplay';np.id='npl';
    np.innerHTML=`<div class="ndisc" style="background:linear-gradient(135deg,${d.ec},#8B5CF6)"></div><div class="ninfo"><div class="ntrack">&#9834; Starboy — The Weeknd</div><div class="nartist">Starboy · 2016</div><div class="nbar"><div class="nprog" id="nprg" style="background:linear-gradient(90deg,${d.ec},#C4B5FD)"></div></div></div>`;
    document.getElementById('mp').appendChild(np);
    let pp=30;npI=setInterval(()=>{pp+=.4;if(pp>100)pp=0;const el=document.getElementById('nprg');if(el)el.style.width=pp+'%';},100);
  }
  document.getElementById('modal').classList.add('open');pChime();
}
function cm(e){if(!e||e.target===document.getElementById('modal')||e.target===document.querySelector('.mbk')){document.getElementById('modal').classList.remove('open');clearInterval(npI);}}

/* ─── NO BUTTON ─── */
function runAway(){
  const b=document.getElementById('bno');
  b.style.left=Math.random()*(innerWidth-130)+'px';
  b.style.top=Math.random()*(innerHeight-60)+'px';
  b.style.right='auto';b.style.bottom='auto';pTick(250,.05);
}

/* ─── YES ─── */
function sayYes(){
  document.getElementById('yes-screen').classList.add('open');pYes();
  let hi=setInterval(spYH,120);setTimeout(()=>clearInterval(hi),10000);
}
</script>
</body>
</html>
