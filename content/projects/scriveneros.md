---
title: "ScrivenerOS"
description: "A calm, focused Linux for a parent and a child. Setup is a wizard, Secure Boot stays on, and it will always be free — with no ID verification, ever."
weight: 1
layout: "scriveneros"
icon: "&#128220;"
status: "wip"
tech: ["Linux", "Fedora", "GNOME", "bootc", "Python", "GTK4", "SvelteKit"]
github: "https://github.com/AnarchySC"
---

<div class="scriveneros-page">
<style>
/* ScrivenerOS project page — scoped under .scriveneros-page, all classes prefixed so- */
.scriveneros-page{
  --so-gold:var(--neon-gold,#FFD000);
  --so-amber:var(--neon-amber,#FAA307);
  --so-verm:var(--neon-orange,#E85D04);
  --so-lapis:var(--neon-blue,#4a7ab5);
  --so-cyan:var(--neon-cyan,#00d4ff);
  --so-green:var(--green,#3fb950);
  --so-ink:var(--text,#c8ccd4);
  --so-bright:#eef0f4;
  --so-muted:var(--text-muted,#6a7080);
  --so-dim:var(--text-dim,#3a4050);
  --so-bg:var(--bg,#05080e);
  --so-surface:var(--bg-surface,#0a0e18);
  --so-card:var(--bg-card,#0d1220);
  --so-card-hover:var(--bg-card-hover,#111828);
  --so-border:var(--border,#141c2e);
  --so-border-glow:var(--border-glow,#1a2540);
  --so-serif:var(--font-heading,'EB Garamond',Georgia,'Times New Roman',serif);
  --so-sans:var(--font-body,'Inter',-apple-system,'Segoe UI',sans-serif);
  --so-mono:var(--font-mono,'JetBrains Mono','SFMono-Regular',Consolas,monospace);
  --so-max:var(--max-width,1100px);
  font-family:var(--so-sans);color:var(--so-ink);background:var(--so-bg);line-height:1.6;
}
.scriveneros-page *{box-sizing:border-box}
.scriveneros-page a{color:inherit}
.so-wrap{max-width:var(--so-max);margin:0 auto;padding:0 24px}
/* ---------- hero ---------- */
.so-hero{padding:88px 0 76px;border-bottom:1px solid var(--so-border);position:relative;overflow:hidden}
.so-hero::before{content:"";position:absolute;inset:0;pointer-events:none;
  background:radial-gradient(ellipse 55% 55% at 18% 25%,rgba(255,208,0,.07),transparent 62%),
             radial-gradient(ellipse 45% 45% at 88% 75%,rgba(74,122,181,.12),transparent 62%)}
.so-hero .so-wrap{display:grid;grid-template-columns:1.15fr .85fr;gap:56px;align-items:center;position:relative}
.so-badge{display:inline-flex;align-items:center;gap:9px;font-family:var(--so-mono);font-size:11px;letter-spacing:.2em;text-transform:uppercase;color:var(--so-gold);border:1px solid rgba(255,208,0,.45);padding:5px 12px;margin-bottom:30px}
.so-badge i{width:6px;height:6px;background:var(--so-gold);display:inline-block;box-shadow:0 0 8px var(--so-gold);animation:so-pulse 2.2s ease-in-out infinite}
@keyframes so-pulse{0%,100%{opacity:1}50%{opacity:.35}}
.so-open{display:flex;gap:28px;align-items:flex-start}
.so-initial{flex:0 0 150px;width:150px;height:150px;filter:drop-shadow(0 12px 30px rgba(0,0,0,.55))}
.so-wordmark{font-family:var(--so-serif);font-size:15px;letter-spacing:.34em;text-transform:uppercase;color:var(--so-amber);margin:6px 0 12px}
.so-title{font-family:var(--so-serif);font-weight:500;font-size:clamp(38px,5.1vw,62px);line-height:1.04;letter-spacing:-.01em;color:var(--so-bright);margin:0}
.so-title em{font-style:italic;color:var(--so-gold);text-shadow:0 0 30px rgba(255,208,0,.25)}
.so-dim{display:block;font-family:var(--so-mono);font-size:13px;color:var(--so-muted);letter-spacing:.04em;margin-top:16px}
.so-lede{font-size:18px;color:var(--so-ink);max-width:560px;margin:26px 0 34px}
.so-ctas{display:flex;flex-wrap:wrap;gap:14px}
.so-btn{display:inline-flex;align-items:center;gap:8px;font-family:var(--so-mono);font-size:13px;letter-spacing:.06em;padding:13px 22px;text-decoration:none;border:1px solid transparent;transition:all .2s;cursor:pointer}
.scriveneros-page .so-btn-primary{background:var(--so-gold);color:#0a0a0a;border-color:var(--so-gold);font-weight:500}
.scriveneros-page .so-btn-primary:hover{background:#ffe04d;color:#0a0a0a;box-shadow:0 0 26px rgba(255,208,0,.35)}
.scriveneros-page .so-btn-ghost{color:var(--so-ink);border-color:var(--so-border-glow);background:transparent}
.scriveneros-page .so-btn-ghost:hover{border-color:var(--so-gold);color:var(--so-gold)}
/* Hours mock window */
.so-window{background:var(--so-card);border:1px solid var(--so-border-glow);box-shadow:0 30px 80px rgba(0,0,0,.55),0 0 0 1px rgba(255,208,0,.05)}
.so-titlebar{display:flex;align-items:center;gap:12px;padding:10px 14px;border-bottom:1px solid var(--so-border);font-family:var(--so-mono);font-size:12px;color:var(--so-muted)}
.so-dots{display:flex;gap:5px}
.so-dots i{width:9px;height:9px;border-radius:50%;display:inline-block;background:var(--so-dim)}
.so-titlebar .so-live{margin-left:auto;color:var(--so-green);font-size:10px;letter-spacing:.14em;text-transform:uppercase}
.so-hours{padding:20px 22px 22px}
.so-hours-head{display:flex;justify-content:space-between;align-items:baseline;gap:12px}
.so-hours-day{font-family:var(--so-serif);font-size:24px;color:var(--so-bright)}
.so-hours-date{font-family:var(--so-mono);font-size:11px;color:var(--so-muted);letter-spacing:.12em;text-transform:uppercase}
.so-count{margin:16px 0 16px;padding:16px 18px;border:1px solid rgba(255,208,0,.28);background:linear-gradient(180deg,rgba(255,208,0,.07),transparent);display:flex;justify-content:space-between;align-items:flex-end;gap:12px}
.so-count-label{font-family:var(--so-mono);font-size:11px;letter-spacing:.18em;text-transform:uppercase;color:var(--so-amber)}
.so-count-num{font-family:var(--so-serif);font-size:46px;line-height:1;color:#fff;margin-top:6px;font-variant-numeric:tabular-nums}
.so-count-next{text-align:right;font-size:12px;color:var(--so-muted);line-height:1.4}
.so-count-next b{display:block;color:var(--so-ink);font-weight:500}
.so-sched{list-style:none;margin:0;padding:0}
.so-sched li{display:grid;grid-template-columns:52px 1fr auto;gap:12px;padding:8px 0;border-top:1px dashed var(--so-border);font-size:14px;align-items:center;color:var(--so-ink)}
.so-sched time{font-family:var(--so-mono);font-size:12px;color:var(--so-muted)}
.so-sched li.so-done span:nth-child(2){color:var(--so-dim);text-decoration:line-through}
.so-sched li.so-now span:nth-child(2){color:#fff;font-weight:500}
.so-tag{font-family:var(--so-mono);font-size:10px;letter-spacing:.12em;text-transform:uppercase;padding:2px 7px;border:1px solid var(--so-border-glow);color:var(--so-muted);white-space:nowrap}
.so-tag.focus{color:var(--so-gold);border-color:rgba(255,208,0,.45)}
.so-tag.free{color:var(--so-green);border-color:rgba(63,185,80,.45)}
.so-tag.imp{color:var(--so-verm);border-color:rgba(232,93,4,.5)}
.so-toast{margin-top:16px;display:flex;gap:12px;align-items:flex-start;padding:12px 14px;background:var(--so-surface);border-left:3px solid var(--so-verm);font-size:13px;opacity:0;transform:translateY(8px);transition:opacity .6s,transform .6s}
.so-toast.show{opacity:1;transform:none}
.so-toast b{color:#fff;font-weight:600;display:block}
.so-toast span{color:var(--so-muted)}
.so-toast .so-pin{font-family:var(--so-mono);font-size:10px;color:var(--so-verm);letter-spacing:.12em;text-transform:uppercase;margin-top:2px;white-space:nowrap}
.so-ask{margin-top:14px;display:flex;justify-content:space-between;align-items:center;gap:12px;font-size:13px;color:var(--so-muted)}
.so-ask button{font-family:var(--so-mono);font-size:11px;letter-spacing:.08em;background:none;border:1px solid var(--so-border-glow);color:var(--so-ink);padding:7px 12px;cursor:pointer;transition:.2s}
.so-ask button:hover{border-color:var(--so-gold);color:var(--so-gold)}
/* ---------- sections ---------- */
.so-section{padding:96px 0;border-top:1px solid var(--so-border)}
.so-label{font-family:var(--so-mono);font-size:11px;letter-spacing:.3em;text-transform:uppercase;color:var(--so-amber);margin-bottom:14px}
.so-label::before{content:"¶";color:var(--so-verm);margin-right:10px;font-family:var(--so-serif);font-size:16px;letter-spacing:0}
.so-h2{font-family:var(--so-serif);font-weight:500;font-size:clamp(32px,4vw,46px);line-height:1.1;color:var(--so-bright);margin:0 0 18px;max-width:700px}
.so-intro{font-size:17px;color:var(--so-muted);max-width:660px;margin:0 0 48px}
.so-intro a{color:var(--so-gold);text-decoration:none;border-bottom:1px solid rgba(255,208,0,.35)}
/* illuminated mini initial */
.so-cap{float:left;font-family:var(--so-serif);font-style:italic;font-size:42px;line-height:1;width:58px;height:58px;display:flex;align-items:center;justify-content:center;color:var(--so-gold);border:1px solid rgba(255,208,0,.5);box-shadow:inset 0 0 0 3px #0b1226,inset 0 0 0 4px rgba(250,163,7,.35);background:#0b1226;margin:4px 16px 6px 0;text-shadow:0 0 12px rgba(255,208,0,.35);flex:0 0 auto}
/* two sides */
.so-two{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--so-border);border:1px solid var(--so-border)}
.so-two > div{background:var(--so-surface);padding:38px 36px}
.so-two h3{font-family:var(--so-serif);font-size:26px;font-weight:500;color:var(--so-bright);margin:0 0 12px}
.so-two p{margin:0 0 12px;color:var(--so-muted);font-size:15px}
.so-two p:last-child{margin-bottom:0}
.so-two .so-who{font-family:var(--so-mono);font-size:11px;letter-spacing:.2em;text-transform:uppercase;color:var(--so-amber);margin-bottom:14px}
.so-two > div:nth-child(2) .so-who{color:var(--so-lapis)}
.so-two > div:nth-child(2) .so-cap{color:var(--so-lapis);border-color:rgba(74,122,181,.6);text-shadow:0 0 12px rgba(74,122,181,.5);box-shadow:inset 0 0 0 3px #0b1226,inset 0 0 0 4px rgba(74,122,181,.35)}
/* features */
.so-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--so-border);border:1px solid var(--so-border)}
.so-feat{background:var(--so-surface);padding:34px 30px 36px;transition:background .2s}
.so-feat:hover{background:var(--so-card-hover)}
.so-feat .so-cap{float:none;margin:0 0 18px;width:52px;height:52px;font-size:36px}
.so-feat h3{font-family:var(--so-serif);font-size:23px;font-weight:500;color:var(--so-bright);margin:0 0 10px;line-height:1.2}
.so-feat p{margin:0;color:var(--so-muted);font-size:15px}
/* companions */
.so-comp{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
.so-comp article{--accent:var(--so-gold);background:var(--so-card);border:1px solid var(--so-border-glow);padding:34px 30px;position:relative}
.so-comp article::before{content:"";position:absolute;top:-1px;left:-1px;right:-1px;height:2px;background:linear-gradient(90deg,var(--accent),transparent 80%)}
.so-comp article.so-ledger{--accent:var(--so-lapis)}
.so-comp article.so-hours-card{--accent:var(--so-verm)}
.so-comp .so-cap{float:none;width:68px;height:68px;font-size:50px;margin:0 0 20px}
.so-comp h3{font-family:var(--so-serif);font-size:32px;font-weight:500;color:#fff;margin:0;line-height:1.1}
.so-role{font-family:var(--so-mono);font-size:11px;letter-spacing:.18em;text-transform:uppercase;color:var(--so-amber);margin:8px 0 16px}
.so-comp p{color:var(--so-muted);font-size:15px;margin:0 0 16px}
.so-lines{list-style:none;padding:0;margin:0;border-top:1px dashed var(--so-border)}
.so-lines li{padding:9px 0;border-bottom:1px dashed var(--so-border);font-size:14px;color:var(--so-ink)}
.so-lines li::before{content:"¶";color:var(--so-verm);font-family:var(--so-serif);margin-right:10px}
/* how it works flow */
.so-flow{margin-top:56px;display:grid;grid-template-columns:1fr auto 1fr auto 1fr;gap:14px;align-items:stretch}
.so-node{background:var(--so-surface);border:1px solid var(--so-border-glow);padding:18px 20px}
.so-node b{display:block;font-family:var(--so-serif);font-size:22px;font-weight:500;color:#fff}
.so-node span{font-family:var(--so-mono);font-size:10px;color:var(--so-muted);letter-spacing:.14em;text-transform:uppercase}
.so-node p{margin:8px 0 0;font-size:13px;color:var(--so-muted)}
.so-arrow{display:flex;align-items:center;justify-content:center;font-family:var(--so-mono);color:var(--so-gold);font-size:22px}
.so-arrow::after{content:"→"}
.so-flow-note{margin-top:20px;font-size:14px;color:var(--so-muted);max-width:780px}
.so-flow-note b{color:var(--so-ink);font-weight:500}
/* promise */
.so-promise{background:linear-gradient(180deg,var(--so-surface),var(--so-bg))}
.so-vows{display:grid;grid-template-columns:1fr 1fr;gap:22px;margin-bottom:22px}
.so-vow{position:relative;padding:36px 34px 34px;border:1px solid rgba(255,208,0,.38);background:var(--so-card)}
.so-vow::before{content:"";position:absolute;inset:6px;border:1px solid rgba(250,163,7,.18);pointer-events:none}
.so-num{font-family:var(--so-serif);color:var(--so-gold);font-size:14px;letter-spacing:.3em;text-transform:uppercase;margin-bottom:14px}
.so-vow blockquote{margin:0;font-family:var(--so-serif);font-size:clamp(24px,2.5vw,30px);line-height:1.3;color:#fff;font-style:italic}
.so-vow blockquote::before{content:"“";color:var(--so-verm);margin-right:2px}
.so-vow blockquote::after{content:"”";color:var(--so-verm);margin-left:2px}
.so-spirit{display:grid;grid-template-columns:repeat(2,1fr);gap:1px;background:var(--so-border);border:1px solid var(--so-border)}
.so-spirit > div{background:var(--so-surface);padding:24px 26px}
.so-spirit h4{font-family:var(--so-serif);font-size:20px;font-weight:500;color:var(--so-bright);margin:0 0 6px}
.so-spirit p{margin:0;font-size:14px;color:var(--so-muted)}
/* roadmap */
.so-road{position:relative;padding-left:34px;max-width:820px}
.so-road::before{content:"";position:absolute;left:8px;top:8px;bottom:8px;width:1px;background:linear-gradient(180deg,var(--so-gold),var(--so-border) 65%,transparent)}
.so-phase{font-family:var(--so-mono);font-size:11px;letter-spacing:.3em;text-transform:uppercase;color:var(--so-dim);margin:0 0 20px;position:relative}
.so-phase:not(:first-child){margin-top:14px}
.so-mile{position:relative;padding:0 0 30px}
.so-mile::before{content:"";position:absolute;left:-30px;top:10px;width:9px;height:9px;background:var(--so-bg);border:1px solid var(--so-gold);transform:rotate(45deg)}
.so-mile.now::before{background:var(--so-gold);box-shadow:0 0 12px rgba(255,208,0,.6)}
.so-mile.later::before{border-color:var(--so-dim)}
.so-mile h3{font-family:var(--so-serif);font-size:24px;font-weight:500;color:var(--so-bright);margin:0 0 6px;display:flex;flex-wrap:wrap;gap:10px;align-items:center;line-height:1.2}
.so-mile p{margin:0;color:var(--so-muted);font-size:15px}
.so-mile.so-featured{background:var(--so-card);border:1px solid rgba(232,93,4,.45);padding:26px 26px 24px;margin:6px 0 34px}
.so-mile.so-featured::before{top:36px}
.so-mile.so-featured h3{font-size:28px}
.so-mile.so-featured p{color:var(--so-ink)}
.so-pill{font-family:var(--so-mono);font-size:10px;letter-spacing:.16em;text-transform:uppercase;padding:3px 8px;border:1px solid var(--so-border-glow);color:var(--so-muted);font-weight:400;white-space:nowrap}
.so-pill.testing{color:var(--so-gold);border-color:rgba(255,208,0,.45)}
.so-pill.building{color:var(--so-cyan);border-color:rgba(0,212,255,.4)}
.so-pill.planned{color:var(--so-lapis);border-color:rgba(74,122,181,.55)}
.so-pill.later{color:var(--so-muted);border-color:var(--so-border-glow)}
.so-pill.only{color:var(--so-verm);border-color:rgba(232,93,4,.55)}
/* under the hood + closing */
.so-hood{border-top:1px solid var(--so-border);padding:30px 0;font-family:var(--so-mono);font-size:12px;color:var(--so-muted);display:flex;flex-wrap:wrap;gap:10px 30px;line-height:1.7}
.so-hood b{color:var(--so-ink);font-weight:500}
.so-close{padding:92px 0;text-align:center;border-top:1px solid var(--so-border);background:radial-gradient(ellipse 50% 70% at 50% 100%,rgba(255,208,0,.09),transparent 70%)}
.so-close .so-h2{margin:0 auto 14px}
.so-close p{color:var(--so-muted);max-width:560px;margin:0 auto 30px;font-size:16px}
.so-close .so-ctas{justify-content:center}
.so-close .so-initial{width:96px;height:96px;flex-basis:96px;margin:0 auto 26px}
/* responsive */
@media (max-width:960px){
  .so-hero .so-wrap{grid-template-columns:1fr;gap:44px}
  .so-grid{grid-template-columns:repeat(2,1fr)}
  .so-comp{grid-template-columns:1fr}
  .so-flow{grid-template-columns:1fr}
  .so-arrow::after{content:"↓"}
  .so-vows,.so-spirit,.so-two{grid-template-columns:1fr}
}
@media (max-width:600px){
  .so-grid{grid-template-columns:1fr}
  .so-hero{padding:56px 0 48px}
  .so-section{padding:64px 0}
  .so-open{gap:18px}
  .so-initial{flex-basis:96px;width:96px;height:96px}
  .so-title{font-size:36px}
  .so-hours{padding:16px}
  .so-count-num{font-size:38px}
  .so-two > div,.so-feat,.so-comp article,.so-vow{padding:26px 22px}
  .so-road{padding-left:26px}
  .so-mile::before{left:-22px}
}
@media (prefers-reduced-motion:reduce){.so-badge i{animation:none}.so-toast{transition:none}}
</style>
<svg width="0" height="0" style="position:absolute" aria-hidden="true">
  <defs>
    <radialGradient id="soField" cx="50%" cy="42%" r="62%"><stop offset="0" stop-color="#1b2c5e"/><stop offset="1" stop-color="#0a1024"/></radialGradient>
    <linearGradient id="soGold" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#ffe88a"/><stop offset=".55" stop-color="#FFD000"/><stop offset="1" stop-color="#b98300"/></linearGradient>
    <symbol id="soInitialS" viewBox="0 0 160 160">
      <rect x="4" y="4" width="152" height="152" fill="url(#soField)" stroke="url(#soGold)" stroke-width="3"/>
      <rect x="13" y="13" width="134" height="134" fill="none" stroke="#FAA307" stroke-width="1" opacity=".55"/>
      <g fill="none" stroke="#FFD000" stroke-width="1.5" stroke-linecap="round" opacity=".9">
        <path d="M22 22c16 2 26 11 29 28"/><path d="M22 22c2 16 11 26 28 29"/>
        <path d="M138 22c-16 2-26 11-29 28"/><path d="M138 22c-2 16-11 26-28 29"/>
        <path d="M22 138c16-2 26-11 29-28"/><path d="M22 138c2-16 11-26 28-29"/>
        <path d="M138 138c-16-2-26-11-29-28"/><path d="M138 138c-2-16-11-26-28-29"/>
        <path d="M36 28c5 0 8 3 8 8" opacity=".7"/><path d="M124 28c-5 0-8 3-8 8" opacity=".7"/>
        <path d="M36 132c5 0 8-3 8-8" opacity=".7"/><path d="M124 132c-5 0-8-3-8-8" opacity=".7"/>
      </g>
      <g fill="#FFD000" opacity=".85">
        <ellipse cx="38" cy="45" rx="2.2" ry="4.5" transform="rotate(-40 38 45)"/><ellipse cx="45" cy="38" rx="2.2" ry="4.5" transform="rotate(50 45 38)"/>
        <ellipse cx="122" cy="45" rx="2.2" ry="4.5" transform="rotate(40 122 45)"/><ellipse cx="115" cy="38" rx="2.2" ry="4.5" transform="rotate(-50 115 38)"/>
        <ellipse cx="38" cy="115" rx="2.2" ry="4.5" transform="rotate(40 38 115)"/><ellipse cx="45" cy="122" rx="2.2" ry="4.5" transform="rotate(-50 45 122)"/>
        <ellipse cx="122" cy="115" rx="2.2" ry="4.5" transform="rotate(-40 122 115)"/><ellipse cx="115" cy="122" rx="2.2" ry="4.5" transform="rotate(50 115 122)"/>
      </g>
      <g fill="#E85D04"><circle cx="51" cy="51" r="2.6"/><circle cx="109" cy="51" r="2.6"/><circle cx="51" cy="109" r="2.6"/><circle cx="109" cy="109" r="2.6"/></g>
      <g fill="#FFD000"><path d="M80 9l4 6-4 6-4-6z"/><path d="M80 139l4 6-4 6-4-6z"/><path d="M9 80l6-4 6 4-6 4z"/><path d="M139 80l6-4 6 4-6 4z"/></g>
      <text x="80" y="118" font-family="'EB Garamond',Georgia,'Times New Roman',serif" font-style="italic" font-size="112" text-anchor="middle" fill="url(#soGold)">S</text>
    </symbol>
  </defs>
</svg>
<!-- ============ HERO ============ -->
<section class="so-hero">
  <div class="so-wrap">
    <div class="so-hero-left">
      <div class="so-badge"><i></i> Private beta · September 2026</div>
      <div class="so-open">
        <svg class="so-initial" role="img" aria-label="Illuminated initial S"><use href="#soInitialS"/></svg>
        <div>
          <div class="so-wordmark">ScrivenerOS</div>
          <h1 class="so-title">An operating system for <em>a parent and a child.</em></h1>
          <span class="so-dim">// mentor and pupil. one shared machine. no terminal required.</span>
        </div>
      </div>
      <p class="so-lede">ScrivenerOS is a kid-oriented Linux that promotes focus, rewards curiosity and calms the soul when the student signs in — and stays delightfully easy for the parent who runs it. Setup is a wizard. Secure Boot stays on. And all of it is free.</p>
      <div class="so-ctas">
        <a class="so-btn so-btn-primary" href="#promise">Read our promise ↓</a>
        <a class="so-btn so-btn-ghost" href="https://github.com/AnarchySC" target="_blank" rel="noopener">Follow the build →</a>
      </div>
    </div>
    <div class="so-hero-right">
      <div class="so-window" aria-label="Preview of the Hours widget">
        <div class="so-titlebar">
          <div class="so-dots"><i></i><i></i><i></i></div>
          <span>Hours — today</span>
          <span class="so-live">● in sync</span>
        </div>
        <div class="so-hours">
          <div class="so-hours-head">
            <div class="so-hours-day">Tuesday</div>
            <div class="so-hours-date">Focus time · 3 apps open</div>
          </div>
          <div class="so-count">
            <div>
              <div class="so-count-label">Focus ends in</div>
              <div class="so-count-num" id="so-count">24:13</div>
            </div>
            <div class="so-count-next">then<b>Free time · Steam unlocks</b></div>
          </div>
          <ul class="so-sched">
            <li class="so-done"><time>09:00</time><span>Reading</span><span class="so-tag">done</span></li>
            <li class="so-now"><time>10:30</time><span>Math</span><span class="so-tag focus">focus</span></li>
            <li><time>12:00</time><span>Lunch</span><span class="so-tag">break</span></li>
            <li><time>13:00</time><span>Free time</span><span class="so-tag free">free</span></li>
            <li><time>15:00</time><span>Piano lesson</span><span class="so-tag imp">important</span></li>
          </ul>
          <div class="so-toast" id="so-toast">
            <div><b>Save your work.</b><span>Focus time ends in five minutes — Math will close on its own.</span></div>
            <div class="so-pin">from Ledger</div>
          </div>
          <div class="so-ask"><span>Need a little longer?</span><button type="button">Ask for 15 more minutes</button></div>
        </div>
      </div>
    </div>
  </div>
</section>
<!-- ============ THE IDEA ============ -->
<section class="so-section" id="idea">
  <div class="so-wrap">
    <div class="so-label">the idea</div>
    <h2 class="so-h2">It's a relationship, not a machine.</h2>
    <p class="so-intro">Most kid-safe computers are built around one user and a wall of locks. ScrivenerOS is built around two people. The student gets a desk that helps them concentrate. The parent gets a book of rules that's a pleasure to keep. Same laptop, one cohesive experience, and every page of it looks like it belongs to the same book.</p>
    <div class="so-two">
      <div>
        <div class="so-who">When the student signs in</div>
        <span class="so-cap">P</span>
        <h3>A quiet desk that wants you to learn.</h3>
        <p>A calm, cohesive desktop: dock on the left, a theme they helped choose, an illuminated initial where a stranger's logo would normally sit. Hours keeps today's plan in the corner so nothing sneaks up on them, and Learn your Linux waits in the dock with lessons that begin with a picture of the thing — not a wall of text.</p>
        <p>Nothing is locked for the sake of it. The student can install Steam, a paint program, a code editor. Rules only exist where a parent wrote one.</p>
      </div>
      <div>
        <div class="so-who">When the parent signs in</div>
        <span class="so-cap">M</span>
        <h3>Everything happens in a wizard or on your phone.</h3>
        <p>First boot walks you through it: your own admin account, the student's account, a theme, the apps you'd like installed (each one explains what it's good for), and whether you're adding more students. No terminal. No firmware menu. Nobody ever asks you to disable Secure Boot.</p>
        <p>After that, the rules live in Ledger on your phone. Change a window, approve a request, send a note — the laptop catches up on its own.</p>
      </div>
    </div>
  </div>
</section>
<!-- ============ FEATURES ============ -->
<section class="so-section" id="features">
  <div class="so-wrap">
    <div class="so-label">what's in the box</div>
    <h2 class="so-h2">Everything a family laptop should already do.</h2>
    <p class="so-intro">Here is the whole feature list, in plain language. Every one of these is either in the current test build or in the companion apps described below.</p>
    <div class="so-grid">
      <div class="so-feat"><span class="so-cap">S</span><h3>Secure Boot, on.</h3><p>Boots with Secure Boot enabled on an unmodified laptop. Nobody is ever told to turn it off, enroll a key, or click through a blue screen full of warnings.</p></div>
      <div class="so-feat"><span class="so-cap">W</span><h3>A wizard, not a terminal.</h3><p>First boot creates the parent's admin account and the student's account, picks a theme, picks apps — each with a plain-English bubble saying what it's good for — and asks whether you're adding more students.</p></div>
      <div class="so-feat"><span class="so-cap">O</span><h3>Open by default.</h3><p>The OS restricts nothing on its own. Kids can install Steam, creative tools, whatever they're into. The managed experience is a layer the parent turns on — Quill ships installed but off.</p></div>
      <div class="so-feat"><span class="so-cap">A</span><h3>Apps, when the parent says.</h3><p>Once Quill and Ledger are paired, every app gets a window: focus time, free time, or never. Outside its window an app simply won't open. Anything newly installed waits for a parent's yes.</p></div>
      <div class="so-feat"><span class="so-cap">U</span><h3>Updates that can't wreck it.</h3><p>ScrivenerOS is an image-based OS. Updates arrive whole and tested, stage quietly in the background, apply on the next reboot, and roll back on their own if anything is wrong.</p></div>
      <div class="so-feat"><span class="so-cap">T</span><h3>Themes, chosen together.</h3><p>Pick a look during setup and the whole desktop follows — icons, colors, the works. Dock on the left, scriptorium branding throughout, no stray upstream logos.</p></div>
      <div class="so-feat"><span class="so-cap">L</span><h3>Learn your Linux.</h3><p>Built-in lessons on the desktop itself. Every topic opens with a picture of the thing it's teaching, then something to try with your own hands. Fifteen topics at launch.</p></div>
      <div class="so-feat"><span class="so-cap">H</span><h3>Hours, on the desk.</h3><p>A tuck-away widget with a countdown, today's schedule and gentle warnings before transitions — so the end of free time is never a surprise, for anyone.</p></div>
      <div class="so-feat"><span class="so-cap">D</span><h3>One disk, one OS.</h3><p>ScrivenerOS takes the whole disk — there is no dual-boot side door for a determined ten-year-old. Re-imaging is never blocked, though. It's your laptop, and it always will be.</p></div>
    </div>
  </div>
</section>
<!-- ============ COMPANIONS ============ -->
<section class="so-section" id="companions">
  <div class="so-wrap">
    <div class="so-label">the companions</div>
    <h2 class="so-h2">Three small apps, one shared page.</h2>
    <p class="so-intro">The OS on its own is a free, safe, kid-oriented Linux. Add the companions and it becomes a seriously managed device — managed in the open, where the student can read the same rules the parent wrote.</p>
    <div class="so-comp">
      <article class="so-quill">
        <span class="so-cap">Q</span>
        <h3>Quill</h3>
        <div class="so-role">the agent on the laptop</div>
        <p>Quill lives on the student's machine. It pulls the parent's ledger, compares it with what's actually on the laptop, and closes the gap — which apps may open right now, which windows are active, which reminders to show. It ships pre-installed and switched off; the parent turns it on during setup or any day later.</p>
        <ul class="so-lines">
          <li>Inventories every app on the machine</li>
          <li>Enforces focus, free time and never</li>
          <li>Blocks new installs until approved</li>
          <li>Reports refusals and time-in-app back</li>
        </ul>
      </article>
      <article class="so-ledger">
        <span class="so-cap">L</span>
        <h3>Ledger</h3>
        <div class="so-role">the parent's book of rules</div>
        <p>A phone-first web app you install straight from the browser — no app store, no account with anyone else. See what's installed on the kid's laptop, set focus time and free time, decide when each app can launch, approve a request with one tap, and send a note that appears on their screen.</p>
        <ul class="so-lines">
          <li>Temporary overrides that expire on their own</li>
          <li>Pause now, with a forced save-your-game warning</li>
          <li>Websites managed in the same focus / free / never list</li>
          <li>Two parents, one ledger; copy a setup to the next kid</li>
          <li>A change history the kid can read too</li>
        </ul>
      </article>
      <article class="so-hours-card">
        <span class="so-cap">H</span>
        <h3>Hours</h3>
        <div class="so-role">the student's day, at a glance</div>
        <p>A widget that tucks away. A countdown, today's schedule, and a heads-up before anything changes. The student chooses which pop-ups they want; the parent can insist on a few — save your work, save your game, the piano lesson is in ten minutes.</p>
        <ul class="so-lines">
          <li>Today view the moment they sign in</li>
          <li>Countdown to the next transition</li>
          <li>Ask for more time, answered from Ledger</li>
          <li>A weekly note home about what got done</li>
        </ul>
      </article>
    </div>
    <div class="so-flow" aria-label="How the companions work together">
      <div class="so-node"><span>desired state</span><b>Ledger</b><p>The parent writes how the laptop should be.</p></div>
      <div class="so-arrow" aria-hidden="true"></div>
      <div class="so-node"><span>reconciler</span><b>Quill</b><p>Compares that with how the laptop actually is, and fixes the difference.</p></div>
      <div class="so-arrow" aria-hidden="true"></div>
      <div class="so-node"><span>what the student sees</span><b>Hours</b><p>Shows the plan, the countdown and any note the parent sent.</p></div>
    </div>
    <p class="so-flow-note"><b>"In compliance" just means there's no difference left.</b> Ledger and Quill talk to each other directly over your home network first; a relay only steps in when you're away from home, and it only carries addresses — never what's being said.</p>
  </div>
</section>
<!-- ============ PROMISE ============ -->
<section class="so-section so-promise" id="promise">
  <div class="so-wrap">
    <div class="so-label">our promise</div>
    <h2 class="so-h2">Two things we will never do to you.</h2>
    <p class="so-intro">Written down, in public, so you can hold us to it.</p>
    <div class="so-vows">
      <div class="so-vow">
        <div class="so-num">I</div>
        <blockquote>ScrivenerOS will never ask for ID verification to use it or its apps.</blockquote>
      </div>
      <div class="so-vow">
        <div class="so-num">II</div>
        <blockquote>All updates and apps made for ScrivenerOS will always be free.</blockquote>
      </div>
    </div>
    <div class="so-spirit">
      <div><h4>Open source, all of it.</h4><p>The OS and its companion apps are developed in public. You can read exactly what the laptop does and doesn't do.</p></div>
      <div><h4>No surveillance features.</h4><p>Ledger shows rules, refusals and time-in-app — the same view the student can see. No screenshots, no keylogging, no location, no reading of messages.</p></div>
      <div><h4>The student can see the rules.</h4><p>Every change lands in a history both sides can read. Trust is easier when nobody is guessing.</p></div>
      <div><h4>How the lights stay on.</h4><p>Optional support and convenience services for families who want them. The software itself is never the product.</p></div>
    </div>
  </div>
</section>
<!-- ============ ROADMAP ============ -->
<section class="so-section" id="roadmap">
  <div class="so-wrap">
    <div class="so-label">the roadmap</div>
    <h2 class="so-h2">Where this is going.</h2>
    <p class="so-intro">The parts of the plan the outside world might actually care about. Internal plumbing not included.</p>
    <div class="so-road">
      <div class="so-phase">Now</div>
      <div class="so-mile now">
        <h3>Beta on the Framework Laptop 12 <span class="so-pill testing">in testing</span></h3>
        <p>Secure Boot on, the setup wizard, themes, the app picker and Learn your Linux — dated test builds are being run on real hardware, and nothing ships until every one of them has been signed off in person.</p>
      </div>
      <div class="so-phase">Next</div>
      <div class="so-mile">
        <h3>Quill <span class="so-pill building">building</span></h3>
        <p>Pairing with Ledger, app windows, usage accounting, and the launch gate that politely says "not right now."</p>
      </div>
      <div class="so-mile">
        <h3>Hours <span class="so-pill building">building</span></h3>
        <p>The countdown, the today view, forced reminders, and the "ask for more time" button that reaches the parent's phone.</p>
      </div>
      <div class="so-mile">
        <h3>Ledger <span class="so-pill building">building</span></h3>
        <p>The phone-first parent app: installed from the browser, works on the home network, reaches the laptop when you're away.</p>
      </div>
      <div class="so-mile">
        <h3>Website rules, per student <span class="so-pill building">building</span></h3>
        <p>Focus, free and never apply to websites too — set per student and enforced on the laptop itself, not just inside one browser's settings.</p>
      </div>
      <div class="so-mile">
        <h3>Learn your Linux, illustrated <span class="so-pill building">building</span></h3>
        <p>Fifteen topics, each with a drawn picture of the real thing on screen and a try-it step.</p>
      </div>
      <div class="so-phase">Planned</div>
      <div class="so-mile so-featured">
        <h3>A Discord alternative <span class="so-pill planned">planned</span> <span class="so-pill only">ScrivenerOS only</span></h3>
        <p>A place to talk that only works between people on ScrivenerOS. No public servers, no strangers wandering in — if they aren't on ScrivenerOS, they aren't in the room.</p>
      </div>
      <div class="so-mile">
        <h3>A scriptorium installer <span class="so-pill planned">planned</span></h3>
        <p>The install screens get the same illuminated look as everything after them.</p>
      </div>
      <div class="so-mile">
        <h3>Deeper appearance options <span class="so-pill planned">planned</span></h3>
        <p>A matching icon set, window animations and color options that follow the chosen theme.</p>
      </div>
      <div class="so-mile">
        <h3>Public update channels <span class="so-pill planned">planned</span></h3>
        <p>Signed images on a public registry with stable and testing channels, so your laptop's updates come from a source you can verify.</p>
      </div>
      <div class="so-phase">Later</div>
      <div class="so-mile later">
        <h3>Framework laptops, pre-installed <span class="so-pill later">later</span></h3>
        <p>Order a Framework with ScrivenerOS already on it and the wizard waiting at first boot.</p>
      </div>
    </div>
  </div>
</section>
<!-- ============ UNDER THE HOOD ============ -->
<section class="so-hood-wrap">
  <div class="so-wrap">
    <div class="so-hood">
      <span><b>Base</b> Universal Blue's Bluefin (Fedora), image-based via bootc</span>
      <span><b>Desktop</b> GNOME</span>
      <span><b>Boot</b> stock Fedora shim, Secure Boot on</span>
      <span><b>Quill &amp; Hours</b> Python + GTK4</span>
      <span><b>Ledger</b> SvelteKit, installable web app</span>
      <span><b>Reference hardware</b> Framework Laptop 12</span>
    </div>
  </div>
</section>
<!-- ============ CLOSING ============ -->
<section class="so-close">
  <div class="so-wrap">
    <svg class="so-initial" role="img" aria-label="Illuminated initial S"><use href="#soInitialS"/></svg>
    <h2 class="so-h2">Want in?</h2>
    <p>The beta is private while it's being tested on real laptops. The build happens in the open, so you can watch it come together — and hold us to the promise above.</p>
    <div class="so-ctas">
      <a class="so-btn so-btn-primary" href="https://github.com/AnarchySC" target="_blank" rel="noopener">Follow the build on GitHub →</a>
      <a class="so-btn so-btn-ghost" href="/projects/">All projects</a>
    </div>
  </div>
</section>
<script>
(function(){
  var el=document.getElementById('so-count');
  if(el){
    var start=24*60+13, s=start;
    setInterval(function(){ s--; if(s<0){ s=start; } var m=Math.floor(s/60), r=s%60; el.textContent=(m<10?'0':'')+m+':'+(r<10?'0':'')+r; },1000);
  }
  var t=document.getElementById('so-toast');
  if(t){ setTimeout(function(){ t.classList.add('show'); },1400); }
})();
</script>
</div>
