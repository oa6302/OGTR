<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>README · Okul Gelişimi ve Akademik Başarıyı İzleme Raporu</title>
<style>
  :root{
    --navy-950:#04102a; --navy-900:#061631; --navy-800:#0b2350; --navy-700:#133a72;
    --navy-600:#1c4a8e; --navy-500:#2a5ba8;
    --orange-600:#e8571a; --orange-500:#ff6b2c; --orange-400:#ff8c42; --orange-300:#ffb07c; --orange-100:#ffe8d6;
    --white:#ffffff; --gray-50:#f8fafc; --gray-100:#f1f5f9; --gray-200:#e2e8f0;
    --gray-300:#cbd5e1; --gray-400:#94a3b8; --gray-500:#64748b; --gray-600:#475569;
    --gray-700:#334155; --gray-800:#1e293b;
    --green:#16a34a; --red:#dc2626; --blue:#2563eb;
    --shadow:0 4px 16px rgba(6,22,49,.08);
    --shadow-lg:0 24px 48px -16px rgba(6,22,49,.22);
    --shadow-orange:0 12px 32px -10px rgba(255,107,44,.5);
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth; scroll-padding-top:80px;}
  body{
    font-family:"Inter","Segoe UI",-apple-system,BlinkMacSystemFont,Roboto,Arial,sans-serif;
    background:
      radial-gradient(900px 500px at 12% 0%, rgba(255,140,66,.07), transparent 60%),
      radial-gradient(800px 500px at 100% 20%, rgba(28,74,142,.07), transparent 60%),
      var(--gray-50);
    color:var(--navy-900); line-height:1.65;
    -webkit-font-smoothing:antialiased;
    min-height:100vh;
  }

  /* NAVBAR */
  .nav{position:sticky; top:0; z-index:100;
    background:rgba(255,255,255,.9);
    backdrop-filter:blur(18px) saturate(180%);
    -webkit-backdrop-filter:blur(18px) saturate(180%);
    border-bottom:1px solid var(--gray-200);}
  .nav-inner{max-width:1220px; margin:0 auto; padding:12px 24px;
    display:flex; align-items:center; justify-content:space-between; gap:16px;}
  .brand{display:flex; align-items:center; gap:12px; min-width:0;}
  .logo{width:42px; height:42px; flex:0 0 42px;
    background:linear-gradient(135deg, var(--navy-700), var(--navy-900));
    border-radius:12px; display:grid; place-items:center; color:#fff;
    font-weight:800; font-size:18px; position:relative; overflow:hidden;
    box-shadow:0 8px 20px -6px rgba(6,22,49,.45);}
  .logo::after{content:""; position:absolute; width:8px; height:8px; border-radius:50%;
    background:var(--orange-500); right:5px; top:5px; box-shadow:0 0 10px var(--orange-400);}
  .brand-text strong{display:block; font-size:13.5px; font-weight:800;
    color:var(--navy-900); letter-spacing:-.01em;}
  .brand-text span{display:block; font-size:11px; color:var(--gray-500); margin-top:1px;}

  .nav-links{display:flex; align-items:center; gap:6px; flex-wrap:wrap;}
  .nav-links a{font-size:12.5px; font-weight:700; color:var(--gray-600);
    text-decoration:none; padding:8px 14px; border-radius:9px;
    transition:all .18s ease; white-space:nowrap;}
  .nav-links a:hover{background:var(--gray-100); color:var(--navy-900);}
  .nav-links a.active{background:linear-gradient(135deg, var(--orange-500), var(--orange-600));
    color:#fff; box-shadow:0 6px 16px -6px rgba(255,107,44,.6);}

  .btn-back{background:#fff; color:var(--navy-800);
    border:1.5px solid var(--gray-300); cursor:pointer; font:inherit;
    font-weight:700; font-size:12.5px; padding:9px 15px; border-radius:10px;
    display:inline-flex; align-items:center; gap:7px;
    text-decoration:none; transition:all .18s ease; white-space:nowrap;}
  .btn-back:hover{background:var(--gray-100); border-color:var(--navy-700); color:var(--navy-700);}

  /* LAYOUT */
  .container{max-width:1220px; margin:0 auto; padding:0 24px;}

  /* HERO */
  .hero{
    background:
      radial-gradient(700px 400px at 85% 20%, rgba(255,140,66,.28), transparent 62%),
      radial-gradient(600px 500px at 5% 100%, rgba(28,74,142,.55), transparent 60%),
      linear-gradient(140deg, var(--navy-900) 0%, var(--navy-800) 48%, var(--navy-950) 100%);
    color:#fff; padding:70px 0 90px; position:relative; overflow:hidden;
    margin-bottom:-40px;
  }
  .hero::before{
    content:""; position:absolute; inset:0;
    background-image:
      linear-gradient(rgba(255,255,255,.045) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,.045) 1px, transparent 1px);
    background-size:48px 48px;
    mask-image:radial-gradient(ellipse at center, #000 22%, transparent 78%);
    -webkit-mask-image:radial-gradient(ellipse at center, #000 22%, transparent 78%);
    pointer-events:none;
  }
  .hero-inner{position:relative; z-index:2; max-width:1220px; margin:0 auto; padding:0 24px;}
  .hero-tag{
    display:inline-flex; align-items:center; gap:9px;
    font-size:11px; font-weight:700; letter-spacing:.22em;
    color:var(--orange-300); text-transform:uppercase;
    background:rgba(255,107,44,.12);
    border:1px solid rgba(255,140,66,.35);
    padding:9px 20px; border-radius:999px; margin-bottom:26px;
  }
  .hero-tag::before{content:""; width:7px; height:7px; border-radius:50%;
    background:var(--orange-500); box-shadow:0 0 12px var(--orange-400);}
  .hero h1{font-size:clamp(28px,4.5vw,46px); line-height:1.1;
    font-weight:800; letter-spacing:-.03em; margin-bottom:18px; max-width:800px;}
  .hero h1 em{font-style:normal;
    background:linear-gradient(100deg, var(--orange-400), var(--orange-300));
    -webkit-background-clip:text; background-clip:text; color:transparent;}
  .hero p{font-size:16px; color:rgba(255,255,255,.78);
    font-weight:500; max-width:680px; line-height:1.6;}
  .hero-meta{display:flex; gap:12px; margin-top:26px; flex-wrap:wrap;}
  .hero-chip{display:inline-flex; align-items:center; gap:7px;
    background:rgba(255,255,255,.08); border:1px solid rgba(255,255,255,.15);
    padding:8px 15px; border-radius:10px;
    font-size:12px; font-weight:700; color:rgba(255,255,255,.9);}
  .hero-chip b{color:var(--orange-300);}

  /* MAIN CARD */
  main{position:relative; z-index:3; padding-bottom:80px;}
  .paper{
    background:#fff; border:1px solid var(--gray-200);
    border-radius:20px; padding:50px 56px;
    box-shadow:var(--shadow-lg);
  }

  /* TOC */
  .toc{
    background:var(--gray-50); border:1px solid var(--gray-200);
    border-radius:14px; padding:22px 26px; margin-bottom:44px;
  }
  .toc-title{
    font-size:11.5px; font-weight:800; letter-spacing:.14em;
    color:var(--gray-500); text-transform:uppercase;
    display:flex; align-items:center; gap:8px; margin-bottom:14px;
  }
  .toc-title::before{
    content:"📖"; font-size:14px; letter-spacing:0;
  }
  .toc-grid{display:grid;
    grid-template-columns:repeat(auto-fit, minmax(220px, 1fr)); gap:6px 24px;}
  .toc-grid a{
    font-size:13px; font-weight:600; color:var(--navy-700);
    text-decoration:none; padding:6px 0; display:flex; align-items:center; gap:8px;
    transition:all .18s ease; border-bottom:1px dashed transparent;
  }
  .toc-grid a:hover{color:var(--orange-600); border-bottom-color:var(--orange-300);}
  .toc-grid a::before{
    content:""; width:6px; height:6px; border-radius:50%;
    background:var(--orange-500); flex-shrink:0;
  }

  /* SECTIONS */
  section{margin-bottom:52px; scroll-margin-top:84px;}

  .section-head{
    display:flex; align-items:center; gap:14px;
    margin-bottom:22px; padding-bottom:14px;
    border-bottom:2px solid var(--gray-200);
  }
  .section-num{
    flex:0 0 auto; min-width:44px; height:44px; padding:0 12px;
    background:linear-gradient(135deg, var(--navy-700), var(--navy-900));
    border-radius:12px; display:grid; place-items:center;
    color:#fff; font-weight:800; font-size:14px; letter-spacing:.02em;
    box-shadow:0 6px 16px -4px rgba(6,22,49,.35);
    position:relative;
  }
  .section-num::after{
    content:""; position:absolute; bottom:-3px; right:-3px;
    width:10px; height:10px; border-radius:50%;
    background:var(--orange-500); border:2px solid #fff;
    box-shadow:0 0 8px rgba(255,107,44,.7);
  }
  .section-head h2{
    font-size:clamp(18px,2vw,22px); font-weight:800;
    letter-spacing:-.02em; color:var(--navy-900); line-height:1.3;
  }
  .section-head p{
    font-size:13px; color:var(--gray-500); margin-top:3px; font-weight:500;
  }

  /* Content */
  h3{
    font-size:15.5px; font-weight:800; color:var(--navy-900);
    margin:26px 0 12px; letter-spacing:-.01em;
    display:flex; align-items:center; gap:9px;
  }
  h3::before{
    content:""; width:4px; height:15px; border-radius:4px;
    background:linear-gradient(180deg, var(--orange-500), var(--orange-600));
  }

  p{margin-bottom:14px; font-size:14px; color:var(--gray-700); line-height:1.7;}
  p b{color:var(--navy-900); font-weight:700;}
  a{color:var(--orange-600); font-weight:600; text-decoration:none;}
  a:hover{text-decoration:underline;}

  ul, ol{margin:12px 0 16px 24px; font-size:14px; color:var(--gray-700); line-height:1.75;}
  ul li, ol li{margin-bottom:6px;}
  ul li b, ol li b{color:var(--navy-900); font-weight:700;}

  code{
    background:var(--gray-100); color:var(--navy-800);
    padding:2px 8px; border-radius:6px;
    font-family:"JetBrains Mono","Fira Code",Consolas,monospace;
    font-size:12.5px; font-weight:600;
    border:1px solid var(--gray-200);
  }

  /* KBD */
  kbd{
    display:inline-block;
    background:linear-gradient(180deg, #fff, var(--gray-100));
    border:1px solid var(--gray-300);
    border-bottom-width:2px;
    border-radius:7px;
    padding:3px 9px;
    font-family:"JetBrains Mono",Consolas,monospace;
    font-size:11.5px; font-weight:700; color:var(--navy-800);
    box-shadow:0 1px 0 var(--gray-300);
    min-width:22px; text-align:center;
    margin:0 2px;
  }

  /* Feature cards */
  .feature-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(260px, 1fr));
    gap:14px; margin:18px 0 24px;
  }
  .feature-card{
    background:var(--gray-50); border:1px solid var(--gray-200);
    border-radius:14px; padding:20px 22px;
    transition:all .22s ease;
    position:relative; overflow:hidden;
  }
  .feature-card::before{
    content:""; position:absolute; left:0; top:0; bottom:0; width:3px;
    background:linear-gradient(180deg, var(--navy-700), var(--orange-500));
    transform:scaleY(0); transform-origin:top;
    transition:transform .3s ease;
  }
  .feature-card:hover{
    transform:translateY(-3px);
    border-color:var(--orange-300);
    background:#fff;
    box-shadow:0 12px 28px -12px rgba(6,22,49,.18);
  }
  .feature-card:hover::before{transform:scaleY(1);}
  .feature-icon{
    width:42px; height:42px; border-radius:11px;
    background:linear-gradient(135deg, var(--navy-800), var(--navy-600));
    display:grid; place-items:center; font-size:20px;
    margin-bottom:12px;
    box-shadow:0 6px 14px -6px rgba(6,22,49,.4);
  }
  .feature-card b{
    display:block; font-size:14px; font-weight:800;
    color:var(--navy-900); margin-bottom:5px; letter-spacing:-.01em;
  }
  .feature-card span{
    font-size:12.5px; color:var(--gray-500); line-height:1.55;
  }

  /* Info boxes */
  .info-box{
    border-radius:12px; padding:16px 20px; margin:16px 0;
    font-size:13.5px; line-height:1.65;
    display:flex; gap:14px; align-items:flex-start;
    border:1px solid transparent;
  }
  .info-box::before{
    font-size:18px; flex-shrink:0; line-height:1.3;
  }
  .info-box.tip{
    background:linear-gradient(135deg, #eff6ff, #dbeafe);
    border-color:#93c5fd; color:#1e40af;
  }
  .info-box.tip::before{content:"💡";}
  .info-box.warn{
    background:linear-gradient(135deg, #fffbeb, #fef3c7);
    border-color:#fcd34d; color:#78350f;
  }
  .info-box.warn::before{content:"⚠️";}
  .info-box.danger{
    background:linear-gradient(135deg, #fef2f2, #fee2e2);
    border-color:#fca5a5; color:#991b1b;
  }
  .info-box.danger::before{content:"🚫";}
  .info-box.success{
    background:linear-gradient(135deg, #f0fdf4, #dcfce7);
    border-color:#86efac; color:#14532d;
  }
  .info-box.success::before{content:"✅";}

  /* Tables */
  table{
    width:100%; border-collapse:separate; border-spacing:0;
    font-size:13px; margin:16px 0 20px;
    border:1px solid var(--gray-200); border-radius:12px;
    overflow:hidden;
  }
  thead th{
    background:linear-gradient(180deg, var(--navy-800), var(--navy-700));
    color:#fff; font-size:10.5px; font-weight:800;
    letter-spacing:.08em; text-transform:uppercase;
    padding:12px 14px; text-align:left;
    border-right:1px solid rgba(255,255,255,.08);
  }
  thead th:last-child{border-right:0;}
  tbody td{
    padding:12px 14px;
    border-bottom:1px solid var(--gray-200);
    border-right:1px solid var(--gray-200);
    vertical-align:top;
    color:var(--gray-700); font-size:13px;
  }
  tbody td:last-child{border-right:0;}
  tbody tr:last-child td{border-bottom:0;}
  tbody tr:nth-child(even) td{background:var(--gray-50);}
  tbody td b{color:var(--navy-900); font-weight:700;}
  tbody td code{font-size:11.5px;}

  /* Shortcut table */
  table.shortcuts td:first-child{width:38%;}
  table.shortcuts td:first-child kbd{margin-right:4px;}

  /* File tree */
  .file-tree{
    background:linear-gradient(180deg, var(--navy-900), var(--navy-950));
    color:#e2e8f0; border-radius:12px;
    padding:22px 26px; margin:18px 0;
    font-family:"JetBrains Mono",Consolas,monospace;
    font-size:12.5px; line-height:1.9;
    border:1px solid var(--navy-800);
    overflow-x:auto;
  }
  .file-tree .folder{color:#ffb07c; font-weight:700;}
  .file-tree .file{color:#94a3b8;}
  .file-tree .highlight{color:#3ecf9b; font-weight:700;}
  .file-tree .comment{color:#64748b; font-style:italic;}
  .file-tree .indent{color:rgba(148,163,184,.4);}

  /* Step list */
  .steps{list-style:none; margin:20px 0; padding:0; counter-reset:step;}
  .steps > li{
    counter-increment:step;
    position:relative; padding:16px 20px 16px 68px;
    background:var(--gray-50); border:1px solid var(--gray-200);
    border-radius:12px; margin-bottom:10px;
    transition:all .18s ease; font-size:13.5px;
    color:var(--gray-700); line-height:1.6;
  }
  .steps > li::before{
    content:counter(step);
    position:absolute; left:16px; top:16px;
    width:36px; height:36px; border-radius:10px;
    background:linear-gradient(135deg, var(--navy-800), var(--navy-600));
    color:#fff; font-weight:800; font-size:14px;
    display:grid; place-items:center;
    box-shadow:0 4px 10px -3px rgba(6,22,49,.35);
  }
  .steps > li:hover{
    border-color:var(--orange-300); background:#fff;
    transform:translateX(3px);
  }
  .steps > li b{color:var(--navy-900); font-weight:800;}

  /* Code block */
  pre{
    background:linear-gradient(180deg, var(--navy-900), var(--navy-950));
    color:#e2e8f0; border-radius:12px;
    padding:20px 24px; margin:16px 0;
    font-family:"JetBrains Mono",Consolas,monospace;
    font-size:12.5px; line-height:1.65;
    overflow-x:auto; position:relative;
    border:1px solid var(--navy-800);
  }
  pre::before{
    content:attr(data-lang);
    position:absolute; top:10px; right:14px;
    font-size:9.5px; font-weight:800;
    letter-spacing:.14em; text-transform:uppercase;
    color:var(--orange-300);
  }
  pre code{
    background:none; color:inherit; padding:0; border:0;
    font-size:inherit; font-weight:500;
  }
  pre .k{color:#ff8c42; font-weight:700;} /* keyword */
  pre .s{color:#3ecf9b;} /* string */
  pre .c{color:#64748b; font-style:italic;} /* comment */
  pre .n{color:#c9f26e;} /* number */
  pre .v{color:#93c5fd;} /* var */

  /* Badge */
  .badge{
    display:inline-flex; align-items:center; gap:5px;
    font-size:10.5px; font-weight:800; letter-spacing:.06em;
    text-transform:uppercase;
    padding:4px 10px; border-radius:999px;
    margin-left:6px;
  }
  .badge.new{background:var(--orange-100); color:var(--orange-600);
    border:1px solid var(--orange-300);}
  .badge.tip{background:#eff6ff; color:#1e40af;
    border:1px solid #93c5fd;}
  .badge.danger{background:#fee2e2; color:#991b1b;
    border:1px solid #fca5a5;}

  /* FAQ */
  .faq-item{
    background:#fff; border:1px solid var(--gray-200);
    border-radius:12px; margin-bottom:10px;
    overflow:hidden; transition:all .18s ease;
  }
  .faq-item:hover{border-color:var(--orange-300); box-shadow:0 6px 18px -8px rgba(6,22,49,.15);}
  .faq-q{
    padding:16px 22px; cursor:pointer;
    display:flex; justify-content:space-between; align-items:center;
    font-size:14px; font-weight:700; color:var(--navy-900);
    gap:12px; user-select:none;
    transition:all .18s ease;
  }
  .faq-q:hover{background:var(--gray-50);}
  .faq-q::after{
    content:"▼"; font-size:10px; color:var(--orange-500);
    transition:transform .25s ease; flex-shrink:0;
  }
  .faq-item.open .faq-q::after{transform:rotate(180deg);}
  .faq-a{
    max-height:0; overflow:hidden;
    transition:max-height .35s ease, padding .3s ease;
    padding:0 22px; font-size:13.5px; color:var(--gray-700);
    line-height:1.7;
  }
  .faq-item.open .faq-a{
    max-height:600px; padding:0 22px 20px;
  }
  .faq-a code{font-size:12px;}

  /* Footer */
  .readme-footer{
    text-align:center; padding:34px 24px 20px;
    border-top:1px solid var(--gray-200);
    margin-top:40px;
    color:var(--gray-500); font-size:12px; line-height:1.8;
  }
  .readme-footer b{color:var(--navy-800); font-weight:700;}
  .readme-footer .version{
    display:inline-flex; align-items:center; gap:6px;
    background:var(--orange-100); border:1px solid var(--orange-300);
    color:var(--orange-600); padding:5px 12px; border-radius:999px;
    font-weight:800; font-size:11px; letter-spacing:.06em;
    text-transform:uppercase; margin-bottom:12px;
  }

  /* Back to top */
  .back-top{
    position:fixed; right:22px; bottom:22px; z-index:90;
    width:46px; height:46px; border-radius:14px;
    background:linear-gradient(135deg, var(--orange-500), var(--orange-600));
    color:#fff; border:0; cursor:pointer; font-size:18px;
    box-shadow:var(--shadow-orange);
    display:grid; place-items:center;
    opacity:0; pointer-events:none;
    transition:all .25s ease;
  }
  .back-top.visible{opacity:1; pointer-events:auto;}
  .back-top:hover{transform:translateY(-3px); box-shadow:0 18px 40px -10px rgba(255,107,44,.7);}

  /* Responsive */
  @media (max-width:900px){
    .paper{padding:34px 26px;}
    .nav-links{display:none;}
  }
  @media (max-width:640px){
    .hero{padding:50px 0 70px;}
    .hero h1{font-size:26px;}
    .paper{padding:26px 18px; border-radius:16px;}
    .section-head{gap:10px;}
    .section-num{min-width:38px; height:38px; padding:0 9px; font-size:12px;}
    .section-head h2{font-size:16px;}
    .toc{padding:16px 18px;}
    table{font-size:12px;}
    thead th, tbody td{padding:10px 10px;}
    pre{padding:16px 16px; font-size:11.5px;}
    .steps > li{padding:14px 16px 14px 58px;}
    .steps > li::before{left:12px; top:14px; width:32px; height:32px; font-size:12px;}
  }

  @media print{
    .nav,.back-top{display:none;}
    .hero{background:#fff; color:#000; border-bottom:2px solid var(--navy-900);}
    .hero h1, .hero h1 em{color:#000; -webkit-text-fill-color:#000;}
    .hero p{color:#333;}
    .paper{box-shadow:none; border:0; padding:0;}
    section{break-inside:avoid; page-break-inside:avoid;}
  }
</style>
</head>
<body>

<!-- NAVBAR -->
<header class="nav">
  <div class="nav-inner">
    <div class="brand">
      <div class="logo">S</div>
      <div class="brand-text">
        <strong>README · Okul Gelişimi Raporu</strong>
        <span>Kullanım Kılavuzu · v2.0</span>
      </div>
    </div>
    <nav class="nav-links">
      <a href="#baslangic" class="active">Başlangıç</a>
      <a href="#ozellikler">Özellikler</a>
      <a href="#kullanim">Kullanım</a>
      <a href="#admin">Admin</a>
      <a href="#kisayollar">Kısayollar</a>
      <a href="#sss">SSS</a>
    </nav>
    <a href="index.html" class="btn-back">
      <span>←</span><span>Rapora Dön</span>
    </a>
  </div>
</header>

<!-- HERO -->
<section class="hero">
  <div class="hero-inner">
    <div class="hero-tag">Kullanım Kılavuzu · README</div>
    <h1>Okul Gelişimi ve Akademik Başarıyı<br><em>İzleme ve Değerlendirme Raporu</em></h1>
    <p>
      Bu kılavuz; raporun nasıl kullanılacağını, düzenleneceğini, PDF olarak kaydedileceğini
      ve admin paneli üzerinden içeriklerin nasıl yönetileceğini adım adım açıklar.
    </p>
    <div class="hero-meta">
      <span class="hero-chip">📄 <b>16</b> Performans Tablosu</span>
      <span class="hero-chip">📅 <b>10</b> Aylık Takip</span>
      <span class="hero-chip">🎯 <b>7</b> Gelişim Alanı</span>
      <span class="hero-chip">📥 <b>4</b> İndirme Formatı</span>
    </div>
  </div>
</section>

<main>
  <div class="container">
    <div class="paper">

      <!-- İÇİNDEKİLER -->
      <nav class="toc">
        <div class="toc-title">İçindekiler</div>
        <div class="toc-grid">
          <a href="#baslangic">1. Hızlı Başlangıç</a>
          <a href="#ozellikler">2. Özellikler</a>
          <a href="#kullanim">3. Temel Kullanım</a>
          <a href="#veri-girme">4. Veri Girişi</a>
          <a href="#pdf">5. PDF İndirme</a>
          <a href="#yedekleme">6. Yedekleme</a>
          <a href="#admin">7. Admin Paneli</a>
          <a href="#kisayollar">8. Klavye Kısayolları</a>
          <a href="#sss">9. Sık Sorulan Sorular</a>
          <a href="#sorun">10. Sorun Giderme</a>
        </div>
      </nav>

      <!-- 1. HIZLI BAŞLANGIÇ -->
      <section id="baslangic">
        <div class="section-head">
          <div class="section-num">01</div>
          <div>
            <h2>Hızlı Başlangıç</h2>
            <p>İlk kez kullanıyorsanız bu adımları takip edin</p>
          </div>
        </div>

        <ol class="steps">
          <li>
            <b>Tarayıcıda açın:</b> <code>index.html</code> dosyasına çift tıklayın. Chrome, Edge veya Firefox önerilir.
          </li>
          <li>
            <b>Verileri girin:</b> Tablo hücrelerine tıklayıp doğrudan yazın. Her hücre otomatik olarak tarayıcıya kaydedilir.
          </li>
          <li>
            <b>Başlıkları düzenleyin:</b> <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>A</kbd> ile admin panelini açın (şifre: <code>admin2026</code>).
          </li>
          <li>
            <b>PDF indirin:</b> Sağ üstteki turuncu <b>"PDF İndir"</b> butonuna tıklayın.
          </li>
          <li>
            <b>Yedek alın:</b> Admin paneli → <b>Yedek / Sıfırla</b> → <b>Tam Yedek İndir</b>. Farklı bir bilgisayarda bu dosyayı yükleyerek devam edebilirsiniz.
          </li>
        </ol>

        <div class="info-box tip">
          <div>
            <b>İpucu:</b> Hiçbir kurulum gerekmez. Tek bir <code>index.html</code> dosyası yeterlidir.
            Tüm veriler tarayıcının <code>localStorage</code> alanında saklanır ve internete gönderilmez.
          </div>
        </div>
      </section>

      <!-- 2. ÖZELLİKLER -->
      <section id="ozellikler">
        <div class="section-head">
          <div class="section-num">02</div>
          <div>
            <h2>Özellikler</h2>
            <p>Raporun sunduğu temel yetenekler</p>
          </div>
        </div>

        <div class="feature-grid">
          <div class="feature-card">
            <div class="feature-icon">🖊️</div>
            <b>Canlı Düzenleme</b>
            <span>Tablo hücrelerine tıklayıp doğrudan yazın. Değişiklikler anında kaydedilir.</span>
          </div>
          <div class="feature-card">
            <div class="feature-icon">📄</div>
            <b>Profesyonel PDF</b>
            <span>17 sayfa, A4 yatay, kapak + üst bilgi + alt bilgi ile baskıya hazır PDF.</span>
          </div>
          <div class="feature-card">
            <div class="feature-icon">⚙️</div>
            <b>Admin Paneli</b>
            <span>Başlıkları, slaytları, satırları ve gündem kartlarını yönetin.</span>
          </div>
          <div class="feature-card">
            <div class="feature-icon">💾</div>
            <b>Yedekleme</b>
            <span>Tüm verileri JSON olarak indirin, başka cihazda geri yükleyin.</span>
          </div>
          <div class="feature-card">
            <div class="feature-icon">📊</div>
            <b>Excel Çıktısı</b>
            <span>Tabloları CSV olarak dışa aktarın, Excel'de düzenleyin.</span>
          </div>
          <div class="feature-card">
            <div class="feature-icon">🖨️</div>
            <b>Yazdırma</b>
            <span>A4 yatay format, her slayt ayrı sayfaya gelecek şekilde optimize.</span>
          </div>
          <div class="feature-card">
            <div class="feature-icon">🖊️</div>
            <b>Düzenleme / Salt Okunur</b>
            <span>Yanlışlıkla yazmayı önlemek için mod değiştirin.</span>
          </div>
          <div class="feature-card">
            <div class="feature-icon">🌓</div>
            <b>Otomatik Kayıt</b>
            <span>Sayfayı kapatsanız bile veriler korunur. Üstelik kayıt saatini gösterir.</span>
          </div>
        </div>
      </section>

      <!-- 3. TEMEL KULLANIM -->
      <section id="kullanim">
        <div class="section-head">
          <div class="section-num">03</div>
          <div>
            <h2>Temel Kullanım</h2>
            <p>Arayüz ve genel kullanım</p>
          </div>
        </div>

        <h3>Üst Araç Çubuğu</h3>
        <table>
          <thead>
            <tr>
              <th style="width:60px">Simge</th>
              <th>İşlev</th>
              <th>Kısayol</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td style="text-align:center;font-size:20px">🖊️</td>
              <td><b>Düzenleme Modu</b><br>Hücreleri düzenlenebilir yapar. Kapatıldığında salt okunur olur.</td>
              <td><kbd>Ctrl</kbd> + <kbd>E</kbd></td>
            </tr>
            <tr>
              <td style="text-align:center;font-size:20px">💾</td>
              <td><b>Kaydet (PDF)</b><br>Raporu PDF olarak bilgisayarınıza kaydeder.</td>
              <td><kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd></td>
            </tr>
            <tr>
              <td style="text-align:center;font-size:20px">📂</td>
              <td><b>Proje Yükle</b><br>Daha önce kaydedilmiş JSON yedeğini yükler.</td>
              <td><kbd>Ctrl</kbd> + <kbd>O</kbd></td>
            </tr>
            <tr>
              <td style="text-align:center;font-size:20px">🖨️</td>
              <td><b>Yazdır</b><br>Tarayıcının yazdırma penceresini açar.</td>
              <td><kbd>Ctrl</kbd> + <kbd>P</kbd></td>
            </tr>
            <tr>
              <td style="text-align:center;font-size:20px">⚙️</td>
              <td><b>Admin Paneli</b><br>Şifreli yönetim panelini açar.</td>
              <td><kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>A</kbd></td>
            </tr>
            <tr>
              <td style="text-align:center;font-size:20px">📄</td>
              <td><b>PDF İndir</b><br>Doğrudan PDF indirir (turuncu buton).</td>
              <td><kbd>Ctrl</kbd> + <kbd>S</kbd></td>
            </tr>
            <tr>
              <td style="text-align:center;font-size:20px">⬇</td>
              <td><b>Formatlar</b><br>Excel / JSON / Yazdır seçenekleri.</td>
              <td>—</td>
            </tr>
          </tbody>
        </table>

        <h3>Durum Çubuğu</h3>
        <p>Rapor içeriğinin hemen üzerinde yer alan durum çubuğu şu bilgileri gösterir:</p>
        <ul>
          <li><b>Otomatik kayıt:</b> Yeşil yanıp sönen nokta kaydetmenin çalıştığını gösterir.</li>
          <li><b>Mod:</b> Düzenleme veya Salt Okunur durumu.</li>
          <li><b>Hücre sayacı:</b> Kaç hücrenin doldurulduğunu gösterir (örn. <code>42 / 320</code>).</li>
          <li><b>Son güncelleme:</b> En son kaydetme saati.</li>
        </ul>
      </section>

      <!-- 4. VERİ GİRİŞİ -->
      <section id="veri-girme">
        <div class="section-head">
          <div class="section-num">04</div>
          <div>
            <h2>Veri Girişi</h2>
            <p>Tablo hücrelerini doldurma</p>
          </div>
        </div>

        <h3>Hücreye Veri Yazma</h3>
        <ol class="steps">
          <li>Düzenleme modu <b>açık</b> olmalı (turuncu 🖊️ butonu aktif).</li>
          <li>Hücreye <b>tıklayın</b> — imleç belirir ve hücre turuncu kenarlık alır.</li>
          <li>Değeri yazın (örn. <code>12</code>, <code>%85</code>, <code>E</code>).</li>
          <li><kbd>Enter</kbd> → sonraki hücreye geçer · <kbd>Esc</kbd> → çıkış.</li>
          <li>Başka bir yere tıkladığınızda veri <b>otomatik kaydedilir</b>.</li>
        </ol>

        <div class="info-box tip">
          <div>
            <b>Akıllı Geçiş:</b> <kbd>Enter</kbd> tuşu satırın sonundaysa otomatik olarak
            bir sonraki satırın ilk hücresine atlar.
          </div>
        </div>

        <h3>Tablo Tipleri</h3>
        <p>Raporda üç farklı tablo tipi kullanılır:</p>
        <table>
          <thead>
            <tr>
              <th>Tip</th>
              <th>Açıklama</th>
              <th>Kullanım</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><b>H / G</b></td>
              <td>Hedef / Gerçekleşen — her ay için iki sütun</td>
              <td>Sayısal hedefler (toplantı, görüşme, faaliyet sayıları)</td>
            </tr>
            <tr>
              <td><b>E / H</b></td>
              <td>Evet / Hayır — her ay için iki sütun</td>
              <td>Yapıldı mı / yapılmadı mı soruları</td>
            </tr>
            <tr>
              <td><b>SINGLE</b></td>
              <td>Tek sütun E/H</td>
              <td>Değerlendirme önlemleri (5 soruluk tablo)</td>
            </tr>
          </tbody>
        </table>

        <h3>Düzenleme Modunu Kapatma</h3>
        <p>
          Verileri girdikten sonra 🖊️ butonuna basarak <b>Salt Okunur</b> moda geçebilirsiniz.
          Bu modda hücreler yanlışlıkla değiştirilemez ve temiz görünür.
        </p>
      </section>

      <!-- 5. PDF İNDİRME -->
      <section id="pdf">
        <div class="section-head">
          <div class="section-num">05</div>
          <div>
            <h2>PDF İndirme</h2>
            <p>Raporu PDF olarak kaydetme</p>
          </div>
        </div>

        <h3>Hızlı PDF İndirme</h3>
        <ol class="steps">
          <li>Sağ üstteki turuncu <b>"PDF İndir"</b> butonuna tıklayın.</li>
          <li>İlerleme çubuğu her sayfayı işlerken artar.</li>
          <li>Tarayıcı otomatik olarak PDF dosyasını indirir.</li>
          <li>Dosya adı: <code>Okul-Gelisimi-Akademik-Basari-İzleme-Raporu.pdf</code></li>
        </ol>

        <h3>PDF İçeriği</h3>
        <p>Oluşturulan PDF <b>17 sayfa</b> içerir:</p>
        <table>
          <thead>
            <tr>
              <th style="width:100px">Sayfa</th>
              <th>İçerik</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><b>1</b></td>
              <td>Kapak — Lacivert-turuncu gradient, kurum adı, tarih, istatistikler</td>
            </tr>
            <tr>
              <td><b>2</b></td>
              <td>Rapor Gündemi — 7 gelişim alanı kartı</td>
            </tr>
            <tr>
              <td><b>3-17</b></td>
              <td>Performans tabloları — Her sayfada üst bilgi, alt bilgi ve sayfa numarası</td>
            </tr>
          </tbody>
        </table>

        <h3>PDF Formatı</h3>
        <ul>
          <li><b>Boyut:</b> A4 Yatay (297 × 210 mm)</li>
          <li><b>Kalite:</b> Yüksek (JPEG quality 0.95, scale 2x)</li>
          <li><b>Renkler:</b> Lacivert (#061631) ve turuncu (#ff6b2c)</li>
          <li><b>Zemin:</b> Beyaz içerik sayfaları, lacivert kapak</li>
          <li><b>Dosya boyutu:</b> Yaklaşık 1-2 MB</li>
        </ul>

        <div class="info-box warn">
          <div>
            <b>Uyarı:</b> PDF oluşturma sırasında sayfayı kapatmayın.
            17 sayfa render ediliyor, ortalama 8-15 saniye sürer.
          </div>
        </div>
      </section>

      <!-- 6. YEDEKLEME -->
      <section id="yedekleme">
        <div class="section-head">
          <div class="section-num">06</div>
          <div>
            <h2>Yedekleme ve Geri Yükleme</h2>
            <p>Verilerinizi güvence altına alın</p>
          </div>
        </div>

        <h3>Tam Yedek Alma</h3>
        <ol class="steps">
          <li>Admin panelini açın (⚙️ veya <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>A</kbd>).</li>
          <li><b>Yedek / Sıfırla</b> sekmesine gelin.</li>
          <li><b>"Tam Yedek İndir (JSON)"</b> butonuna tıklayın.</li>
          <li>İndirilen dosyayı güvenli bir yerde saklayın.</li>
        </ol>

        <h3>Yedek İçeriği</h3>
        <p>Tam yedek dosyası şunları içerir:</p>
        <ul>
          <li>Tüm başlıklar, kurum bilgileri, tarih, admin şifresi</li>
          <li>Kapak istatistikleri (3 adet)</li>
          <li>Slayt yapısı (başlık, açıklama, kategori, tip, satırlar)</li>
          <li>Gündem kartları (7 adet, düzenlenmiş haliyle)</li>
          <li>Tüm tablo hücrelerindeki veriler</li>
        </ul>

        <h3>Yedeği Geri Yükleme</h3>
        <ol class="steps">
          <li>Navbar'daki 📂 butonuna tıklayın.</li>
          <li>JSON yedek dosyasını seçin.</li>
          <li>Tüm içerik otomatik yüklenir ve rapor yeniden çizilir.</li>
        </ol>

        <div class="info-box success">
          <div>
            <b>Farklı cihazda çalışma:</b> Yedek dosyasını başka bir bilgisayara kopyalayıp
            📂 butonuyla yükleyerek kaldığınız yerden devam edebilirsiniz.
          </div>
        </div>
      </section>

      <!-- 7. ADMIN PANELİ -->
      <section id="admin">
        <div class="section-head">
          <div class="section-num">07</div>
          <div>
            <h2>Admin Paneli</h2>
            <p>Tüm içerikleri yönetin</p>
          </div>
        </div>

        <h3>Giriş</h3>
        <p>
          Navbar'daki <b>⚙️</b> butonuna tıklayın veya <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>A</kbd>
          kısayolunu kullanın.
        </p>

        <div class="info-box tip">
          <div>
            <b>Varsayılan şifre:</b> <code>admin2026</code><br>
            Admin panelindeki <b>Genel Bilgiler</b> sekmesinden değiştirilebilir.
          </div>
        </div>

        <h3>4 Sekme</h3>

        <h3 style="margin-top:30px">📋 Genel Bilgiler</h3>
        <p>Aşağıdaki tüm alanlar düzenlenebilir. Kaydettiğinizde rapor <b>otomatik güncellenir</b>.</p>
        <table>
          <thead>
            <tr>
              <th>Alan</th>
              <th>Etki Alanı</th>
            </tr>
          </thead>
          <tbody>
            <tr><td><b>Rapor Başlığı (Uzun)</b></td><td>Navbar, tarayıcı sekmesi, PDF</td></tr>
            <tr><td><b>Rapor Başlığı (Kısa)</b></td><td>PDF üst bilgi</td></tr>
            <tr><td><b>Kurum</b></td><td>Tüm sayfa alt bilgileri, kapak etiketi</td></tr>
            <tr><td><b>Okul Adı</b></td><td>Kapak sayfası</td></tr>
            <tr><td><b>Eğitim Yılı</b></td><td>Kapak, navbar</td></tr>
            <tr><td><b>Dosya Adı</b></td><td>İndirilen PDF/CSV/JSON dosyası</td></tr>
            <tr><td><b>Rapor Tarihi</b></td><td>Kapak ve PDF footer</td></tr>
            <tr><td><b>Admin Şifresi</b></td><td>Panele giriş şifresi</td></tr>
            <tr><td><b>3 Kapak İstatistiği</b></td><td>Kapak — sayfa sayısı, tablo, ay</td></tr>
            <tr><td><b>Sayfa Alt Yazısı</b></td><td>Sayfa footer metni</td></tr>
          </tbody>
        </table>

        <h3>📑 Slaytlar</h3>
        <p>Her slaytı düzenleyebilir, silebilir veya yeni slayt ekleyebilirsiniz.</p>
        <ul>
          <li><b>✏️ Düzenle:</b> Başlık, açıklama, kategori, tablo tipi (H/G, E/H, SINGLE)</li>
          <li><b>🗑 Sil:</b> Slaytı tamamen kaldırır (kapak hariç)</li>
          <li><b>➕ Yeni Slayt Ekle:</b> Boş şablon ekler</li>
          <li><b>↻ Varsayılana Dön:</b> Orijinal 17 slaytı geri yükler</li>
        </ul>

        <h3 style="margin-top:30px">Satır Editörü</h3>
        <p>Slayt düzenlerken her satır için:</p>
        <ul>
          <li><b>▲ Yukarı:</b> Satırı bir üste taşır</li>
          <li><b>▼ Aşağı:</b> Satırı bir alta taşır</li>
          <li><b>🗑 Sil:</b> Satırı kaldırır</li>
          <li><b>➕ Satır Ekle:</b> Alt tarafa boş satır ekler</li>
        </ul>

        <h3>🎯 Gündem</h3>
        <p>Kapak sonrası "Rapor Gündemi" slaytındaki 7 kartı düzenleyin.</p>
        <ul>
          <li>Her kart için <b>ikon</b> (emoji), <b>başlık</b> ve <b>açıklama</b></li>
          <li>Yazarken anlık güncellenir</li>
          <li>➕ Yeni Kart Ekle · 🗑 Sil · ↻ Sıfırla</li>
        </ul>

        <h3>💾 Yedek / Sıfırla</h3>
        <ul>
          <li><b>Tam Yedek İndir (JSON):</b> Tüm veriler tek dosyada</li>
          <li><b>Yedekten Geri Yükle:</b> JSON dosyası seçerek tam restorasyon</li>
          <li><b>Tüm Verileri Sıfırla:</b> 2 aşamalı onay ile fabrika ayarları</li>
          <li><b>Depolama Bilgisi:</b> Kullanılan alan ve hücre sayısı</li>
        </ul>

        <div class="info-box danger">
          <div>
            <b>Dikkat:</b> "Tüm Verileri Sıfırla" işlemi <b>geri alınamaz</b>.
            Önce mutlaka yedek alın.
          </div>
        </div>
      </section>

      <!-- 8. KISAYOLLAR -->
      <section id="kisayollar">
        <div class="section-head">
          <div class="section-num">08</div>
          <div>
            <h2>Klavye Kısayolları</h2>
            <p>Hızlı işlem için kısayollar</p>
          </div>
        </div>

        <h3>Genel Kısayollar</h3>
        <table class="shortcuts">
          <thead>
            <tr>
              <th>Kısayol</th>
              <th>İşlev</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><kbd>Ctrl</kbd> + <kbd>S</kbd></td>
              <td>Hızlı PDF indir</td>
            </tr>
            <tr>
              <td><kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd></td>
              <td>Kaydet butonu (PDF olarak kaydet)</td>
            </tr>
            <tr>
              <td><kbd>Ctrl</kbd> + <kbd>O</kbd></td>
              <td>Proje yükle (JSON)</td>
            </tr>
            <tr>
              <td><kbd>Ctrl</kbd> + <kbd>P</kbd></td>
              <td>Yazdır</td>
            </tr>
            <tr>
              <td><kbd>Ctrl</kbd> + <kbd>E</kbd></td>
              <td>Düzenleme modunu aç/kapat</td>
            </tr>
            <tr>
              <td><kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>A</kbd></td>
              <td>Admin panelini aç</td>
            </tr>
            <tr>
              <td><kbd>Esc</kbd></td>
              <td>Açık modalı kapat</td>
            </tr>
          </tbody>
        </table>

        <h3>Hücre Düzenleme</h3>
        <table class="shortcuts">
          <thead>
            <tr>
              <th>Kısayol</th>
              <th>İşlev</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><kbd>Enter</kbd></td>
              <td>Sonraki hücreye geç (satır sonunda alt satıra atlar)</td>
            </tr>
            <tr>
              <td><kbd>Esc</kbd></td>
              <td>Hücreden çık</td>
            </tr>
            <tr>
              <td><kbd>Tab</kbd></td>
              <td>Sonraki hücreye geç</td>
            </tr>
          </tbody>
        </table>
      </section>

      <!-- 9. SSS -->
      <section id="sss">
        <div class="section-head">
          <div class="section-num">09</div>
          <div>
            <h2>Sık Sorulan Sorular</h2>
            <p>Kullanıcıların en çok sorduğu sorular</p>
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">Verilerim nerede saklanıyor?</div>
          <div class="faq-a">
            Tüm veriler tarayıcınızın <code>localStorage</code> alanında saklanır. Hiçbir veri
            internete gönderilmez. Farklı bir bilgisayarda veya tarayıcıda açtığınızda
            veriler görünmez — bu durumda yedek dosyasını yüklemeniz gerekir.
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">PDF neden tek sayfa iniyordu / karanlık çıkıyordu?</div>
          <div class="faq-a">
            Bu sorun eski sürümlerde <code>html2pdf</code> kütüphanesinin tüm sayfaları
            tek seferde yakalamaya çalışmasından kaynaklanıyordu. Şimdiki sürümde her sayfa
            <b>tek tek</b> render edilip PDF'e eklenir. Zemin beyaz, içerik sayfaları
            açık renktedir.
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">Aynı anda birden fazla kişi kullanabilir mi?</div>
          <div class="faq-a">
            Hayır. Bu rapor <b>yerel</b> çalışır (sunucu yoktur). Her kullanıcı kendi
            tarayıcısında kendi verileriyle çalışır. Ortak kullanım için bir kişi doldurup
            yedeği diğerlerine gönderir.
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">Admin şifresini unuttum, ne yapmalıyım?</div>
          <div class="faq-a">
            Tarayıcı konsolunda şu komutu çalıştırın:
            <pre data-lang="JavaScript"><code><span class="v">localStorage</span>.<span class="k">removeItem</span>(<span class="s">"rapor-config"</span>); location.<span class="k">reload</span>();</code></pre>
            Bu, tüm yapılandırmayı fabrika ayarlarına döndürür (şifre <code>admin2026</code> olur)
            ancak girilen tablo verileri korunur.
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">Yeni bir slayt ekledim ama PDF'te görünmüyor?</div>
          <div class="faq-a">
            Slayt eklendikten sonra mutlaka <b>Kaydet</b> butonuna basmalısınız.
            Değişiklikler admin panelinden yapıldığında otomatik kaydedilir ama
            sayfa numaralarını güncellemek için rapor yeniden çizilir.
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">CSV dosyası Excel'de Türkçe karakterleri bozuk gösteriyor?</div>
          <div class="faq-a">
            CSV dosyası <b>UTF-8 BOM</b> ile kaydedilir, bu sayede Excel Türkçe karakterleri
            (ı, ş, ğ, ü, ö, ç) doğru gösterir. Yine de sorun yaşarsanız, Excel'de
            <b>Veri → Metinden Al</b> yolunu kullanıp kodlamayı <code>UTF-8</code> seçin.
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">PDF'te neden bazı hücreler boş görünüyor?</div>
          <div class="faq-a">
            PDF, tarayıcıdaki <b>mevcut</b> durumu yakalar. Hücreler boşsa henüz doldurulmamıştır.
            PDF üretmeden önce tabloyu kontrol edin.
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">Kapak istatistiklerini nasıl değiştiririm?</div>
          <div class="faq-a">
            Admin paneli → <b>Genel Bilgiler</b> → en alttaki 3 istatistik alanı.
            Her biri için ayrı <b>değer</b> ve <b>etiket</b> girebilirsiniz.
          </div>
        </div>

        <div class="faq-item">
          <div class="faq-q">Birden fazla slayt sildim, geri alabilir miyim?</div>
          <div class="faq-a">
            Admin paneli → <b>Slaytlar</b> → <b>↻ Varsayılan Slaytlara Dön</b> butonuyla
            orijinal 17 slayta dönebilirsiniz. Ancak bu işlem <b>tüm özelleştirmeleri sıfırlar</b>.
            Silmeden önce yedek almanızı öneririz.
          </div>
        </div>
      </section>

      <!-- 10. SORUN GİDERME -->
      <section id="sorun">
        <div class="section-head">
          <div class="section-num">10</div>
          <div>
            <h2>Sorun Giderme</h2>
            <p>Yaygın sorunlar ve çözümleri</p>
          </div>
        </div>

        <table>
          <thead>
            <tr>
              <th style="width:32%">Sorun</th>
              <th>Çözüm</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><b>Veriler kaydedilmiyor</b></td>
              <td>Tarayıcıda <b>gizli mod</b> aktif olabilir. Normal modda açın. Ayrıca çerezlerin engellenmediğinden emin olun.</td>
            </tr>
            <tr>
              <td><b>PDF oluşturulmuyor</b></td>
              <td>Sayfayı yenileyin (<kbd>Ctrl</kbd>+<kbd>F5</kbd>). İnternet bağlantınızı kontrol edin (CDN kütüphaneleri yüklenir).</td>
            </tr>
            <tr>
              <td><b>Hücreler düzenlenmiyor</b></td>
              <td>🖊️ Düzenleme modunun <b>açık</b> olduğundan emin olun. Turuncu renkliyse açık.</td>
            </tr>
            <tr>
              <td><b>Admin girişi çalışmıyor</b></td>
              <td>Şifreyi <b>büyük/küçük harf</b> duyarlı girin. Varsayılan: <code>admin2026</code>. Çalışmazsa yukarıdaki SSS'deki konsol komutunu kullanın.</td>
            </tr>
            <tr>
              <td><b>Yazdırırken fazla sayfa çıkıyor</b></td>
              <td>Yazdırma ayarlarında <b>"Yatay"</b> yönlendirmeyi ve <b>"Kenar boşluğu: Yok"</b> seçeneğini seçin.</td>
            </tr>
            <tr>
              <td><b>Excel'de Türkçe karakterler bozuk</b></td>
              <td>CSV dosyasını Excel'e <b>Veri → Metinden Al</b> yoluyla UTF-8 kodlaması seçerek alın.</td>
            </tr>
            <tr>
              <td><b>Yedek dosyası yüklenmiyor</b></td>
              <td>Dosyanın <code>.json</code> uzantılı ve bu rapora ait olduğundan emin olun. Bozuk dosyalar için hata mesajı gösterilir.</td>
            </tr>
            <tr>
              <td><b>PDF'te koyu/boş sayfalar</b></td>
              <td>Tarayıcı önbelleğini temizleyin (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Del</kbd>). Sayfayı yenileyin.</td>
            </tr>
          </tbody>
        </table>

        <div class="info-box tip">
          <div>
            <b>Önerilen Tarayıcılar:</b> Chrome 90+, Edge 90+, Firefox 88+.
            Safari ve mobil tarayıcılarda PDF üretimi daha yavaş olabilir.
          </div>
        </div>

        <h3>Tarayıcı Konsolunu Açma</h3>
        <ul>
          <li>Windows / Linux: <kbd>F12</kbd> veya <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>I</kbd></li>
          <li>Mac: <kbd>Cmd</kbd>+<kbd>Option</kbd>+<kbd>I</kbd></li>
          <li>Console sekmesinden hataları görebilirsiniz</li>
        </ul>

        <h3>Depolamayı Sıfırlama (Konsol)</h3>
        <p>Tüm verileri tamamen silmek için:</p>
        <pre data-lang="JavaScript"><code><span class="c">// Tüm rapor verilerini sil</span>
Object.<span class="k">keys</span>(<span class="v">localStorage</span>)
  .<span class="k">filter</span>(k <span class="k">=></span> k.<span class="k">startsWith</span>(<span class="s">"rapor-"</span>))
  .<span class="k">forEach</span>(k <span class="k">=></span> <span class="v">localStorage</span>.<span class="k">removeItem</span>(k));

<span class="c">// Sayfayı yenile</span>
location.<span class="k">reload</span>();</code></pre>
      </section>

      <!-- FOOTER -->
      <footer class="readme-footer">
        <div class="version">📘 README · v2.0</div>
        <div>
          <b>Samsat İlçe Milli Eğitim Müdürlüğü</b><br>
          Okul Gelişimi ve Akademik Başarıyı İzleme ve Değerlendirme Raporu
        </div>
        <div style="margin-top:10px;font-size:11.5px;color:var(--gray-400)">
          Bu kılavuz raporla birlikte gelir. Sorularınız için İlçe MEM ile iletişime geçin.
        </div>
      </footer>

    </div>
  </div>
</main>

<button class="back-top" id="backTop" aria-label="Yukarı çık">↑</button>

<script>
  /* Aktif menü takibi */
  const sections = document.querySelectorAll("section[id]");
  const navLinks = document.querySelectorAll(".nav-links a");

  function updateActiveLink(){
    const scrollY = window.scrollY + 120;
    let current = "";
    sections.forEach(sec => {
      if (sec.offsetTop <= scrollY) current = sec.id;
    });
    navLinks.forEach(a => {
      a.classList.toggle("active", a.getAttribute("href") === "#" + current);
    });
  }

  /* Back to top */
  const backTop = document.getElementById("backTop");
  function handleScroll(){
    backTop.classList.toggle("visible", window.scrollY > 400);
    updateActiveLink();
  }
  window.addEventListener("scroll", handleScroll, { passive:true });

  backTop.addEventListener("click", () => {
    window.scrollTo({ top: 0, behavior: "smooth" });
  });

  /* FAQ aç/kapat */
  document.querySelectorAll(".faq-q").forEach(q => {
    q.addEventListener("click", () => {
      const item = q.closest(".faq-item");
      const isOpen = item.classList.contains("open");
      document.querySelectorAll(".faq-item").forEach(i => i.classList.remove("open"));
      if (!isOpen) item.classList.add("open");
    });
  });

  /* İlk FAQ'yu aç */
  const firstFaq = document.querySelector(".faq-item");
  if (firstFaq) firstFaq.classList.add("open");

  /* Klavye kısayolları */
  document.addEventListener("keydown", e => {
    if (e.key === "Home") window.scrollTo({ top: 0, behavior: "smooth" });
    if (e.key === "End") window.scrollTo({ top: document.body.scrollHeight, behavior: "smooth" });
  });

  handleScroll();
</script>
</body>
</html>
