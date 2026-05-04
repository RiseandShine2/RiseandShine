<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rise & Shine · Digital Books for a Better Life</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Nunito:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --rose:#c9796a; --rose-dark:#a85e51; --rose-pale:#faf0ec;
  --teal:#4a8c8c; --teal-dark:#356666; --teal-light:#6db3b3; --teal-pale:#e6f4f4;
  --sand:#f7f2eb; --sand-dark:#e8e0d4; --blush:#f2e8e1; --blush-mid:#e8d5c8;
  --ink:#1c1c1c; --ink-mid:#3d3d3d; --ink-light:#666; --white:#fff;
  --border:rgba(74,140,140,0.15);
  --admin-bg:#0f1923; --admin-sidebar:#162230; --admin-card:#1e2f40;
  --admin-border:rgba(74,140,140,0.2); --admin-accent:#4a8c8c;
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{font-family:'Nunito',sans-serif;background:var(--sand);color:var(--ink);overflow-x:hidden;}
.page{display:none;background:var(--sand);}
.page.active{display:block;}
#admin.page.active{background:var(--admin-bg);}

/* ── NAV ── */
nav{position:fixed;top:0;left:0;right:0;z-index:300;display:flex;align-items:center;justify-content:space-between;padding:16px 52px;background:rgba(247,242,235,0.96);backdrop-filter:blur(16px);border-bottom:1px solid var(–blush-mid);}
.nav-logo{font-family:‘Playfair Display’,serif;font-size:24px;font-weight:900;color:var(–ink);text-decoration:none;cursor:pointer;letter-spacing:.5px;}
.nav-logo span{color:var(–rose);font-style:italic;}
.nav-links{display:flex;gap:28px;list-style:none;align-items:center;}
.nav-links a{font-size:13px;font-weight:600;letter-spacing:1px;color:var(–ink-mid);text-decoration:none;transition:color .2s;cursor:pointer;}
.nav-links a:hover{color:var(–teal);}
.nav-pill{background:var(–teal)!important;color:#fff!important;padding:9px 20px;border-radius:100px;transition:background .2s!important;}
.nav-pill:hover{background:var(–teal-dark)!important;}
.nav-account-btns{display:flex;gap:10px;align-items:center;}
.nav-btn-login{font-size:12px;font-weight:700;color:var(–teal);background:var(–teal-pale);border:1.5px solid var(–teal);padding:8px 18px;border-radius:100px;cursor:pointer;transition:all .2s;font-family:‘Nunito’,sans-serif;}
.nav-btn-login:hover{background:var(–teal);color:#fff;}

/* ── BUTTONS ── */
.btn-rose{display:inline-block;background:var(–rose);color:#fff;font-family:‘Nunito’,sans-serif;font-size:14px;font-weight:700;padding:13px 32px;border-radius:100px;text-decoration:none;border:none;cursor:pointer;transition:all .25s;box-shadow:0 4px 20px rgba(201,121,106,.3);}
.btn-rose:hover{background:var(–rose-dark);transform:translateY(-2px);}
.btn-teal{display:inline-block;background:var(–teal);color:#fff;font-family:‘Nunito’,sans-serif;font-size:14px;font-weight:700;padding:13px 32px;border-radius:100px;text-decoration:none;border:none;cursor:pointer;transition:all .25s;box-shadow:0 4px 20px rgba(74,140,140,.3);}
.btn-teal:hover{background:var(–teal-dark);transform:translateY(-2px);}
.btn-ghost{display:inline-block;background:transparent;color:var(–ink);font-family:‘Nunito’,sans-serif;font-size:14px;font-weight:700;padding:12px 30px;border-radius:100px;text-decoration:none;border:2px solid var(–blush-mid);cursor:pointer;transition:all .25s;}
.btn-ghost:hover{border-color:var(–teal);color:var(–teal);}

/* ── SECTION COMMONS ── */
.tag{display:inline-block;font-size:11px;font-weight:700;letter-spacing:3px;text-transform:uppercase;color:var(–teal);margin-bottom:12px;}
.s-head{text-align:center;margin-bottom:52px;}
.s-head h2{font-family:‘Playfair Display’,serif;font-size:clamp(28px,4vw,48px);font-weight:900;color:var(–ink);line-height:1.15;}
.s-head p{font-size:16px;color:var(–ink-light);margin-top:12px;line-height:1.7;}

/* ════════════════════════════
STORE PAGES
════════════════════════════ */

/* HERO */
.hero{min-height:100vh;display:grid;grid-template-columns:1fr 1fr;position:relative;overflow:hidden;}
.hero-left{background:var(–sand);display:flex;flex-direction:column;justify-content:center;padding:140px 56px 80px 72px;position:relative;z-index:1;}
.hero-right{position:relative;overflow:hidden;}
.hero-right img{width:100%;height:100%;object-fit:cover;display:block;}
.hero-right::after{content:’’;position:absolute;inset:0;background:linear-gradient(to right,var(–sand) 0%,transparent 30%);}
.hero-tag{display:inline-flex;align-items:center;gap:8px;background:var(–teal-pale);border:1px solid rgba(74,140,140,.3);color:var(–teal-dark);font-size:11px;font-weight:700;letter-spacing:2px;text-transform:uppercase;padding:8px 18px;border-radius:100px;margin-bottom:28px;width:fit-content;}
.hero h1{font-family:‘Playfair Display’,serif;font-size:clamp(42px,5.5vw,70px);font-weight:900;line-height:1.08;color:var(–ink);margin-bottom:20px;}
.hero h1 em{font-style:italic;color:var(–rose);}
.hero-desc{font-size:17px;line-height:1.8;color:var(–ink-mid);max-width:460px;margin-bottom:36px;}
.hero-btns{display:flex;gap:14px;flex-wrap:wrap;margin-bottom:48px;}
.hero-stats{display:flex;gap:32px;flex-wrap:wrap;padding-top:32px;border-top:1px solid var(–blush-mid);}
.stat-num{font-family:‘Playfair Display’,serif;font-size:30px;font-weight:900;color:var(–teal);line-height:1;}
.stat-lbl{font-size:12px;color:var(–ink-light);margin-top:3px;font-weight:600;}

/* TRUST */
.trust{background:var(–white);padding:18px 52px;display:flex;justify-content:center;gap:48px;flex-wrap:wrap;border-bottom:1px solid var(–sand-dark);}
.trust-item{display:flex;align-items:center;gap:10px;font-size:13px;font-weight:600;color:var(–ink-mid);}

/* ABOUT STRIP */
.about-strip{display:grid;grid-template-columns:1fr 1fr;min-height:440px;overflow:hidden;}
.about-strip-img{position:relative;overflow:hidden;}
.about-strip-img img{width:100%;height:100%;object-fit:cover;display:block;}
.about-strip-text{background:var(–teal);padding:64px;display:flex;flex-direction:column;justify-content:center;}
.about-strip-text .tag{color:rgba(255,255,255,.55);}
.about-strip-text h2{font-family:‘Playfair Display’,serif;font-size:clamp(26px,3vw,40px);font-weight:900;color:#fff;line-height:1.2;margin-bottom:16px;}
.about-strip-text p{font-size:15px;line-height:1.8;color:rgba(255,255,255,.8);margin-bottom:10px;}
.about-strip-text a{color:rgba(255,255,255,.6);text-decoration:underline;cursor:pointer;font-size:14px;font-weight:600;margin-top:8px;display:inline-block;}
.about-strip-text a:hover{color:#fff;}

/* CATEGORIES */
.categories{padding:80px 52px;background:var(–sand);}
.cat-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(155px,1fr));gap:14px;max-width:1000px;margin:0 auto;}
.cat-pill{background:var(–white);border:1.5px solid var(–sand-dark);border-radius:16px;padding:22px 14px;text-align:center;cursor:pointer;transition:all .2s;text-decoration:none;}
.cat-pill:hover,.cat-pill.active{background:var(–teal);border-color:var(–teal);}
.cat-pill:hover .cat-name,.cat-pill.active .cat-name{color:#fff;}
.cat-pill:hover .cat-count,.cat-pill.active .cat-count{color:rgba(255,255,255,.6);}
.cat-emoji{font-size:26px;display:block;margin-bottom:8px;transition:transform .2s;}
.cat-pill:hover .cat-emoji{transform:scale(1.2);}
.cat-name{font-size:13px;font-weight:700;color:var(–ink);transition:color .2s;}
.cat-count{font-size:11px;color:var(–ink-light);margin-top:3px;transition:color .2s;}

/* STORE */
.store{padding:80px 52px;background:var(–blush);}
.books-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:28px;max-width:1100px;margin:0 auto;}
.book-card{background:var(–white);border-radius:20px;overflow:hidden;border:1px solid var(–blush-mid);transition:all .3s;display:flex;flex-direction:column;box-shadow:0 2px 16px rgba(0,0,0,.04);}
.book-card:hover{transform:translateY(-7px);box-shadow:0 24px 56px rgba(201,121,106,.15);border-color:var(–rose);}
.book-cover-area{height:220px;position:relative;overflow:hidden;}
.book-cover-area img{width:100%;height:100%;object-fit:cover;display:block;transition:transform .4s;}
.book-card:hover .book-cover-area img{transform:scale(1.05);}
.book-cover-fallback{width:100%;height:100%;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:24px;text-align:center;}
.cover-teal{background:linear-gradient(135deg,#4a8c8c,#2a5e5e);}
.cover-rose{background:linear-gradient(135deg,#c9796a,#8a4a3a);}
.cover-lav{background:linear-gradient(135deg,#9b8ec4,#6a5a9e);}
.book-badge{position:absolute;top:14px;right:14px;background:var(–rose);color:#fff;font-size:10px;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;padding:5px 14px;border-radius:100px;}
.book-badge.soon{background:var(–teal);}
.book-body{padding:24px;flex:1;display:flex;flex-direction:column;}
.book-cat{font-size:11px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(–teal);margin-bottom:6px;}
.book-stars{color:var(–rose);font-size:13px;letter-spacing:1px;margin-bottom:8px;}
.book-title{font-family:‘Playfair Display’,serif;font-size:20px;font-weight:700;color:var(–ink);line-height:1.25;margin-bottom:10px;}
.book-blurb{font-size:13px;line-height:1.7;color:var(–ink-light);flex:1;margin-bottom:20px;}
.book-foot{display:flex;align-items:center;justify-content:space-between;}
.book-price-num{font-family:‘Playfair Display’,serif;font-size:30px;font-weight:900;color:var(–ink);}
.book-price-num sup{font-size:16px;vertical-align:super;color:var(–ink-light);}
.btn-buy{background:var(–rose);color:#fff;font-family:‘Nunito’,sans-serif;font-size:12px;font-weight:700;letter-spacing:1px;text-transform:uppercase;padding:11px 22px;border-radius:100px;text-decoration:none;border:none;cursor:pointer;transition:all .2s;box-shadow:0 4px 16px rgba(201,121,106,.3);}
.btn-buy:hover{background:var(–rose-dark);transform:translateY(-1px);}
.btn-waitlist{background:var(–teal);box-shadow:0 4px 16px rgba(74,140,140,.3);}
.btn-waitlist:hover{background:var(–teal-dark);}

/* FEATURED */
.featured{display:grid;grid-template-columns:1fr 1fr;min-height:540px;overflow:hidden;}
.featured-img{position:relative;overflow:hidden;}
.featured-img img{width:100%;height:100%;object-fit:cover;display:block;}
.featured-text{background:linear-gradient(135deg,#1c3535,#2a4a4a);padding:64px;display:flex;flex-direction:column;justify-content:center;}
.featured-text .tag{color:var(–teal-light);}
.featured-text h2{font-family:‘Playfair Display’,serif;font-size:clamp(26px,3vw,42px);font-weight:900;color:#fff;line-height:1.15;margin-bottom:14px;}
.featured-text>p{font-size:15px;line-height:1.8;color:rgba(255,255,255,.6);margin-bottom:22px;}
.feat-list{list-style:none;display:flex;flex-direction:column;gap:9px;margin-bottom:28px;}
.feat-list li{display:flex;gap:10px;font-size:14px;color:rgba(255,255,255,.75);align-items:flex-start;}
.feat-dot{width:7px;height:7px;border-radius:50%;background:var(–teal-light);flex-shrink:0;margin-top:6px;}
.feat-price{display:flex;align-items:baseline;gap:10px;margin-bottom:26px;}
.feat-amount{font-family:‘Playfair Display’,serif;font-size:52px;font-weight:900;color:#fff;line-height:1;}
.feat-note{font-size:13px;color:rgba(255,255,255,.35);}

/* IMG BANNER */
.img-banner{height:300px;position:relative;overflow:hidden;}
.img-banner img{width:100%;height:100%;object-fit:cover;display:block;}
.img-banner-overlay{position:absolute;inset:0;background:rgba(28,53,53,.6);display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:24px;}
.img-banner-overlay h2{font-family:‘Playfair Display’,serif;font-size:clamp(24px,4vw,48px);font-weight:900;color:#fff;line-height:1.15;margin-bottom:12px;}
.img-banner-overlay p{font-size:15px;color:rgba(255,255,255,.7);max-width:540px;}

/* WHY */
.why{padding:80px 52px;background:var(–white);}
.why-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:22px;max-width:1000px;margin:0 auto;}
.why-card{background:var(–sand);border-radius:20px;padding:34px 26px;text-align:center;border:1px solid var(–sand-dark);transition:all .25s;}
.why-card:hover{background:var(–teal-pale);border-color:var(–teal-light);transform:translateY(-4px);box-shadow:0 12px 36px rgba(74,140,140,.12);}
.why-icon{font-size:38px;margin-bottom:12px;}
.why-title{font-family:‘Playfair Display’,serif;font-size:19px;font-weight:700;color:var(–ink);margin-bottom:9px;}
.why-desc{font-size:13px;line-height:1.7;color:var(–ink-light);}

/* NEWSLETTER */
.newsletter{position:relative;overflow:hidden;padding:96px 52px;text-align:center;}
.newsletter-bg{position:absolute;inset:0;z-index:0;}
.newsletter-bg img{width:100%;height:100%;object-fit:cover;display:block;}
.newsletter-bg::after{content:’’;position:absolute;inset:0;background:rgba(26,53,53,.8);}
.newsletter-inner{position:relative;z-index:1;max-width:540px;margin:0 auto;}
.newsletter .tag{color:var(–teal-light);}
.newsletter h2{font-family:‘Playfair Display’,serif;font-size:clamp(26px,4vw,44px);font-weight:900;color:#fff;margin-bottom:12px;}
.newsletter p{font-size:15px;color:rgba(255,255,255,.65);line-height:1.7;margin-bottom:28px;}
.email-row{display:flex;max-width:440px;margin:0 auto;border-radius:100px;overflow:hidden;background:#fff;box-shadow:0 8px 32px rgba(0,0,0,.2);}
.email-inp{flex:1;padding:14px 20px;font-family:‘Nunito’,sans-serif;font-size:14px;border:none;outline:none;background:transparent;color:var(–ink);}
.email-inp::placeholder{color:#aaa;}
.email-sub{background:var(–rose);color:#fff;font-family:‘Nunito’,sans-serif;font-size:13px;font-weight:700;padding:14px 24px;border:none;cursor:pointer;transition:background .2s;white-space:nowrap;border-radius:0 100px 100px 0;}
.email-sub:hover{background:var(–rose-dark);}
.email-note{font-size:12px;color:rgba(255,255,255,.35);margin-top:12px;}

/* ════════════════════════════
INNER PAGES
════════════════════════════ */
.inner-page{padding:120px 52px 80px;min-height:100vh;background:var(–sand);}
.inner-wrap{max-width:760px;margin:0 auto;}
.inner-tag{font-size:11px;font-weight:700;letter-spacing:3px;text-transform:uppercase;color:var(–teal);display:block;margin-bottom:12px;}
.inner-page h1{font-family:‘Playfair Display’,serif;font-size:clamp(34px,5vw,60px);font-weight:900;color:var(–ink);line-height:1.1;margin-bottom:26px;}
.inner-page h1 em{font-style:italic;color:var(–rose);}
.inner-bar{width:56px;height:4px;background:linear-gradient(90deg,var(–teal),var(–rose));border-radius:2px;margin-bottom:36px;}
.prose p{font-size:16px;line-height:1.85;color:var(–ink-mid);margin-bottom:16px;}
.prose h3{font-family:‘Playfair Display’,serif;font-size:22px;font-weight:700;color:var(–ink);margin:32px 0 10px;}
.prose ul{padding-left:20px;margin-bottom:16px;}
.prose ul li{font-size:15px;line-height:1.8;color:var(–ink-mid);margin-bottom:7px;}
.prose strong{color:var(–ink);font-weight:700;}
.pill-date{display:inline-block;background:var(–teal-pale);border:1px solid rgba(74,140,140,.3);color:var(–teal-dark);font-size:12px;font-weight:600;padding:6px 16px;border-radius:100px;margin-bottom:30px;}
.founders-row{display:grid;grid-template-columns:1fr 1fr;gap:20px;margin:36px 0;}
.founder-card{background:var(–white);border-radius:20px;padding:30px 22px;text-align:center;border:1px solid var(–sand-dark);transition:all .2s;}
.founder-card:hover{border-color:var(–teal-light);transform:translateY(-4px);box-shadow:0 12px 36px rgba(74,140,140,.1);}
.f-avatar{width:70px;height:70px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:26px;margin:0 auto 12px;}
.f-teal{background:var(–teal-pale);border:2px solid var(–teal);}
.f-rose{background:var(–rose-pale);border:2px solid var(–rose);}
.f-name{font-family:‘Playfair Display’,serif;font-size:21px;font-weight:700;color:var(–ink);margin-bottom:4px;}
.f-role{font-size:11px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(–rose);margin-bottom:10px;}
.f-bio{font-size:13px;line-height:1.7;color:var(–ink-light);}
.contact-row{display:grid;grid-template-columns:1fr 1fr;gap:20px;margin:30px 0;}
.contact-card{background:var(–white);border-radius:16px;padding:26px;border:1px solid var(–sand-dark);transition:all .2s;}
.contact-card:hover{border-color:var(–teal);transform:translateY(-3px);box-shadow:0 8px 28px rgba(74,140,140,.1);}
.c-icon{font-size:26px;margin-bottom:9px;}
.c-label{font-size:11px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(–teal);margin-bottom:5px;}
.c-val{font-family:‘Playfair Display’,serif;font-size:17px;font-weight:700;color:var(–ink);}
.c-val a{color:var(–rose);text-decoration:none;}
.c-val a:hover{text-decoration:underline;}
.c-note{font-size:13px;color:var(–ink-light);margin-top:5px;line-height:1.6;}

/* ════════════════════════════
AUTH MODALS
════════════════════════════ */
.modal-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.55);z-index:1000;align-items:center;justify-content:center;padding:20px;}
.modal-box{background:#fff;border-radius:24px;padding:44px 40px;max-width:420px;width:100%;position:relative;text-align:center;box-shadow:0 32px 80px rgba(0,0,0,.25);}
.modal-close{position:absolute;top:16px;right:20px;background:none;border:none;font-size:22px;cursor:pointer;color:#aaa;}
.modal-close:hover{color:#555;}
.modal-logo{font-family:‘Playfair Display’,serif;font-size:22px;font-weight:900;color:var(–ink);margin-bottom:6px;}
.modal-logo span{color:var(–rose);font-style:italic;}
.modal-subtitle{font-size:13px;color:var(–ink-light);margin-bottom:28px;}
.modal-tabs{display:flex;gap:0;background:var(–sand);border-radius:100px;padding:4px;margin-bottom:28px;}
.modal-tab{flex:1;padding:9px;border-radius:100px;border:none;background:transparent;font-family:‘Nunito’,sans-serif;font-size:13px;font-weight:700;cursor:pointer;color:var(–ink-light);transition:all .2s;}
.modal-tab.active{background:#fff;color:var(–teal);box-shadow:0 2px 8px rgba(0,0,0,.08);}
.auth-form{display:flex;flex-direction:column;gap:14px;text-align:left;}
.auth-form label{font-size:12px;font-weight:700;letter-spacing:1px;color:var(–ink-mid);margin-bottom:2px;display:block;}
.auth-form input{width:100%;padding:12px 16px;border:1.5px solid var(–sand-dark);border-radius:10px;font-family:‘Nunito’,sans-serif;font-size:14px;color:var(–ink);outline:none;transition:border .2s;}
.auth-form input:focus{border-color:var(–teal);}
.auth-submit{width:100%;background:var(–teal);color:#fff;font-family:‘Nunito’,sans-serif;font-size:14px;font-weight:700;padding:14px;border-radius:100px;border:none;cursor:pointer;transition:background .2s;margin-top:4px;}
.auth-submit:hover{background:var(–teal-dark);}
.auth-msg{font-size:12px;color:var(–ink-light);text-align:center;margin-top:8px;}
.auth-err{font-size:13px;color:var(–rose);font-weight:600;text-align:center;padding:10px;background:var(–rose-pale);border-radius:8px;display:none;}

/* CHECKOUT MODAL */
.modal-emoji{font-size:44px;margin-bottom:10px;}
.modal-title{font-family:‘Playfair Display’,serif;font-size:20px;font-weight:700;color:var(–ink);margin-bottom:4px;line-height:1.3;}
.modal-sub{font-size:13px;color:var(–ink-light);margin-bottom:6px;}
.modal-price-big{font-family:‘Playfair Display’,serif;font-size:48px;font-weight:900;color:var(–ink);margin:12px 0 4px;line-height:1;}
.modal-note{font-size:12px;color:#aaa;margin-bottom:22px;}
.paypal-btn{display:block;width:100%;background:#0070ba;color:#fff;font-family:‘Nunito’,sans-serif;font-size:15px;font-weight:700;padding:15px 24px;border-radius:100px;text-decoration:none;text-align:center;transition:background .2s;box-shadow:0 4px 20px rgba(0,112,186,.3);}
.paypal-btn:hover{background:#005ea3;}
.modal-secure{font-size:11px;color:#ccc;margin-top:12px;}

/* ════════════════════════════
CUSTOMER DASHBOARD
════════════════════════════ */
.cust-dash{padding:100px 52px 60px;min-height:100vh;background:var(–sand);}
.cust-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:40px;}
.cust-header h1{font-family:‘Playfair Display’,serif;font-size:36px;font-weight:900;color:var(–ink);}
.cust-header h1 span{color:var(–rose);font-style:italic;}
.cust-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:24px;}
.cust-card{background:var(–white);border-radius:20px;border:1px solid var(–sand-dark);overflow:hidden;transition:all .2s;}
.cust-card:hover{transform:translateY(-4px);box-shadow:0 12px 36px rgba(74,140,140,.12);border-color:var(–teal-light);}
.cust-card-cover{height:160px;display:flex;align-items:center;justify-content:center;font-size:52px;}
.cust-card-body{padding:20px;}
.cust-card-title{font-family:‘Playfair Display’,serif;font-size:18px;font-weight:700;color:var(–ink);margin-bottom:6px;}
.cust-card-date{font-size:12px;color:var(–ink-light);margin-bottom:14px;}
.cust-empty{text-align:center;padding:60px 20px;color:var(–ink-light);}
.cust-empty div{font-size:56px;margin-bottom:16px;}
.cust-empty p{font-size:16px;line-height:1.7;}

/* ════════════════════════════
ADMIN DASHBOARD
════════════════════════════ */
#admin{background:var(–admin-bg);min-height:100vh;}
.page{min-height:0;}
.admin-layout{display:grid;grid-template-columns:260px 1fr;min-height:100vh;}
.admin-sidebar{background:var(–admin-sidebar);padding:32px 0;border-right:1px solid var(–admin-border);position:sticky;top:0;height:100vh;overflow-y:auto;}
.admin-logo{font-family:‘Playfair Display’,serif;font-size:22px;font-weight:900;color:#fff;padding:0 28px;margin-bottom:8px;}
.admin-logo span{color:var(–rose);font-style:italic;}
.admin-role{font-size:11px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:rgba(255,255,255,.3);padding:0 28px;margin-bottom:32px;display:block;}
.admin-nav{list-style:none;}
.admin-nav li a{display:flex;align-items:center;gap:12px;padding:13px 28px;font-size:14px;font-weight:600;color:rgba(255,255,255,.5);text-decoration:none;cursor:pointer;transition:all .2s;border-left:3px solid transparent;}
.admin-nav li a:hover,.admin-nav li a.active{color:#fff;background:rgba(74,140,140,.12);border-left-color:var(–teal);}
.admin-nav li a .nav-icon{font-size:18px;width:22px;text-align:center;}
.admin-divider{height:1px;background:var(–admin-border);margin:20px 28px;}
.admin-main{padding:40px 48px;overflow-y:auto;}
.admin-topbar{display:flex;justify-content:space-between;align-items:center;margin-bottom:36px;}
.admin-topbar h1{font-family:‘Playfair Display’,serif;font-size:28px;font-weight:900;color:#fff;}
.admin-topbar h1 span{color:var(–teal-light);font-style:italic;}
.admin-user-pill{display:flex;align-items:center;gap:10px;background:var(–admin-card);border:1px solid var(–admin-border);padding:10px 18px;border-radius:100px;}
.admin-user-pill span{font-size:13px;color:rgba(255,255,255,.7);font-weight:600;}
.admin-logout{background:none;border:none;color:rgba(255,255,255,.4);font-size:12px;cursor:pointer;font-family:‘Nunito’,sans-serif;font-weight:600;transition:color .2s;}
.admin-logout:hover{color:var(–rose);}

/* ADMIN STATS */
.admin-stats{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:20px;margin-bottom:36px;}
.admin-stat{background:var(–admin-card);border:1px solid var(–admin-border);border-radius:16px;padding:24px;}
.admin-stat-icon{font-size:28px;margin-bottom:10px;}
.admin-stat-num{font-family:‘Playfair Display’,serif;font-size:34px;font-weight:900;color:#fff;line-height:1;}
.admin-stat-lbl{font-size:12px;color:rgba(255,255,255,.4);margin-top:4px;font-weight:600;letter-spacing:.5px;}

/* ADMIN PANELS */
.admin-panel{display:none;}
.admin-panel.active{display:block;}
.admin-section-title{font-family:‘Playfair Display’,serif;font-size:22px;font-weight:700;color:#fff;margin-bottom:20px;}

/* ADMIN CARD */
.admin-card{background:var(–admin-card);border:1px solid var(–admin-border);border-radius:16px;padding:28px;margin-bottom:24px;}
.admin-card-title{font-size:14px;font-weight:700;color:rgba(255,255,255,.5);letter-spacing:1px;text-transform:uppercase;margin-bottom:18px;}

/* ADMIN TABLE */
.admin-table{width:100%;border-collapse:collapse;}
.admin-table th{text-align:left;font-size:11px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:rgba(255,255,255,.3);padding:0 14px 12px;border-bottom:1px solid var(–admin-border);}
.admin-table td{padding:14px;font-size:14px;color:rgba(255,255,255,.7);border-bottom:1px solid rgba(255,255,255,.05);vertical-align:middle;}
.admin-table tr:last-child td{border-bottom:none;}
.admin-table tr:hover td{background:rgba(255,255,255,.02);}
.tbl-badge{display:inline-block;font-size:10px;font-weight:700;letter-spacing:1px;text-transform:uppercase;padding:4px 12px;border-radius:100px;}
.tbl-live{background:rgba(74,140,140,.2);color:var(–teal-light);}
.tbl-soon{background:rgba(155,142,196,.2);color:#c4b8e8;}
.tbl-actions{display:flex;gap:8px;}
.tbl-btn{font-size:11px;font-weight:700;padding:6px 14px;border-radius:100px;border:none;cursor:pointer;font-family:‘Nunito’,sans-serif;transition:all .2s;}
.tbl-edit{background:rgba(74,140,140,.2);color:var(–teal-light);}
.tbl-edit:hover{background:var(–teal);color:#fff;}
.tbl-del{background:rgba(201,121,106,.2);color:#e8a090;}
.tbl-del:hover{background:var(–rose);color:#fff;}

/* ADMIN FORM */
.admin-form{display:grid;grid-template-columns:1fr 1fr;gap:18px;}
.admin-form.single{grid-template-columns:1fr;}
.admin-field{display:flex;flex-direction:column;gap:7px;}
.admin-field.full{grid-column:1/-1;}
.admin-label{font-size:12px;font-weight:700;letter-spacing:1px;color:rgba(255,255,255,.5);text-transform:uppercase;}
.admin-input,.admin-select,.admin-textarea{background:var(–admin-bg);border:1.5px solid var(–admin-border);border-radius:10px;padding:12px 16px;font-family:‘Nunito’,sans-serif;font-size:14px;color:#fff;outline:none;transition:border .2s;width:100%;}
.admin-input:focus,.admin-select:focus,.admin-textarea:focus{border-color:var(–teal);}
.admin-select option{background:var(–admin-bg);}
.admin-textarea{resize:vertical;min-height:90px;}
.admin-btn{background:var(–teal);color:#fff;font-family:‘Nunito’,sans-serif;font-size:13px;font-weight:700;padding:13px 28px;border-radius:100px;border:none;cursor:pointer;transition:background .2s;letter-spacing:.5px;}
.admin-btn:hover{background:var(–teal-dark);}
.admin-btn-rose{background:var(–rose);}
.admin-btn-rose:hover{background:var(–rose-dark);}
.admin-save-msg{font-size:13px;color:var(–teal-light);font-weight:600;display:none;margin-top:10px;}

/* ADMIN TOGGLE */
.toggle-wrap{display:flex;align-items:center;gap:12px;}
.toggle{position:relative;width:46px;height:26px;}
.toggle input{opacity:0;width:0;height:0;}
.toggle-slider{position:absolute;inset:0;background:#2a3a4a;border-radius:26px;cursor:pointer;transition:.3s;}
.toggle-slider::before{content:’’;position:absolute;width:18px;height:18px;left:4px;bottom:4px;background:#fff;border-radius:50%;transition:.3s;}
.toggle input:checked+.toggle-slider{background:var(–teal);}
.toggle input:checked+.toggle-slider::before{transform:translateX(20px);}
.toggle-label{font-size:14px;color:rgba(255,255,255,.65);font-weight:600;}

/* FOOTER */
footer{background:#1c2e2e;padding:56px 52px 30px;}
.footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr;gap:48px;margin-bottom:44px;}
.f-brand .nav-logo{display:block;margin-bottom:12px;color:var(–sand);cursor:pointer;}
.f-brand p{font-size:13px;color:rgba(255,255,255,.35);line-height:1.7;max-width:280px;}
.f-brand .f-email{font-size:13px;color:var(–teal-light);margin-top:10px;}
.f-brand .f-email a{color:var(–teal-light);text-decoration:none;}
.f-col h4{font-size:11px;font-weight:700;letter-spacing:3px;text-transform:uppercase;color:rgba(255,255,255,.3);margin-bottom:16px;}
.f-col a{display:block;font-size:14px;color:rgba(255,255,255,.5);text-decoration:none;margin-bottom:10px;cursor:pointer;transition:color .2s;}
.f-col a:hover{color:var(–teal-light);}
.f-bottom{border-top:1px solid rgba(255,255,255,.07);padding-top:22px;display:flex;justify-content:space-between;font-size:12px;color:rgba(255,255,255,.2);flex-wrap:wrap;gap:10px;}

/* RESPONSIVE */
@media(max-width:768px){
nav{padding:14px 20px;}
.nav-links{display:none;}
.hero{grid-template-columns:1fr;}
.hero-right{display:none;}
.hero-left{padding:100px 24px 60px;}
.about-strip,.featured{grid-template-columns:1fr;}
.about-strip-img,.featured-img{height:240px;}
.categories,.store,.why,.newsletter{padding:60px 20px;}
.footer-grid{grid-template-columns:1fr;gap:28px;}
.founders-row,.contact-row{grid-template-columns:1fr;}
.inner-page{padding:100px 20px 60px;}
.admin-layout{grid-template-columns:1fr;}
.admin-sidebar{display:none;}
.cust-dash{padding:90px 20px 40px;}
.admin-main{padding:100px 20px 40px;}
.admin-form{grid-template-columns:1fr;}
}

@keyframes fadeUp{from{opacity:0;transform:translateY(24px);}to{opacity:1;transform:translateY(0);}}
.hero-left>*{animation:fadeUp .7s ease both;}
.hero-tag{animation-delay:0s!important;}
.hero h1{animation-delay:.1s!important;}
.hero-desc{animation-delay:.2s!important;}
.hero-btns{animation-delay:.3s!important;}
.hero-stats{animation-delay:.4s!important;}
</style>

</head>
<body>

<!-- NAV -->

<nav id="main-nav">
  <a class="nav-logo" onclick="showPage('home')">Rise<span>&</span>Shine</a>
  <ul class="nav-links">
    <li><a onclick="showPage('home');goTo('#store')">Books</a></li>
    <li><a onclick="showPage('home');goTo('#categories')">Topics</a></li>
    <li><a onclick="showPage('about')">About Us</a></li>
    <li><a onclick="showPage('contact')">Contact</a></li>
    <li><a onclick="showPage('home');goTo('#newsletter')" class="nav-pill">Free Gift 🎁</a></li>
  </ul>
  <div class="nav-account-btns" id="nav-account-area">
    <button class="nav-btn-login" onclick="openAuthModal('customer')">My Account</button>
    <button class="nav-btn-login" style="background:var(--rose-pale);border-color:var(--rose);color:var(--rose-dark);" onclick="openAuthModal('admin')">Admin</button>
  </div>
</nav>

<!-- ══════════ HOME ══════════ -->

<div id="home" class="page active">
  <section class="hero">
    <div class="hero-left">
      <div class="hero-tag">✨ Digital Books for a Better Life</div>
      <h1>Books that <em>uplift,</em> inspire & transform.</h1>
      <p class="hero-desc">Rise & Shine is a growing collection of practical e-books on money, mindset, health, and growth — written clearly, priced fairly, for real people ready to bloom.</p>
      <div class="hero-btns">
        <button onclick="goTo('#store')" class="btn-rose">Shop All Books</button>
        <button onclick="goTo('#featured')" class="btn-ghost">Our Favourite ↓</button>
      </div>
      <div class="hero-stats">
        <div><div class="stat-num">7</div><div class="stat-lbl">Chapters</div></div>
        <div><div class="stat-num">90</div><div class="stat-lbl">Day Plan</div></div>
        <div><div class="stat-num">$7</div><div class="stat-lbl">Only</div></div>
        <div><div class="stat-num">$0</div><div class="stat-lbl">To Start</div></div>
      </div>
    </div>
    <div class="hero-right">
      <img src="https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=900&q=80" alt="Peaceful mountain sunrise">
    </div>
  </section>

  <div class="trust">
    <div class="trust-item">📥 Instant download</div>
    <div class="trust-item">💳 Secure PayPal checkout</div>
    <div class="trust-item">✅ Beginner-friendly</div>
    <div class="trust-item">📧 Delivered to your inbox</div>
    <div class="trust-item">🔄 New books coming soon</div>
  </div>

  <div class="about-strip">
    <div class="about-strip-img">
      <img src="https://images.unsplash.com/photo-1499209974431-9dddcece7f88?w=800&q=80" alt="Morning journal and coffee">
    </div>
    <div class="about-strip-text">
      <span class="tag">Who We Are</span>
      <h2>Two friends building something meaningful.</h2>
      <p>We're Amelia and Veerpal — and we started Rise & Shine because everyone deserves access to clear, practical guidance on the things that shape daily life.</p>
      <p>No fluff. No jargon. Just real knowledge, at a price that makes sense.</p>
      <a onclick="showPage('about')">Read our full story →</a>
    </div>
  </div>

  <section class="categories" id="categories">
    <div class="s-head">
      <span class="tag">Browse by Topic</span>
      <h2>What would you like to work on?</h2>
    </div>
    <div class="cat-grid" id="cat-grid">
      <!-- Populated by JS -->
    </div>
  </section>

  <section class="store" id="store">
    <div class="s-head">
      <span class="tag">The Collection</span>
      <h2>All Books</h2>
      <p>Practical, beginner-friendly guides written for real life.</p>
    </div>
    <div class="books-grid" id="books-grid">
      <!-- Populated by JS -->
    </div>
  </section>

  <section class="featured" id="featured">
    <div class="featured-img">
      <img src="ebook_cover.jpeg" alt="Break Free From Paycheck-to-Paycheck"
           onerror="this.src='https://images.unsplash.com/photo-1554224155-6726b3ff858f?w=800&q=80'">
    </div>
    <div class="featured-text">
      <span class="tag">Start Here</span>
      <h2>Your money. Your rules. Starting now.</h2>
      <p>65% of Americans live paycheck to paycheck — not because they're bad with money, but because nobody ever taught them. This book changes that.</p>
      <ul class="feat-list">
        <li><span class="feat-dot"></span>Build your first $1,000 emergency fund in 90 days</li>
        <li><span class="feat-dot"></span>Crush debt with two proven payoff strategies</li>
        <li><span class="feat-dot"></span>Start investing with as little as $5 a week</li>
        <li><span class="feat-dot"></span>Automate your finances so money runs itself</li>
        <li><span class="feat-dot"></span>Full 90-day week-by-week action plan included</li>
      </ul>
      <div class="feat-price">
        <div class="feat-amount">$7</div>
        <div class="feat-note">One-time · Instant PDF</div>
      </div>
      <button onclick="openCheckout()" class="btn-rose">Get Instant Access →</button>
    </div>
  </section>

  <div class="img-banner">
    <img src="https://images.unsplash.com/photo-1490730141103-6cac27aaab94?w=1400&q=80" alt="Sunrise over calm water">
    <div class="img-banner-overlay">
      <h2>"You don't need to earn six figures. You just need to start."</h2>
      <p>Every great journey begins with a single decision. Make yours today.</p>
    </div>
  </div>

  <section class="why">
    <div class="s-head">
      <span class="tag">Why Rise & Shine</span>
      <h2>Books built for real beginners</h2>
    </div>
    <div class="why-grid">
      <div class="why-card"><div class="why-icon">📖</div><div class="why-title">Plain English</div><div class="why-desc">No jargon. Every concept explained so you can actually use what you learn.</div></div>
      <div class="why-card"><div class="why-icon">⚡</div><div class="why-title">Instantly Actionable</div><div class="why-desc">Every chapter ends with clear steps. You'll know exactly what to do.</div></div>
      <div class="why-card"><div class="why-icon">💰</div><div class="why-title">Affordable Prices</div><div class="why-desc">Quality guidance shouldn't cost a fortune. Priced for everyday budgets.</div></div>
      <div class="why-card"><div class="why-icon">🌱</div><div class="why-title">Real Life Focus</div><div class="why-desc">Written for normal incomes and real obstacles — not hypothetical situations.</div></div>
    </div>
  </section>

  <section class="newsletter" id="newsletter">
    <div class="newsletter-bg">
      <img src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=1400&q=80" alt="Peaceful forest">
    </div>
    <div class="newsletter-inner">
      <span class="tag">Free Gift 🎁</span>
      <h2>Get your free money checklist</h2>
      <p>Join Rise & Shine and receive a free 90-Day Money Transformation Checklist — plus early access to new books and exclusive discounts.</p>
      <div class="email-row">
        <input type="email" class="email-inp" placeholder="Your email address">
        <button class="email-sub">Send It Free →</button>
      </div>
      <p class="email-note">No spam, ever. Unsubscribe anytime.</p>
    </div>
  </section>
</div>

<!-- ══════════ ABOUT ══════════ -->

<div id="about" class="page">
  <section class="inner-page">
    <div class="inner-wrap">
      <span class="inner-tag">Our Story</span>
      <h1>Two friends. One <em>big</em> dream.</h1>
      <div class="inner-bar"></div>
      <div class="prose">
        <p>Rise & Shine was born from a simple belief: that life-changing knowledge shouldn't be locked behind expensive courses or paywalls most people can't afford. It should be clear, practical, and in your hands the moment you need it.</p>
        <p>We're Amelia and Veerpal — two friends who got tired of watching people around us struggle with the same things we once struggled with ourselves. Money stress. Feeling stuck. Knowing something needed to change but not knowing where to start.</p>
        <p>Rise & Shine is our answer. A growing library of beginner-friendly e-books on the topics that actually shape your daily life. Written plainly. Priced fairly. Designed to work.</p>
        <p>We're just getting started — and we're so glad you're here with us.</p>
      </div>
      <div class="founders-row">
        <div class="founder-card"><div class="f-avatar f-teal">🌿</div><div class="f-name">Amelia</div><div class="f-role">Co-Founder</div><div class="f-bio">Amelia brings warmth and creativity. She's the heart behind Rise & Shine's voice — making complex topics feel approachable, human, and real.</div></div>
        <div class="founder-card"><div class="f-avatar f-rose">✨</div><div class="f-name">Veerpal</div><div class="f-role">Co-Founder</div><div class="f-bio">Veerpal is driven by the idea that practical knowledge is the most powerful gift. Detail-oriented and passionate about quality — she makes sure every book is worth every penny.</div></div>
      </div>
      <div class="prose"><p style="font-family:'Playfair Display',serif;font-size:20px;font-style:italic;color:var(--ink);text-align:center;">"We started something new — and we're building it for you." — Amelia & Veerpal</p></div>
      <div style="margin-top:36px;display:flex;gap:14px;flex-wrap:wrap;">
        <button onclick="showPage('home');goTo('#store')" class="btn-teal">Browse Our Books</button>
        <button onclick="showPage('contact')" class="btn-ghost">Get in Touch</button>
      </div>
    </div>
  </section>
</div>

<!-- ══════════ CONTACT ══════════ -->

<div id="contact" class="page">
  <section class="inner-page">
    <div class="inner-wrap">
      <span class="inner-tag">Get in Touch</span>
      <h1>We'd love to <em>hear</em> from you.</h1>
      <div class="inner-bar"></div>
      <div class="prose"><p>Whether you have a question about an order, feedback on a book, or just want to say hello — we read every message.</p></div>
      <div class="contact-row">
        <div class="contact-card"><div class="c-icon">📧</div><div class="c-label">Email Us</div><div class="c-val" id="contact-email-display"><a href="mailto:riseandshinebooks@gmail.com">riseandshinebooks@gmail.com</a></div><div class="c-note">We reply within 1–2 business days.</div></div>
        <div class="contact-card"><div class="c-icon">⏰</div><div class="c-label">Response Time</div><div class="c-val">1–2 Business Days</div><div class="c-note">We're a small team and take every message seriously.</div></div>
      </div>
      <div class="prose">
        <h3>Order & Download Issues</h3>
        <p>Having trouble after purchase? Email us with your payment confirmation and we'll sort it out right away.</p>
        <h3>Partnerships & Collaborations</h3>
        <p>Interested in working with Rise & Shine? We'd love to chat.</p>
      </div>
    </div>
  </section>
</div>

<!-- ══════════ PRIVACY ══════════ -->

<div id="privacy" class="page">
  <section class="inner-page">
    <div class="inner-wrap">
      <span class="inner-tag">Legal</span>
      <h1>Privacy <em>Policy</em></h1>
      <div class="inner-bar"></div>
      <span class="pill-date">Last updated: May 2026</span>
      <div class="prose">
        <p>Rise & Shine is committed to protecting your personal information. This policy explains how we collect, use, and safeguard your data.</p>
        <h3>1. Information We Collect</h3>
        <ul><li><strong>Contact info</strong> — name and email when you sign up or contact us.</li><li><strong>Purchase info</strong> — transaction data via PayPal. We don't store card details.</li><li><strong>Usage data</strong> — basic analytics via cookies.</li></ul>
        <h3>2. How We Use It</h3>
        <ul><li>To process orders and deliver digital products</li><li>To send newsletters you've opted into</li><li>To respond to your enquiries</li><li>To improve our website</li></ul>
        <h3>3. Sharing</h3><p>We do not sell your data. We only share limited data with service providers under confidentiality agreements.</p>
        <h3>4. Your Rights</h3><p>You may request access, correction, or deletion of your data by emailing <strong>riseandshinebooks@gmail.com</strong>.</p>
        <h3>5. Contact</h3><p>Questions? Email <strong>riseandshinebooks@gmail.com</strong>.</p>
      </div>
    </div>
  </section>
</div>

<!-- ══════════ REFUND ══════════ -->

<div id="refund" class="page">
  <section class="inner-page">
    <div class="inner-wrap">
      <span class="inner-tag">Legal</span>
      <h1>Refund <em>Policy</em></h1>
      <div class="inner-bar"></div>
      <span class="pill-date">Last updated: May 2026</span>
      <div class="prose">
        <p>Please read carefully before purchasing from Rise & Shine.</p>
        <h3>All Sales Are Final</h3>
        <p>Due to the digital nature of our products, <strong>all sales are final</strong>. We do not offer refunds, exchanges, or credits once a purchase is completed.</p>
        <h3>Before You Buy</h3>
        <p>Read all product descriptions carefully. Email <strong>riseandshinebooks@gmail.com</strong> with any questions before purchasing.</p>
        <h3>Technical Issues</h3>
        <p>If you can't access your purchase due to a technical error, contact us immediately — we will always ensure you receive what you paid for.</p>
      </div>
      <div style="margin-top:32px;"><button onclick="showPage('contact')" class="btn-teal">Contact Us</button></div>
    </div>
  </section>
</div>

<!-- ══════════ CUSTOMER DASHBOARD ══════════ -->

<div id="customer-dash" class="page">
  <div class="cust-dash">
    <div class="cust-header">
      <h1>Welcome back, <span id="cust-name-display">Reader</span> 👋</h1>
      <button onclick="logout()" class="btn-ghost" style="padding:10px 22px;font-size:13px;">Sign Out</button>
    </div>
    <p style="font-size:15px;color:var(--ink-light);margin-bottom:32px;">Your purchased books appear here. After payment, email us and we'll add your book to your library.</p>
    <div class="cust-grid" id="cust-purchases">
      <div class="cust-empty">
        <div>📚</div>
        <p>No purchases yet.<br>Head to the <a onclick="showPage('home');goTo('#store')" style="color:var(--teal);cursor:pointer;font-weight:700;">store</a> to get your first book!</p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════ ADMIN DASHBOARD ══════════ -->

<div id="admin" class="page">
  <div class="admin-layout">
    <!-- SIDEBAR -->
    <aside class="admin-sidebar">
      <div class="admin-logo">Rise<span>&</span>Shine</div>
      <span class="admin-role">Merchant Portal</span>
      <ul class="admin-nav">
        <li><a onclick="adminTab('overview')" class="active" id="tab-overview"><span class="nav-icon">📊</span> Overview</a></li>
        <li><a onclick="adminTab('products')" id="tab-products"><span class="nav-icon">📚</span> Products</a></li>
        <li><a onclick="adminTab('add-product')" id="tab-add-product"><span class="nav-icon">➕</span> Add Product</a></li>
        <li><a onclick="adminTab('store-settings')" id="tab-store-settings"><span class="nav-icon">⚙️</span> Store Settings</a></li>
        <li><a onclick="adminTab('contact-settings')" id="tab-contact-settings"><span class="nav-icon">📧</span> Contact Info</a></li>
        <div class="admin-divider"></div>
        <li><a onclick="showPage('home')" id="tab-view-store"><span class="nav-icon">🌐</span> View Store</a></li>
        <li><a onclick="logout()"><span class="nav-icon">🚪</span> Sign Out</a></li>
      </ul>
    </aside>

```
<!-- MAIN -->
<main class="admin-main">
  <div class="admin-topbar">
    <h1>Admin <span>Dashboard</span></h1>
    <div class="admin-user-pill">
      <span>👑 Amelia & Veerpal</span>
      <button class="admin-logout" onclick="logout()">Sign out</button>
    </div>
  </div>

  <!-- OVERVIEW -->
  <div class="admin-panel active" id="panel-overview">
    <div class="admin-stats">
      <div class="admin-stat"><div class="admin-stat-icon">📚</div><div class="admin-stat-num" id="stat-products">1</div><div class="admin-stat-lbl">Total Products</div></div>
      <div class="admin-stat"><div class="admin-stat-icon">✅</div><div class="admin-stat-num" id="stat-live">1</div><div class="admin-stat-lbl">Live Products</div></div>
      <div class="admin-stat"><div class="admin-stat-icon">⏳</div><div class="admin-stat-num" id="stat-soon">2</div><div class="admin-stat-lbl">Coming Soon</div></div>
      <div class="admin-stat"><div class="admin-stat-icon">💳</div><div class="admin-stat-num">PayPal</div><div class="admin-stat-lbl">Payment Method</div></div>
    </div>
    <div class="admin-card">
      <div class="admin-card-title">Quick Actions</div>
      <div style="display:flex;gap:12px;flex-wrap:wrap;">
        <button onclick="adminTab('add-product')" class="admin-btn">➕ Add New Product</button>
        <button onclick="adminTab('store-settings')" class="admin-btn">⚙️ Store Settings</button>
        <button onclick="adminTab('contact-settings')" class="admin-btn">📧 Update Contact</button>
        <button onclick="showPage('home')" class="admin-btn" style="background:rgba(255,255,255,.1);">🌐 View Live Store</button>
      </div>
    </div>
    <div class="admin-card">
      <div class="admin-card-title">💡 Manual Delivery Reminder</div>
      <p style="font-size:14px;color:rgba(255,255,255,.6);line-height:1.7;">When a customer pays via PayPal, you'll receive an email notification. Reply to the customer with the PDF attached using your delivery email template. Aim to send within a few hours of payment.</p>
    </div>
  </div>

  <!-- PRODUCTS -->
  <div class="admin-panel" id="panel-products">
    <div class="admin-section-title">Manage Products</div>
    <div class="admin-card">
      <table class="admin-table">
        <thead><tr><th>Product</th><th>Category</th><th>Price</th><th>Status</th><th>Actions</th></tr></thead>
        <tbody id="admin-products-table"></tbody>
      </table>
    </div>
  </div>

  <!-- ADD PRODUCT -->
  <div class="admin-panel" id="panel-add-product">
    <div class="admin-section-title" id="add-product-title">Add New Product</div>
    <div class="admin-card">
      <div class="admin-form" id="product-form">
        <div class="admin-field">
          <label class="admin-label">Product Title</label>
          <input class="admin-input" id="prod-title" placeholder="e.g. Mindset Reset">
        </div>
        <div class="admin-field">
          <label class="admin-label">Category</label>
          <select class="admin-select" id="prod-cat">
            <option>Personal Finance</option>
            <option>Self-Improvement</option>
            <option>Health & Wellness</option>
            <option>Career & Business</option>
            <option>Relationships</option>
          </select>
        </div>
        <div class="admin-field">
          <label class="admin-label">Price (USD)</label>
          <input class="admin-input" id="prod-price" type="number" placeholder="7" min="0">
        </div>
        <div class="admin-field">
          <label class="admin-label">Status</label>
          <select class="admin-select" id="prod-status">
            <option value="live">Live</option>
            <option value="soon">Coming Soon</option>
          </select>
        </div>
        <div class="admin-field full">
          <label class="admin-label">Description</label>
          <textarea class="admin-textarea" id="prod-desc" placeholder="Short description of the book..."></textarea>
        </div>
        <div class="admin-field full">
          <label class="admin-label">Cover Colour (for placeholder)</label>
          <select class="admin-select" id="prod-colour">
            <option value="cover-teal">Teal</option>
            <option value="cover-rose">Rose</option>
            <option value="cover-lav">Lavender</option>
          </select>
        </div>
        <div class="admin-field full">
          <label class="admin-label">Cover Emoji</label>
          <input class="admin-input" id="prod-emoji" placeholder="💵" maxlength="2">
        </div>
      </div>
      <div style="margin-top:24px;display:flex;gap:12px;align-items:center;">
        <button onclick="saveProduct()" class="admin-btn">💾 Save Product</button>
        <button onclick="cancelEdit()" class="admin-btn" style="background:rgba(255,255,255,.08);" id="cancel-edit-btn">Cancel</button>
        <span class="admin-save-msg" id="product-save-msg">✓ Product saved!</span>
      </div>
    </div>
  </div>

  <!-- STORE SETTINGS -->
  <div class="admin-panel" id="panel-store-settings">
    <div class="admin-section-title">Store Settings</div>
    <div class="admin-card">
      <div class="admin-card-title">PayPal Payment Link</div>
      <div class="admin-form single">
        <div class="admin-field">
          <label class="admin-label">PayPal Checkout URL</label>
          <input class="admin-input" id="setting-paypal" value="https://www.paypal.com/ncp/payment/9HGP4FXCKBAC2" placeholder="https://www.paypal.com/ncp/payment/...">
        </div>
      </div>
      <button onclick="saveSettings()" class="admin-btn" style="margin-top:18px;">💾 Save Settings</button>
      <span class="admin-save-msg" id="settings-save-msg">✓ Settings saved!</span>
    </div>
    <div class="admin-card" style="margin-top:0;">
      <div class="admin-card-title">Store Visibility</div>
      <div style="display:flex;flex-direction:column;gap:16px;">
        <div class="toggle-wrap">
          <label class="toggle"><input type="checkbox" checked><span class="toggle-slider"></span></label>
          <span class="toggle-label">Store is live and accepting customers</span>
        </div>
        <div class="toggle-wrap">
          <label class="toggle"><input type="checkbox" checked><span class="toggle-slider"></span></label>
          <span class="toggle-label">Show "Coming Soon" products</span>
        </div>
        <div class="toggle-wrap">
          <label class="toggle"><input type="checkbox" checked><span class="toggle-slider"></span></label>
          <span class="toggle-label">Show newsletter signup section</span>
        </div>
      </div>
    </div>
  </div>

  <!-- CONTACT SETTINGS -->
  <div class="admin-panel" id="panel-contact-settings">
    <div class="admin-section-title">Contact Information</div>
    <div class="admin-card">
      <div class="admin-form">
        <div class="admin-field full">
          <label class="admin-label">Business Email</label>
          <input class="admin-input" id="setting-email" value="riseandshinebooks@gmail.com" placeholder="your@email.com">
        </div>
        <div class="admin-field">
          <label class="admin-label">Founder 1 Name</label>
          <input class="admin-input" id="setting-founder1" value="Amelia" placeholder="Name">
        </div>
        <div class="admin-field">
          <label class="admin-label">Founder 2 Name</label>
          <input class="admin-input" id="setting-founder2" value="Veerpal" placeholder="Name">
        </div>
        <div class="admin-field full">
          <label class="admin-label">Instagram Handle (optional)</label>
          <input class="admin-input" id="setting-instagram" placeholder="@riseandshinebooks">
        </div>
      </div>
      <button onclick="saveContactSettings()" class="admin-btn" style="margin-top:20px;">💾 Save Contact Info</button>
      <span class="admin-save-msg" id="contact-save-msg">✓ Contact info saved!</span>
    </div>
  </div>

</main>
```

  </div>
</div>

<!-- FOOTER -->

<footer id="main-footer">
  <div class="footer-grid">
    <div class="f-brand">
      <a class="nav-logo" onclick="showPage('home')" style="color:var(--sand);">Rise<span style="color:var(--rose);font-style:italic;">&</span>Shine</a>
      <p>Practical e-books for people ready to grow. Privately owned by Amelia & Veerpal.</p>
      <div class="f-email">📧 <a href="mailto:riseandshinebooks@gmail.com">riseandshinebooks@gmail.com</a></div>
    </div>
    <div class="f-col">
      <h4>Books</h4>
      <a onclick="showPage('home');goTo('#store')">Browse All Books</a>
      <a onclick="showPage('home');goTo('#newsletter')">Join Waitlist</a>
    </div>
    <div class="f-col">
      <h4>Company</h4>
      <a onclick="showPage('about')">About Us</a>
      <a onclick="showPage('contact')">Contact</a>
      <a onclick="showPage('privacy')">Privacy Policy</a>
      <a onclick="showPage('refund')">Refund Policy</a>
    </div>
  </div>
  <div class="f-bottom">
    <span>© 2026 Rise & Shine. All rights reserved.</span>
    <span>Made with ☀️ by Amelia & Veerpal</span>
  </div>
</footer>

<!-- ═══ AUTH MODAL ═══ -->

<div id="auth-modal" class="modal-overlay">
  <div class="modal-box">
    <button class="modal-close" onclick="closeModal('auth-modal')">✕</button>
    <div class="modal-logo">Rise<span>&</span>Shine</div>
    <div class="modal-subtitle" id="auth-subtitle">Sign in to your account</div>
    <div class="modal-tabs">
      <button class="modal-tab active" id="tab-signin" onclick="switchAuthTab('signin')">Sign In</button>
      <button class="modal-tab" id="tab-signup" onclick="switchAuthTab('signup')">Create Account</button>
    </div>
    <div class="auth-err" id="auth-err"></div>
    <div class="auth-form" id="signin-form">
      <div>
        <label>Email</label>
        <input type="email" id="signin-email" placeholder="your@email.com">
      </div>
      <div>
        <label>Password</label>
        <input type="password" id="signin-password" placeholder="••••••••">
      </div>
      <button class="auth-submit" onclick="doSignIn()">Sign In</button>
      <p class="auth-msg">Admin login: use your merchant credentials</p>
    </div>
    <div class="auth-form" id="signup-form" style="display:none;">
      <div>
        <label>Your Name</label>
        <input type="text" id="signup-name" placeholder="e.g. Jessica">
      </div>
      <div>
        <label>Email</label>
        <input type="email" id="signup-email" placeholder="your@email.com">
      </div>
      <div>
        <label>Password</label>
        <input type="password" id="signup-password" placeholder="Choose a password">
      </div>
      <button class="auth-submit" onclick="doSignUp()">Create Account</button>
    </div>
  </div>
</div>

<!-- ═══ CHECKOUT MODAL ═══ -->

<div id="checkout-modal" class="modal-overlay">
  <div class="modal-box">
    <button class="modal-close" onclick="closeModal('checkout-modal')">✕</button>
    <div class="modal-emoji">💵</div>
    <div class="modal-title">Break Free From Paycheck-to-Paycheck</div>
    <div class="modal-sub">Instant PDF Download · 2026 Edition · 7 Chapters</div>
    <div class="modal-price-big">$7</div>
    <div class="modal-note">One-time payment · No subscription</div>
    <a href="https://www.paypal.com/ncp/payment/9HGP4FXCKBAC2" target="_blank" class="paypal-btn">💳 &nbsp;Pay $7 with PayPal</a>
    <div class="modal-secure">🔒 Secure checkout via PayPal · E-book delivered to your email within a few hours</div>
  </div>
</div>

<script>
// ═══════════════════════════════
// DATA STORE
// ═══════════════════════════════
let storeData = {
  paypalLink: "https://www.paypal.com/ncp/payment/9HGP4FXCKBAC2",
  email: "riseandshinebooks@gmail.com",
  products: [
    { id:1, title:"Break Free From Paycheck-to-Paycheck", category:"Personal Finance", price:7, status:"live", desc:"The complete beginner's guide to budgeting, crushing debt, building an emergency fund, and starting to invest — even on a tight income.", emoji:"💵", colour:"cover-teal", stars:true, badge:"⭐ Bestseller", img:"ebook_cover.jpeg" },
    { id:2, title:"Mindset Reset", category:"Self-Improvement", price:9, status:"soon", desc:"Rewire the thought patterns holding you back and build the mental habits of high-performers — starting from zero.", emoji:"🧠", colour:"cover-lav", stars:false },
    { id:3, title:"Eat Well, Feel Well", category:"Health & Wellness", price:8, status:"soon", desc:"Simple, sustainable nutrition habits for busy people who want to feel better without complicated diets.", emoji:"💪", colour:"cover-rose", stars:false },
  ],
  users: [
    { email:"admin@riseandshinebooks.com", password:"riseshine2026", role:"admin" },
    { email:"amelia@riseandshinebooks.com", password:"riseshine2026", role:"admin" },
    { email:"veerpal@riseandshinebooks.com", password:"riseshine2026", role:"admin" },
  ],
  currentUser: null,
  editingProductId: null
};

// ═══════════════════════════════
// PAGE NAVIGATION
// ═══════════════════════════════
function showPage(id) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  const isAdmin = id === 'admin';
  document.getElementById('main-nav').style.display = isAdmin ? 'none' : '';
  document.getElementById('main-footer').style.display = isAdmin ? 'none' : '';
  window.scrollTo({ top:0, behavior:'smooth' });
}

function goTo(selector) {
  setTimeout(() => {
    const el = document.querySelector(selector);
    if (el) el.scrollIntoView({ behavior:'smooth' });
  }, 120);
}

// ═══════════════════════════════
// AUTH
// ═══════════════════════════════
let authMode = 'customer';

function openAuthModal(mode) {
  authMode = mode;
  document.getElementById('auth-subtitle').textContent = mode === 'admin' ? 'Merchant sign in' : 'Sign in to your account';
  document.getElementById('auth-err').style.display = 'none';
  clearAuthFields();
  openModal('auth-modal');
}

function switchAuthTab(tab) {
  document.getElementById('signin-form').style.display = tab === 'signin' ? 'flex' : 'none';
  document.getElementById('signup-form').style.display = tab === 'signup' ? 'flex' : 'none';
  document.getElementById('tab-signin').classList.toggle('active', tab === 'signin');
  document.getElementById('tab-signup').classList.toggle('active', tab === 'signup');
  document.getElementById('auth-err').style.display = 'none';
}

function clearAuthFields() {
  ['signin-email','signin-password','signup-name','signup-email','signup-password'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.value = '';
  });
}

function showAuthErr(msg) {
  const el = document.getElementById('auth-err');
  el.textContent = msg;
  el.style.display = 'block';
}

function doSignIn() {
  const email = document.getElementById('signin-email').value.trim().toLowerCase();
  const password = document.getElementById('signin-password').value;
  if (!email || !password) return showAuthErr('Please fill in all fields.');

  const found = storeData.users.find(u => u.email.toLowerCase() === email && u.password === password);

  if (found) {
    storeData.currentUser = found;
    closeModal('auth-modal');
    if (found.role === 'admin') {
      showPage('admin');
      renderAdminProducts();
      updateAdminStats();
    } else {
      document.getElementById('cust-name-display').textContent = found.name || 'Reader';
      showPage('customer-dash');
    }
  } else {
    showAuthErr('Incorrect email or password. Try again.');
  }
}

function doSignUp() {
  const name = document.getElementById('signup-name').value.trim();
  const email = document.getElementById('signup-email').value.trim().toLowerCase();
  const password = document.getElementById('signup-password').value;
  if (!name || !email || !password) return showAuthErr('Please fill in all fields.');
  if (password.length < 6) return showAuthErr('Password must be at least 6 characters.');
  if (storeData.users.find(u => u.email.toLowerCase() === email)) return showAuthErr('An account with this email already exists.');

  const newUser = { email, password, name, role:'customer' };
  storeData.users.push(newUser);
  storeData.currentUser = newUser;
  closeModal('auth-modal');
  document.getElementById('cust-name-display').textContent = name;
  showPage('customer-dash');
}

function logout() {
  storeData.currentUser = null;
  showPage('home');
}

// ═══════════════════════════════
// MODALS
// ═══════════════════════════════
function openModal(id) {
  document.getElementById(id).style.display = 'flex';
  document.body.style.overflow = 'hidden';
}

function closeModal(id) {
  document.getElementById(id).style.display = 'none';
  document.body.style.overflow = '';
}

function openCheckout() {
  // Update PayPal link dynamically
  document.querySelector('.paypal-btn').href = storeData.paypalLink;
  openModal('checkout-modal');
}

// Close modals on overlay click
document.querySelectorAll('.modal-overlay').forEach(overlay => {
  overlay.addEventListener('click', function(e) {
    if (e.target === this) closeModal(this.id);
  });
});

// ═══════════════════════════════
// RENDER STORE
// ═══════════════════════════════
function renderStore() {
  const grid = document.getElementById('books-grid');
  grid.innerHTML = storeData.products.map(p => `
    <div class="book-card">
      <div class="book-cover-area">
        ${p.img ? `<img src="${p.img}" alt="${p.title}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex';">` : ''}
        <div class="book-cover-fallback ${p.colour}" style="display:${p.img ? 'none' : 'flex'};">
          <div style="font-size:40px;margin-bottom:8px;">${p.emoji}</div>
          <div style="font-family:'Playfair Display',serif;font-size:17px;font-weight:700;color:#fff;line-height:1.2;">${p.title}</div>
        </div>
        <span class="book-badge ${p.status === 'soon' ? 'soon' : ''}">${p.status === 'live' ? (p.badge || '⭐ Bestseller') : '🔔 Coming Soon'}</span>
      </div>
      <div class="book-body">
        <div class="book-cat">${p.category}</div>
        ${p.stars ? '<div class="book-stars">★★★★★</div>' : ''}
        <div class="book-title">${p.title}</div>
        <div class="book-blurb">${p.desc}</div>
        <div class="book-foot">
          <div class="book-price-num"><sup>$</sup>${p.price}</div>
          ${p.status === 'live'
            ? `<button onclick="openCheckout()" class="btn-buy">Buy Now →</button>`
            : `<button onclick="goTo('#newsletter')" class="btn-buy btn-waitlist">Join Waitlist</button>`
          }
        </div>
      </div>
    </div>
  `).join('');
}

function renderCategories() {
  const cats = [...new Set(storeData.products.map(p => p.category))];
  const emojis = { 'Personal Finance':'💵','Self-Improvement':'🧠','Health & Wellness':'💪','Career & Business':'💼','Relationships':'❤️' };
  const all = [
    ...cats.map(c => ({ name:c, emoji: emojis[c] || '📖', count: storeData.products.filter(p=>p.category===c).length })),
    { name:'Mindset', emoji:'🧘', count:0, soon:true },
    { name:'Career & Business', emoji:'💼', count:0, soon:true },
    { name:'Relationships', emoji:'❤️', count:0, soon:true },
  ].filter((v,i,a)=>a.findIndex(t=>t.name===v.name)===i);

  document.getElementById('cat-grid').innerHTML = all.map((c,i) => `
    <a onclick="goTo('#store')" class="cat-pill ${i===0?'active':''}">
      <span class="cat-emoji">${c.emoji}</span>
      <div class="cat-name">${c.name}</div>
      <div class="cat-count">${c.count > 0 ? c.count+' book'+(c.count>1?'s':'') : 'Coming soon'}</div>
    </a>
  `).join('');
}

// ═══════════════════════════════
// ADMIN
// ═══════════════════════════════
function adminTab(tab) {
  document.querySelectorAll('.admin-panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.admin-nav a').forEach(a => a.classList.remove('active'));
  document.getElementById('panel-'+tab).classList.add('active');
  const tabEl = document.getElementById('tab-'+tab);
  if (tabEl) tabEl.classList.add('active');
  if (tab === 'products') renderAdminProducts();
}

function renderAdminProducts() {
  const tbody = document.getElementById('admin-products-table');
  tbody.innerHTML = storeData.products.map(p => `
    <tr>
      <td><strong style="color:#fff;">${p.emoji} ${p.title}</strong></td>
      <td>${p.category}</td>
      <td><strong style="color:#fff;">$${p.price}</strong></td>
      <td><span class="tbl-badge ${p.status === 'live' ? 'tbl-live' : 'tbl-soon'}">${p.status === 'live' ? '● Live' : '○ Soon'}</span></td>
      <td><div class="tbl-actions">
        <button onclick="editProduct(${p.id})" class="tbl-btn tbl-edit">✏️ Edit</button>
        <button onclick="deleteProduct(${p.id})" class="tbl-btn tbl-del">🗑 Delete</button>
      </div></td>
    </tr>
  `).join('');
}

function updateAdminStats() {
  document.getElementById('stat-products').textContent = storeData.products.length;
  document.getElementById('stat-live').textContent = storeData.products.filter(p=>p.status==='live').length;
  document.getElementById('stat-soon').textContent = storeData.products.filter(p=>p.status==='soon').length;
}

function saveProduct() {
  const title   = document.getElementById('prod-title').value.trim();
  const cat     = document.getElementById('prod-cat').value;
  const price   = parseFloat(document.getElementById('prod-price').value);
  const status  = document.getElementById('prod-status').value;
  const desc    = document.getElementById('prod-desc').value.trim();
  const colour  = document.getElementById('prod-colour').value;
  const emoji   = document.getElementById('prod-emoji').value || '📖';

  if (!title || !price || !desc) return alert('Please fill in all required fields.');

  if (storeData.editingProductId) {
    const idx = storeData.products.findIndex(p => p.id === storeData.editingProductId);
    if (idx > -1) {
      storeData.products[idx] = { ...storeData.products[idx], title, category:cat, price, status, desc, colour, emoji };
    }
    storeData.editingProductId = null;
    document.getElementById('add-product-title').textContent = 'Add New Product';
    document.getElementById('cancel-edit-btn').style.display = 'none';
  } else {
    const newId = Math.max(...storeData.products.map(p=>p.id), 0) + 1;
    storeData.products.push({ id:newId, title, category:cat, price, status, desc, emoji, colour, stars:false });
  }

  // Clear form
  ['prod-title','prod-price','prod-desc','prod-emoji'].forEach(id => document.getElementById(id).value = '');

  // Show saved message
  const msg = document.getElementById('product-save-msg');
  msg.style.display = 'inline';
  setTimeout(() => msg.style.display = 'none', 2500);

  renderStore();
  renderCategories();
  updateAdminStats();
}

function editProduct(id) {
  const p = storeData.products.find(p => p.id === id);
  if (!p) return;
  storeData.editingProductId = id;
  document.getElementById('prod-title').value    = p.title;
  document.getElementById('prod-cat').value      = p.category;
  document.getElementById('prod-price').value    = p.price;
  document.getElementById('prod-status').value   = p.status;
  document.getElementById('prod-desc').value     = p.desc;
  document.getElementById('prod-colour').value   = p.colour;
  document.getElementById('prod-emoji').value    = p.emoji;
  document.getElementById('add-product-title').textContent = '✏️ Edit Product';
  document.getElementById('cancel-edit-btn').style.display = 'inline-block';
  adminTab('add-product');
}

function cancelEdit() {
  storeData.editingProductId = null;
  ['prod-title','prod-price','prod-desc','prod-emoji'].forEach(id => document.getElementById(id).value = '');
  document.getElementById('add-product-title').textContent = 'Add New Product';
  document.getElementById('cancel-edit-btn').style.display = 'none';
}

function deleteProduct(id) {
  if (!confirm('Are you sure you want to delete this product?')) return;
  storeData.products = storeData.products.filter(p => p.id !== id);
  renderAdminProducts();
  renderStore();
  renderCategories();
  updateAdminStats();
}

function saveSettings() {
  storeData.paypalLink = document.getElementById('setting-paypal').value.trim();
  const msg = document.getElementById('settings-save-msg');
  msg.style.display = 'inline';
  setTimeout(() => msg.style.display = 'none', 2500);
}

function saveContactSettings() {
  const email = document.getElementById('setting-email').value.trim();
  storeData.email = email;
  // Update contact page display
  const el = document.getElementById('contact-email-display');
  if (el) el.innerHTML = `<a href="mailto:${email}">${email}</a>`;
  const msg = document.getElementById('contact-save-msg');
  msg.style.display = 'inline';
  setTimeout(() => msg.style.display = 'none', 2500);
}

// ═══════════════════════════════
// INIT
// ═══════════════════════════════
renderStore();
renderCategories();
document.getElementById('cancel-edit-btn').style.display = 'none';
</script>

</body>
</html>
