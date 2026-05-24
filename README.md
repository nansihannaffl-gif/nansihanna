<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nansi Hanna | Elite Motional Financial</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=Inter:wght@200;300;400;500&family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&family=Playfair+Display:ital,wght@0,700;0,900;1,400;1,700&family=Dancing+Script:wght@700&family=Great+Vibes&family=Bebas+Neue&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
<script>emailjs.init("WbOWdf4BrqPs0xVqY");</script>
<script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/11.8.1/firebase-app.js";
  import { getFirestore, collection, getDocs, addDoc, updateDoc, doc, deleteDoc, query, where } from "https://www.gstatic.com/firebasejs/11.8.1/firebase-firestore.js";

  const firebaseConfig = {
    apiKey: "AIzaSyAq-wMLXLS-tNhEQsc4fVr8IwOrQuYl6wY",
    authDomain: "elite-motion-5ae0f.firebaseapp.com",
    projectId: "elite-motion-5ae0f",
    storageBucket: "elite-motion-5ae0f.firebasestorage.app",
    messagingSenderId: "154669536353",
    appId: "1:154669536353:web:8a6f3c8fd9621225a80620",
    measurementId: "G-EQ77M5PBRQ"
  };

  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);
  window._db = db;
  window._fbCollection = collection;
  window._fbGetDocs = getDocs;
  window._fbAddDoc = addDoc;
  window._fbUpdateDoc = updateDoc;
  window._fbDoc = doc;
  window._fbQuery = query;
  window._fbWhere = where;
  window._fbDeleteDoc = deleteDoc;

  // Load recruits from Firebase on start
  async function loadRecruits() {
    try {
      const snap = await getDocs(collection(db, "recruits"));
      recruits = [];
      snap.forEach(d => recruits.push({...d.data(), _firebaseId: d.id}));
      window._recruitsLoaded = true;
    } catch(e) { console.error("Firebase load error:", e); }
  }
  window._loadRecruits = loadRecruits;
  loadRecruits();
</script>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --white:#000000;
  --cream:#0a0a0a;
  --cream2:#111111;
  --blush:#0f0f0f;
  --gold:#d8b8c0;
  --gold-soft:#e8e0d8;
  --gold-glow:rgba(216,184,192,0.18);
  --gold-glow-sm:rgba(216,184,192,0.10);
  --gold2:#a09080;
  --beige:#e8ddd0;
  --beige-bright:#f5ede0;
  --beige-glow:rgba(232,221,208,0.20);
  --dark:#f0ece6;
  --taupe:#6a6058;
  --emerald:#2a4a3a;
  --emerald-acc:rgba(42,74,58,0.22);
  --muted-white:rgba(240,236,230,0.06);
  --pink:rgba(216,184,192,0.55);
  --pink-soft:rgba(216,184,192,0.12);
  --border:#1a1a1a;
}
html{scroll-behavior:smooth}
.svc-card:hover{background:var(--cream2) !important}
.svc-card:hover .svc-bar{width:100% !important}
body{background:var(--white);color:var(--dark);font-family:'Inter',sans-serif;font-weight:300;overflow-x:hidden;}

.page{display:none;min-height:100vh}
.page.active{display:block}

@keyframes fadeIn{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}
@keyframes auroraDrift1{0%,100%{transform:translate(-20%,-20%) scale(1);opacity:0.8}50%{transform:translate(10%,10%) scale(1.3);opacity:1}}
@keyframes auroraDrift2{0%,100%{transform:translate(20%,10%) scale(1.1);opacity:0.7}50%{transform:translate(-10%,-15%) scale(0.9);opacity:1}}
.aurora-layer{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:0;overflow:hidden}
.aurora-layer .a1{position:absolute;width:180%;height:180%;top:-40%;left:-40%;background:radial-gradient(ellipse 55% 45% at 40% 50%,rgba(160,144,128,0.28) 0%,transparent 60%);animation:auroraDrift1 9s ease-in-out infinite}
.aurora-layer .a2{position:absolute;width:180%;height:180%;top:-40%;left:-40%;background:radial-gradient(ellipse 45% 55% at 65% 40%,rgba(160,144,128,0.20) 0%,transparent 55%);animation:auroraDrift2 11s ease-in-out infinite}
.aurora-layer .a3{display:none}
.aurora-layer .a4{position:absolute;width:100%;height:100%;top:0;left:0;background:radial-gradient(ellipse 70% 60% at 50% 42%,rgba(160,144,128,0.22) 0%,rgba(160,144,128,0.10) 35%,transparent 70%);pointer-events:none}
@keyframes expandW{from{width:0}to{width:60px}}
@keyframes marquee{from{transform:translateX(0)}to{transform:translateX(-50%)}}
@keyframes softFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-5px)}}
@keyframes subtleFade{from{opacity:0}to{opacity:1}}
@keyframes glowPulse{0%,100%{filter:brightness(1)}50%{filter:brightness(1.04)}}
@keyframes goldShimmer{0%,100%{opacity:0.6}50%{opacity:1}}

/* ============ TOP NAV ============ */
.top-nav{
  display:grid;
  grid-template-columns:1fr auto 1fr;
  align-items:center;
  padding:16px 40px;
  border-bottom:1px solid var(--border);
  background:transparent;
  position:sticky;top:0;z-index:100;
}
.nav-left{display:flex;gap:28px;align-items:center}
.nav-left a{font-size:10px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);text-decoration:none;transition:color .2s}
.nav-left a:hover{color:var(--dark)}
.nav-center{text-align:center}
.nav-center h1{font-family:'Cormorant Garamond',serif;font-size:18px;font-weight:400;letter-spacing:.25em;text-transform:uppercase;color:var(--dark)}
.nav-center p{font-size:8px;font-weight:400;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-top:2px}
.nav-right{display:flex;gap:28px;align-items:center;justify-content:flex-end}
.nav-right a{font-size:10px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);text-decoration:none;transition:color .2s}
.nav-right a:hover{color:var(--dark)}
.nav-cta{padding:9px 20px;background:transparent;color:var(--beige);font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;border:1px solid rgba(232,221,208,0.30);cursor:pointer;transition:all .3s;font-family:'Inter',sans-serif}
.nav-cta:hover{background:rgba(232,221,208,0.08);border-color:var(--beige)}

/* ============ HERO ============ */
.hero{
  padding:32px 40px 32px;
  text-align:center;
  background:transparent;
  max-width:100%;
  min-height:calc(100vh - 80px);
  display:flex;
  flex-direction:column;
  justify-content:center;
  margin:0 auto;
}
.hero-eyebrow{font-size:9px;font-weight:300;letter-spacing:.35em;text-transform:uppercase;color:var(--taupe);margin-bottom:18px;animation:fadeIn .7s ease both}
.hero-name{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(58px,9vw,100px);
  font-weight:600;
  letter-spacing:.04em;
  text-transform:uppercase;
  color:var(--dark);
  line-height:.95;
  margin-bottom:14px;
  animation:fadeIn .7s .1s ease both;
}
.hero-sub{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(22px,3.5vw,40px);font-weight:300;font-style:italic;letter-spacing:.02em;
  color:var(--gold2);margin-bottom:10px;
  animation:fadeIn .7s .2s ease both;
}
.hero-divider{
  width:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--beige),var(--gold),var(--beige-bright),transparent);
  margin:0 auto 40px;
  animation:expandW .8s .3s ease forwards;
}

/* ============ VIDEO BLOCK ============ */
.video-block{
  position:relative;
  max-width:720px;
  margin:0 auto 32px;
  animation:fadeIn .8s .4s ease both,softFloat 6s 1.5s ease-in-out infinite;
}
/* Decorative side image */

.video-frame{
  position:relative;
  background:transparent;
  border:0.5px solid rgba(160,144,128,0.28);
  padding:4px;
  box-shadow:0 0 40px 12px rgba(160,144,128,0.18),0 0 80px 32px rgba(160,144,128,0.10),0 0 120px 60px rgba(160,144,128,0.06);
}
.video-inner{
  position:relative;
  background:transparent;
  overflow:hidden;
  cursor:pointer;
}
/* Cinematic video thumbnail overlay */
.video-cinematic-overlay{
  position:absolute;inset:0;
  background:linear-gradient(
    135deg,
    rgba(13,13,14,0.45) 0%,
    rgba(13,13,14,0.15) 40%,
    rgba(13,13,14,0.05) 60%,
    rgba(248,232,240,0.09) 85%,
    rgba(216,184,192,0.08) 100%
  );
  pointer-events:none;
  z-index:1;
}
.video-cinematic-overlay::before{
  content:'';
  position:absolute;top:0;left:0;right:0;
  height:1px;
  background:linear-gradient(90deg,transparent,rgba(216,184,192,0.3),transparent);
}
.video-cinematic-overlay::after{
  content:'';
  position:absolute;bottom:0;left:0;right:0;
  height:1px;
  background:linear-gradient(90deg,transparent,rgba(216,184,192,0.2),transparent);
}
.video-inner img{
  width:100%;
  aspect-ratio:16/9;
  object-fit:cover;
  display:block;
  opacity:0.88;
  filter:contrast(1.04) brightness(0.96);
  transition:opacity .3s,filter .3s;
}
.video-inner:hover img{opacity:0.78;filter:contrast(1.05) brightness(0.92)}
.video-play-btn{
  position:absolute;
  inset:0;
  display:flex;
  align-items:center;
  justify-content:center;
}
.video-play-btn span{
  width:64px;height:64px;border-radius:50%;
  background:rgba(0,0,0,0.6);
  border:1.5px solid rgba(255,255,255,0.5);
  display:flex;align-items:center;justify-content:center;
  font-size:22px;color:#fff;
  transition:all .3s;
}
.video-inner:hover .video-play-btn span{background:rgba(216,184,192,0.5);border-color:rgba(216,184,192,0.9);transform:scale(1.08)}
/* Title overlay on video */
.video-title-overlay{
  position:absolute;
  inset:0;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  background:rgba(14,14,15,0.28);
  backdrop-filter:blur(0px);
}
.video-title-overlay h2{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(28px,5vw,52px);
  font-weight:400;
  letter-spacing:.15em;
  text-transform:uppercase;
  color:var(--dark);
  line-height:1;
}
.video-title-overlay h2 em{
  font-style:italic;
  display:block;
  font-size:.55em;
  letter-spacing:.35em;
  color:var(--taupe);
  margin-bottom:6px;
}
.video-title-overlay p{
  font-size:9px;
  font-weight:300;
  letter-spacing:.3em;
  text-transform:uppercase;
  color:var(--taupe);
  margin-top:10px;
}
.watch-agency-btn{
  margin-top:18px;
  padding:9px 24px;
  border:1px solid var(--dark);
  background:transparent;
  color:var(--dark);
  font-family:'Inter',sans-serif;
  font-size:9px;
  font-weight:300;
  letter-spacing:.2em;
  text-transform:uppercase;
  cursor:pointer;
  transition:all .25s;
  text-decoration:none;
  display:inline-block;
}
.watch-agency-btn:hover{background:var(--dark);color:#fff}

/* Circular badge */
.video-badge-circle{
  position:absolute;
  right:-24px;
  top:50%;
  transform:translateY(-50%);
  width:72px;height:72px;
  border-radius:50%;
  background:var(--cream);
  border:1px solid var(--border);
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  z-index:5;
  box-shadow:0 2px 12px rgba(0,0,0,0.08);
}
.video-badge-circle span{font-family:'Cormorant Garamond',serif;font-size:9px;font-style:italic;color:var(--taupe);text-align:center;line-height:1.3;letter-spacing:.05em}

/* ============ MAIN CTA ============ */
.main-cta-wrap{text-align:center;margin-bottom:64px;animation:fadeIn .8s .5s ease both}
.main-cta{
  display:inline-block;
  padding:18px 64px;
  background:#f0ece6;
  color:#0d0d0e;
  font-family:'Inter',sans-serif;
  font-size:11px;
  font-weight:400;
  letter-spacing:.3em;
  text-transform:uppercase;
  border:none;
  cursor:pointer;
  transition:all .4s;
  box-shadow:0 0 30px 8px rgba(216,184,192,0.30),0 0 55px 18px rgba(216,184,192,0.15);
  animation:glowPulse 3s ease-in-out infinite;
}
.main-cta:hover{background:var(--gold);color:#0d0d0e;transform:translateY(-2px);box-shadow:0 0 40px 14px rgba(216,184,192,0.45),0 0 72px 30px rgba(216,184,192,0.25)}

/* ============ STATS ============ */
.stats-row{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  max-width:760px;
  margin:0 auto 0;
  padding-top:40px;
  border-top:1px solid var(--border);
  animation:fadeIn .8s .6s ease both;
}
.stat{text-align:center;padding:0 24px}
.stat:not(:last-child){border-right:1px solid var(--border)}
.stat-num{font-family:'Cormorant Garamond',serif;font-size:36px;font-weight:400;color:var(--gold);letter-spacing:.05em}
.stat-label{font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-top:5px}

/* ============ ABOUT / PHOTO ============ */
.about-strip{
  max-width:860px;margin:72px auto 0;
  display:grid;grid-template-columns:1fr 2fr;gap:56px;
  align-items:center;padding:0 40px;
  animation:fadeIn .8s .7s ease both;
}
.about-photo-wrap{
  position:relative;
  aspect-ratio:3/4;
  background:var(--cream2);
  border:1px solid var(--border);
  overflow:hidden;
}
.about-photo-wrap::after{
  content:'';
  position:absolute;inset:0;
  background:radial-gradient(ellipse 80% 60% at 50% 80%,rgba(216,184,192,0.14) 0%,transparent 70%);
}
.about-photo-inner{
  width:100%;height:100%;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  gap:12px;
}
.about-photo-placeholder{
  font-family:'Cormorant Garamond',serif;
  font-size:11px;font-style:italic;
  color:var(--taupe);letter-spacing:.15em;
  text-align:center;line-height:2;
}
.about-photo-placeholder span{
  display:block;font-size:28px;opacity:0.3;margin-bottom:8px;
}
.about-text{}
.about-eyebrow{font-size:8px;font-weight:300;letter-spacing:.35em;text-transform:uppercase;color:var(--gold);margin-bottom:14px}
.about-heading{font-family:'Cormorant Garamond',serif;font-size:clamp(24px,3.5vw,38px);font-weight:400;color:var(--dark);line-height:1.2;margin-bottom:18px}
.about-heading em{font-style:italic;color:var(--gold)}
.about-body{font-size:14px;color:var(--taupe);line-height:1.85;font-family:'Cormorant Garamond',serif;font-style:italic;margin-bottom:20px}
.about-badge{
  display:inline-flex;align-items:center;gap:8px;
  padding:8px 16px;
  border:1px solid rgba(216,184,192,0.25);
  background:rgba(216,184,192,0.05);
  font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--gold);
}

/* ============ TESTIMONIALS ============ */
.testimonials-strip{
  max-width:1000px;margin:72px auto 0;padding:0 40px;
  animation:fadeIn .8s .8s ease both;
}
.testimonials-eyebrow{font-size:8px;font-weight:300;letter-spacing:.35em;text-transform:uppercase;color:var(--gold2);text-align:center;margin-bottom:36px}
.testimonials-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border)}
.testimonial-card{
  background:var(--white);padding:32px 24px;
  display:flex;flex-direction:column;justify-content:space-between;
}
.t-quote{
  font-family:'Cormorant Garamond',serif;
  font-size:16px;font-style:italic;
  color:var(--dark);line-height:1.7;
  margin-bottom:20px;flex:1;
}
.t-attr{font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe)}
.t-attr strong{color:var(--gold);display:block;margin-bottom:2px;letter-spacing:.15em;font-weight:300}
.t-stars{color:var(--gold);font-size:10px;margin-bottom:14px;letter-spacing:2px}

/* ============ MARQUEE ============ */
.marquee-wrap{
  background:var(--cream2);
  border-top:1px solid var(--border);
  border-bottom:1px solid var(--border);
  padding:11px 0;
  overflow:hidden;
  margin-top:72px;
}
.marquee-track{display:flex;white-space:nowrap;animation:marquee 25s linear infinite}
.marquee-item{
  display:inline-flex;align-items:center;gap:20px;
  padding:0 28px;
  font-size:9px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;color:var(--taupe);
  font-family:'Inter',sans-serif;
}
.marquee-dot{color:var(--gold);font-size:8px}

/* ============ HOW IT WORKS ============ */
.section{padding:80px 60px;max-width:1100px;margin:0 auto}
.section-header{text-align:center;margin-bottom:56px}
.section-eyebrow{font-size:9px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:12px}
.section-title{font-family:'Cormorant Garamond',serif;font-size:clamp(32px,4vw,52px);font-weight:400;color:var(--dark);letter-spacing:.05em}
.section-title em{font-style:italic;color:var(--gold2)}

.cards-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border)}
.info-card{
  background:var(--white);
  padding:36px 28px;
  position:relative;overflow:hidden;
  transition:all .35s;cursor:default;
  min-height:180px;display:flex;flex-direction:column;justify-content:center;
}
.info-card::after{content:'';position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--gold);transition:width .4s}
.info-card:hover{background:var(--cream2);box-shadow:0 0 24px 4px rgba(216,184,192,0.07),0 0 48px 12px rgba(216,184,192,0.03)}
.info-card:hover::after{width:100%}
.info-card:hover .card-front{opacity:0;transform:translateY(-6px)}
.info-card:hover .card-back{opacity:1;transform:translateY(0)}
.card-front{transition:all .3s}
.card-back{position:absolute;inset:0;padding:28px;opacity:0;transform:translateY(6px);transition:all .3s;display:flex;flex-direction:column;justify-content:center}
.card-icon{font-size:26px;margin-bottom:14px}
.card-title{font-family:'Cormorant Garamond',serif;font-size:20px;font-weight:300;color:var(--dark);margin-bottom:6px}
.card-hint{display:none}
.card-back-label{font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--gold2);margin-bottom:10px}
.card-back-text{font-family:'Cormorant Garamond',serif;font-size:16px;color:var(--dark);line-height:1.7}
.card-back-text strong{color:var(--gold2)}

/* ============ CONTINUE SECTION ============ */
.cta-section{
  background:var(--cream2);
  border-top:1px solid var(--border);
  padding:80px 60px;
  text-align:center;
}
.cta-eyebrow{font-size:9px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:16px}
.cta-title{font-family:'Cormorant Garamond',serif;font-size:clamp(32px,5vw,60px);font-weight:400;color:var(--dark);margin-bottom:8px;letter-spacing:.05em}
.cta-title em{font-style:italic;color:var(--gold2)}
.cta-sub{font-size:13px;color:var(--taupe);margin-bottom:36px;font-style:italic;font-family:'Cormorant Garamond',serif;font-size:18px}
#continue-btn{
  display:inline-block;padding:16px 56px;
  background:var(--dark);color:var(--cream);
  font-family:'Inter',sans-serif;font-size:13px;font-weight:500;
  letter-spacing:.25em;text-transform:uppercase;border:none;cursor:pointer;transition:all .3s;
  box-shadow:0 0 28px 6px rgba(216,184,192,0.25),0 0 56px 16px rgba(232,221,208,0.15);
  animation:glowPulse 3s ease-in-out infinite;
}
#continue-btn:hover{background:var(--gold);transform:translateY(-2px);box-shadow:0 0 40px 12px rgba(216,184,192,0.40),0 0 80px 28px rgba(232,221,208,0.25)}

/* ============ QUIZ ============ */
#page-quiz{background:transparent;display:none}
#page-quiz.active{display:block}
#page-form,#page-calendar,#page-confirm,#page-not-a-fit{background:transparent;display:none;align-items:center;justify-content:center}
#page-form.active,#page-calendar.active,#page-confirm.active,#page-not-a-fit.active{display:flex}
#page-admin-login,#page-portal-login{background:transparent;display:none;align-items:center;justify-content:center}
#page-admin-login.active,#page-portal-login.active{display:flex}
#page-admin,#page-portal,#page-eli-admin{display:none;min-height:100vh;background:var(--cream)}
#page-admin.active,#page-portal.active,#page-eli-admin.active{display:block}
#page-eli-login{background:transparent;display:none;align-items:center;justify-content:center}
#page-eli-login.active{display:flex}

.quiz-inner{max-width:640px;width:100%;margin:0 auto;padding:80px 32px;text-align:center}
.quiz-progress{display:flex;gap:6px;justify-content:center;margin-bottom:52px}
.qp-dot{width:28px;height:1px;background:var(--border);transition:background .4s}
.qp-dot.done{background:var(--gold)}
.qp-dot.active{background:var(--dark)}
.quiz-q-num{font-size:9px;font-weight:300;letter-spacing:.3em;color:var(--taupe);margin-bottom:18px;text-transform:uppercase}
.quiz-question{font-family:'Cormorant Garamond',serif;font-size:clamp(22px,4vw,36px);font-weight:400;color:var(--dark);line-height:1.3;margin-bottom:44px}
.quiz-options{display:flex;flex-direction:column;gap:8px;margin-bottom:36px}
.quiz-opt{padding:16px 24px;border:1px solid var(--border);background:var(--white);color:var(--dark);font-family:'Inter',sans-serif;font-size:13px;cursor:pointer;transition:all .2s;text-align:left}
.quiz-opt:hover{border-color:var(--dark);background:var(--cream)}
.quiz-opt.selected{border-color:var(--dark);background:var(--dark);color:var(--cream)}
.quiz-next{padding:14px 44px;background:var(--dark);color:var(--cream);font-family:'Inter',sans-serif;font-size:10px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;border:none;cursor:pointer;transition:all .3s;opacity:0;pointer-events:none}
.quiz-next.visible{opacity:1;pointer-events:all}
.quiz-next:hover{background:var(--gold)}

/* ============ FORM ============ */
.form-inner{max-width:560px;width:100%;margin:0 auto;padding:80px 32px;text-align:center}
.form-eyebrow{font-size:9px;font-weight:300;letter-spacing:.3em;color:var(--gold2);margin-bottom:12px;text-transform:uppercase}
.form-title{font-family:'Cormorant Garamond',serif;font-size:clamp(30px,5vw,50px);font-weight:400;color:var(--dark);margin-bottom:8px}
.form-sub{font-family:'Cormorant Garamond',serif;font-size:17px;font-style:italic;color:var(--taupe);margin-bottom:40px}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:12px}
.form-field{display:flex;flex-direction:column;gap:5px;text-align:left}
.form-field.full{grid-column:1/-1}
.form-field label{font-size:8px;font-weight:300;letter-spacing:.2em;color:var(--taupe);text-transform:uppercase}
.form-field input,.form-field select{background:#fff;border:1px solid var(--border);color:#1a1a1a;padding:13px 14px;font-family:'Inter',sans-serif;font-size:13px;outline:none;transition:border-color .2s;width:100%;-webkit-appearance:none}
.form-field input:focus,.form-field select:focus{border-color:var(--dark)}
.form-field select option{background:#fff;color:#1a1a1a}
.form-field input:-webkit-autofill,
.form-field input:-webkit-autofill:hover,
.form-field input:-webkit-autofill:focus{
  -webkit-box-shadow:0 0 0 1000px #fff inset !important;
  -webkit-text-fill-color:#1a1a1a !important;
  box-shadow:0 0 0 1000px #fff inset !important;
  border-color:var(--gold) !important;
  transition:background-color 5000s ease-in-out 0s;
}
.submit-btn{width:100%;padding:16px;background:var(--dark);color:var(--cream);font-family:'Inter',sans-serif;font-size:10px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;border:none;cursor:pointer;margin-top:8px;transition:all .3s}
.submit-btn:hover{background:var(--gold)}

/* ============ CALENDAR ============ */
.cal-inner{max-width:660px;width:100%;margin:0 auto;padding:80px 32px;text-align:center}
.cal-eyebrow{font-size:9px;font-weight:300;letter-spacing:.3em;color:var(--gold2);margin-bottom:12px;text-transform:uppercase}
.cal-title{font-family:'Cormorant Garamond',serif;font-size:clamp(26px,4vw,44px);font-weight:400;color:var(--dark);margin-bottom:36px}
.cal-host{display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:32px}
.cal-avatar{width:52px;height:52px;border-radius:50%;background:var(--cream2);border:0.25px solid var(--border);display:flex;align-items:center;justify-content:center;font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--dark);font-weight:400}
.cal-host-name{font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--dark);text-align:left}
.cal-host-title{font-size:9px;color:var(--taupe);letter-spacing:.15em;font-weight:300;text-transform:uppercase;text-align:left}
.calendar-widget{border:0.25px solid var(--border);background:var(--white);padding:24px;margin-bottom:20px}
.cal-month{display:flex;align-items:center;justify-content:space-between;margin-bottom:20px}
.cal-month span{font-size:11px;font-weight:300;letter-spacing:.2em;color:var(--dark);text-transform:uppercase}
.cal-nav{background:none;border:0.25px solid var(--border);color:var(--taupe);width:30px;height:30px;cursor:pointer;font-size:13px;transition:all .2s}
.cal-nav:hover{border-color:var(--dark);color:var(--dark)}
.cal-days-header{display:grid;grid-template-columns:repeat(7,1fr);gap:3px;margin-bottom:6px}
.cal-day-label{font-size:8px;font-weight:300;letter-spacing:.08em;color:var(--taupe);text-align:center;padding:3px 0;text-transform:uppercase}
.cal-days{display:grid;grid-template-columns:repeat(7,1fr);gap:3px}
.cal-day{aspect-ratio:1;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--border);cursor:default;transition:all .2s}
.cal-day.available{color:var(--dark);cursor:pointer;border:0.25px solid var(--border)}
.cal-day.available:hover{border-color:var(--dark);background:var(--dark);color:var(--cream)}
.cal-day.selected{background:var(--dark);color:var(--cream);border-color:var(--dark)}
.cal-day.past{color:var(--border)}
.time-slots{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:20px}
.time-slot{padding:11px;border:0.25px solid var(--border);color:var(--taupe);font-size:11px;font-weight:300;letter-spacing:.1em;cursor:pointer;transition:all .2s;text-align:center}
.time-slot.available{color:var(--dark);cursor:pointer}
.time-slot.available:hover{border-color:var(--dark);background:var(--dark);color:var(--cream)}
.time-slot.selected{background:var(--dark);color:var(--cream);border-color:var(--dark)}
.book-btn{width:100%;padding:15px;background:var(--dark);color:var(--cream);font-family:'Inter',sans-serif;font-size:10px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;border:none;cursor:pointer;transition:all .3s;opacity:.35;pointer-events:none}
.book-btn.ready{opacity:1;pointer-events:all}
.book-btn.ready:hover{background:var(--gold)}

/* ============ CONFIRM ============ */
.confirm-inner{max-width:480px;width:100%;margin:0 auto;padding:80px 32px;text-align:center}
.confirm-check{width:60px;height:60px;border-radius:50%;border:1px solid var(--gold);display:flex;align-items:center;justify-content:center;margin:0 auto 24px;font-size:22px;color:var(--gold)}
.confirm-title{font-family:'Cormorant Garamond',serif;font-size:clamp(28px,5vw,48px);font-weight:400;color:var(--dark);margin-bottom:10px}
.confirm-sub{font-family:'Cormorant Garamond',serif;font-size:17px;font-style:italic;color:var(--taupe);line-height:1.7;margin-bottom:28px}
.confirm-details{border:1px solid var(--border);padding:20px;background:var(--cream);text-align:left;margin-bottom:20px}
.confirm-row{display:flex;justify-content:space-between;padding:7px 0;border-bottom:1px solid var(--border);font-size:12px}
.confirm-row:last-child{border-bottom:none}
.confirm-row .key{color:var(--taupe);font-size:8px;letter-spacing:.15em;text-transform:uppercase;font-weight:300;display:flex;align-items:center}
.confirm-row .val{font-family:'Cormorant Garamond',serif;font-size:15px;font-style:italic;color:var(--dark)}
.confirm-note{font-size:11px;color:var(--taupe);line-height:1.7}

/* ============ ADMIN ============ */
.admin-login-box{max-width:360px;width:100%;padding:48px 36px;border:1px solid var(--border);background:var(--white);text-align:center}
.admin-login-box h2{font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:400;color:var(--dark);margin-bottom:6px}
.admin-login-box p{font-family:'Cormorant Garamond',serif;font-size:15px;font-style:italic;color:var(--taupe);margin-bottom:28px}
.admin-login-box input{width:100%;background:var(--cream);border:1px solid var(--border);color:var(--dark);padding:13px 14px;font-family:'Inter',sans-serif;font-size:13px;outline:none;margin-bottom:10px;transition:border-color .2s}
.admin-login-box input:focus{border-color:var(--dark)}
.admin-login-btn{width:100%;padding:13px;background:var(--dark);color:var(--cream);font-family:'Inter',sans-serif;font-size:10px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;border:none;cursor:pointer;transition:all .3s}
.admin-login-btn:hover{background:var(--gold)}
.admin-err{color:#b00;font-size:11px;margin-top:8px;font-style:italic;display:none;font-family:'Cormorant Garamond',serif}
.admin-header{background:var(--white);border-bottom:1px solid var(--border);padding:16px 32px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:100}
.admin-header h1{font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:400;color:var(--dark)}
.admin-header span{font-size:10px;color:var(--taupe);letter-spacing:.1em;font-weight:300}
.admin-body{padding:32px;max-width:1200px;margin:0 auto}
.admin-stats{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:28px}
.stat-card{border:1px solid var(--border);padding:20px;background:var(--white)}
.stat-num{font-family:'Cormorant Garamond',serif;font-size:40px;color:var(--dark);font-weight:400}
.stat-label{font-size:8px;font-weight:300;letter-spacing:.2em;color:var(--taupe);text-transform:uppercase;margin-top:4px}
.admin-table-wrap{border:1px solid var(--border);background:var(--white);overflow:hidden}
.admin-table-head{display:grid;grid-template-columns:2fr 1.5fr 1fr 1fr 1fr 1.5fr;border-bottom:1px solid var(--border);padding:12px 20px;background:var(--cream)}
.admin-table-head span{font-size:8px;font-weight:300;letter-spacing:.15em;color:var(--taupe);text-transform:uppercase}
.recruit-row{display:grid;grid-template-columns:2fr 2fr 1fr 1fr 1.5fr 1fr;padding:15px 20px;align-items:center;transition:background .2s}
.recruit-row:hover{background:var(--cream)}
.recruit-name{font-family:'Cormorant Garamond',serif;font-size:17px;color:var(--dark)}
.recruit-email,.recruit-contact{font-size:11px;color:var(--taupe);margin-top:1px}
.recruit-state{font-size:12px;color:var(--dark)}
.rank-select{background:var(--white);border:1px solid var(--border);color:var(--dark);padding:5px 8px;font-family:'Inter',sans-serif;font-size:9px;font-weight:300;letter-spacing:.1em;outline:none;cursor:pointer;text-transform:uppercase}
.rank-select:focus{border-color:var(--dark)}
.recruited-btn{padding:7px 14px;background:var(--dark);color:var(--cream);font-family:'Inter',sans-serif;font-size:8px;font-weight:300;letter-spacing:.1em;border:none;cursor:pointer;transition:all .2s;text-transform:uppercase}
.recruited-btn:hover{background:var(--gold)}
.recruited-btn.done{background:var(--cream);color:var(--taupe);cursor:default;border:1px solid var(--border)}

/* ============ PORTAL ============ */
.portal-header{background:var(--white);border-bottom:1px solid var(--border);padding:16px 32px;display:flex;align-items:center;justify-content:space-between}
.portal-header h1{font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:400;color:var(--dark)}
.portal-body{padding:40px 32px;max-width:760px;margin:0 auto}
.portal-welcome{font-family:'Cormorant Garamond',serif;font-size:clamp(28px,4vw,46px);font-weight:400;color:var(--dark);margin-bottom:6px}
.portal-sub{font-family:'Cormorant Garamond',serif;font-size:17px;font-style:italic;color:var(--taupe);margin-bottom:36px}
.step-container{display:flex;flex-direction:column;gap:6px}
.step-item{border:1px solid var(--border);overflow:hidden;transition:border-color .3s;background:var(--white)}
.step-item.unlocked{border-color:var(--dark)}
.step-item.completed{border-color:var(--gold);background:var(--cream)}
.step-item.locked{opacity:.45;pointer-events:none}
.step-item.next-up{opacity:.8;border-color:var(--border)}
.step-header{display:flex;align-items:center;gap:14px;padding:18px 22px;cursor:pointer}
.step-num{width:30px;height:30px;border-radius:50%;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:9px;font-weight:300;color:var(--taupe);flex-shrink:0}
.step-item.unlocked .step-num{border-color:var(--dark);color:var(--dark)}
.step-item.completed .step-num{background:var(--dark);color:var(--cream);border-color:var(--dark)}
.step-title-wrap{flex:1}
.step-title{font-family:'Cormorant Garamond',serif;font-size:18px;color:var(--dark)}
.step-item.locked .step-title{color:var(--taupe)}
.step-status{font-size:8px;font-weight:300;letter-spacing:.15em;margin-top:2px;text-transform:uppercase;color:var(--taupe)}
.step-item.unlocked .step-status{color:var(--gold2)}
.step-arrow{color:var(--taupe);font-size:11px}
.step-body{display:none;padding:0 22px 22px;border-top:1px solid var(--border)}
.step-body.open{display:block}
.step-content{font-size:13px;color:var(--dark);line-height:1.8;margin-bottom:14px;padding-top:18px}
.step-content a{color:var(--gold2);text-decoration:none;font-weight:300}
.step-content strong{color:var(--dark);font-weight:300}
.complete-step-btn{padding:11px 28px;background:var(--dark);color:var(--cream);font-family:'Inter',sans-serif;font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;border:none;cursor:pointer;transition:all .3s}
.complete-step-btn:hover{background:var(--gold)}
.wait-notice{padding:10px 14px;border:1px solid var(--border);font-size:12px;color:var(--taupe);background:var(--cream);font-style:italic;font-family:'Cormorant Garamond',serif}
.substep{display:flex;gap:12px;align-items:flex-start;background:var(--cream);border:1px solid var(--border);padding:14px 16px;border-left:3px solid var(--gold)}
.substep-num{min-width:22px;height:22px;border-radius:50%;background:var(--dark);color:var(--cream);font-size:10px;font-weight:400;display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:1px;font-family:'Inter',sans-serif}
.substep span:last-child{font-size:13px;color:var(--dark);line-height:1.7}

/* CONTACT BUBBLE */
.contact-bubble{
  position:fixed;bottom:28px;right:28px;
  display:flex;align-items:center;gap:12px;
  background:var(--dark);color:var(--cream);
  padding:12px 18px 12px 14px;
  border-radius:40px;
  box-shadow:0 4px 24px rgba(0,0,0,0.18);
  text-decoration:none;
  z-index:9990;
  transition:all .3s;
  cursor:pointer;
}
.contact-bubble:hover{background:var(--gold);transform:translateY(-2px);box-shadow:0 8px 32px rgba(0,0,0,0.22)}
.contact-bubble-icon{font-size:20px;line-height:1}
.contact-bubble-text{display:flex;flex-direction:column;gap:1px}
.contact-bubble-label{font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--blush);font-family:'Inter',sans-serif}
.contact-bubble-name{font-family:'Cormorant Garamond',serif;font-size:15px;font-weight:400;color:var(--cream);line-height:1.2}
.contact-bubble-num{font-size:10px;font-weight:300;letter-spacing:.1em;color:var(--gold);font-family:'Inter',sans-serif}
.contact-bubble:hover .contact-bubble-num{color:var(--cream)}
.contact-bubble:hover .contact-bubble-label{color:rgba(255,255,255,0.7)}

/* TOAST */
.toast{position:fixed;bottom:28px;left:50%;transform:translateX(-50%) translateY(70px);background:var(--dark);color:var(--cream);padding:12px 28px;font-family:'Inter',sans-serif;font-size:9px;font-weight:300;letter-spacing:.2em;z-index:9999;transition:transform .4s;pointer-events:none;text-transform:uppercase}
.toast.show{transform:translateX(-50%) translateY(0)}

/* HIDDEN NAV */
.hidden-nav{display:none}

@media(max-width:700px){
  .top-nav{grid-template-columns:1fr;text-align:center;gap:8px;padding:10px 16px}
  .nav-left,.nav-right{display:none}
  .hero{padding:28px 16px 24px}
  .hero p{word-break:break-word;font-size:clamp(26px,7vw,42px) !important}
  .video-block{max-width:100%;margin:0 auto 18px}
  .video-block::before{display:none}
  .video-badge-circle{display:none}
  .section{padding:28px 12px}
  .section-title{font-size:clamp(28px,7vw,44px) !important}
  .cards-grid{grid-template-columns:1fr}
  .form-grid{grid-template-columns:1fr}
  .admin-stats{grid-template-columns:1fr 1fr}
  .admin-table-head,.recruit-row{grid-template-columns:1fr 1fr}
  .stats-row{grid-template-columns:1fr 1fr;gap:0}
  .stat{padding:0 12px}
  .stat-num{font-size:28px !important}
  .stat-label{font-size:8px !important}
  .time-slots{grid-template-columns:1fr 1fr}
  .main-cta{padding:14px 22px;font-size:9px;width:90%;display:block;margin:0 auto}
  #continue-btn{width:90%;font-size:10px;padding:14px 16px}
  .about-strip{grid-template-columns:1fr;gap:24px;padding:0 14px}
  .testimonials-strip{padding:0 14px}
  .cal-inner{padding:28px 12px}
  .form-inner{padding:28px 12px}
  .quiz-inner{padding:28px 12px}
  .confirm-inner{padding:28px 12px}
  .cta-section{padding:40px 14px}
  .login-box{padding:28px 16px}
  .side-menu{width:85vw}
  #calc-grid{grid-template-columns:1fr !important}
  #calc-grid>div:nth-child(2){display:none}
  #income-calc{padding:28px 12px}
  #income-calc>div[style*="max-width:480px"]{max-width:100% !important}
  #calc-before-num,#calc-after-num{font-size:30px !important}
  .recruit-row{display:flex;flex-direction:column;gap:6px;padding:12px}
  .recruit-name{font-size:15px !important}
  .recruit-email,.recruit-contact{font-size:10px !important}
  .admin-body{padding:10px}
  .portal-body{padding:18px 12px}
  .portal-welcome{font-size:clamp(22px,6vw,34px) !important}
  .portal-sub{font-size:12px !important}
  .step-header{padding:12px}
  .step-item{padding:0}
  input[type=range]{-webkit-appearance:none;appearance:none;height:6px;border-radius:3px;touch-action:pan-x}
  input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:28px;height:28px;border-radius:50%;background:var(--dark);cursor:pointer;border:2px solid var(--gold)}
  .cal-days{gap:3px}
  .cal-day{font-size:13px;min-height:32px}
  .time-slots{gap:6px}
  .time-slot{padding:12px 6px;font-size:11px}
  #bottom-banner{padding:7px 0;font-size:8px}
  .admin-header{padding:14px 16px}
  .admin-header h1{font-size:18px !important}
  /* Admin table on mobile — stack columns */
  .admin-table-head{display:none !important}
  #recruit-table .recruit-row{grid-template-columns:1fr !important}
  /* Stat cards smaller */
  .stat-card{padding:16px 10px}
  /* Pipeline tiles wrap tighter */
  #pipeline-view>div:first-child{gap:5px}

  /* Hero 3-col collapses: video first, cards below */
  #hero-3col { display:none !important; }
  #mobile-story { display:flex !important; }

  /* Credential block stacks on mobile */
  #credential-strip-inner { flex-direction: column !important; }
  #credential-strip-inner > div:first-child { flex: none !important; border-right: none !important; border-bottom: 0.5px solid rgba(160,144,128,0.18) !important; }

  /* Touch fix: replicate hover states on tap for info-card and svc-card */
  .info-card.touch-active{background:var(--cream2);box-shadow:0 0 24px 4px rgba(216,184,192,0.07),0 0 48px 12px rgba(216,184,192,0.03)}
  .info-card.touch-active::after{width:100%}
  .info-card.touch-active .card-front{opacity:0;transform:translateY(-6px)}
  .info-card.touch-active .card-back{opacity:1;transform:translateY(0)}
  .svc-card.touch-active{background:var(--cream2) !important}
  .svc-card.touch-active .svc-bar{width:100% !important}
}

/* ============ HAMBURGER MENU ============ */
.hamburger{position:fixed;top:20px;right:24px;z-index:9999;cursor:pointer;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:6px;padding:14px 18px;background:transparent;border:1px solid rgba(232,221,208,0.22);backdrop-filter:blur(8px);transition:all .35s;box-shadow:0 0 24px 4px rgba(216,184,192,0.08)}
.hamburger span{display:block;width:22px;height:1px;background:var(--dark);transition:all .35s}
.hamburger span:nth-child(2){width:14px;align-self:flex-end}
.hamburger:hover{border-color:rgba(232,221,208,0.55);background:rgba(232,221,208,0.06);box-shadow:0 0 32px 8px rgba(216,184,192,0.14)}
.hamburger:hover span{background:var(--beige-bright)}
.hamburger:hover span:nth-child(2){width:22px}
.hamburger-label{font-size:7px;font-weight:300;letter-spacing:.22em;color:var(--taupe);text-transform:uppercase;margin-top:1px;font-family:'Inter',sans-serif;transition:color .3s}
.hamburger:hover .hamburger-label{color:var(--dark)}

.side-menu{position:fixed;top:0;right:-320px;width:300px;height:100vh;background:var(--white);border-left:1px solid var(--border);z-index:9998;transition:right .4s cubic-bezier(.4,0,.2,1);padding:80px 40px 40px;display:flex;flex-direction:column;gap:0;box-shadow:-8px 0 32px rgba(0,0,0,0.06)}
.side-menu.open{right:0}
.side-menu-overlay{position:fixed;inset:0;background:rgba(0,0,0,0.15);z-index:9997;display:none;backdrop-filter:blur(2px)}
.side-menu-overlay.open{display:block}

.side-menu-label{font-size:8px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--taupe);margin-bottom:20px;padding-bottom:10px;border-bottom:1px solid var(--border)}
.side-menu-item{display:flex;flex-direction:column;gap:4px;padding:20px 0;border-bottom:1px solid var(--border);cursor:pointer;transition:all .2s}
.side-menu-item:hover .side-item-title{color:var(--gold2)}
.side-item-icon{font-size:20px;margin-bottom:4px}
.side-item-title{font-family:'Cormorant Garamond',serif;font-size:22px;font-weight:400;color:var(--dark);transition:color .2s}
.side-item-desc{font-size:10px;color:var(--taupe);letter-spacing:.1em;font-style:italic;font-family:'Cormorant Garamond',serif}

.side-menu-footer{margin-top:auto;font-size:9px;color:var(--border);letter-spacing:.15em;text-transform:uppercase;font-family:'Inter',sans-serif}

/* Login screen overlay */
#page-admin-login,#page-portal-login{
  background:var(--cream);
  position:relative;
}
#page-admin-login::before,#page-portal-login::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,var(--cream2) 0%,var(--white) 60%);
  z-index:0;
}
.login-wrap{position:relative;z-index:1;display:flex;flex-direction:column;align-items:center;justify-content:center;min-height:100vh;padding:40px 20px}
.login-brand{text-align:center;margin-bottom:48px}
.login-brand h1{font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:400;letter-spacing:.25em;text-transform:uppercase;color:var(--dark);margin-bottom:4px}
.login-brand p{font-size:8px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;color:var(--taupe)}
.login-brand .login-brand-divider{width:40px;height:1px;background:var(--gold);margin:12px auto}
.login-box{width:100%;max-width:400px;background:var(--white);border:1px solid var(--border);padding:48px 40px;text-align:center;box-shadow:0 8px 40px rgba(0,0,0,0.05)}
.login-icon{font-size:32px;margin-bottom:20px;display:block}
.login-box h2{font-family:'Cormorant Garamond',serif;font-size:32px;font-weight:400;color:var(--dark);margin-bottom:6px}
.login-box .login-role{font-size:8px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;color:var(--gold2);margin-bottom:24px;display:block}
.login-box .login-desc{font-family:'Cormorant Garamond',serif;font-size:16px;font-style:italic;color:var(--taupe);margin-bottom:28px;line-height:1.6}
.login-input-wrap{position:relative;margin-bottom:16px}
.login-input-wrap input{width:100%;background:var(--cream);border:1px solid var(--border);border-bottom:2px solid var(--border);color:var(--dark);padding:15px 16px;font-family:'Inter',sans-serif;font-size:14px;outline:none;transition:all .2s;text-align:center;letter-spacing:.1em}
.login-input-wrap input:focus{border-color:var(--dark);border-bottom-color:var(--dark);background:var(--white)}
.login-submit{width:100%;padding:15px;background:var(--dark);color:var(--cream);font-family:'Inter',sans-serif;font-size:10px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;border:none;cursor:pointer;transition:all .3s;margin-bottom:20px}
.login-submit:hover{background:var(--gold)}
.login-err{color:#b00;font-size:11px;margin-bottom:14px;font-style:italic;display:none;font-family:'Cormorant Garamond',serif}
.login-switch{padding-top:20px;border-top:1px solid var(--border);font-size:10px;color:var(--taupe);letter-spacing:.1em}
.login-switch a{color:var(--gold2);text-decoration:none;font-weight:300;letter-spacing:.1em}
.login-switch a:hover{color:var(--dark)}
.login-back{display:inline-flex;align-items:center;gap:6px;margin-top:20px;font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);cursor:pointer;text-decoration:none;transition:color .2s;background:none;border:none;font-family:'Inter',sans-serif}
.login-back:hover{color:var(--dark)}
</style>
</head>
<body>

<div class="toast" id="toast"></div>


<!-- Side menu overlay -->
<div class="side-menu-overlay" id="menu-overlay" onclick="toggleMenu()"></div>

<!-- Side menu -->
<div class="side-menu" id="side-menu">
  <button onclick="toggleMenu()" style="position:absolute;top:20px;right:20px;background:none;border:none;cursor:pointer;font-size:18px;color:var(--taupe);font-family:Jost,sans-serif;padding:8px">✕</button>
  <p class="side-menu-label">Navigation</p>
  <div class="side-menu-item" onclick="showPage('landing');toggleMenu()">
    <span class="side-item-icon">🏠</span>
    <span class="side-item-title">Home</span>
    <span class="side-item-desc">Back to the main page</span>
  </div>
  <div class="side-menu-item" onclick="showPage('services');toggleMenu()">
    <span class="side-item-icon">🛡️</span>
    <span class="side-item-title">What is Insurance?</span>
    <span class="side-item-desc">Products & carriers we offer</span>
  </div>
  <div class="side-menu-item" onclick="goToQuiz();toggleMenu()">
    <span class="side-item-icon">✍️</span>
    <span class="side-item-title">Apply Now</span>
    <span class="side-item-desc">See if it's a good fit</span>
  </div>
  <div style="margin-top:auto;padding-top:24px;border-top:1px solid var(--border);display:flex;gap:24px;justify-content:center">
    <span onclick="showPage('admin-login');toggleMenu()" style="font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);cursor:pointer;transition:color .25s" onmouseover="this.style.color='var(--dark)'" onmouseout="this.style.color='var(--taupe)'">Owner Login</span>
    <span style="font-size:9px;color:var(--taupe);opacity:0.65">·</span>
    <span onclick="showPage('portal-login');toggleMenu()" style="font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);cursor:pointer;transition:color .25s" onmouseover="this.style.color='var(--dark)'" onmouseout="this.style.color='var(--taupe)'">Team Login</span>
  </div>
  <div class="side-menu-footer">Nansi Hanna · Elite Motional Financial</div>
</div>


<!-- Fixed hamburger menu button — outside all pages so it's always visible -->
<button class="hamburger" onclick="toggleMenu()" id="hamburger-btn" aria-label="Open menu">
  <span></span>
  <span></span>
  <span></span>
  <div class="hamburger-label">Menu</div>
</button>

<!-- ===== AURORA BACKGROUND ===== -->
<div class="aurora-layer"><div class="a1"></div><div class="a2"></div><div class="a3"></div><div class="a4"></div></div>

<!-- ===== LANDING ===== -->
<div id="page-landing" class="page active" style="position:relative">

  <nav class="top-nav">
    <div class="nav-left">
      <a href="#" onclick="showPage('landing')">Home</a>
      <a href="#" onclick="showPage('services')">What is Insurance?</a>
    </div>
    <div class="nav-center">
      <h1>Nansi Hanna</h1>
      <p>Elite Motional Financial</p>
    </div>
    <div class="nav-right">
    </div>
  </nav>

  <div class="hero">
    <p style="font-family:'Cormorant Garamond',serif;font-size:clamp(36px,6vw,64px);font-weight:700;color:var(--dark);margin:0 0 0;line-height:1.05;letter-spacing:.01em;animation:fadeIn .7s ease both">I used to work 3 jobs only making $2K a month. Now I make that in <em style="color:var(--gold2);font-style:italic">30 minutes.</em></p>
    <div style="margin-bottom:32px"></div>

    <!-- HERO 2-COL: story | video — desktop -->
    <div id="hero-3col" style="display:grid;grid-template-columns:420px 1fr;gap:24px;align-items:start;max-width:100%;margin:0 auto;animation:fadeIn .8s .4s ease both">

      <!-- LEFT: Full story card -->
      <div style="display:flex;flex-direction:column;gap:18px;padding:28px 24px;border:0.5px solid rgba(160,144,128,0.28);box-shadow:0 0 40px 12px rgba(160,144,128,0.15),0 0 80px 32px rgba(160,144,128,0.09),0 0 120px 60px rgba(160,144,128,0.05);">

        <p style="font-family:'Cormorant Garamond',serif;font-size:clamp(16px,1.6vw,20px);font-weight:300;font-style:italic;color:var(--dark);line-height:1.8;margin:0">Quit my 3 jobs. Only had <strong style="font-style:normal;font-weight:600">$527</strong> in the bank. So I decided to try insurance sales.</p>

        <!-- Bank ending balance -->
        <div style="border:0.5px solid rgba(160,144,128,0.15);overflow:hidden;cursor:pointer" onclick="document.getElementById('bank-lightbox').style.display='flex'">
          <img src="data:image/png;base64,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" alt="Bank Statement $527.48" style="width:100%;display:block;image-rendering:crisp-edges;image-rendering:-webkit-optimize-contrast;">
        </div>

        <div onclick="document.getElementById('bank-lightbox').style.display='flex'" style="cursor:pointer;margin-top:-4px" onmouseover="this.style.opacity='.6'" onmouseout="this.style.opacity='1'">
          <span style="font-size:7px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe)">view proof →</span>
        </div>

        <div style="width:24px;height:0.5px;background:rgba(160,144,128,0.3)"></div>

        <p style="font-family:'Cormorant Garamond',serif;font-size:clamp(16px,1.6vw,20px);font-weight:300;font-style:italic;color:var(--dark);line-height:1.8;margin:0">Fast forward 6 months later —</p>

        <!-- FFL screenshot -->
        <div onclick="document.getElementById('proof-lightbox').style.display='flex'" style="cursor:pointer;border:0.5px solid rgba(160,144,128,0.15);overflow:hidden;transition:opacity .25s" onmouseover="this.style.opacity='.75'" onmouseout="this.style.opacity='1'">
          <img src="data:image/png;base64,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AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARdF97Z+f6KShF0X3tn5/opKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEXRfe2fn+ikoRdF97Z+f6KSgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABF0X3tn5/opKEZRfe2fn+ikmAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARlF97Z+f6EmRlF97Z+f6EmAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARtF96Z+f6EkRtH96Z+f6EkAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARtO5GTtcvdkkiKVD3hqnMRGvTiRO5fEDOBje2xeV/oh+e3w+WT0T6gZQMT2+HyyeifUdoQ+WT0T6gZYMTtCHySeifU/O0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqAP/9k=" alt="FFL Production Dashboard" style="width:100%;display:block;filter:grayscale(12%)">
        </div>

        <div style="font-family:'Cormorant Garamond',serif;font-size:clamp(24px,2.8vw,36px);font-weight:600;color:var(--gold2);letter-spacing:.01em;line-height:1">Already at $140K.</div>

        <div style="font-size:7px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe)">— Nansi Hanna</div>

      </div>

      <!-- RIGHT: Video -->
      <div class="video-block" style="margin:0">
        <div class="video-frame">
          <div class="video-inner">
            <a href="https://www.youtube.com/watch?v=CWUlLByKYA4" target="_blank" style="display:block;text-decoration:none">
              <div class="video-inner">
                <img src="https://img.youtube.com/vi/CWUlLByKYA4/maxresdefault.jpg" alt="Agency Overview">
                <div class="video-cinematic-overlay"></div>
                <div class="video-play-btn"><span>▶</span></div>
              </div>
            </a>
          </div>
        </div>
      </div>

    </div>

    <!-- MOBILE STORY STRIP — shown only on mobile instead of 3col -->
    <div id="mobile-story" style="display:none;flex-direction:column;gap:20px;max-width:100%;animation:fadeIn .8s .4s ease both">

      <!-- Video full width -->
      <div class="video-block" style="margin:0">
        <div class="video-frame">
          <div class="video-inner">
            <a href="https://www.youtube.com/watch?v=CWUlLByKYA4" target="_blank" style="display:block;text-decoration:none">
              <div class="video-inner">
                <img src="https://img.youtube.com/vi/CWUlLByKYA4/maxresdefault.jpg" alt="Agency Overview">
                <div class="video-cinematic-overlay"></div>
                <div class="video-play-btn"><span>▶</span></div>
              </div>
            </a>
          </div>
        </div>
      </div>

      <!-- Story + proof -->
      <div style="border:0.5px solid rgba(160,144,128,0.18);padding:20px 16px;display:flex;flex-direction:column;gap:16px">

        <p style="font-family:'Cormorant Garamond',serif;font-size:18px;font-weight:300;font-style:italic;color:var(--dark);line-height:1.8;margin:0">Quit my 3 jobs. Only had <strong style="font-style:normal;font-weight:600">$527</strong> in the bank. So I decided to try insurance sales.</p>

        <!-- Ending balance crop -->
        <div style="border:0.5px solid rgba(160,144,128,0.15);overflow:hidden">
          <img src="data:image/png;base64,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" alt="Bank Statement Ending Balance $527.48" style="width:100%;display:block;filter:grayscale(15%)">
        </div>

        <div style="width:24px;height:0.5px;background:rgba(160,144,128,0.3)"></div>

        <p style="font-family:'Cormorant Garamond',serif;font-size:18px;font-weight:300;font-style:italic;color:var(--dark);line-height:1.8;margin:0">Fast forward 6 months later —</p>

        <!-- FFL screenshot -->
        <div onclick="document.getElementById('proof-lightbox').style.display='flex'" style="cursor:pointer;border:0.5px solid rgba(160,144,128,0.15);overflow:hidden;transition:opacity .25s" onmouseover="this.style.opacity='.75'" onmouseout="this.style.opacity='1'">
          <img src="data:image/png;base64,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AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARdF97Z+f6KShF0X3tn5/opKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEXRfe2fn+ikoRdF97Z+f6KSgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABF0X3tn5/opKEZRfe2fn+ikmAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARlF97Z+f6EmRlF97Z+f6EmAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARtF96Z+f6EkRtH96Z+f6EkAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARtO5GTtcvdkkiKVD3hqnMRGvTiRO5fEDOBje2xeV/oh+e3w+WT0T6gZQMT2+HyyeifUdoQ+WT0T6gZYMTtCHySeifU/O0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqAP/9k=" alt="FFL Production Dashboard" style="width:100%;display:block;filter:grayscale(12%)">
        </div>
        <p style="font-family:'Cormorant Garamond',serif;font-size:18px;font-weight:300;font-style:italic;color:var(--dark);line-height:1.8;margin:0">Already at <strong style="font-style:normal;font-weight:600;color:var(--gold2)">$140K.</strong></p>
        <div style="font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);text-align:center">Tap screenshot to view full proof</div>

      </div>
    </div>

    <!-- BANK LIGHTBOX -->
    <div id="bank-lightbox" onclick="this.style.display='none'" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,0.88);z-index:9995;align-items:center;justify-content:center;cursor:pointer;backdrop-filter:blur(6px)">
      <div style="max-width:680px;width:92%;padding:3px;border:0.5px solid rgba(160,144,128,0.3);background:var(--cream)">
        <img src="data:image/png;base64,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" alt="Bank Statement" style="width:100%;display:block">
        <div style="padding:10px 14px;font-size:8px;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);font-family:'Inter',sans-serif;text-align:center">Bank Statement &mdash; Ending Balance $527.48 &middot; Tap anywhere to close</div>
      </div>
    </div>

    <!-- LIGHTBOX -->
    <div id="proof-lightbox" onclick="this.style.display='none'" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,0.88);z-index:9995;align-items:center;justify-content:center;cursor:pointer;backdrop-filter:blur(6px)">
      <div style="max-width:680px;width:92%;padding:3px;border:0.5px solid rgba(160,144,128,0.3);background:var(--cream)">
        <img src="data:image/png;base64,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AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARdF97Z+f6KShF0X3tn5/opKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEXRfe2fn+ikoRdF97Z+f6KSgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABF0X3tn5/opKEZRfe2fn+ikmAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARlF97Z+f6EmRlF97Z+f6EmAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARtF96Z+f6EkRtH96Z+f6EkAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARtO5GTtcvdkkiKVD3hqnMRGvTiRO5fEDOBje2xeV/oh+e3w+WT0T6gZQMT2+HyyeifUdoQ+WT0T6gZYMTtCHySeifU/O0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqO0IfJJ6J9QMwGH2hD5JPRPqAP/9k=" alt="Production Proof" style="width:100%;display:block">
        <div style="padding:10px 14px;font-size:8px;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);font-family:'Inter',sans-serif;text-align:center">FFL Dashboard &mdash; Personal Production YTD &middot; Tap anywhere to close</div>
      </div>
    </div>

    <!-- HOW IT WORKS TOGGLE -->
    <div style="text-align:center;margin:56px auto 0;max-width:700px;padding-bottom:80px;position:relative">
      <button class="main-cta" onclick="toggleHowItWorks()" id="how-it-works-btn" style="position:relative">How I Escaped the 9–5 ↓</button>
    </div>
  </div>

  <!-- HOW IT WORKS (hidden until clicked) -->
  <div id="how-it-works-section" style="display:none;background:radial-gradient(ellipse 80% 60% at 50% 50%,rgba(216,184,192,0.05) 0%,transparent 70%)">
    <div class="section">
      <div class="section-header">
        <p class="section-eyebrow">How It Works</p>
        <h2 class="section-title">Everything you need to <em>know.</em></h2>
      </div>
      <div class="cards-grid">
        <div class="info-card">
          <div class="card-front">
            <div class="card-title"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="#c8a94e" stroke-width="1.5" style="vertical-align:middle;margin-right:8px"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>How You Get Paid</div>
          </div>
          <div class="card-back">
            <div class="card-back-label">Commission Structure</div>
            <div class="card-back-text">Client pays <strong>$100/month</strong> × 12 = <strong>$1,200/year</strong>. At <strong>85% commission</strong> you earn <strong>$1,020 per policy</strong> in 3 days. Scale up to <strong>100%</strong> as you grow.</div>
          </div>
        </div>
        <div class="info-card">
          <div class="card-front">
            <div class="card-title"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="#c84a4a" stroke-width="1.5" style="vertical-align:middle;margin-right:8px"><polyline points="23 6 13.5 15.5 8.5 10.5 1 18"/><polyline points="17 6 23 6 23 12"/></svg>Commission Rate</div>
          </div>
          <div class="card-back">
            <div class="card-back-label">Your Rate</div>
            <div class="card-back-text">Start at <strong>85%</strong> — one of the highest in the industry. Grow to <strong>100%</strong> as you produce. No ceiling. Ever.</div>
          </div>
        </div>
        <div class="info-card">
          <div class="card-front">
            <div class="card-title"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="#4a7ec8" stroke-width="1.5" style="vertical-align:middle;margin-right:8px"><rect x="2" y="5" width="20" height="14" rx="2"/><line x1="2" y1="10" x2="22" y2="10"/></svg>Cost to Start</div>
          </div>
          <div class="card-back">
            <div class="card-back-label">What It Costs</div>
            <div class="card-back-text">Only cost is your government-required exam & license. We cover the rest — <strong>free course</strong> + <strong>2½ months of free leads</strong> included. Average agent makes <strong>$15K</strong> their first month.</div>
          </div>
        </div>
        <div class="info-card">
          <div class="card-front">
            <div class="card-title"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="#a06cc8" stroke-width="1.5" style="vertical-align:middle;margin-right:8px"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"/><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>Do I Need Experience?</div>
          </div>
          <div class="card-back">
            <div class="card-back-label">Zero Experience Needed</div>
            <div class="card-back-text">Agents come from restaurants, warehouses, barbershops — and hit <strong>$15K+</strong> their first month. We train you from day one.</div>
          </div>
        </div>
        <div class="info-card">
          <div class="card-front">
            <div class="card-title"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="#4a9e6a" stroke-width="1.5" style="vertical-align:middle;margin-right:8px"><line x1="12" y1="1" x2="12" y2="23"/><path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/></svg>Earning Potential</div>
          </div>
          <div class="card-back">
            <div class="card-back-label">Uncapped Income</div>
            <div class="card-back-text">Earning potential is <strong>uncapped</strong>. You can make anywhere from <strong>$5K to $250K a month</strong> — it's simply a matter of how much work you put in.</div>
          </div>
        </div>
        <div class="info-card">
          <div class="card-front">
            <div class="card-title"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="#e8a84a" stroke-width="1.5" style="vertical-align:middle;margin-right:8px"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>How Long Until I Make Money?</div>
          </div>
          <div class="card-back">
            <div class="card-back-label">Timeline</div>
            <div class="card-back-text">First commission within <strong>30 days</strong> of licensing. With 2–3 months of dedication, agents consistently hit <strong>$15K+/month.</strong></div>
          </div>
        </div>
      </div>
    </div>

    <!-- MAGICAL INCOME CALCULATOR -->
    <div id="income-calc" style="padding:64px 32px;text-align:center;position:relative;overflow:hidden">
      <div style="position:absolute;inset:0;background:radial-gradient(ellipse 70% 60% at 50% 50%,rgba(216,184,192,0.08) 0%,transparent 70%);pointer-events:none"></div>
      <p style="font-size:9px;font-weight:300;letter-spacing:.35em;text-transform:uppercase;color:var(--taupe);margin-bottom:16px">Your Reality Check</p>
      <h2 style="font-family:'Cormorant Garamond',serif;font-size:clamp(28px,5vw,48px);font-weight:300;color:var(--dark);line-height:1.1;margin-bottom:8px">What if you started <em style="font-style:italic;color:var(--taupe)">today?</em></h2>
      <p style="font-size:11px;color:var(--taupe);font-weight:300;margin-bottom:48px;letter-spacing:.04em">Drag to your current income. Watch what's possible.</p>

      <!-- SLIDER -->
      <div style="max-width:480px;margin:0 auto 48px">
        <div style="display:flex;justify-content:space-between;margin-bottom:10px">
          <span style="font-size:9px;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe)">Your current monthly income</span>
          <span id="calc-current-label" style="font-size:9px;letter-spacing:.2em;text-transform:uppercase;color:var(--dark);font-weight:400">$3,000</span>
        </div>
        <input type="range" id="calc-slider" min="500" max="20000" step="500" value="3000"
          style="width:100%;-webkit-appearance:none;appearance:none;height:1px;background:var(--border);outline:none;cursor:pointer;accent-color:var(--dark);touch-action:pan-x">
      </div>

      <!-- BEFORE / AFTER -->
      <div id="calc-grid" style="max-width:600px;margin:0 auto;display:grid;grid-template-columns:1fr auto 1fr;gap:0;align-items:center">

        <!-- BEFORE -->
        <div style="padding:32px 24px;border:0.5px solid var(--border);background:var(--cream);position:relative">
          <p style="font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--taupe);margin-bottom:20px">Where You Are</p>
          <div id="calc-before-num" style="font-family:'Cormorant Garamond',serif;font-size:52px;font-weight:300;color:var(--gold-soft);line-height:1;transition:all .4s ease">$3,000</div>
          <p style="font-size:8px;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-top:8px;opacity:0.6">per month</p>
          <div style="margin-top:20px;padding-top:20px;border-top:0.5px solid var(--border)">
            <div id="calc-before-year" style="font-size:12px;color:var(--taupe);font-weight:300;transition:all .4s ease">$36,000 / year</div>
            <div style="font-size:9px;color:var(--taupe);opacity:0.5;margin-top:4px;letter-spacing:.08em">trading time for money</div>
          </div>
        </div>

        <!-- ARROW -->
        <div style="padding:0 16px;display:flex;flex-direction:column;align-items:center;gap:6px">
          <div style="width:0.5px;height:30px;background:var(--border)"></div>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="var(--taupe)" stroke-width="1"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          <div style="width:0.5px;height:30px;background:var(--border)"></div>
        </div>

        <!-- AFTER -->
        <div style="padding:32px 24px;border:0.5px solid rgba(255,255,255,0.22);background:var(--cream2);position:relative;box-shadow:0 0 40px 16px rgba(255,255,255,0.28),0 0 80px 36px rgba(255,255,255,0.16),0 0 130px 60px rgba(20,140,60,0.10),0 0 200px 90px rgba(216,184,192,0.08)">
          <p style="font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--taupe);margin-bottom:20px">Where You Could Be</p>
          <div id="calc-after-num" style="font-family:'Cormorant Garamond',serif;font-size:52px;font-weight:300;color:var(--dark);line-height:1;transition:all .6s cubic-bezier(.34,1.56,.64,1)">$15,300</div>
          <p style="font-size:8px;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-top:8px;opacity:0.6">per month at Elite Motional Financial</p>
          <div style="margin-top:20px;padding-top:20px;border-top:0.5px solid rgba(20,140,60,0.25)">
            <div id="calc-after-year" style="font-size:12px;color:var(--dark);font-weight:300;transition:all .6s ease">$183,600 / year</div>
            <div id="calc-multiplier" style="font-size:9px;color:var(--taupe);margin-top:4px;letter-spacing:.08em;transition:all .4s ease">5.1× your current income</div>
          </div>
          <!-- glow pulse dot -->
          <div style="position:absolute;top:16px;right:16px;width:6px;height:6px;border-radius:50%;background:var(--gold);animation:glowPulse 2s ease-in-out infinite"></div>
        </div>
      </div>

      <!-- GAP LINE -->
      <div style="max-width:600px;margin:24px auto 0;padding:16px 24px;border:0.5px solid var(--border);background:var(--cream);display:flex;align-items:center;justify-content:space-between">
        <span style="font-size:9px;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe)">The gap you're leaving behind</span>
        <span id="calc-gap" style="font-family:'Cormorant Garamond',serif;font-size:22px;font-weight:300;color:var(--dark);transition:all .5s ease">$12,300 / mo</span>
      </div>
      <p style="font-size:9px;color:var(--taupe);margin-top:12px;font-style:italic;opacity:0.6">Based on FFL's average first-month agent income at 85% commission</p>
    </div>

    <!-- FINAL CTA -->
    <div style="text-align:center;padding:48px 32px 64px">
      <p style="font-family:'Cormorant Garamond',serif;font-size:clamp(18px,3vw,26px);font-weight:300;font-style:italic;color:var(--gold2);letter-spacing:.06em;margin-bottom:24px">It's simple, not easy...</p>
      <button id="continue-btn" onclick="goToQuiz()">See If It's a Good Fit →</button>
    </div>
  </div>

</div>

<!-- ===== SERVICES ===== -->
<div id="page-services" class="page">

  <nav class="top-nav">
    <div class="nav-left">
      <a href="#" onclick="showPage('landing')">Home</a>
      <a href="#" onclick="showPage('services')" style="color:var(--dark)">What is Insurance?</a>
    </div>
    <div class="nav-center">
      <h1>Nansi Hanna</h1>
      <p>Elite Motional Financial</p>
    </div>
    <div class="nav-right">
    </div>
  </nav>

  <!-- HERO BANNER -->
  <div style="text-align:center;padding:72px 40px 56px;border-bottom:1px solid var(--border);background:radial-gradient(ellipse 80% 50% at 50% 0%,rgba(232,221,208,0.12) 0%,transparent 70%)">
    <p style="font-size:9px;font-weight:300;letter-spacing:.35em;text-transform:uppercase;color:var(--taupe);margin-bottom:18px;animation:fadeIn .6s ease both">What We Do</p>
    <h1 style="font-family:'Cormorant Garamond',serif;font-size:clamp(38px,7vw,76px);font-weight:400;letter-spacing:.12em;text-transform:uppercase;color:var(--dark);line-height:1;margin-bottom:14px;animation:fadeIn .7s .1s ease both">Family First Life</h1>
    <div style="width:0;height:1px;background:linear-gradient(90deg,transparent,var(--beige),var(--gold),var(--beige-bright),transparent);margin:0 auto 32px;animation:expandW .8s .3s ease forwards"></div>
    <p style="font-family:'Cormorant Garamond',serif;font-size:clamp(16px,2.2vw,22px);font-style:italic;color:var(--gold2);max-width:620px;margin:0 auto;line-height:1.7;animation:fadeIn .7s .3s ease both">Protecting families. Building legacies. Creating financial freedom — one policy at a time.</p>
  </div>

  <!-- WHO WE ARE -->
  <div style="max-width:900px;margin:0 auto;padding:72px 48px 0;display:grid;grid-template-columns:1fr 1fr;gap:64px;align-items:center">
    <div style="animation:fadeIn .8s .2s ease both">
      <p style="font-size:8px;font-weight:300;letter-spacing:.35em;text-transform:uppercase;color:var(--gold);margin-bottom:14px">Who We Are</p>
      <h2 style="font-family:'Cormorant Garamond',serif;font-size:clamp(26px,3.5vw,40px);font-weight:400;color:var(--dark);line-height:1.2;margin-bottom:20px">America's #1 Independent Life Insurance Agency</h2>
      <p style="font-family:'Cormorant Garamond',serif;font-size:17px;font-style:italic;color:var(--taupe);line-height:1.85;margin-bottom:18px">Family First Life (FFL) is a national insurance marketing organization dedicated to one mission: putting families first. We partner with the top-rated carriers in the country to offer clients the very best in life insurance, mortgage protection, and final expense coverage.</p>
      <p style="font-size:13px;color:var(--taupe);line-height:1.9;font-weight:300">Founded on the belief that every family deserves financial security, FFL has grown into a powerhouse of over 35,000 licensed agents across the United States — all working to protect the people who matter most.</p>
    </div>
    <div style="animation:fadeIn .8s .35s ease both">
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--border)">
        <div style="background:var(--cream2);padding:32px 24px;text-align:center">
          <div style="font-family:'Cormorant Garamond',serif;font-size:42px;font-weight:400;color:var(--gold);letter-spacing:.05em">35K+</div>
          <div style="font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-top:6px">Licensed Agents</div>
        </div>
        <div style="background:var(--cream2);padding:32px 24px;text-align:center">
          <div style="font-family:'Cormorant Garamond',serif;font-size:42px;font-weight:400;color:var(--gold);letter-spacing:.05em">#1</div>
          <div style="font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-top:6px">Independent IMO</div>
        </div>
        <div style="background:var(--cream2);padding:32px 24px;text-align:center">
          <div style="font-family:'Cormorant Garamond',serif;font-size:42px;font-weight:400;color:var(--gold);letter-spacing:.05em">85%</div>
          <div style="font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-top:6px">Starting Commission</div>
        </div>
        <div style="background:var(--cream2);padding:32px 24px;text-align:center">
          <div style="font-family:'Cormorant Garamond',serif;font-size:42px;font-weight:400;color:var(--gold);letter-spacing:.05em">A+</div>
          <div style="font-size:8px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-top:6px">Carrier Ratings</div>
        </div>
      </div>
    </div>
  </div>

  <!-- WHAT WE SELL -->
  <div style="max-width:1000px;margin:72px auto 0;padding:0 48px">
    <div style="text-align:center;margin-bottom:52px;animation:fadeIn .7s .1s ease both">
      <p style="font-size:8px;font-weight:300;letter-spacing:.35em;text-transform:uppercase;color:var(--gold2);margin-bottom:12px">Our Products</p>
      <h2 style="font-family:'Cormorant Garamond',serif;font-size:clamp(28px,4vw,48px);font-weight:400;color:var(--dark);letter-spacing:.05em">What We <em style="font-style:italic;color:var(--gold2)">Sell</em></h2>
    </div>

    <div style="display:grid;grid-template-columns:repeat(2,1fr);gap:1px;background:var(--border);animation:fadeIn .8s .2s ease both">

      <!-- FINAL EXPENSE -->
      <div class="svc-card" style="background:var(--white);padding:40px 30px;position:relative;overflow:hidden;transition:background .3s">
        <div style="font-size:32px;margin-bottom:18px">🕊️</div>
        <p style="font-size:8px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:10px">Most Popular</p>
        <h3 style="font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:400;color:var(--dark);margin-bottom:14px">Final Expense Insurance</h3>
        <p style="font-size:13px;color:var(--taupe);line-height:1.85;font-weight:300;margin-bottom:20px">Affordable whole-life policies designed to cover funeral costs, medical bills, and other end-of-life expenses — so families are never left with a financial burden during the hardest moments of their lives.</p>
        <ul style="list-style:none;padding:0;display:flex;flex-direction:column;gap:8px">
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Coverage from $5,000 to $50,000</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>No medical exam required</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Guaranteed acceptance options</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Premiums never increase</li>
        </ul>
        <div style="position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--gold);transition:width .4s" class="svc-bar"></div>
      </div>

      <!-- MORTGAGE PROTECTION -->
      <div class="svc-card" style="background:var(--white);padding:40px 30px;position:relative;overflow:hidden;transition:background .3s">
        <div style="font-size:32px;margin-bottom:18px">🏡</div>
        <p style="font-size:8px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:10px">High Demand</p>
        <h3 style="font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:400;color:var(--dark);margin-bottom:14px">Mortgage Protection</h3>
        <p style="font-size:13px;color:var(--taupe);line-height:1.85;font-weight:300;margin-bottom:20px">Term life policies tailored specifically to pay off a client's mortgage if they pass away unexpectedly — ensuring their family keeps the home they built together, no matter what.</p>
        <ul style="list-style:none;padding:0;display:flex;flex-direction:column;gap:8px">
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Tied to your exact mortgage balance</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Return of premium options</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Disability & critical illness riders</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Coverage up to $1,000,000+</li>
        </ul>
        <div style="position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--gold);transition:width .4s" class="svc-bar"></div>
      </div>

      <!-- TERM & WHOLE LIFE -->
      <div class="svc-card" style="background:var(--white);padding:40px 30px;position:relative;overflow:hidden;transition:background .3s">
        <div style="font-size:32px;margin-bottom:18px">🛡️</div>
        <p style="font-size:8px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:10px">Comprehensive</p>
        <h3 style="font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:400;color:var(--dark);margin-bottom:14px">Term & Whole Life</h3>
        <p style="font-size:13px;color:var(--taupe);line-height:1.85;font-weight:300;margin-bottom:20px">Whether a family needs short-term income replacement or permanent lifelong coverage with cash value, we have the right policy from the nation's top-rated carriers to fit every budget.</p>
        <ul style="list-style:none;padding:0;display:flex;flex-direction:column;gap:8px">
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>10, 20, 30-year term options</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Whole life with cash accumulation</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Instant approval on many plans</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Coverage from $50K to $5M</li>
        </ul>
        <div style="position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--gold);transition:width .4s" class="svc-bar"></div>
      </div>

      <!-- IUL -->
      <div class="svc-card" style="background:var(--white);padding:40px 30px;position:relative;overflow:hidden;transition:background .3s">
        <div style="font-size:32px;margin-bottom:18px">📈</div>
        <p style="font-size:8px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:10px">Wealth Building</p>
        <h3 style="font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:400;color:var(--dark);margin-bottom:14px">Indexed Universal Life (IUL)</h3>
        <p style="font-size:13px;color:var(--taupe);line-height:1.85;font-weight:300;margin-bottom:20px">A powerful permanent life insurance policy that builds tax-advantaged cash value tied to a market index — giving clients both lifelong protection and a vehicle for long-term wealth growth without direct market risk.</p>
        <ul style="list-style:none;padding:0;display:flex;flex-direction:column;gap:8px">
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Coverage from $50,000 to $500,000+</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Tax-free cash value accumulation</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Index-linked growth, 0% floor</li>
          <li style="font-size:11px;color:var(--taupe);display:flex;gap:8px;align-items:flex-start"><span style="color:var(--gold);margin-top:1px">—</span>Retirement income supplement</li>
        </ul>
        <div style="position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--gold);transition:width .4s" class="svc-bar"></div>
      </div>

    </div>
  </div>

  <!-- TOP CARRIERS -->
  <div style="max-width:900px;margin:72px auto 0;padding:0 48px;text-align:center;animation:fadeIn .8s .2s ease both">
    <p style="font-size:8px;font-weight:300;letter-spacing:.35em;text-transform:uppercase;color:var(--taupe);margin-bottom:32px">Carriers We Work With</p>
    <div style="display:flex;flex-wrap:wrap;justify-content:center;gap:12px">
      <span style="padding:10px 20px;border:1px solid var(--border);font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe)">Americo</span>
      <span style="padding:10px 20px;border:1px solid var(--border);font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe)">Mutual of Omaha</span>
      <span style="padding:10px 20px;border:1px solid var(--border);font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe)">AMAM</span>
      <span style="padding:10px 20px;border:1px solid var(--border);font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe)">Aetna</span>
      <span style="padding:10px 20px;border:1px solid var(--border);font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe)">Chubb</span>
      <span style="padding:10px 20px;border:1px solid var(--border);font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe)">Corebridge</span>
      <span style="padding:10px 20px;border:1px solid var(--border);font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe)">Transamerica</span>
      <span style="padding:10px 20px;border:1px solid var(--border);font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe)">Independent Broker</span>
    </div>
  </div>

  <!-- BOTTOM CTA -->
  <div style="text-align:center;padding:80px 40px;margin-top:72px;background:var(--cream2);border-top:1px solid var(--border)">
    <p style="font-size:9px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:16px">Ready to Help Families?</p>
    <h2 style="font-family:'Cormorant Garamond',serif;font-size:clamp(28px,4.5vw,54px);font-weight:400;color:var(--dark);margin-bottom:10px;letter-spacing:.05em">Join Nansi &amp; the FFL <em style="font-style:italic;color:var(--gold2)">Team</em></h2>
    <p style="font-family:'Cormorant Garamond',serif;font-size:18px;font-style:italic;color:var(--taupe);margin-bottom:36px">Sell products that change lives. Build a career you're proud of.</p>
    <button onclick="goToQuiz()" style="display:inline-block;padding:16px 56px;background:transparent;color:var(--beige-bright);font-family:'Inter',sans-serif;font-size:10px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;border:1px solid rgba(232,221,208,0.50);cursor:pointer;transition:all .4s;box-shadow:0 0 28px 6px rgba(232,221,208,0.14)">Apply With Me →</button>
  </div>

</div>

<!-- ===== QUIZ ===== -->
<div id="page-quiz" class="page">
  <nav class="top-nav">
    <div class="nav-left">
      <a href="#" onclick="showPage('landing')">Home</a>
      <a href="#" onclick="showPage('services')">What is Insurance?</a>
    </div>
    <div class="nav-center">
      <h1>Nansi Hanna</h1>
      <p>Elite Motional Financial</p>
    </div>
    <div class="nav-right">
    </div>
  </nav>
  <div style="display:flex;align-items:center;justify-content:center">
  <div class="quiz-inner">
    <div class="quiz-progress" id="quiz-progress"></div>
    <div class="quiz-q-num" id="quiz-q-num">Question 1 of 6</div>
    <div class="quiz-question" id="quiz-question"></div>
    <div class="quiz-options" id="quiz-options"></div>
    <button class="quiz-next" id="quiz-next" onclick="nextQuestion()">Next →</button>
  </div>
  </div>
</div>

<!-- ===== NOT A FIT ===== -->
<div id="page-not-a-fit" class="page" style="min-height:100vh;background:transparent;align-items:center;justify-content:center">
  <div style="max-width:480px;width:100%;padding:80px 32px;text-align:center">
    <p style="font-size:9px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--taupe);margin-bottom:24px">Application Result</p>
    <h2 style="font-family:'Cormorant Garamond',serif;font-size:clamp(28px,5vw,44px);font-weight:300;color:var(--dark);margin-bottom:16px;line-height:1.2">It doesn't look like<br><em style="font-style:italic;color:var(--taupe)">this is a good fit</em></h2>
    <div style="width:40px;height:0.5px;background:var(--border);margin:24px auto"></div>
    <p style="font-family:'Cormorant Garamond',serif;font-size:17px;font-style:italic;color:var(--taupe);line-height:1.8;margin-bottom:32px">Based on your answers, this opportunity may not align with where you are right now — and that's okay. This role requires a very specific mindset and commitment level.</p>
    <button onclick="showPage('landing')" style="padding:12px 32px;background:transparent;color:var(--dark);border:0.5px solid var(--border);font-family:'Inter',sans-serif;font-size:9px;font-weight:300;letter-spacing:.22em;text-transform:uppercase;cursor:pointer">Back to Home</button>
  </div>
</div>

<!-- ===== FORM ===== -->
<div id="page-form" class="page">
  <div class="form-inner">
    <div class="form-eyebrow">You Made It This Far</div>
    <h2 class="form-title">This Might Be a Good Fit.</h2>
    <p class="form-sub">Let's schedule a 5-minute call.</p>
    <form id="recruit-form" autocomplete="on" onsubmit="return false">
    <div class="form-grid">
      <div class="form-field"><label>First Name</label><input type="text" id="f-first" name="given-name" placeholder="First name" autocomplete="given-name"></div>
      <div class="form-field"><label>Last Name</label><input type="text" id="f-last" name="family-name" placeholder="Last name" autocomplete="family-name"></div>
      <div class="form-field"><label>Email Address</label><input type="email" id="f-email" name="email" placeholder="your@email.com" autocomplete="email"></div>
      <div class="form-field"><label>Phone Number</label><input type="tel" id="f-phone" name="tel" placeholder="(000) 000-0000" autocomplete="tel"></div>
      <div class="form-field full"><label>Instagram Handle <span style="font-weight:300;color:var(--taupe);font-size:10px;letter-spacing:.05em">(optional)</span></label><input type="text" id="f-instagram" name="instagram" placeholder="@yourhandle" autocomplete="off"></div>
      <div class="form-field full"><label>State You Live In</label>
        <select id="f-state" name="state" autocomplete="address-level1">
          <option value="">Select your state...</option>
          <option>Alabama</option><option>Alaska</option><option>Arizona</option><option>Arkansas</option><option>California</option><option>Colorado</option><option>Connecticut</option><option>Delaware</option><option>Florida</option><option>Georgia</option><option>Hawaii</option><option>Idaho</option><option>Illinois</option><option>Indiana</option><option>Iowa</option><option>Kansas</option><option>Kentucky</option><option>Louisiana</option><option>Maine</option><option>Maryland</option><option>Massachusetts</option><option>Michigan</option><option>Minnesota</option><option>Mississippi</option><option>Missouri</option><option>Montana</option><option>Nebraska</option><option>Nevada</option><option>New Hampshire</option><option>New Jersey</option><option>New Mexico</option><option>New York</option><option>North Carolina</option><option>North Dakota</option><option>Ohio</option><option>Oklahoma</option><option>Oregon</option><option>Pennsylvania</option><option>Rhode Island</option><option>South Carolina</option><option>South Dakota</option><option>Tennessee</option><option>Texas</option><option>Utah</option><option>Vermont</option><option>Virginia</option><option>Washington</option><option>West Virginia</option><option>Wisconsin</option><option>Wyoming</option>
        </select>
      </div>
    </div>
    <button type="button" class="submit-btn" onclick="submitForm()">Submit & Book My Call →</button>
    </form>
  </div>
</div>

<!-- ===== CALENDAR ===== -->
<div id="page-calendar" class="page">
  <div class="cal-inner">
    <p class="cal-eyebrow">Almost There</p>
    <h2 class="cal-title">Book Your Interview</h2>
    <p style="font-family:'Cormorant Garamond',serif;font-size:17px;font-style:italic;color:var(--taupe);margin-bottom:36px">Pick a date and time — Nansi will be there.</p>

    <div class="cal-host">
      <div class="cal-avatar">N</div>
      <div>
        <div class="cal-host-name">Nansi Hanna</div>
        <div class="cal-host-title">Elite Motional Financial · 15 min intro call</div>
      </div>
    </div>

    <div class="calendar-widget">
      <div class="cal-month">
        <button class="cal-nav" onclick="prevMonth()">‹</button>
        <span id="cal-month-label"></span>
        <button class="cal-nav" onclick="nextMonth()">›</button>
      </div>
      <div class="cal-days-header">
        <div class="cal-day-label">Sun</div><div class="cal-day-label">Mon</div><div class="cal-day-label">Tue</div><div class="cal-day-label">Wed</div><div class="cal-day-label">Thu</div><div class="cal-day-label">Fri</div><div class="cal-day-label">Sat</div>
      </div>
      <div class="cal-days" id="cal-days"></div>
    </div>

    <div id="time-slots-section" style="display:none;margin-top:20px;text-align:left">
      <p style="font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe);margin-bottom:12px">Available Times</p>
      <div class="time-slots" id="time-slots"></div>
    </div>

    <button class="book-btn" id="book-btn" onclick="bookAppointment()">Confirm Booking →</button>
  </div>
</div>

<!-- ===== CONFIRM ===== -->
<div id="page-confirm" class="page">
  <div class="confirm-inner">
    <div class="confirm-check">✓</div>
    <h2 class="confirm-title">You're Booked.</h2>
    <p class="confirm-sub">A confirmation has been sent to your email and phone. Nansi will see you soon.</p>
    <div class="confirm-details" id="confirm-details"></div>
    <p class="confirm-note">Check your inbox and texts for your appointment details.</p>
  </div>
</div>

<!-- ===== ADMIN LOGIN ===== -->
<div id="page-admin-login" class="page">
  <div class="login-wrap">
    <div class="login-brand">
      <h1>Nansi Hanna</h1>
      <div class="login-brand-divider"></div>
      <p>Elite Motional Financial</p>
    </div>
    <div class="login-box">
      <span class="login-icon">🔐</span>
      <h2>Owner Login</h2>
      <span class="login-role">Full Dashboard Access</span>
      <p class="login-desc">Enter your password to view all recruits, manage ranks, and track progress.</p>
      <div class="login-input-wrap">
        <input type="password" id="admin-pw" placeholder="Enter password" autocomplete="off" spellcheck="false" onkeydown="if(event.key==='Enter')adminLogin()">
      </div>
      <div class="login-err" id="admin-err">Incorrect password. Please try again.</div>
      <button class="login-submit" onclick="adminLogin()">View My Dashboard →</button>
      <div class="login-switch" style="display:flex;flex-direction:column;gap:8px;margin-top:16px">
        <span>Admin? <a href="#" onclick="showPage('eli-login')">Admin Login →</a></span>
        <span>Team member? <a href="#" onclick="showPage('portal-login')">Team Login →</a></span>
      </div>
    </div>
    <button class="login-back" onclick="showPage('landing')">← Back to Site</button>
  </div>
</div>

<!-- ===== ELI ADMIN LOGIN ===== -->
<div id="page-eli-login" class="page">
  <div class="login-wrap">
    <div class="login-brand">
      <h1>Nansi Hanna</h1>
      <div class="login-brand-divider"></div>
      <p>Elite Motional Financial</p>
    </div>
    <div class="login-box">
      <span class="login-icon">👤</span>
      <h2>Admin Login</h2>
      <span class="login-role">Hiring Manager Access</span>
      <p class="login-desc">Enter your admin password to view recruit information.</p>
      <div class="login-input-wrap">
        <input type="password" id="eli-pw" placeholder="Enter password" autocomplete="off" spellcheck="false" onkeydown="if(event.key==='Enter')eliLogin()">
      </div>
      <div class="login-err" id="eli-err">Incorrect password. Please try again.</div>
      <button class="login-submit" onclick="eliLogin()">Access Dashboard →</button>
      <div class="login-switch">Owner? <a href="#" onclick="showPage('admin-login')">Owner Login →</a></div>
    </div>
    <button class="login-back" onclick="showPage('landing')">← Back to Site</button>
  </div>
</div>

<!-- ===== ELI DASHBOARD ===== -->
<div id="page-eli-admin" class="page">
  <div class="admin-header">
    <h1>Admin Dashboard</h1>
    <div style="display:flex;align-items:center;gap:20px"><span id="eli-date"></span><button onclick="showPage('landing')" style="padding:8px 16px;background:var(--dark);color:var(--cream);border:none;font-family:Jost,sans-serif;font-size:9px;font-weight:300;letter-spacing:.15em;text-transform:uppercase;cursor:pointer">Back to Site</button></div>
  </div>
  <!-- TABS -->
  <div style="display:flex;gap:0;border-bottom:1px solid var(--border);background:var(--cream);padding:0 32px">
    <button id="eli-tab-recruits" onclick="switchEliTab('recruits')" style="padding:14px 24px;background:var(--dark);color:var(--cream);border:none;font-family:Inter,sans-serif;font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;border-bottom:2px solid var(--gold)">👥 Recruits</button>

  </div>
  <!-- RECRUITS TAB -->
  <div id="eli-tab-recruits-panel" class="admin-body">
    <div class="admin-table-wrap">
      <div style="display:grid;grid-template-columns:2fr 2fr 1fr 1fr 1fr;padding:12px 20px;background:var(--dark);border-bottom:1px solid var(--border)">
        <span style="font-size:8px;font-weight:300;letter-spacing:.15em;color:var(--beige);text-transform:uppercase">Name</span>
        <span style="font-size:8px;font-weight:300;letter-spacing:.15em;color:var(--beige);text-transform:uppercase">Email</span>
        <span style="font-size:8px;font-weight:300;letter-spacing:.15em;color:var(--beige);text-transform:uppercase">Phone</span>
        <span style="font-size:8px;font-weight:300;letter-spacing:.15em;color:var(--beige);text-transform:uppercase">State</span>
        <span style="font-size:8px;font-weight:300;letter-spacing:.15em;color:var(--beige);text-transform:uppercase">Current Step</span>
      </div>
      <div id="eli-table"></div>
    </div>
  </div>

</div>

<!-- ===== ADMIN DASHBOARD ===== -->
<div id="page-admin" class="page">
  <div class="admin-header">
    <h1>Owner Dashboard</h1>
    <div style="display:flex;align-items:center;gap:20px"><span id="admin-date"></span><button onclick="showPage('landing')" style="padding:8px 16px;background:var(--dark);color:var(--cream);border:none;font-family:Jost,sans-serif;font-size:9px;font-weight:300;letter-spacing:.15em;text-transform:uppercase;cursor:pointer">Back to Site</button></div>
  </div>
  <!-- TABS -->
  <div style="display:flex;gap:0;border-bottom:1px solid var(--border);background:var(--cream);padding:0 32px">
    <button id="tab-recruits" onclick="switchAdminTab('recruits')" style="padding:14px 24px;background:var(--dark);color:var(--cream);border:none;font-family:Inter,sans-serif;font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;border-bottom:2px solid var(--gold)">👥 Recruits</button>
    <button id="tab-pipeline" onclick="switchAdminTab('pipeline')" style="padding:14px 24px;background:transparent;color:var(--taupe);border:none;font-family:Inter,sans-serif;font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;border-bottom:2px solid transparent">📊 Pipeline</button>
    <button id="tab-calendar" onclick="switchAdminTab('calendar')" style="padding:14px 24px;background:transparent;color:var(--taupe);border:none;font-family:Inter,sans-serif;font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;border-bottom:2px solid transparent">📅 Calendar</button>

  </div>

  <!-- RECRUITS TAB -->
  <div id="admin-tab-recruits" class="admin-body">
    <div class="admin-stats">
      <div class="stat-card" onclick="filterTable('all')" style="cursor:pointer"><div class="stat-num" id="stat-total">0</div><div class="stat-label">Total Applied</div></div>
      <div class="stat-card" onclick="filterTable('booked')" style="cursor:pointer"><div class="stat-num" id="stat-booked">0</div><div class="stat-label">Booked Calls</div></div>
      <div class="stat-card" onclick="filterTable('recruited')" style="cursor:pointer"><div class="stat-num" id="stat-recruited">0</div><div class="stat-label">Total Recruited</div></div>
    </div>

    <div class="admin-table-wrap">
      <div class="admin-table-head" style="grid-template-columns:2fr 2fr 1fr 1fr 1.5fr 1fr;background:var(--dark)">
        <span style="color:var(--beige)">Name</span><span style="color:var(--beige)">Contact & Appointment</span><span style="color:var(--beige)">Rank</span><span style="color:var(--beige)">Progress</span><span style="color:var(--beige)">Action</span><span style="color:var(--beige)">Answers</span>
      </div>
      <div id="recruit-table"></div>
    </div>
  </div>

  <!-- PIPELINE TAB -->
  <div id="admin-tab-pipeline" class="admin-body" style="display:none">
    <div id="pipeline-view"></div>
  </div>

  <!-- CALENDAR TAB -->
  <div id="admin-tab-calendar" class="admin-body" style="display:none">
    <div id="admin-calendar-view"></div>
  </div>


</div>

<!-- ===== PORTAL LOGIN ===== -->
<div id="page-portal-login" class="page">
  <div class="login-wrap">
    <div class="login-brand">
      <h1>Nansi Hanna</h1>
      <div class="login-brand-divider"></div>
      <p>Elite Motional Financial</p>
    </div>
    <div class="login-box">
      <span class="login-icon">👥</span>
      <h2>Team Login</h2>
      <span class="login-role">Onboarding Portal Access</span>
      <p class="login-desc">Enter your access code to view your onboarding steps and track your progress to getting licensed.</p>
      <div class="login-input-wrap" style="position:relative">
        <input type="text" id="portal-pw" placeholder="Enter access code" onkeydown="if(event.key==='Enter')portalLogin()" autocomplete="off" autocorrect="off" autocapitalize="none" spellcheck="false" style="-webkit-text-security:disc;text-security:disc;padding-right:48px">
        <button type="button" id="portal-pw-toggle" onclick="(function(){var i=document.getElementById('portal-pw');var on=i.style.webkitTextSecurity==='none';i.style.webkitTextSecurity=on?'disc':'none';i.style.textSecurity=on?'disc':'none';document.getElementById('portal-pw-toggle').textContent=on?'👁':'🙈'})()" style="position:absolute;right:12px;top:50%;transform:translateY(-50%);background:none;border:none;cursor:pointer;font-size:16px;color:var(--taupe);padding:0;line-height:1">👁</button>
      </div>
      <div class="login-err" id="portal-err">Incorrect access code. Please try again.</div>
      <button class="login-submit" onclick="portalLogin()">Access My Portal →</button>
      <div class="login-switch">Owner? <a href="#" onclick="showPage('admin-login')">Owner Login →</a></div>
      <div style="margin-top:24px;padding-top:20px;border-top:1px solid var(--border);font-size:12px;color:var(--taupe);font-family:'Cormorant Garamond',serif;font-style:italic;line-height:1.7">Have any questions? Contact Nansi —<br><a href="tel:6195587851" style="color:var(--gold2);text-decoration:none;font-weight:400">619-558-7851</a></div>
    </div>
    <button class="login-back" onclick="showPage('landing')">← Back to Site</button>
  </div>
</div>

<!-- ===== PORTAL ===== -->
<div id="page-portal" class="page">
  <div class="portal-header">
    <h1>Your Onboarding Portal</h1>
    <div style="display:flex;align-items:center;gap:16px">
      <a href="sms:6195587851" style="display:flex;align-items:center;gap:8px;text-decoration:none;padding:8px 14px;border:1px solid var(--border);background:var(--cream)">
        <span style="font-size:16px">💬</span>
        <div style="display:flex;flex-direction:column;gap:1px">
          <span style="font-size:8px;font-weight:300;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe);font-family:Jost,sans-serif">Have a question?</span>
          <span style="font-family:'Cormorant Garamond',serif;font-size:14px;color:var(--dark)">Contact Nansi</span>
        </div>
      </a>
      <span style="font-size:10px;color:var(--taupe);letter-spacing:.1em;font-weight:300;font-family:Jost,sans-serif">FAMILY FIRST LIFE</span>
      <button onclick="showPage('landing')" style="padding:8px 16px;background:var(--dark);color:var(--cream);border:none;font-family:Jost,sans-serif;font-size:9px;font-weight:300;letter-spacing:.15em;text-transform:uppercase;cursor:pointer">Back to Site</button>
    </div>
  </div>
  <div class="portal-body">
    <h2 class="portal-welcome">Welcome to the Team.</h2>
    <p class="portal-sub">Complete each step in order. Your progress is tracked automatically.</p>
    <div id="portal-progress" style="margin-bottom:28px"></div>
    <div class="step-container" id="step-container"></div>
  </div>
</div>

<script>
const ADMIN_HASH = "62003047facd4f7c305c0e20ccd9e40c6118ef40fb7ea88925f78b483afc2824";
const ELI_HASH   = "0cea5f96b56820de05a2e32fbd2bb780ca6fd659252572f9bc572bde25483d55";
// Separate hash for portal owner preview (same password but isolated check)
const PORTAL_ADMIN_HASH = "62003047facd4f7c305c0e20ccd9e40c6118ef40fb7ea88925f78b483afc2824";

async function hashInput(str){
  const buf = await crypto.subtle.digest("SHA-256", new TextEncoder().encode(str));
  return Array.from(new Uint8Array(buf)).map(b=>b.toString(16).padStart(2,"0")).join("");
}

// ============ RATE LIMITING ============
// Stores: { attempts: number, lockedUntil: timestamp }
var _loginAttempts = {admin:0, eli:0, portal:0};
var _loginLockUntil = {admin:0, eli:0, portal:0};
var MAX_ATTEMPTS = 5;
var LOCK_DURATION_MS = 15 * 60 * 1000; // 15 minutes

function checkRateLimit(role){
  var now = Date.now();
  if(_loginLockUntil[role] && now < _loginLockUntil[role]){
    var minsLeft = Math.ceil((_loginLockUntil[role] - now) / 60000);
    showToast("Too many attempts. Try again in " + minsLeft + " min.");
    return false; // blocked
  }
  return true; // allowed
}

function recordFailedAttempt(role){
  _loginAttempts[role] = (_loginAttempts[role] || 0) + 1;
  if(_loginAttempts[role] >= MAX_ATTEMPTS){
    _loginLockUntil[role] = Date.now() + LOCK_DURATION_MS;
    _loginAttempts[role] = 0;
    showToast("Too many failed attempts. Locked for 15 minutes.");
  }
}

function resetAttempts(role){
  _loginAttempts[role] = 0;
  _loginLockUntil[role] = 0;
}

// ============ SESSION TIMEOUT ============
var SESSION_TIMEOUT_MS = 30 * 60 * 1000; // 30 minutes
var _sessionTimer = null;
var _sessionRole = null; // "admin" | "eli" | "portal"

function startSession(role){
  _sessionRole = role;
  resetSessionTimer();
}

function resetSessionTimer(){
  if(_sessionTimer) clearTimeout(_sessionTimer);
  _sessionTimer = setTimeout(function(){
    expireSession();
  }, SESSION_TIMEOUT_MS);
}

function expireSession(){
  if(!_sessionRole) return;
  var role = _sessionRole;
  _sessionRole = null;
  currentRecruit = null;
  showToast("Session expired. Please log in again.");
  if(role === "admin") showPage("admin-login");
  else if(role === "eli") showPage("eli-login");
  else showPage("portal-login");
}

// Reset timer on any user interaction when logged in
document.addEventListener("click", function(){ if(_sessionRole) resetSessionTimer(); }, true);
document.addEventListener("keydown", function(){ if(_sessionRole) resetSessionTimer(); }, true);
document.addEventListener("touchstart", function(){ if(_sessionRole) resetSessionTimer(); }, true);

// ============ SECURE RECRUIT ID ============
function generateSecureId(){
  var arr = new Uint8Array(16);
  crypto.getRandomValues(arr);
  return Array.from(arr).map(function(b){ return b.toString(16).padStart(2,"0"); }).join("");
}

// ============ SECURE PORTAL ACCESS CODE ============
function generateAccessCode(){
  // 12 random hex chars — e.g. "a3f9c2e1b047"
  var arr = new Uint8Array(6);
  crypto.getRandomValues(arr);
  return Array.from(arr).map(function(b){ return b.toString(16).padStart(2,"0"); }).join("");
}

let recruits = JSON.parse(localStorage.getItem("nh_recruits") || "[]");
let currentRecruit = null;
let quizAnswers = [];
let currentQ = 0;
let selectedDate = null;
let selectedTime = null;
let calYear, calMonth;
let portalSteps = null;

const now = new Date();
calYear = now.getFullYear();
calMonth = now.getMonth();
const minBookDate = new Date(2026, 4, 23); // May 23 2026 — available from today

const questions = [
  {
    q: "Let's say you had to get 30 no's before you could get to a yes. How would you handle that rejection?",
    opts: ["I trust the process and stay consistent", "I reassess my approach and keep going", "I start to doubt if it is worth it", "I am already looking for something else"]
  },
  {
    q: "What does success mean to you and how badly do you actually want it?",
    opts: null,
    type: "text",
    placeholder: "Share your answer in at least one sentence..."
  },
  {
    q: "What is your why? Why do you want to do this?",
    opts: null,
    type: "text",
    placeholder: "Share in 2 to 3 sentences. Be real — this is what matters most."
  },
  {
    q: "Are you eventually able to put in 10–12 hours a day, Monday through Saturday, to building your own business?",
    opts: ["Yes, absolutely — I'm ready to commit", "Maybe — I need to think about it", "No, I can't commit to that right now"],
    type: "commitment",
    note: "If you have school or other commitments, that's okay — as long as you're working towards this full time."
  }
];

const qLabels = [
  "3 weeks in, no results — mindset?",
  "What does success mean to you?",
  "What is your why?",
  "Availability commitment"
];

const qOpts = [
  ["I trust the process and stay consistent", "I reassess my approach and keep going", "I start to doubt if it is worth it", "I am already looking for something else"],
  null,
  null,
  ["Yes, absolutely — I'm ready to commit", "Maybe — I need to think about it", "No, I can't commit to that right now"]
];

const stepsData = [
  {phase:"PRE-EXAM",title:"Book Your Exam",status:"Start Here",content:"Follow these steps exactly to book your state life insurance licensing exam:<br><br><div class='substep'><span class='substep-num'>1</span><span><strong>Find your state's info sheet</strong> — Click the link below, find your state, and click on its <strong>Info Sheet</strong>.<br><br><a href='https://email.no-reply.a4aleadshub.com/c/eJx0k0-TqjoQxT8N7JhKQkBYZKF3xD-jo8xz_vg2VkgaRSDJDRF0Pv0rfbde3cV92-4-fap-3UccKskM1zjO3y72kyKx3s0AwasvGY_4KE2wL3XLK8WUDiyY5vbEKW-Ay-50KZ6Ebn_1D3pQYLtTZQ7uZoDxIyhxe1SlDwyPohFCMY1SH1peNYcWuo4f4e7f6-2toWU2NZrPF5NVFtfDr6nHqkHbumz077W7jCARFzhNg4iSIqAp8IAjEQdYQCxRlOKEit8lnQPz0FGIRiklAcFJFNAU0YDjMg4IwglFAhckwT6ovrJataAcM1bLi3CVVv6JUVKEJZSUxxElZcjDgmKMAUIZIZkksV8xgkiEUkTxiKAofYKowCOKIQXMBSljj6L_Zdmwk3Om88KxRzKPZFKL7umo9bGBe98jWWfsQwDguvuARzIss2653qJ3kNnJnPmg5G4cfTRz2dadmm_m6XRvEid-rDa5RzKQlfNIeKykFz4jvxGHfyFVyoFVvGHvJOvk7KP-wunEzs-8lhNK9srsxy8nUu2L73S99kh2azf7_rrQu3x_-fp-r1-P5D3ha-GRLN_0nUnWy-VQaOWR7JvTzCOTv6YLO12MqTHH60_Qq2xJ-tnR8kv94yVXYZ7_XKRD8qXzxeTWbofc5G_4i0yHUE0L9emRiWuGIt3WdTJXqvfIBA238999uSJwnUb4OkNJtkYr6ISekeeFy7fPH-00yd_k1iPZS0PVbge1Uvskn9Ly1ZjTJlxePrefu-H8cl4IL3z2G_3IRGgTXubLcFw4dFNoVyXo6rfgTloybirfWN1XEiy7n09opUA4bX3LeNNBqbXyKDresT7O2umLFcAenIOq64P7S4P1HQN3-O-9Hbub_9HZMaHbwx-D2jPyTwAAAP__0K9B-Q' target='_blank' style='font-weight:400;font-size:14px'>→ Click HERE to find your state</a></span></div><br><div class='substep'><span class='substep-num'>2</span><span><strong>Open the Info Sheet</strong> — On that page, click the <strong>Info Sheet link</strong> for your state. It will take you to <strong>Xcel Solutions</strong>.</span></div><br><div class='substep'><span class='substep-num'>3</span><span><strong>Schedule your exam</strong> — On the Xcel Solutions page, scroll down to the <strong>2nd step</strong> that says <em>\"Schedule State Examination\"</em> and click the link.</span></div><br><div class='substep'><span class='substep-num'>4</span><span><strong>Select your exam</strong> — On the scheduling site, make sure you select the <strong>Life Exam</strong>. Pick a date at least <strong>2 weeks + 2 days from today</strong>.</span></div><br><div class='substep'><span class='substep-num'>5</span><span><strong>Take a screenshot</strong> of your exam confirmation and save it — you'll need it for the next step.</span></div><br><div class='wait-notice'>✅ Once booked, mark this step complete to unlock Step 2 where you'll email your confirmation.</div>",completable:true,adminUnlock:false},
  {phase:"",title:"Email Your Exam Confirmation",status:"Action Required",content:"Email your exam confirmation screenshot directly to Nansi:<br><br><strong><a href='mailto:alsefoon@gmail.com'>alsefoon@gmail.com</a></strong><br><br>Subject: <strong>EXAM CONFIRMATION – [Your Full Name]</strong><br><br>Attach your confirmation screenshot. Once sent, mark this step complete and wait for Nansi to unlock Step 3.",completable:true,adminUnlock:false},
  {phase:"",title:"Wait for Admin Response",status:"Pending Review",content:"Your confirmation has been sent. Nansi will review it and unlock your next step.<br><br><div class='wait-notice'>⏳ This step is unlocked by your admin — sit tight!</div>",completable:false,adminUnlock:true},
  {phase:"STUDYING",title:"Log Into the Free Course",status:"Access Your Training",content:"Your free course access has been approved. Log in using the details Nansi sent you and confirm you can access the material.<br><br>Once you're in, mark this step complete.",completable:true,adminUnlock:false},
  {phase:"",title:"Study — Main Material",status:"Hit the Books",content:"Go through every module in your course. Take notes. Watch every video. Don't skip anything.<br><br>When you feel confident you've covered the material, mark this step complete.",completable:true,adminUnlock:false},
  {phase:"",title:"Study Extra Quizlets",status:"Extra Prep",content:"Drill these flashcard sets until you know them cold:<br><br>📚 <a href='https://quizlet.com/244799365/life-insurance-practice-exam-flash-cards/' target='_blank'><strong>Life Insurance Practice Exam Flash Cards</strong></a><br><br>📚 <a href='https://quizlet.com/416762772/life-insurance-exam-questions-flash-cards/' target='_blank'><strong>Life Insurance Exam Questions</strong></a><br><br>📚 <a href='https://quizlet.com/162655458/life-insurance-practice-test-questions-flash-cards/' target='_blank'><strong>Life Insurance Practice Test Questions</strong></a><br><br>Once you feel ready, mark this step complete.",completable:true,adminUnlock:false},
  {phase:"POST-EXAM",title:"Take Your Exam",status:"Exam Day",content:"You're ready. Show up early. Bring a valid government-issued photo ID. Stay calm — you've put in the work.<br><br>After you <strong>pass</strong>, come back here and mark this step complete.",completable:true,adminUnlock:false},
  {phase:"",title:"Send Your Pass Results to Admin",status:"Action Required",content:"Congratulations on passing! Now email Nansi your proof:<br><br><strong><a href='mailto:alsefoon@gmail.com'>alsefoon@gmail.com</a></strong><br><br>Subject: <strong>PASSED – [Your Full Name]</strong><br><br>Attach a <strong>screenshot of your license or passing score</strong>. Once sent, mark complete.",completable:true,adminUnlock:false},
  {phase:"",title:"Admin Verifies Your Results",status:"Under Review",content:"Nansi is reviewing your pass results. Once verified, you'll receive your next-level course password.<br><br><div class='wait-notice'>⏳ This step is unlocked by your admin — hang tight, you're almost there!</div>",completable:false,adminUnlock:true},
  {phase:"",title:"Receive Your Course Password",status:"Access Granted",content:"Your course password has been sent by Nansi. Use it to access your next-level training and the full agent portal.<br><br><strong>Welcome to the team — officially. 🖤</strong>",completable:true,adminUnlock:false},
  {phase:"",title:"Get Contracted with Carrier",status:"Final Step",content:"You're licensed and trained — now it's time to get contracted with your carrier so you can start writing business.<br><br>Nansi will provide your Discord and WhatsApp community links once you're contracted.<br><br><strong>The journey starts now.</strong>",completable:true,adminUnlock:false}
];

function fmtTime(s){if(!isFinite(s)||isNaN(s))return "0:00";return Math.floor(s/60)+":"+String(Math.floor(s%60)).padStart(2,"0")}

// Returns true if an appointment string like "Friday, May 23, 2026 at 3:00 PM" is in the past
function isApptPast(apptStr){
  if(!apptStr) return false;
  try {
    var parts = apptStr.split(" at ");
    var dateStr = parts[0];
    var timeStr = parts[1] || "11:59 PM";
    var dt = new Date(dateStr + " " + timeStr);
    return dt < new Date();
  } catch(e){ return false; }
}

// Auto-clear past appointments from Firebase + local and mark recruit back to "applied"
function autoClearPastAppointments(){
  var changed = false;
  recruits.forEach(function(r){
    if(r.appt && isApptPast(r.appt)){
      r.appt = null;
      changed = true;
      // Sync to Firebase
      if(window._db && r._firebaseId){
        window._fbUpdateDoc(window._fbDoc(window._db,"recruits",r._firebaseId),{appt:null}).catch(function(e){console.error("Firebase clear appt error:",e)});
      }
    }
  });
  if(changed) saveRecruits();
  return changed;
}

function showPage(name){
  document.querySelectorAll(".page").forEach(function(p){p.classList.remove("active")});
  var el = document.getElementById("page-"+name);
  if(el) el.classList.add("active");
  var banner = document.getElementById("bottom-banner");
  if(banner) banner.style.display = (name==="landing") ? "block" : "none";
  var overlay = document.getElementById("landing-bg-overlay");
  if(overlay){
    overlay.style.display = (name==="landing") ? "block" : "none";
    if(name==="landing") positionOverlay();
  }
  if(name === "calendar"){
    setTimeout(function(){ renderCalendar(); }, 100);
  }
}

function positionOverlay(){
  var overlay = document.getElementById("landing-bg-overlay");
  var nav = document.querySelector("#page-landing .top-nav");
  var banner = document.getElementById("bottom-banner");
  if(!overlay||!nav||!banner) return;
  var navBottom = nav.getBoundingClientRect().bottom + window.scrollY;
  var bannerTop = window.innerHeight - banner.offsetHeight;
  overlay.style.top = navBottom + "px";
  overlay.style.left = "0";
  overlay.style.right = "0";
  overlay.style.bottom = banner.offsetHeight + "px";
  overlay.style.height = "auto";
}

window.addEventListener("resize", positionOverlay);
window.addEventListener("load", function(){ if(document.getElementById("page-landing").classList.contains("active")) positionOverlay(); });

// Auto-redirect to Team Login if URL has ?login=team
// Auto-unlock step 3 if URL has ?unlock=RECRUITID
(function(){
  var params = new URLSearchParams(window.location.search);
  if(params.get("login") === "team") showPage("portal-login");
  // ?unlock=FIREBASE_DOC_ID — uses the opaque Firebase document ID (not the numeric recruit ID)
  var unlockFirebaseId = params.get("unlock");
  if(unlockFirebaseId && window._db && /^[a-zA-Z0-9]{10,30}$/.test(unlockFirebaseId)){
    setTimeout(function(){
      // Directly fetch by Firebase document ID — much harder to guess than a timestamp
      var docRef = window._fbDoc(window._db,"recruits",unlockFirebaseId);
      window._fbGetDocs(window._fbQuery(window._fbCollection(window._db,"recruits"),window._fbWhere("__name__","==",docRef))).then(function(snap){
        if(snap.empty){
          // Fallback: try getting directly
          return window._fbGetDocs(window._fbCollection(window._db,"recruits")).then(function(allSnap){
            allSnap.forEach(function(d){
              if(d.id === unlockFirebaseId){
                var r = {...d.data(), _firebaseId: d.id};
                doUnlockStep3(r, d.id);
              }
            });
          });
        }
        snap.forEach(function(d){
          var r = {...d.data(), _firebaseId: d.id};
          doUnlockStep3(r, d.id);
        });
      }).catch(function(e){
        // Fallback scan
        window._fbGetDocs(window._fbCollection(window._db,"recruits")).then(function(allSnap){
          allSnap.forEach(function(d){
            if(d.id === unlockFirebaseId){
              var r = {...d.data(), _firebaseId: d.id};
              doUnlockStep3(r, d.id);
            }
          });
        }).catch(function(e2){console.error("Unlock error:",e2)});
      });
    }, 2000);
  }
})();

function doUnlockStep3(r, firebaseDocId){
  var stepsKey = "nh_steps_"+r.id;
  var steps = JSON.parse(localStorage.getItem(stepsKey) || "null");
  if(!steps) steps = stepsData.map(function(s,i){return {completed:false,unlocked:i===0,open:false}});
  steps[2].unlocked = true;
  steps[2].open = true;
  localStorage.setItem(stepsKey, JSON.stringify(steps));
  window._fbUpdateDoc(window._fbDoc(window._db,"recruits",firebaseDocId),{step:2}).catch(function(e){});
  showToast("Step 3 unlocked for "+r.first+" "+r.last+" ✓");
}

function switchEliTab(tab){
  ["recruits"].forEach(function(t){
    var panel = document.getElementById("eli-tab-"+t+"-panel");
    var btn = document.getElementById("eli-tab-"+t);
    if(panel) panel.style.display = t===tab ? "block" : "none";
    if(btn){
      btn.style.background = t===tab ? "var(--dark)" : "transparent";
      btn.style.color = t===tab ? "var(--cream)" : "var(--taupe)";
      btn.style.borderBottom = t===tab ? "2px solid var(--gold)" : "2px solid transparent";
    }
  });
  if(tab==="inbox") return;
}

function eliLogin(){
  if(!checkRateLimit("eli")) return;
  var pw = document.getElementById("eli-pw").value;
  document.getElementById("eli-err").style.display="none";
  hashInput(pw).then(function(hash){
    if(hash === ELI_HASH){
      resetAttempts("eli");
      document.getElementById("eli-pw").value = "";
      if(window._db){
        window._fbGetDocs(window._fbCollection(window._db,"recruits")).then(function(snap){
          recruits = [];
          snap.forEach(function(d){ recruits.push({...d.data(), _firebaseId: d.id}); });
          saveRecruits();
          startSession("eli");
          showPage("eli-admin");
          renderEliAdmin();
        }).catch(function(e){ startSession("eli"); showPage("eli-admin"); renderEliAdmin(); });
      } else { startSession("eli"); showPage("eli-admin"); renderEliAdmin(); }
    } else {
      recordFailedAttempt("eli");
      document.getElementById("eli-err").style.display="block";
    }
  });
}

function renderEliAdmin(){
  document.getElementById("eli-date").textContent = new Date().toLocaleDateString("en-US",{weekday:"long",year:"numeric",month:"long",day:"numeric"});
  var table = document.getElementById("eli-table");
  var stepNames = ["Book Exam","Email Confirmation","Waiting on Admin","Log Into Course","Study Main Material","Study Quizlets","Take Exam","Send Pass Results","Admin Verifying","Receive Password","Get Contracted"];
  if(!recruits.length){
    table.innerHTML = "<div style='padding:40px;text-align:center;font-size:14px;color:var(--taupe);font-style:italic;font-family:Cormorant Garamond,serif'>No recruits yet.</div>";
    return;
  }
  table.innerHTML = recruits.map(function(r,i){
    var prog = r.portalProgress || 0;
    var stepLabel = r.recruited ? (prog >= 11 ? "✓ All Done" : "Step "+(prog+1)+": "+(stepNames[prog]||"")) : "Not Yet Recruited";
    var rowBg = i%2===0 ? "var(--cream)" : "var(--cream2)";
    return "<div style='display:grid;grid-template-columns:2fr 2fr 1fr 1fr 1fr;padding:14px 20px;border-bottom:1px solid var(--border);align-items:center;background:"+rowBg+"'><div><div style='font-family:Cormorant Garamond,serif;font-size:16px;color:var(--beige-bright)'>"+r.first+" "+r.last+"</div><div style='font-size:10px;color:var(--taupe);margin-top:2px'>"+(r.date||"")+"</div></div><div style='font-size:12px;color:var(--beige)'>"+r.email+"</div><div style='font-size:12px;color:var(--beige)'>"+r.phone+"</div><div style='font-size:12px;color:var(--beige)'>"+r.state+"</div><div style='font-size:11px;color:var(--gold2)'>"+stepLabel+"</div></div>";
  }).join("");
}

function goToQuiz(){initQuiz();showPage("quiz")}
function toggleHowItWorks(){
  var section=document.getElementById("how-it-works-section");
  var btn=document.getElementById("how-it-works-btn");
  if(section.style.display==="none"){
    section.style.display="block";
    btn.textContent="How It Works ↑";
    section.scrollIntoView({behavior:"smooth",block:"start"});
  } else {
    section.style.display="none";
    btn.textContent="How It Works ↓";
  }
}

function initQuiz(){quizAnswers=[];currentQ=0;renderQuestion()}

function renderQuestion(){
  var q = questions[currentQ];
  document.getElementById("quiz-q-num").textContent = "Question "+(currentQ+1)+" of "+questions.length;
  document.getElementById("quiz-question").textContent = q.q;
  var opts = document.getElementById("quiz-options");
  opts.innerHTML = "";
  var next = document.getElementById("quiz-next");
  next.classList.remove("visible");
  next.textContent = currentQ === questions.length-1 ? "See Results" : "Next";

  if(q.type === "text"){
    var ta = document.createElement("textarea");
    ta.id = "quiz-text-answer";
    ta.placeholder = q.placeholder || "Share your answer...";
    ta.style.cssText = "width:100%;min-height:110px;background:#faf7f2;border:1px solid #e8ddd2;color:#2a2018;padding:14px;font-family:Cormorant Garamond,serif;font-size:16px;outline:none;resize:none;line-height:1.6;transition:border-color .2s";
    var minChars = 10;
    ta.oninput = function(){
      quizAnswers[currentQ] = this.value.trim();
      if(this.value.trim().length > minChars){next.classList.add("visible")}
      else{next.classList.remove("visible")}
    };
    opts.appendChild(ta);
    var hint = document.createElement("p");
    hint.style.cssText = "font-size:10px;color:#9a8878;margin-top:8px;letter-spacing:.1em;font-style:italic";
    hint.textContent = "At least one sentence required to continue";
    opts.appendChild(hint);
  } else if(q.type === "commitment"){
    q.opts.forEach(function(o,i){
      var btn = document.createElement("button");
      btn.className = "quiz-opt";
      btn.textContent = o;
      btn.onclick = function(){
        selectOpt(btn,i);
        // Save Yes/No as readable text immediately
        if(i===0) quizAnswers[currentQ] = "Yes, absolutely — I'm ready to commit";
        if(i===2) quizAnswers[currentQ] = "No, I can't commit to that right now";
        // Show/hide maybe box
        var maybeBox = document.getElementById("maybe-inline-box");
        if(maybeBox) maybeBox.style.display = i===1 ? "block" : "none";
        if(i!==1){
          var mt = document.getElementById("maybe-text");
          if(mt) mt.value = "";
        }
      };
      opts.appendChild(btn);
    });

    // Inline maybe box — hidden by default
    var maybeBox = document.createElement("div");
    maybeBox.id = "maybe-inline-box";
    maybeBox.style.cssText = "display:none;margin-top:20px;border:1px solid var(--gold);background:var(--cream);padding:20px;animation:fadeIn .3s ease";
    maybeBox.innerHTML = "<p style='font-family:Cormorant Garamond,serif;font-size:19px;font-weight:600;color:var(--dark);margin-bottom:6px;line-height:1.4'>Explain more about your situation — how much time can you put in?</p><p style='font-size:11px;font-weight:400;letter-spacing:.12em;text-transform:uppercase;color:var(--gold2);margin-bottom:14px'>Keep in mind this is full time.</p><textarea id='maybe-text' placeholder='Tell us about your current situation...' style='width:100%;min-height:90px;background:#faf7f2;border:1px solid #e8ddd2;color:#2a2018;padding:14px;font-family:Cormorant Garamond,serif;font-size:15px;outline:none;resize:none;line-height:1.6;transition:border-color .2s' oninput='quizAnswers[currentQ]=\"Maybe: \"+this.value.trim();'></textarea><p style='font-size:10px;color:#9a8878;margin-top:6px;font-style:italic;letter-spacing:.08em'>Required — must answer to continue</p>";
    opts.appendChild(maybeBox);

    if(q.note){
      var noteEl = document.createElement("p");
      noteEl.style.cssText = "font-size:14px;color:var(--taupe);margin-top:18px;font-style:italic;font-family:Cormorant Garamond,serif;line-height:1.7;text-align:center";
      noteEl.textContent = q.note;
      opts.appendChild(noteEl);
    }
  } else {
    q.opts.forEach(function(o,i){
      var btn = document.createElement("button");
      btn.className = "quiz-opt";
      btn.textContent = o;
      btn.onclick = function(){selectOpt(btn,i)};
      opts.appendChild(btn);
    });
  }

  var prog = document.getElementById("quiz-progress");
  prog.innerHTML = "";
  questions.forEach(function(_,i){
    var d = document.createElement("div");
    d.className = "qp-dot"+(i<currentQ?" done":i===currentQ?" active":"");
    prog.appendChild(d);
  });
}

function selectOpt(btn,idx){
  document.querySelectorAll(".quiz-opt").forEach(function(b){b.classList.remove("selected")});
  btn.classList.add("selected");
  quizAnswers[currentQ] = idx;
  document.getElementById("quiz-next").classList.add("visible");
}

function nextQuestion(){
  if(quizAnswers[currentQ]===undefined && questions[currentQ].type!=="text" && questions[currentQ].type!=="availability") return;

  // If commitment question
  if(questions[currentQ].type === "commitment"){
    if(quizAnswers[currentQ] === 2){
      showPage("not-a-fit");
      return;
    }
    if(quizAnswers[currentQ] === 1 || (typeof quizAnswers[currentQ] === "string" && quizAnswers[currentQ].startsWith("Maybe:"))){
      var maybeText = document.getElementById("maybe-text");
      if(!maybeText || maybeText.value.trim().length < 10){
        if(maybeText) maybeText.style.borderColor = "var(--gold)";
        maybeText && maybeText.focus();
        return;
      }
      quizAnswers[currentQ] = "Maybe: " + maybeText.value.trim();
    }
  }

  currentQ++;
  if(currentQ >= questions.length){
    var lastOptCount = quizAnswers.filter(function(a){return a===3}).length;
    if(lastOptCount >= 3){showPage("not-a-fit")}
    else{showPage("form")}
  }
  else{renderQuestion()}
}

function submitForm(){
  var first = document.getElementById("f-first").value.trim();
  var last = document.getElementById("f-last").value.trim();
  var email = document.getElementById("f-email").value.trim();
  var phone = document.getElementById("f-phone").value.trim();
  var state = document.getElementById("f-state").value;
  var instagram = document.getElementById("f-instagram").value.trim().replace(/^@/,"");
  if(!first||!last||!email||!phone||!state){showToast("Please fill in all fields");return}
  currentRecruit = {id:generateSecureId(),first:first,last:last,email:email,phone:phone,state:state,instagram:instagram,rank:"B",recruited:false,step:0,date:new Date().toLocaleDateString(),quizAnswers:quizAnswers.slice(),appt:null,accessCode:null};
  recruits.push(currentRecruit);
  saveRecruits();
  // Save to Firebase
  if(window._db){
    window._fbAddDoc(window._fbCollection(window._db,"recruits"), currentRecruit).then(function(docRef){
      currentRecruit._firebaseId = docRef.id;
    }).catch(function(e){console.error("Firebase save error:",e)});
  }
  showPage("calendar");
}

function getAnswerText(qIdx, answerVal){
  // If the answer is already a string (text answer or maybe explanation), return it directly
  if(typeof answerVal === "string") return answerVal || "—";
  if(qOpts[qIdx] === null) return answerVal || "—";
  return qOpts[qIdx][answerVal] || "—";
}

function toggleRecruit(i){
  var el = document.getElementById("recruit-detail-"+i);
  if(el) el.style.display = el.style.display === "none" ? "block" : "none";
}

function renderAdmin(){
  autoClearPastAppointments();
  document.getElementById("admin-date").textContent = new Date().toLocaleDateString("en-US",{weekday:"long",year:"numeric",month:"long",day:"numeric"});
  document.getElementById("stat-total").textContent = recruits.length;
  document.getElementById("stat-booked").textContent = recruits.filter(function(r){return r.appt && !isApptPast(r.appt)}).length;
  document.getElementById("stat-recruited").textContent = recruits.filter(function(r){return r.recruited}).length;
  filterTable(currentFilter);
}

var currentFilter = 'all';
function filterTable(filter){
  currentFilter = filter;
  var filtered = recruits.slice();
  if(filter==='booked') filtered = recruits.filter(function(r){return r.appt && !isApptPast(r.appt)});
  if(filter==='recruited') filtered = recruits.filter(function(r){return r.recruited});
  // Sort newest at top, oldest at bottom
  filtered.sort(function(a,b){ return (b.id||0) - (a.id||0); });
  var table = document.getElementById("recruit-table");
  if(!filtered.length){
    table.innerHTML = "<div style='padding:40px;text-align:center;font-size:14px;color:var(--beige);font-style:italic;font-family:Cormorant Garamond,serif'>No recruits yet. They will appear here once they apply.</div>";
    return;
  }
  table.innerHTML = filtered.map(function(r,i){
    var realIdx = recruits.indexOf(r);
    var answers = qLabels.map(function(label,qi){
      return "<div style='padding:12px 16px;background:var(--cream2);border:1px solid var(--border);margin-bottom:8px'><div style='font-size:9px;font-weight:300;letter-spacing:.15em;text-transform:uppercase;color:var(--gold2);margin-bottom:6px'>"+label+"</div><div style='font-family:Cormorant Garamond,serif;font-size:16px;color:var(--beige);font-style:italic'>"+(r.quizAnswers&&r.quizAnswers[qi]!==undefined?getAnswerText(qi,r.quizAnswers[qi]):"Not answered")+"</div></div>";
    }).join("");

    var rowBg = realIdx%2===0 ? "var(--cream)" : "var(--cream2)";
    return "<div style='border-bottom:1px solid var(--border)'><div class='recruit-row' onclick='toggleRecruit("+realIdx+")' style='cursor:pointer;background:"+rowBg+"'><div><div class='recruit-name' style='color:var(--beige-bright)'>"+r.first+" "+r.last+"</div><div class='recruit-email' style='color:var(--gold2)'>"+r.email+"</div><div class='recruit-email' style='color:var(--taupe);font-size:10px'>"+(r.date||"")+"</div></div><div><div class='recruit-contact' style='color:var(--beige)'>"+r.phone+"</div><div class='recruit-contact' style='margin-top:3px;color:var(--beige)'>"+r.state+"</div>"+(r.instagram?"<div class='recruit-contact' style='margin-top:4px'><a href='https://instagram.com/"+r.instagram+"' target='_blank' style='display:inline-flex;align-items:center;gap:5px;color:var(--gold2);text-decoration:none;font-size:10px;letter-spacing:.05em;transition:color .2s' onmouseover='this.style.color=\"var(--beige)\"' onmouseout='this.style.color=\"var(--gold2)\"'><svg width='11' height='11' viewBox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='1.8'><rect x='2' y='2' width='20' height='20' rx='5'/><circle cx='12' cy='12' r='4'/><circle cx='17.5' cy='6.5' r='1' fill='currentColor' stroke='none'/></svg>@"+r.instagram+"</a></div>":"")+"<div class='recruit-contact' style='margin-top:3px'>"+(r.appt ? (isApptPast(r.appt) ? "<span style='color:var(--taupe);font-size:10px'>📋 Past Appointment: "+r.appt+"</span>" : "<span style='color:var(--gold)'>✓ Booked: "+r.appt+"</span>") : "<span style='color:var(--taupe);font-size:10px'>No appointment booked</span>")+"</div></div><div><select class='rank-select' onchange='setRank("+realIdx+",this.value)' onclick='event.stopPropagation()' style='color:var(--beige);background:var(--cream2);border:1px solid var(--border)'><option "+(r.rank==="A"?"selected":"")+" value='A'>A</option><option "+(r.rank==="B"?"selected":"")+" value='B'>B</option><option "+(r.rank==="C"?"selected":"")+" value='C'>C</option></select></div><div style='font-size:11px;color:var(--gold2);font-weight:300'>"+(function(){var prog=r.portalProgress||0;var total=11;var steps=["Book Exam","Email Confirmation","Waiting on Admin","Log Into Course","Study Main Material","Study Quizlets","Take Exam","Send Pass Results","Admin Verifying","Receive Password","Get Contracted"];var label=prog>=total?"✓ All Done":("Step "+(prog+1)+"/"+total+": "+(steps[prog]||""));return label;}())+"</div><div style='display:flex;flex-direction:column;gap:6px'><select class='rank-select' onchange='setRecruitStatus("+realIdx+",this.value)' onclick='event.stopPropagation()' style='min-width:130px;background:"+(r.recruited?"var(--gold)":"var(--cream2)")+";color:"+(r.recruited?"#fff":"var(--beige)")+";border:1px solid "+(r.recruited?"var(--gold)":"var(--border)")+"'><option value='unrecruited' "+(r.recruited?"":"selected")+">Unrecruited</option><option value='recruited' "+(r.recruited?"selected":"")+">✓ Recruited</option></select>"+(r.step===2||r.step===8?"<button class='recruited-btn' style='background:var(--gold);color:#fff;border:none;margin-top:4px;font-weight:400' onclick='event.stopPropagation();adminUnlockStep("+realIdx+")'>🔓 Unlock Step "+((r.step||0)+1)+"</button>":"")+"<button class='recruited-btn' style='background:transparent;color:#c04040;border:1px solid rgba(192,64,64,0.35);margin-top:4px;font-size:8px;letter-spacing:.18em' onclick='event.stopPropagation();deleteRecruit("+realIdx+")'>Remove</button>"+"</div><div style='color:var(--gold2);font-size:12px'>View Answers</div></div><div id='recruit-detail-"+realIdx+"' style='display:none;padding:24px 20px;background:var(--cream2);border-top:1px solid var(--border)'><p style='font-size:8px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;color:var(--gold2);margin-bottom:16px'>Quiz Answers</p>"+answers+"</div></div>";
  }).join("");
}

function switchAdminTab(tab){
  ["recruits","pipeline","calendar"].forEach(function(t){
    var panel = document.getElementById("admin-tab-"+t);
    var btn = document.getElementById("tab-"+t);
    if(panel) panel.style.display = t===tab ? "block" : "none";
    if(btn){
      btn.style.background = t===tab ? "var(--dark)" : "transparent";
      btn.style.color = t===tab ? "var(--cream)" : "var(--taupe)";
      btn.style.borderBottom = t===tab ? "2px solid var(--gold)" : "2px solid transparent";
    }
  });
  if(tab==="pipeline") renderPipeline();
  if(tab==="calendar"){ autoClearPastAppointments(); renderAdminCalendar(); renderAdmin(); }
}

function renderAdminCalendar(){
  autoClearPastAppointments();
  var el = document.getElementById("admin-calendar-view");
  if(!el) return;

  // Get upcoming (non-past) booked recruits sorted by appointment date
  var booked = recruits.filter(function(r){ return r.appt && !isApptPast(r.appt); }).slice();
  booked.sort(function(a,b){
    return new Date(a.appt) - new Date(b.appt);
  });

  if(!booked.length){
    el.innerHTML = "<div style='padding:60px;text-align:center;font-family:Cormorant Garamond,serif;font-size:20px;font-style:italic;color:var(--taupe)'>No upcoming appointments.</div>";
    return;
  }

  // Group by date string
  var groups = {};
  var order = [];
  booked.forEach(function(r){
    var parts = r.appt.split(" at ");
    var dateKey = parts[0] || r.appt;
    if(!groups[dateKey]){ groups[dateKey]=[]; order.push(dateKey); }
    groups[dateKey].push(r);
  });

  var container = document.createElement("div");
  container.style.cssText = "max-width:700px";

  var header = document.createElement("p");
  header.style.cssText = "font-size:9px;font-weight:300;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:24px";
  header.textContent = booked.length + " Upcoming Appointment" + (booked.length!==1?"s":"");
  container.appendChild(header);

  order.forEach(function(dateKey){
    var dateGroup = document.createElement("div");
    dateGroup.style.cssText = "margin-bottom:28px";

    var dateHeader = document.createElement("div");
    dateHeader.style.cssText = "font-family:Cormorant Garamond,serif;font-size:22px;color:var(--dark);margin-bottom:10px;padding-bottom:8px;border-bottom:1px solid var(--border)";
    dateHeader.textContent = dateKey;
    dateGroup.appendChild(dateHeader);

    groups[dateKey].forEach(function(r){
      var parts = r.appt.split(" at ");
      var time = parts[1] || "";

      var row = document.createElement("div");
      row.style.cssText = "display:flex;align-items:center;justify-content:space-between;padding:14px 18px;background:var(--cream);border:1px solid var(--border);margin-bottom:6px;cursor:pointer;transition:border-color .2s,background .2s";
      row.onmouseover = function(){ this.style.borderColor="var(--gold)"; this.style.background="var(--cream2)"; };
      row.onmouseout = function(){ this.style.borderColor="var(--border)"; this.style.background="var(--cream)"; };
      row.onclick = function(){ showProfilePopup(r); };

      var left = document.createElement("div");
      left.style.cssText = "display:flex;align-items:center;gap:16px";

      var timeEl = document.createElement("div");
      timeEl.style.cssText = "font-family:Cormorant Garamond,serif;font-size:15px;font-weight:600;color:var(--gold);min-width:70px";
      timeEl.textContent = time;

      var info = document.createElement("div");
      var nameEl = document.createElement("div");
      nameEl.style.cssText = "font-family:Cormorant Garamond,serif;font-size:18px;color:var(--dark)";
      nameEl.textContent = r.first + " " + r.last;
      var contactEl = document.createElement("div");
      contactEl.style.cssText = "font-size:10px;color:var(--taupe);margin-top:2px";
      contactEl.textContent = r.email + " · " + r.phone;
      info.appendChild(nameEl);
      info.appendChild(contactEl);

      left.appendChild(timeEl);
      left.appendChild(info);

      var right = document.createElement("div");
      right.style.cssText = "display:flex;flex-direction:column;align-items:flex-end;gap:6px";
      var callLabel = document.createElement("div");
      callLabel.style.cssText = "font-size:9px;color:var(--gold2);letter-spacing:.1em;text-transform:uppercase";
      callLabel.textContent = "5 min call";
      var viewBtn = document.createElement("div");
      viewBtn.style.cssText = "font-size:9px;color:var(--taupe);letter-spacing:.08em;text-transform:uppercase;border:1px solid var(--border);padding:4px 10px;transition:all .2s";
      viewBtn.textContent = "View Profile";
      right.appendChild(callLabel);
      right.appendChild(viewBtn);

      row.appendChild(left);
      row.appendChild(right);
      dateGroup.appendChild(row);
    });

    container.appendChild(dateGroup);
  });

  el.innerHTML = "";
  el.appendChild(container);
}

function showProfilePopup(r){
  var existing = document.getElementById("profile-popup");
  if(existing) document.body.removeChild(existing);
  var popup = document.createElement("div");
  popup.id = "profile-popup";
  popup.style.cssText = "position:fixed;inset:0;background:rgba(0,0,0,0.6);z-index:9999;display:flex;align-items:center;justify-content:center;backdrop-filter:blur(4px)";
  var answers = qLabels.map(function(label,qi){
    return "<div style='padding:10px 14px;background:var(--cream2);border:1px solid var(--border);margin-bottom:6px'><div style='font-size:8px;font-weight:300;letter-spacing:.15em;text-transform:uppercase;color:var(--gold2);margin-bottom:4px'>"+label+"</div><div style='font-family:Cormorant Garamond,serif;font-size:15px;color:var(--beige);font-style:italic'>"+(r.quizAnswers&&r.quizAnswers[qi]!==undefined?getAnswerText(qi,r.quizAnswers[qi]):"Not answered")+"</div></div>";
  }).join("");
  popup.innerHTML = "<div style='background:var(--white);border:1px solid var(--border);padding:36px;max-width:500px;width:90%;max-height:85vh;overflow-y:auto'><div style='display:flex;justify-content:space-between;align-items:center;margin-bottom:24px'><div><div style='font-family:Cormorant Garamond,serif;font-size:28px;color:var(--beige-bright)'>"+r.first+" "+r.last+"</div><div style='font-size:10px;color:var(--gold2);letter-spacing:.1em;margin-top:2px'>"+r.state+"</div></div><button onclick='document.body.removeChild(document.getElementById(\"profile-popup\"))' style='background:none;border:1px solid var(--border);color:var(--taupe);width:32px;height:32px;cursor:pointer;font-size:16px'>×</button></div><div style='display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:20px'><div style='padding:12px;background:var(--cream2);border:1px solid var(--border)'><div style='font-size:8px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe);margin-bottom:4px'>Email</div><div style='font-size:13px;color:var(--beige)'>"+r.email+"</div></div><div style='padding:12px;background:var(--cream2);border:1px solid var(--border)'><div style='font-size:8px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe);margin-bottom:4px'>Phone</div><div style='font-size:13px;color:var(--beige)'>"+r.phone+"</div></div>"+(r.instagram?"<div style='padding:12px;background:var(--cream2);border:1px solid var(--border)'><div style='font-size:8px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe);margin-bottom:4px'>Instagram</div><a href='https://instagram.com/"+r.instagram+"' target='_blank' style='font-size:13px;color:var(--gold2);text-decoration:none'>@"+r.instagram+"</a></div>":"")+(r.appt?"<div style='padding:12px;background:var(--cream2);border:1px solid var(--border)'><div style='font-size:8px;letter-spacing:.15em;text-transform:uppercase;color:var(--taupe);margin-bottom:4px'>Appointment</div><div style='font-size:13px;color:var(--gold)'>"+r.appt+"</div></div>":"")+"</div><p style='font-size:8px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;color:var(--gold2);margin-bottom:12px'>Quiz Answers</p>"+answers+"</div>";
  document.body.appendChild(popup);
}

function renderPipeline(){
  var allStages = [
    {key:"Applied", label:"Applied", color:"var(--taupe)"},
    {key:"Booked a Call", label:"Booked Call", color:"var(--gold2)"},
    {key:"Step 1 — Book Exam", label:"Book Exam", color:"var(--dark)"},
    {key:"Step 2 — Email Confirmation", label:"Email Confirm.", color:"var(--dark)"},
    {key:"Step 3 — Waiting on Admin", label:"Waiting Admin", color:"var(--dark)"},
    {key:"Step 4 — Log Into Course", label:"Log In Course", color:"var(--dark)"},
    {key:"Step 5 — Study Main Material", label:"Study Material", color:"var(--dark)"},
    {key:"Step 6 — Study Quizlets", label:"Study Quizlets", color:"var(--dark)"},
    {key:"Step 7 — Take Exam", label:"Take Exam", color:"var(--dark)"},
    {key:"Step 8 — Send Pass Results", label:"Send Results", color:"var(--dark)"},
    {key:"Step 9 — Admin Verifying", label:"Admin Verify", color:"var(--dark)"},
    {key:"Step 10 — Receive Password", label:"Recv. Password", color:"var(--dark)"},
    {key:"Step 11 — Get Contracted", label:"Get Contracted", color:"var(--dark)"},
    {key:"✓ All Done", label:"All Done ✓", color:"var(--gold)"}
  ];
  var stages = {};
  allStages.forEach(function(s){ stages[s.key] = []; });
  var stepNames = ["Step 1 — Book Exam","Step 2 — Email Confirmation","Step 3 — Waiting on Admin","Step 4 — Log Into Course","Step 5 — Study Main Material","Step 6 — Study Quizlets","Step 7 — Take Exam","Step 8 — Send Pass Results","Step 9 — Admin Verifying","Step 10 — Receive Password","Step 11 — Get Contracted"];
  recruits.forEach(function(r){
    if(!r.recruited){
      if(r.appt && !isApptPast(r.appt)) stages["Booked a Call"].push(r);
      else stages["Applied"].push(r);
      return;
    }
    var prog = r.portalProgress || 0;
    if(prog >= 11){ stages["✓ All Done"].push(r); return; }
    stages[stepNames[prog] || "Step 1 — Book Exam"].push(r);
  });

  var el = document.getElementById("pipeline-view");

  // Selected stage state
  if(!window._pipelineSelected) window._pipelineSelected = null;

  function renderTiles(){
    el.innerHTML = "";

    // Tiles row
    var tilesRow = document.createElement("div");
    tilesRow.style.cssText = "display:flex;flex-wrap:wrap;gap:8px;margin-bottom:24px";
    allStages.forEach(function(s){
      var count = stages[s.key].length;
      var isSelected = window._pipelineSelected === s.key;
      var tile = document.createElement("div");
      tile.style.cssText = "padding:10px 14px;border:1px solid "+(isSelected?"var(--gold)":"var(--border)")+";background:"+(isSelected?"var(--cream2)":"var(--white)")+";cursor:pointer;transition:all .2s;min-width:100px;text-align:center";
      tile.innerHTML = "<div style='font-size:18px;font-family:Cormorant Garamond,serif;color:"+s.color+";font-weight:400'>"+count+"</div><div style='font-size:8px;letter-spacing:.12em;text-transform:uppercase;color:"+(isSelected?"var(--beige)":"var(--taupe)")+";margin-top:3px'>"+s.label+"</div>";
      tile.onmouseover = function(){ if(!isSelected) this.style.borderColor="var(--dark)"; };
      tile.onmouseout = function(){ if(!isSelected) this.style.borderColor="var(--border)"; };
      tile.onclick = function(){
        window._pipelineSelected = isSelected ? null : s.key;
        renderTiles();
      };
      tilesRow.appendChild(tile);
    });
    el.appendChild(tilesRow);

    // People panel
    if(window._pipelineSelected){
      var people = stages[window._pipelineSelected];
      var panel = document.createElement("div");
      panel.style.cssText = "border:1px solid var(--gold);background:var(--cream2);padding:20px";
      var stageInfo = allStages.find(function(s){return s.key===window._pipelineSelected});
      panel.innerHTML = "<p style='font-size:9px;font-weight:300;letter-spacing:.25em;text-transform:uppercase;color:var(--gold2);margin-bottom:16px'>"+(stageInfo?stageInfo.label:window._pipelineSelected)+"</p>";
      if(!people.length){
        panel.innerHTML += "<p style='font-family:Cormorant Garamond,serif;font-size:16px;font-style:italic;color:var(--taupe)'>No one in this stage yet.</p>";
      } else {
        var grid = document.createElement("div");
        grid.style.cssText = "display:flex;flex-wrap:wrap;gap:10px";
        people.forEach(function(r){
          var card = document.createElement("div");
          card.style.cssText = "padding:14px 18px;background:var(--white);border:1px solid var(--border);cursor:pointer;min-width:200px;transition:border-color .2s";
          card.onmouseover = function(){ this.style.borderColor="var(--gold)"; };
          card.onmouseout = function(){ this.style.borderColor="var(--border)"; };
          card.onclick = function(){ showProfilePopup(r); };
          card.innerHTML = "<div style='font-family:Cormorant Garamond,serif;font-size:17px;color:var(--beige-bright)'>"+r.first+" "+r.last+"</div><div style='font-size:10px;color:var(--gold2);margin-top:3px'>"+r.email+"</div><div style='font-size:10px;color:var(--taupe);margin-top:2px'>"+r.phone+"</div>"+(r.appt?"<div style='font-size:10px;color:var(--gold);margin-top:4px'>📅 "+r.appt+"</div>":"");
          grid.appendChild(card);
        });
        panel.appendChild(grid);
      }
      el.appendChild(panel);
    }
  }
  renderTiles();
}

function setRank(idx,val){recruits[idx].rank=val;saveRecruits();renderAdmin()}
function setRecruitStatus(idx,val){
  if(val==="recruited"){
    recruits[idx].recruited=true;
    var r=recruits[idx];
    // Generate a cryptographically random access code if not already set
    var code = r.accessCode && r.accessCode.length >= 12 ? r.accessCode : generateAccessCode();
    recruits[idx].accessCode = code;
    saveRecruits();
    renderAdmin();
    // Persist recruited + accessCode to Firebase in one write
    if(window._db && r._firebaseId){
      window._fbUpdateDoc(window._fbDoc(window._db,"recruits",r._firebaseId),{recruited:true,accessCode:code}).catch(function(e){console.error("Firebase update error:",e)});
    }
    var pass = code;
    emailjs.send("service_vjilj5a","template_kj4fvdx",{
      name: r.first,
      email: r.email,
      password: pass
    }).then(function(){
      showToast("Welcome email sent to "+r.first+" ✓");
    },function(err){
      showToast("Email failed — check EmailJS settings");
      console.error("EmailJS error:",err);
    });
  } else {
    recruits[idx].recruited=false;saveRecruits();renderAdmin();
    // Sync to Firebase
    if(window._db && recruits[idx]._firebaseId){
      window._fbUpdateDoc(window._fbDoc(window._db,"recruits",recruits[idx]._firebaseId),{recruited:false}).catch(function(e){console.error("Firebase update error:",e)});
    }
    showToast(recruits[idx].first+"'s access has been revoked");
  }
}
function adminUnlockStep(idx){recruits[idx].step=(recruits[idx].step||0)+1;saveRecruits();renderAdmin();showToast("Step unlocked for "+recruits[idx].first)}

function deleteRecruit(idx){
  var r = recruits[idx];
  if(!confirm("Delete " + r.first + " " + r.last + "? This cannot be undone.")) return;
  // Delete from Firebase
  if(window._db && r._firebaseId){
    window._fbDeleteDoc(window._fbDoc(window._db,"recruits",r._firebaseId)).catch(function(e){console.error("Delete error:",e)});
  }
  // Clear their portal steps from localStorage
  localStorage.removeItem("nh_steps_"+r.id);
  // Remove from local array
  recruits.splice(idx,1);
  saveRecruits();
  renderAdmin();
  showToast(r.first+" deleted ✓");
}

function deleteAllRecruits(){
  if(!confirm("Delete ALL applicants? This cannot be undone.")) return;
  // Clear Firebase
  if(window._db){
    window._fbGetDocs(window._fbCollection(window._db,"recruits")).then(function(snap){
      snap.forEach(function(d){
        window._fbDeleteDoc(window._fbDoc(window._db,"recruits",d.id)).catch(function(e){console.error("Delete error:",e)});
      });
    });
  }
  // Clear local
  recruits = [];
  localStorage.removeItem("nh_recruits");
  saveRecruits();
  renderAdmin();
  showToast("All applicants deleted ✓");
}

function adminLogin(){
  if(!checkRateLimit("admin")) return;
  var pw = document.getElementById("admin-pw").value;
  document.getElementById("admin-err").style.display="none";
  hashInput(pw).then(function(hash){
    if(hash === ADMIN_HASH){
      resetAttempts("admin");
      document.getElementById("admin-pw").value = "";
      if(window._db){
        window._fbGetDocs(window._fbCollection(window._db,"recruits")).then(function(snap){
          recruits = [];
          snap.forEach(function(d){ recruits.push({...d.data(), _firebaseId: d.id}); });
          saveRecruits();
          startSession("admin");
          showPage("admin");renderAdmin();
        }).catch(function(e){
          console.error("Firebase load error:",e);
          startSession("admin");
          showPage("admin");renderAdmin();
        });
      } else {
        startSession("admin");
        showPage("admin");renderAdmin();
      }
    } else {
      recordFailedAttempt("admin");
      document.getElementById("admin-err").style.display="block";
    }
  });
}

function portalLogin(){
  if(!checkRateLimit("portal")) return;
  var pw = document.getElementById("portal-pw").value.trim();
  document.getElementById("portal-err").style.display="none";

  // Check if it's the owner preview (admin password in portal)
  hashInput(pw).then(function(hash){
    if(hash === PORTAL_ADMIN_HASH){
      resetAttempts("portal");
      document.getElementById("portal-pw").value = "";
      currentRecruit = {first:"Nansi",last:"Hanna",email:"nansihanna.ffl@gmail.com",phone:"",state:"",rank:"A",recruited:true,step:0,id:"admin-preview"};
      startSession("portal");
      showPage("portal");initPortalSteps();renderPortal();
      return;
    }

    // Match against stored secure access code (accessCode field on recruit)
    var pwLower = pw.toLowerCase();
    var matched = recruits.find(function(r){
      return r.accessCode && pwLower === r.accessCode.toLowerCase() && r.recruited;
    });
    if(matched){
      resetAttempts("portal");
      document.getElementById("portal-pw").value = "";
      currentRecruit=matched;
      startSession("portal");
      showPage("portal");initPortalSteps();renderPortal();
      return;
    }

    // Fall back to Firebase lookup
    if(window._db){
      window._fbGetDocs(window._fbQuery(window._fbCollection(window._db,"recruits"),window._fbWhere("recruited","==",true))).then(function(snap){
        var fbMatched = null;
        snap.forEach(function(d){
          var r = {...d.data(), _firebaseId: d.id};
          var personal = r.first.toLowerCase()+r.last.toLowerCase()+'2026'; if((r.accessCode && pwLower === r.accessCode.toLowerCase()) || pwLower === personal) fbMatched = r;
        });
        if(fbMatched){
          resetAttempts("portal");
          document.getElementById("portal-pw").value = "";
          currentRecruit = fbMatched;
          var exists = recruits.find(function(r){return r.id === fbMatched.id});
          if(!exists) recruits.push(fbMatched);
          saveRecruits();
          startSession("portal");
          showPage("portal");initPortalSteps();renderPortal();
        } else {
          recordFailedAttempt("portal");
          document.getElementById("portal-err").style.display="block";
        }
      }).catch(function(e){
        console.error("Firebase login error:",e);
        recordFailedAttempt("portal");
        document.getElementById("portal-err").style.display="block";
      });
    } else {
      recordFailedAttempt("portal");
      document.getElementById("portal-err").style.display="block";
    }
  });
}

function initPortalSteps(){
  var saved = currentRecruit ? localStorage.getItem("nh_steps_"+currentRecruit.id) : null;
  portalSteps = saved ? JSON.parse(saved) : stepsData.map(function(s,i){return {completed:false,unlocked:i===0,open:false}});
  if(!saved) savePortalSteps();
}

function renderPortal(){
  var container = document.getElementById("step-container");
  container.innerHTML = "";
  // Count progress
  var done = portalSteps.filter(function(s){return s.completed}).length;
  var total = stepsData.length;
  var pct = Math.round((done/total)*100);
  // Progress bar
  var prog = document.getElementById("portal-progress");
  if(prog){
    prog.innerHTML = "<div style='display:flex;justify-content:space-between;align-items:center;margin-bottom:8px'><span style='font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;color:var(--taupe)'>Progress</span><span style='font-size:9px;font-weight:300;letter-spacing:.15em;color:var(--gold2)'>"+done+" / "+total+" Steps</span></div><div style='height:2px;background:var(--border);width:100%'><div style='height:2px;background:var(--gold);width:"+pct+"%;transition:width .5s'></div></div>";
  }
  // Find the index of the first unlocked-but-not-completed step
  var currentActive = -1;
  for(var ci=0;ci<portalSteps.length;ci++){
    if(portalSteps[ci].unlocked && !portalSteps[ci].completed){currentActive=ci;break;}
  }
  var lastPhase = "";
  stepsData.forEach(function(s,i){
    var state = portalSteps[i];
    // Phase label
    if(s.phase && s.phase !== lastPhase){
      lastPhase = s.phase;
      var phaseEl = document.createElement("div");
      phaseEl.style.cssText = "font-size:8px;font-weight:400;letter-spacing:.3em;text-transform:uppercase;color:var(--taupe);padding:18px 0 8px;border-top:1px solid var(--border);margin-top:4px";
      phaseEl.textContent = s.phase;
      container.appendChild(phaseEl);
    }
    var cls, statusText;
    if(state.completed){
      cls="step-item completed";
      statusText="✓ Completed";
    } else if(state.unlocked){
      cls="step-item unlocked";
      statusText=s.status;
    } else if(i === currentActive+1){
      cls="step-item next-up";
      statusText="Up Next — Locked";
    } else {
      cls="step-item locked";
      statusText="Locked";
    }
    var el = document.createElement("div");
    var canClick = (state.unlocked || state.completed) ? "onclick='toggleStep("+i+")' style='cursor:pointer'" : "";
    var lockBadge = (!state.unlocked && !state.completed) ? "<div style='color:var(--border);font-size:14px'>🔒</div>" : (state.completed ? "<div style='color:var(--gold);font-size:16px'>✓</div>" : "<div class='step-arrow'>›</div>");
    el.className = cls;
    el.innerHTML = "<div class='step-header' "+canClick+"><div class='step-num'>"+String(i+1).padStart(2,"0")+"</div><div class='step-title-wrap'><div class='step-title'>"+s.title+"</div><div class='step-status'>"+statusText+"</div></div>"+lockBadge+"</div>"+((state.unlocked||state.completed)?"<div class='step-body "+(state.open?"open":"")+"' id='step-body-"+i+"'><div class='step-content'>"+s.content+"</div>"+(state.unlocked&&!state.completed&&s.completable?"<button class='complete-step-btn' onclick='completeStep("+i+")'>Mark Complete ✓</button>":"")+(state.completed?"<button onclick='uncompleteStep("+i+")' style='margin-top:10px;padding:8px 20px;background:transparent;border:1px solid var(--border);color:var(--taupe);font-family:\"Inter\",sans-serif;font-size:9px;font-weight:300;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;transition:all .25s' onmouseover='this.style.borderColor=\"var(--dark)\";this.style.color=\"var(--dark)\"' onmouseout='this.style.borderColor=\"var(--border)\";this.style.color=\"var(--taupe)\"'>← Go Back</button>":"")+"</div>":"");
    container.appendChild(el);
  });
}

function toggleStep(i){
  if(!portalSteps[i].unlocked && !portalSteps[i].completed) return;
  portalSteps[i].open = !portalSteps[i].open;
  savePortalSteps();
  renderPortal();
}

function sendNansiNotification(subject, messageBody, recruitName){
  emailjs.send("service_vjilj5a", "template_kldk4r8", {
    name: "Elite Motional Portal — " + recruitName,
    subject: subject,
    message: messageBody,
    reply_to: "nansihanna.ffl@gmail.com"
  }).then(function(){
    console.log("Nansi notified: " + subject);
  }, function(err){
    console.error("EmailJS notification error:", err);
  });
}

function completeStep(i){
  portalSteps[i].completed = true;
  portalSteps[i].open = false;
  var next = i+1;
  if(next < stepsData.length){
    portalSteps[next].unlocked = true;
    if(!stepsData[next].adminUnlock) portalSteps[next].open = true;
  }
  savePortalSteps();
  renderPortal();
  showToast("Step "+(i+1)+" complete!");

  if(!currentRecruit) return;
  var r = currentRecruit;
  var fullName = r.first + " " + r.last;

  // Step 2 (index 1) — exam confirmation sent — Nansi needs to unlock Step 3
  if(i === 1){
    sendNansiNotification(
      "ACTION REQUIRED — Unlock Step 3 for " + fullName,
      "Hi Nansi,\n\n" +
      fullName + " has completed Step 2 and emailed you their exam confirmation.\n\n" +
      "ACTION NEEDED NOW:\n" +
      "Log into the Owner Dashboard and click the Unlock button next to " + r.first + " " + r.last + " to unlock Step 3.\n\n" +
      "BOTH STEPS THAT REQUIRE YOU:\n" +
      "  Step 3 — Unlock NOW (exam confirmation received)\n" +
      "  Step 9 — Unlock LATER (after they email you their passing exam results)\n\n" +
      "RECRUIT INFO:\n" +
      "  Name:  " + fullName + "\n" +
      "  Email: " + r.email + "\n" +
      "  Phone: " + r.phone + "\n" +
      "  State: " + r.state + "\n\n" +
      "— Elite Motional Financial Portal",
      fullName
    );
  }

  // Step 8 (index 7) — pass results sent — Nansi needs to unlock Step 9
  if(i === 7){
    sendNansiNotification(
      "ACTION REQUIRED — Unlock Step 9 for " + fullName,
      "Hi Nansi,\n\n" +
      fullName + " has passed their exam and emailed you their results.\n\n" +
      "ACTION NEEDED NOW:\n" +
      "Log into the Owner Dashboard and click the Unlock button next to " + r.first + " " + r.last + " to unlock Step 9.\n\n" +
      "RECRUIT INFO:\n" +
      "  Name:  " + fullName + "\n" +
      "  Email: " + r.email + "\n" +
      "  Phone: " + r.phone + "\n" +
      "  State: " + r.state + "\n\n" +
      "— Elite Motional Financial Portal",
      fullName
    );
  }
}

function uncompleteStep(i){
  portalSteps[i].completed = false;
  portalSteps[i].open = true;
  savePortalSteps();
  renderPortal();
  showToast("Step "+(i+1)+" reopened");
}

function renderCalendar(){
  var months=["January","February","March","April","May","June","July","August","September","October","November","December"];
  document.getElementById("cal-month-label").textContent = months[calMonth]+" "+calYear;
  var days = document.getElementById("cal-days");
  days.innerHTML = "";
  var first = new Date(calYear,calMonth,1).getDay();
  var total = new Date(calYear,calMonth+1,0).getDate();
  for(var i=0;i<first;i++){var e=document.createElement("div");e.className="cal-day empty";days.appendChild(e)}
  for(var d=1;d<=total;d++){
    var date=new Date(calYear,calMonth,d);
    var el=document.createElement("div");
    el.textContent=d;
    var isPast=date<minBookDate;
    var isSunday=date.getDay()===0;
    if(isPast||isSunday){el.className="cal-day past"}
    else{el.className="cal-day available";(function(dt){el.onclick=function(){selectDate(el,dt)}})(date)}
    days.appendChild(el);
  }
  document.getElementById("time-slots-section").style.display="none";
  document.getElementById("book-btn").classList.remove("ready");
  selectedDate=null;selectedTime=null;
}

function selectDate(el,date){
  document.querySelectorAll(".cal-day").forEach(function(c){c.classList.remove("selected")});
  el.classList.add("selected");
  selectedDate=date;
  var times=["12:30 PM","3:00 PM","7:00 PM"];
  var ts=document.getElementById("time-slots");
  ts.innerHTML="";
  times.forEach(function(t){
    var btn=document.createElement("div");
    btn.className="time-slot available";
    btn.textContent=t;
    (function(time){btn.onclick=function(){selectTime(btn,time)}})(t);
    ts.appendChild(btn);
  });
  document.getElementById("time-slots-section").style.display="block";
  selectedTime=null;
  document.getElementById("book-btn").classList.remove("ready");
}

function selectTime(el,t){
  document.querySelectorAll(".time-slot").forEach(function(s){s.classList.remove("selected")});
  el.classList.add("selected");
  selectedTime=t;
  document.getElementById("book-btn").classList.add("ready");
}

function prevMonth(){calMonth--;if(calMonth<0){calMonth=11;calYear--}renderCalendar()}
function nextMonth(){calMonth++;if(calMonth>11){calMonth=0;calYear++}renderCalendar()}

function bookAppointment(){
  if(!selectedDate||!selectedTime) return;
  var dateStr=selectedDate.toLocaleDateString("en-US",{weekday:"long",year:"numeric",month:"long",day:"numeric"});
  var apptStr = dateStr+" at "+selectedTime;
  if(currentRecruit){
    currentRecruit.appt = apptStr;
    saveRecruits();
    // Save to Firebase
    if(window._db && currentRecruit._firebaseId){
      window._fbUpdateDoc(window._fbDoc(window._db,"recruits",currentRecruit._firebaseId),{appt:apptStr}).catch(function(e){console.error("Firebase appt error:",e)});
    } else if(window._db){
      window._fbGetDocs(window._fbQuery(window._fbCollection(window._db,"recruits"),window._fbWhere("id","==",currentRecruit.id))).then(function(snap){
        snap.forEach(function(d){
          window._fbUpdateDoc(window._fbDoc(window._db,"recruits",d.id),{appt:apptStr});
        });
      });
    }

    var r = currentRecruit;
    var fullName = r.first + " " + r.last;

    // Email recruit confirmation
    emailjs.send("service_vjilj5a", "template_kldk4r8", {
      name: fullName,
      subject: "Your Call is Booked — " + dateStr + " at " + selectedTime,
      message: "Hi " + r.first + ",\n\nYour 5-minute intro call with Nansi Hanna is confirmed!\n\nDATE:  " + dateStr + "\nTIME:  " + selectedTime + "\nDURATION:  5 minutes\n\nNansi will reach out to you at:\n  Phone: " + r.phone + "\n  Email: " + r.email + "\n\nIf you have any questions beforehand, you can text Nansi at 619-558-7851.\n\nSee you soon!\n— Elite Motional Financial",
      reply_to: "nansihanna.ffl@gmail.com"
    }).then(function(){
      console.log("Confirmation sent to recruit");
    }, function(err){
      console.error("Recruit email error:", err);
    });

    // Email Nansi notification
    sendNansiNotification(
      "New Call Booked — " + fullName + " on " + dateStr + " at " + selectedTime,
      "Hi Nansi,\n\nA new call has been booked!\n\nDATE:  " + dateStr + "\nTIME:  " + selectedTime + "\nDURATION:  5 minutes\n\nRECRUIT INFO:\n  Name:   " + fullName + "\n  Email:  " + r.email + "\n  Phone:  " + r.phone + "\n  State:  " + r.state + "\n\nLog into the Owner Dashboard → Calendar tab to see all your upcoming appointments.\n\n— Elite Motional Financial Portal",
      fullName
    );
  }
  document.getElementById("confirm-details").innerHTML="<div class='confirm-row'><div class='key'>Name</div><div class='val'>"+currentRecruit.first+" "+currentRecruit.last+"</div></div><div class='confirm-row'><div class='key'>Email</div><div class='val'>"+currentRecruit.email+"</div></div><div class='confirm-row'><div class='key'>Phone</div><div class='val'>"+currentRecruit.phone+"</div></div><div class='confirm-row'><div class='key'>Date and Time</div><div class='val'>"+dateStr+" at "+selectedTime+"</div></div><div class='confirm-row'><div class='key'>Duration</div><div class='val'>5-minute intro call</div></div>";
  showPage("confirm");
  showToast("Booking confirmed!");
}

function saveRecruits(){localStorage.setItem("nh_recruits",JSON.stringify(recruits))}
function savePortalSteps(){if(currentRecruit){localStorage.setItem("nh_steps_"+currentRecruit.id,JSON.stringify(portalSteps));currentRecruit.portalProgress=portalSteps.filter(function(s){return s.completed}).length;saveRecruits();}}

function showToast(msg){
  var t=document.getElementById("toast");
  t.textContent=msg;
  t.classList.add("show");
  setTimeout(function(){t.classList.remove("show")},3000);
}

function toggleMenu(){
  document.getElementById("side-menu").classList.toggle("open");
  document.getElementById("menu-overlay").classList.toggle("open");
}

// Mobile touch fix: tap to reveal hover state on info-card and svc-card
document.addEventListener('touchstart', function(e){
  var card = e.target.closest('.info-card, .svc-card');
  if(card){
    var selector = card.classList.contains('info-card') ? '.info-card' : '.svc-card';
    document.querySelectorAll(selector).forEach(function(c){ if(c !== card) c.classList.remove('touch-active'); });
    card.classList.toggle('touch-active');
  }
}, {passive:true});

// Income calculator
document.addEventListener('DOMContentLoaded', function(){
  var slider = document.getElementById('calc-slider');
  if(!slider) return;
  var FFL_AVG = 15300;
  function fmt(n){return '$'+n.toLocaleString()}
  function animate(el, newVal){
    el.style.transform='scale(1.04)';
    el.style.opacity='0.6';
    setTimeout(function(){
      el.textContent=newVal;
      el.style.transform='scale(1)';
      el.style.opacity='1';
    },150);
  }
  slider.addEventListener('input', function(){
    var current = parseInt(this.value);
    var after = Math.max(FFL_AVG, Math.round(current * 5.1 / 100) * 100);
    var gap = after - current;
    var mult = (after/current).toFixed(1);
    document.getElementById('calc-current-label').textContent = fmt(current);
    animate(document.getElementById('calc-before-num'), fmt(current));
    animate(document.getElementById('calc-after-num'), fmt(after));
    document.getElementById('calc-before-year').textContent = fmt(current*12)+' / year';
    document.getElementById('calc-after-year').textContent = fmt(after*12)+' / year';
    document.getElementById('calc-gap').textContent = fmt(gap)+' / mo';
    document.getElementById('calc-multiplier').textContent = mult+'× your current income';
  });
});
</script>

<!-- FIXED BOTTOM MARQUEE BANNER - landing only -->
<div id="bottom-banner" style="position:fixed;bottom:0;left:0;right:0;z-index:9996;background:#000;border-top:1px solid rgba(255,255,255,0.08);padding:11px 0;overflow:hidden;display:block">
  <div style="display:flex;white-space:nowrap;animation:marquee 30s linear infinite">
    <div style="display:inline-flex;align-items:center;gap:48px;padding:0 48px;flex-shrink:0">
      <span style="font-size:9px;font-weight:300;letter-spacing:.28em;text-transform:uppercase;color:#fff;font-family:'Inter',sans-serif">Wake Up to Morning Deposits</span>
      <span style="color:rgba(255,255,255,0.25);font-size:9px">|</span>
      <span style="font-size:9px;font-weight:300;letter-spacing:.28em;text-transform:uppercase;color:#fff;font-family:'Inter',sans-serif">Make Uncapped Commission</span>
      <span style="color:rgba(255,255,255,0.25);font-size:9px">|</span>
      <span style="font-size:9px;font-weight:300;letter-spacing:.28em;text-transform:uppercase;color:#fff;font-family:'Inter',sans-serif">No Limit to How Much You Can Make</span>
      <span style="color:rgba(255,255,255,0.25);font-size:9px">|</span>
      <span style="font-size:9px;font-weight:300;letter-spacing:.28em;text-transform:uppercase;color:#fff;font-family:'Inter',sans-serif">It's Your Own Business</span>
      <span style="color:rgba(255,255,255,0.25);font-size:9px">|</span>
    </div>
    <div style="display:inline-flex;align-items:center;gap:48px;padding:0 48px;flex-shrink:0" aria-hidden="true">
      <span style="font-size:9px;font-weight:300;letter-spacing:.28em;text-transform:uppercase;color:#fff;font-family:'Inter',sans-serif">Wake Up to Morning Deposits</span>
      <span style="color:rgba(255,255,255,0.25);font-size:9px">|</span>
      <span style="font-size:9px;font-weight:300;letter-spacing:.28em;text-transform:uppercase;color:#fff;font-family:'Inter',sans-serif">Make Uncapped Commission</span>
      <span style="color:rgba(255,255,255,0.25);font-size:9px">|</span>
      <span style="font-size:9px;font-weight:300;letter-spacing:.28em;text-transform:uppercase;color:#fff;font-family:'Inter',sans-serif">No Limit to How Much You Can Make</span>
      <span style="color:rgba(255,255,255,0.25);font-size:9px">|</span>
      <span style="font-size:9px;font-weight:300;letter-spacing:.28em;text-transform:uppercase;color:#fff;font-family:'Inter',sans-serif">It's Your Own Business</span>
      <span style="color:rgba(255,255,255,0.25);font-size:9px">|</span>
    </div>
  </div>
</div>

</body>
</html>
