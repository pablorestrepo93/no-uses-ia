<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Space+Grotesk:wght@500;600;700;800&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#0a0a0f;--bg2:#111118;--card:#181824;
  --acc:#7c5cfc;--accl:#a98fff;--accg:rgba(124,92,252,0.28);
  --teal:#00d4aa;--tealg:rgba(0,212,170,0.22);
  --gold:#f5c842;--red:#ff6b6b;
  --t1:#f4f4fc;--t2:#b8b8d0;--tm:#72728a;
  --bdr:rgba(255,255,255,0.09);--bdra:rgba(124,92,252,0.4);
}
html{scroll-behavior:smooth}
body{font-family:'Inter',sans-serif;background:var(--bg);color:var(--t1);overflow-x:hidden;font-size:16px;line-height:1.6}

/* ── PROGRESS BAR ── */
.progbar{
  background:rgba(10,10,15,0.97);border-bottom:1px solid var(--bdr);
  padding:14px 36px;display:flex;align-items:center;justify-content:space-between;gap:20px;
}
.prog-logo{font-family:'Space Grotesk',sans-serif;font-size:14px;font-weight:700;
  display:flex;align-items:center;gap:8px;color:var(--t1);}
.prog-logo .dot{width:28px;height:28px;background:linear-gradient(135deg,var(--acc),var(--teal));
  border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:14px;}
.prog-dots{display:flex;gap:6px;align-items:center}
.pdot{width:8px;height:8px;border-radius:50%;background:var(--bdr);border:1px solid rgba(255,255,255,.1);
  cursor:pointer;transition:all .25s;}
.pdot.m1{background:var(--acc);}
.pdot.m2{background:var(--accl);}
.pdot.m3{background:var(--teal);}
.pdot.ex{background:var(--gold);}
.prog-label{font-size:12px;color:var(--tm);font-weight:500;white-space:nowrap;}

/* ── SLIDE BASE ── */
.slide{
  min-height:600px;padding:72px 60px;
  position:relative;overflow:hidden;
  display:flex;flex-direction:column;justify-content:center;
}
.slide.full{padding:80px 60px}
.slide.alt{background:var(--bg2)}
.slide.center{align-items:center;text-align:center}
.slide-num{
  position:absolute;top:28px;right:36px;
  font-family:'Space Grotesk',sans-serif;
  font-size:11px;font-weight:700;letter-spacing:.12em;
  color:var(--tm);text-transform:uppercase;
}
.slide-wrap{max-width:1000px;width:100%;}
.slide.center .slide-wrap{margin:0 auto;}
.sdivider{height:1px;background:linear-gradient(90deg,var(--bdra),transparent);margin:40px 0;}

/* ── TYPE SCALE ── */
.tag{
  display:inline-flex;align-items:center;gap:8px;
  font-size:11px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;
  color:var(--accl);margin-bottom:20px;
}
.tag::before{content:"";width:18px;height:2px;background:var(--acc);display:inline-block;border-radius:2px;}
.tag.teal{color:var(--teal);}
.tag.teal::before{background:var(--teal);}
.tag.gold{color:var(--gold);}
.tag.gold::before{background:var(--gold);}
.tag.red{color:var(--red);}
.tag.red::before{background:var(--red);}

h1.slide-h{
  font-family:'Space Grotesk',sans-serif;
  font-size:clamp(44px,6.5vw,88px);font-weight:800;
  line-height:1.02;letter-spacing:-.03em;margin-bottom:22px;
}
h2.slide-h{
  font-family:'Space Grotesk',sans-serif;
  font-size:clamp(32px,4.5vw,60px);font-weight:800;
  line-height:1.07;letter-spacing:-.025em;margin-bottom:18px;color:var(--t1);
}
h3.slide-h{
  font-family:'Space Grotesk',sans-serif;
  font-size:clamp(22px,3vw,38px);font-weight:800;
  line-height:1.12;letter-spacing:-.02em;margin-bottom:14px;color:var(--t1);
}
.slide-sub{font-size:clamp(16px,2vw,20px);color:var(--t2);line-height:1.65;max-width:640px;}
.slide-sub.full{max-width:100%;}
.grad-text{
  background:linear-gradient(135deg,var(--accl),var(--teal));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.teal-text{color:var(--teal);}
.gold-text{color:var(--gold);}
.acc-text{color:var(--accl);}

/* ── GRID UTILS ── */
.g2{display:grid;grid-template-columns:1fr 1fr;gap:20px;}
.g3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:18px;}
.g4{display:grid;grid-template-columns:1fr 1fr 1fr 1fr;gap:16px;}
.g5{display:grid;grid-template-columns:repeat(5,1fr);gap:14px;}

/* ── CARD BASE ── */
.card{background:var(--card);border:1px solid var(--bdr);border-radius:18px;padding:28px;transition:border-color .3s;}
.card:hover{border-color:var(--bdra);}
.card.hi{border-color:var(--bdra);background:rgba(124,92,252,.07);}
.card.tealhi{border-color:rgba(0,212,170,.35);background:rgba(0,212,170,.05);}
.card.goldhi{border-color:rgba(245,200,66,.3);background:rgba(245,200,66,.05);}
.card.redhi{border-color:rgba(255,107,107,.25);background:rgba(255,107,107,.04);}
.card-ico{font-size:28px;margin-bottom:14px;}
.card h4{font-size:17px;font-weight:700;margin-bottom:8px;color:var(--t1);}
.card p{font-size:15px;color:var(--t2);line-height:1.65;}
.card h5{font-size:15px;font-weight:700;margin-bottom:8px;color:var(--t1);}

/* ── BIG STAT ── */
.bigstat-row{display:flex;gap:48px;align-items:center;flex-wrap:wrap;margin-top:8px;}
.bigstat .n{
  font-family:'Space Grotesk',sans-serif;font-size:64px;font-weight:900;line-height:1;
  background:linear-gradient(135deg,var(--accl),var(--teal));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.bigstat .l{font-size:14px;color:var(--tm);margin-top:6px;font-weight:500;}
.bigstat-div{width:1px;height:56px;background:var(--bdr);}

/* ── TOOL CARDS ── */
.tool-card{
  background:var(--card);border:1px solid var(--bdr);border-radius:16px;
  padding:24px;transition:border-color .3s,transform .2s;
}
.tool-card:hover{border-color:var(--bdra);transform:translateY(-3px);}
.tool-name{font-family:'Space Grotesk',sans-serif;font-size:16px;font-weight:800;margin-bottom:6px;color:var(--t1);}
.tool-tag{font-size:11px;font-weight:700;letter-spacing:.06em;text-transform:uppercase;margin-bottom:12px;}
.tool-tag.purple{color:var(--accl);}
.tool-tag.teal{color:var(--teal);}
.tool-tag.blue{color:#7dd3fc;}
.tool-tag.green{color:#86efac;}
.tool-desc{font-size:14px;color:var(--t2);line-height:1.6;margin-bottom:14px;}
.tool-best{font-size:12px;font-weight:600;padding:5px 12px;border-radius:20px;
  background:rgba(255,255,255,.05);border:1px solid var(--bdr);color:var(--tm);}

/* ── ROCOF ── */
.rocof-card{border-radius:18px;padding:22px 18px;text-align:center;}
.rocof-card .rl{font-family:'Space Grotesk',sans-serif;font-size:52px;font-weight:900;line-height:1;margin-bottom:8px;}
.rocof-card .rw{font-size:13px;font-weight:800;text-transform:uppercase;letter-spacing:.07em;margin-bottom:10px;}
.rocof-card .rd{font-size:13px;color:var(--t2);line-height:1.5;}
.rc1{background:rgba(124,92,252,.14);border:1px solid rgba(124,92,252,.4);}
.rc1 .rl,.rc1 .rw{color:var(--accl);}
.rc2{background:rgba(160,100,255,.1);border:1px solid rgba(160,100,255,.3);}
.rc2 .rl,.rc2 .rw{color:#c084fc;}
.rc3{background:rgba(100,180,255,.09);border:1px solid rgba(100,180,255,.28);}
.rc3 .rl,.rc3 .rw{color:#7dd3fc;}
.rc4{background:rgba(0,212,170,.1);border:1px solid rgba(0,212,170,.35);}
.rc4 .rl,.rc4 .rw{color:var(--teal);}
.rc5{background:rgba(245,200,66,.09);border:1px solid rgba(245,200,66,.3);}
.rc5 .rl,.rc5 .rw{color:var(--gold);}

/* ── PROMPT BLOCK ── */
.prompt-block{
  background:rgba(0,0,0,.35);border:1px solid var(--bdr);
  border-radius:14px;padding:20px 24px;
  font-size:15px;color:var(--t2);line-height:1.75;font-style:italic;
}
.prompt-block strong{color:var(--accl);font-style:normal;}
.prompt-block.good{border-color:rgba(0,212,252,.3);background:rgba(0,212,170,.06);}
.prompt-block.good strong{color:var(--teal);}
.prompt-block.bad{border-color:rgba(255,107,107,.25);background:rgba(255,107,107,.05);}
.prompt-block.bad strong{color:var(--red);}
.pb-label{font-size:11px;font-weight:800;letter-spacing:.1em;text-transform:uppercase;
  margin-bottom:10px;display:flex;align-items:center;gap:7px;}
.pb-label.bad{color:var(--red);}
.pb-label.good{color:var(--teal);}
.pb-label.neutral{color:var(--accl);}

/* ── STEPS ── */
.steps{display:flex;flex-direction:column;gap:12px;}
.step{display:flex;align-items:flex-start;gap:14px;}
.step-n{
  width:28px;height:28px;flex-shrink:0;
  border-radius:50%;background:var(--acc);color:#fff;
  display:flex;align-items:center;justify-content:center;
  font-family:'Space Grotesk',sans-serif;font-size:12px;font-weight:800;
}
.step-n.teal{background:var(--teal);}
.step-n.gold{background:var(--gold);color:#0a0a0f;}
.step-body h6{font-size:15px;font-weight:700;color:var(--t1);margin-bottom:3px;}
.step-body p{font-size:14px;color:var(--t2);line-height:1.55;}

/* ── EXERCISE SLIDE ── */
.slide.exercise{background:linear-gradient(135deg,rgba(245,200,66,.06),rgba(124,92,252,.05)),var(--bg);}
.ex-header{display:flex;align-items:center;gap:16px;margin-bottom:32px;}
.ex-badge{
  background:rgba(245,200,66,.13);border:1px solid rgba(245,200,66,.4);
  color:var(--gold);font-size:11px;font-weight:800;
  padding:8px 18px;border-radius:50px;letter-spacing:.08em;text-transform:uppercase;
}
.ex-timer{
  background:rgba(255,255,255,.05);border:1px solid var(--bdr);
  color:var(--t2);font-size:13px;font-weight:600;
  padding:8px 16px;border-radius:50px;display:flex;align-items:center;gap:7px;
}
.ex-box{
  background:var(--card);border:2px solid rgba(245,200,66,.3);
  border-radius:20px;padding:32px;
}
.ex-box h3{font-family:'Space Grotesk',sans-serif;font-size:22px;font-weight:800;margin-bottom:8px;color:var(--t1);}
.ex-box .ex-desc{font-size:16px;color:var(--t2);margin-bottom:24px;line-height:1.65;}
.ex-options{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.ex-opt{
  border:1px solid rgba(245,200,66,.2);border-radius:12px;
  padding:16px 18px;background:rgba(245,200,66,.04);
  font-size:14px;color:var(--t2);line-height:1.5;
}
.ex-opt strong{color:var(--gold);font-size:15px;display:block;margin-bottom:4px;}

/* ── BEFORE / AFTER ── */
.ba-wrap{display:grid;grid-template-columns:1fr auto 1fr;gap:14px;align-items:start;}
.ba-col{background:var(--card);border:1px solid var(--bdr);border-radius:14px;overflow:hidden;}
.ba-head{padding:12px 18px;font-size:12px;font-weight:800;letter-spacing:.07em;text-transform:uppercase;}
.ba-head.bad{background:rgba(255,107,107,.1);color:var(--red);border-bottom:1px solid rgba(255,107,107,.2);}
.ba-head.good{background:rgba(0,212,170,.08);color:var(--teal);border-bottom:1px solid rgba(0,212,170,.2);}
.ba-body{padding:16px 18px;}
.ba-item{font-size:14px;color:var(--t2);padding:7px 0;border-bottom:1px solid var(--bdr);line-height:1.5;}
.ba-item:last-child{border-bottom:none;}
.ba-arrow{font-size:32px;align-self:center;text-align:center;color:var(--accl);}

/* ── COVER SLIDE specific ── */
.cover-bg{
  background:
    radial-gradient(ellipse 90% 70% at 50% -5%,rgba(124,92,252,.22) 0%,transparent 70%),
    radial-gradient(ellipse 50% 40% at 85% 95%,rgba(0,212,170,.1) 0%,transparent 60%),
    var(--bg);
}
.cover-grid{
  position:absolute;inset:0;z-index:0;
  background-image:linear-gradient(rgba(255,255,255,.03) 1px,transparent 1px),
                   linear-gradient(90deg,rgba(255,255,255,.03) 1px,transparent 1px);
  background-size:60px 60px;
  -webkit-mask-image:radial-gradient(ellipse at center,black 25%,transparent 75%);
  mask-image:radial-gradient(ellipse at center,black 25%,transparent 75%);
}
.cover-inner{position:relative;z-index:1;}

/* ── FLOW CHAIN ── */
.flow{display:flex;align-items:center;gap:10px;flex-wrap:wrap;margin-top:14px;}
.flow-step{
  background:var(--card);border:1px solid var(--bdr);border-radius:12px;
  padding:14px 20px;font-size:15px;font-weight:700;color:var(--t1);
}
.flow-step.active{border-color:var(--bdra);background:rgba(124,92,252,.1);color:var(--accl);}
.flow-step.teal{border-color:rgba(0,212,170,.35);background:rgba(0,212,170,.08);color:var(--teal);}
.flow-arrow{font-size:20px;color:var(--tm);}

/* ── RULE CARDS ── */
.rule-row{display:flex;flex-direction:column;gap:10px;}
.rule{
  display:flex;align-items:flex-start;gap:14px;
  background:var(--card);border:1px solid var(--bdr);border-radius:14px;
  padding:18px 22px;
}
.rule .ri{font-size:22px;flex-shrink:0;}
.rule h5{font-size:15px;font-weight:700;color:var(--t1);margin-bottom:4px;}
.rule p{font-size:14px;color:var(--t2);line-height:1.55;}
.rule.danger{border-color:rgba(255,107,107,.3);background:rgba(255,107,107,.04);}
.rule.safe{border-color:rgba(0,212,170,.3);background:rgba(0,212,170,.04);}

/* ── PACT ── */
.pact-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;}
.pact-item{
  background:var(--card);border:1px solid var(--bdr);border-radius:16px;
  padding:24px 20px;text-align:center;
}
.pact-item .pi{font-size:32px;margin-bottom:12px;}
.pact-item h5{font-size:15px;font-weight:700;color:var(--t1);margin-bottom:7px;}
.pact-item p{font-size:13px;color:var(--t2);line-height:1.55;}

/* ── CLOSE SLIDE ── */
.close-banner{
  background:linear-gradient(135deg,rgba(124,92,252,.1),rgba(0,212,170,.07));
  border:1px solid var(--bdra);border-radius:24px;padding:56px;text-align:center;
}
.btn-p{
  background:linear-gradient(135deg,var(--acc),var(--accl));color:#fff;border:none;
  padding:16px 40px;border-radius:50px;font-size:16px;font-weight:700;
  cursor:pointer;text-decoration:none;display:inline-flex;align-items:center;gap:8px;
  box-shadow:0 8px 28px var(--accg);transition:transform .2s,box-shadow .2s;
}
.btn-p:hover{transform:translateY(-2px);box-shadow:0 14px 40px var(--accg);}

/* ── FOOTER ── */
.foot{background:var(--bg);border-top:1px solid var(--bdr);padding:40px 60px;text-align:center;}
.flogo{font-family:'Space Grotesk',sans-serif;font-size:17px;font-weight:800;
  background:linear-gradient(135deg,var(--accl),var(--teal));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  margin-bottom:10px;}
.foot p{font-size:13px;color:var(--tm);}

/* ── RESPONSIVE ── */
@media(max-width:860px){
  .slide{padding:52px 24px;min-height:auto;}
  .progbar{padding:12px 20px;}
  .g2,.g3,.g4,.g5{grid-template-columns:1fr;}
  .ba-wrap{grid-template-columns:1fr;}
  .ba-arrow{display:none;}
  .bigstat-row{gap:28px;}
  .bigstat .n{font-size:44px;}
  .pact-grid{grid-template-columns:1fr;}
  .ex-options{grid-template-columns:1fr;}
  .foot{padding:36px 24px;}
}
</style>
</head>
<body>

<!-- PROGRESS BAR -->
<div class="progbar">
  <div class="prog-logo">
    <span class="dot">⚡</span>
    De Prompts a Resultados
  </div>
  <div class="prog-dots">
    <a href="#s1" class="pdot m1" title="Portada"></a>
    <a href="#s2" class="pdot m1" title="Bienvenida"></a>
    <a href="#s3" class="pdot m1" title="Por qué hoy"></a>
    <a href="#s4" class="pdot m1" title="El pacto"></a>
    <a href="#s5" class="pdot m1" title="Cómo funciona la IA"></a>
    <a href="#s6" class="pdot m1" title="Las herramientas"></a>
    <a href="#s7" class="pdot m1" title="Seguridad"></a>
    <a href="#s8" class="pdot ex" title="Ejercicio 1"></a>
    <a href="#s9" class="pdot m2" title="Por qué fallan"></a>
    <a href="#s10" class="pdot m2" title="ROCOF"></a>
    <a href="#s11" class="pdot m2" title="Demos en vivo"></a>
    <a href="#s12" class="pdot ex" title="Ejercicio 2"></a>
    <a href="#s13" class="pdot m3" title="Cambio de mentalidad"></a>
    <a href="#s14" class="pdot m3" title="El flujo"></a>
    <a href="#s15" class="pdot m3" title="Construcción en vivo"></a>
    <a href="#s16" class="pdot ex" title="Proyecto final"></a>
    <a href="#s17" class="pdot m3" title="Lo que cambió"></a>
    <a href="#s18" class="pdot m3" title="Cierre"></a>
  </div>
  <div class="prog-label">18 slides · 4 horas</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 01 — PORTADA -->
<!-- ══════════════════════════════════════════ -->
<div id="s1" class="slide full center cover-bg" style="padding:100px 60px;">
  <div class="cover-grid"></div>
  <div class="cover-inner slide-wrap">
    <div class="tag" style="justify-content:center;margin-bottom:28px;">Masterclass · IA Aplicada para Profesionales</div>
    <h1 class="slide-h" style="text-align:center;">
      <span style="display:block;color:var(--t1);">No uses IA.</span>
      <span class="grad-text" style="display:block;">Piensa con ella.</span>
    </h1>
    <p class="slide-sub" style="margin:0 auto 48px;text-align:center;">
      Hoy vas a aprender a convertir la inteligencia artificial
      en tu ventaja competitiva más real y más usable.
    </p>
    <div class="bigstat-row" style="justify-content:center;">
      <div class="bigstat"><div class="n">4h</div><div class="l">de trabajo real</div></div>
      <div class="bigstat-div"></div>
      <div class="bigstat"><div class="n">3</div><div class="l">módulos prácticos</div></div>
      <div class="bigstat-div"></div>
      <div class="bigstat"><div class="n">6</div><div class="l">entregables tuyos</div></div>
    </div>
  </div>
  <div class="slide-num">01 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 02 — BIENVENIDA -->
<!-- ══════════════════════════════════════════ -->
<div id="s2" class="slide alt">
  <div class="slide-wrap">
    <div class="tag">Bienvenida</div>
    <h2 class="slide-h">Hoy este espacio es tuyo.</h2>
    <p class="slide-sub" style="margin-bottom:40px;">
      No hay respuestas incorrectas. No hay preguntas tontas.<br/>
      Lo único que importa es que salgas con algo que puedas usar mañana.
    </p>
    <div class="pact-grid">
      <div class="pact-item">
        <div class="pi">🧠</div>
        <h5>Abre tu mente</h5>
        <p>La IA no es magia ni amenaza. Es una herramienta y hoy aprendes a dominarla.</p>
      </div>
      <div class="pact-item" style="border-color:var(--bdra);background:rgba(124,92,252,.06);">
        <div class="pi">💻</div>
        <h5>Abre tu herramienta</h5>
        <p>ChatGPT, Claude, Gemini o Perplexity. Tenla lista. Todo se hace en tiempo real.</p>
      </div>
      <div class="pact-item">
        <div class="pi">✋</div>
        <h5>Participa activamente</h5>
        <p>Cada ejercicio está diseñado para tu trabajo real. Sin participación, no hay transformación.</p>
      </div>
    </div>
  </div>
  <div class="slide-num">02 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 03 — POR QUÉ HOY -->
<!-- ══════════════════════════════════════════ -->
<div id="s3" class="slide">
  <div class="slide-wrap">
    <div class="tag red">El problema</div>
    <h2 class="slide-h">¿Te suena alguna de estas?</h2>
    <div class="g2" style="margin-top:10px;">
      <div class="card redhi">
        <div class="card-ico">🔁</div>
        <h4>"Siempre me da lo mismo"</h4>
        <p>Escribes una pregunta, recibes algo genérico. Lo editas a mano y pierdes más tiempo del que ahorraste.</p>
      </div>
      <div class="card">
        <div class="card-ico">🎯</div>
        <h4>"Sé que hay más, pero no sé cómo llegar"</h4>
        <p>Ves demos increíbles. Cuando tú lo intentas, los resultados no se parecen en nada a lo que viste.</p>
      </div>
      <div class="card">
        <div class="card-ico">⏱️</div>
        <h4>"La IA me consume más tiempo del que ahorra"</h4>
        <p>Intentas, falla, borras, vuelves a intentar. Al final lo hiciste tú solo más rápido.</p>
      </div>
      <div class="card redhi">
        <div class="card-ico">📉</div>
        <h4>"Mi competencia ya va adelante"</h4>
        <p>La brecha no es de herramientas. Es de método. Eso es exactamente lo que vas a cambiar hoy.</p>
      </div>
    </div>
  </div>
  <div class="slide-num">03 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 04 — EL PACTO DEL DÍA -->
<!-- ══════════════════════════════════════════ -->
<div id="s4" class="slide alt center">
  <div class="slide-wrap">
    <div class="tag gold" style="justify-content:center;">El pacto del día</div>
    <h2 class="slide-h">Una sola regla.</h2>
    <p class="slide-sub" style="margin:0 auto 48px;">
      Cada concepto que expliquemos, lo probarás en vivo.<br/>
      No antes, no después. Ahora.
    </p>
    <div class="g3">
      <div class="card goldhi" style="text-align:center;">
        <div style="font-size:40px;margin-bottom:14px;">🚫</div>
        <h4>Nada de tomar solo apuntes</h4>
        <p>Los apuntes no cambian hábitos. La práctica sí.</p>
      </div>
      <div class="card goldhi" style="text-align:center;">
        <div style="font-size:40px;margin-bottom:14px;">✅</div>
        <h4>Ejecuta mientras aprendes</h4>
        <p>Cada módulo termina con algo construido. Eso es lo que te llevas.</p>
      </div>
      <div class="card goldhi" style="text-align:center;">
        <div style="font-size:40px;margin-bottom:14px;">💬</div>
        <h4>Pregunta cuando quieras</h4>
        <p>Este espacio es tuyo. No hay preguntas fuera de lugar.</p>
      </div>
    </div>
  </div>
  <div class="slide-num">04 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 05 — CÓMO FUNCIONA LA IA -->
<!-- ══════════════════════════════════════════ -->
<div id="s5" class="slide" style="background:linear-gradient(135deg,rgba(124,92,252,.05),transparent),var(--bg);">
  <div class="slide-wrap">
    <div class="tag">Módulo 1 · Bases</div>
    <h2 class="slide-h">La IA no piensa.<br/><span class="grad-text">Predice.</span></h2>
    <p class="slide-sub" style="margin-bottom:40px;">
      Y esa diferencia lo cambia todo — especialmente la forma en que le hablas.
    </p>
    <div class="g2">
      <div>
        <div class="card hi" style="margin-bottom:16px;">
          <h4>¿Qué hace realmente la IA?</h4>
          <p>Predice la siguiente palabra más probable dado el contexto que le diste. Cuanto más claro sea ese contexto, más precisa y útil será su respuesta.</p>
        </div>
        <div class="card">
          <h4>La analogía del chef</h4>
          <p>Si le dices "haz algo rico", improvisa con lo que tiene. Si le dices exactamente qué quieres, cómo y para quién: te sorprende cada vez.</p>
        </div>
      </div>
      <div>
        <div class="card tealhi" style="margin-bottom:16px;">
          <h4 class="teal-text">✓ Lo que SÍ puede hacer</h4>
          <p>Sintetizar, generar, estructurar, iterar, analizar, editar, reformatear, traducir, comparar, proponer, criticar.</p>
        </div>
        <div class="card redhi">
          <h4 style="color:var(--red);">✗ Lo que NO puede hacer</h4>
          <p>Verificar hechos recientes sin fuentes, tener criterio ético profundo, reemplazar tu experiencia y conocimiento del contexto.</p>
        </div>
      </div>
    </div>
  </div>
  <div class="slide-num">05 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 06 — LAS 4 HERRAMIENTAS -->
<!-- ══════════════════════════════════════════ -->
<div id="s6" class="slide alt">
  <div class="slide-wrap">
    <div class="tag">Módulo 1 · Herramientas</div>
    <h2 class="slide-h">No son iguales.<br/>Elige la correcta.</h2>
    <p class="slide-sub" style="margin-bottom:36px;">Cada herramienta tiene un perfil. Conocerlos te ahorra tiempo.</p>
    <div class="g4">
      <div class="tool-card">
        <div style="font-size:26px;margin-bottom:10px;">⚡</div>
        <div class="tool-name">ChatGPT</div>
        <div class="tool-tag purple">OpenAI</div>
        <div class="tool-desc">La más versátil y reconocida. Excelente para tareas generales, código, redacción y análisis.</div>
        <div class="tool-best">Mejor para: todo tipo de tareas</div>
      </div>
      <div class="tool-card" style="border-color:var(--bdra);">
        <div style="font-size:26px;margin-bottom:10px;">🧠</div>
        <div class="tool-name">Claude</div>
        <div class="tool-tag purple">Anthropic</div>
        <div class="tool-desc">Destaca en redacción larga, análisis de documentos densos y razonamiento matizado.</div>
        <div class="tool-best">Mejor para: documentos y análisis</div>
      </div>
      <div class="tool-card">
        <div style="font-size:26px;margin-bottom:10px;">🔍</div>
        <div class="tool-name">Perplexity</div>
        <div class="tool-tag blue">Perplexity AI</div>
        <div class="tool-desc">Búsqueda con fuentes citadas. Ideal para investigación rápida y datos verificables.</div>
        <div class="tool-best">Mejor para: investigación</div>
      </div>
      <div class="tool-card">
        <div style="font-size:26px;margin-bottom:10px;">🌐</div>
        <div class="tool-name">Gemini</div>
        <div class="tool-tag green">Google</div>
        <div class="tool-desc">Integración nativa con Gmail, Drive y Workspace. Ideal si tu flujo vive en Google.</div>
        <div class="tool-best">Mejor para: ecosistema Google</div>
      </div>
    </div>
    <p style="margin-top:24px;font-size:14px;color:var(--tm);">💡 No necesitas todas. Elige una, domínala. Las demás vienen solas.</p>
  </div>
  <div class="slide-num">06 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 07 — SEGURIDAD -->
<!-- ══════════════════════════════════════════ -->
<div id="s7" class="slide">
  <div class="slide-wrap">
    <div class="tag red">Módulo 1 · Seguridad</div>
    <h2 class="slide-h">Antes de escribir:<br/><span style="color:var(--red);">reglas de oro.</span></h2>
    <p class="slide-sub" style="margin-bottom:36px;">Tu información y la de tu empresa son tu responsabilidad.</p>
    <div class="g2">
      <div class="rule-row">
        <div class="rule danger">
          <span class="ri">🚫</span>
          <div>
            <h5>Nunca ingreses datos personales de clientes</h5>
            <p>Nombres, cédulas, información de contacto, historiales. Nada que identifique a alguien real.</p>
          </div>
        </div>
        <div class="rule danger">
          <span class="ri">🔒</span>
          <div>
            <h5>Nunca ingreses información financiera</h5>
            <p>Números de cuenta, cifras confidenciales, presupuestos internos sin aprobación.</p>
          </div>
        </div>
        <div class="rule danger">
          <span class="ri">⚠️</span>
          <div>
            <h5>Nunca ingreses contraseñas ni accesos</h5>
            <p>Ninguna plataforma ni herramienta de IA necesita tus credenciales. Jamás.</p>
          </div>
        </div>
      </div>
      <div class="rule-row">
        <div class="rule safe">
          <span class="ri">✅</span>
          <div>
            <h5>Sí puedes usar contexto genérico de tu rol</h5>
            <p>"Soy gerente comercial en una empresa de servicios B2B" — sin nombres ni datos específicos.</p>
          </div>
        </div>
        <div class="rule safe">
          <span class="ri">✅</span>
          <div>
            <h5>Sí puedes usar situaciones anonimizadas</h5>
            <p>"Tengo un cliente que..." sin identificarlo. La IA no necesita el nombre para darte valor.</p>
          </div>
        </div>
        <div class="rule safe">
          <span class="ri">✅</span>
          <div>
            <h5>Sí puedes configurar tu perfil profesional</h5>
            <p>Tu cargo, industria, retos y objetivos generales. Eso es tuyo y genera los mejores resultados.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="slide-num">07 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 08 — EJERCICIO 1 -->
<!-- ══════════════════════════════════════════ -->
<div id="s8" class="slide exercise">
  <div class="slide-wrap">
    <div class="ex-header">
      <div class="ex-badge">✏️ Ejercicio 1</div>
      <div class="ex-timer">⏱ 10 minutos</div>
      <div class="tag gold" style="margin:0;">Módulo 1</div>
    </div>
    <div class="ex-box">
      <h3>Configura tu herramienta ahora</h3>
      <p class="ex-desc">Vas a personalizar tu IA con instrucciones del sistema.<br/>
      Al terminar, tendrás un asistente que trabaja específicamente para ti — no para nadie más.</p>
      <div class="steps">
        <div class="step">
          <div class="step-n gold">1</div>
          <div class="step-body">
            <h6>Abre tu herramienta y ve a "Instrucciones del sistema" o "Personalizar"</h6>
            <p>ChatGPT → Configuración → Personalizar ChatGPT · Claude → Perfil</p>
          </div>
        </div>
        <div class="step">
          <div class="step-n gold">2</div>
          <div class="step-body">
            <h6>Pega y completa esta plantilla con TU información real</h6>
          </div>
        </div>
      </div>
      <div class="prompt-block" style="margin:18px 0;">
        <strong>Plantilla base:</strong><br/>
        "Soy [tu nombre], trabajo como [tu cargo] en [tu industria]. Mi principal reto hoy es [reto concreto]. Respóndeme siempre en español, con estructura clara usando bullets cuando sea útil. Prioriza la aplicabilidad práctica. Si no tienes información suficiente, pregúntame antes de suponer."
      </div>
      <div class="step">
        <div class="step-n gold">3</div>
        <div class="step-body">
          <h6>Escribe una pregunta simple de tu trabajo actual y observa la diferencia</h6>
          <p>Nota cómo la respuesta ya tiene más contexto y relevancia para tu rol.</p>
        </div>
      </div>
    </div>
  </div>
  <div class="slide-num">08 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 09 — POR QUÉ FALLAN LOS PROMPTS -->
<!-- ══════════════════════════════════════════ -->
<div id="s9" class="slide alt" style="background:linear-gradient(135deg,rgba(124,92,252,.06),transparent),var(--bg2);">
  <div class="slide-wrap">
    <div class="tag">Módulo 2 · Ingeniería de Prompts</div>
    <h2 class="slide-h">El problema no es la IA.<br/><span class="acc-text">Eres tú.</span></h2>
    <p class="slide-sub" style="margin-bottom:36px;">
      (Y eso es buena noticia — porque tú sí puedes cambiar.)
    </p>
    <div class="ba-wrap">
      <div class="ba-col">
        <div class="ba-head bad">✗ Prompt que falla</div>
        <div class="ba-body">
          <div class="ba-item">"Ayúdame con un email"</div>
          <div class="ba-item">"Hazme una presentación"</div>
          <div class="ba-item">"Dame ideas para mi negocio"</div>
          <div class="ba-item">"Resume esto"</div>
          <div class="ba-item">"¿Cómo mejoro mis ventas?"</div>
        </div>
      </div>
      <div class="ba-arrow">→</div>
      <div class="ba-col">
        <div class="ba-head good">✓ Por qué falla</div>
        <div class="ba-body">
          <div class="ba-item">Sin destinatario, tono, ni objetivo</div>
          <div class="ba-item">Sin audiencia, extensión, ni estructura</div>
          <div class="ba-item">Sin industria, etapa, ni restricciones</div>
          <div class="ba-item">Sin foco, formato, ni extensión objetivo</div>
          <div class="ba-item">Sin contexto: ¿qué vendes? ¿a quién? ¿ahora qué?</div>
        </div>
      </div>
    </div>
    <p style="margin-top:28px;font-size:17px;color:var(--t1);font-weight:600;">
      La IA da lo que recibe. Si le das poco, te devuelve poco.<br/>
      <span style="color:var(--accl);">El framework ROCOF cambia eso.</span>
    </p>
  </div>
  <div class="slide-num">09 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 10 — ROCOF -->
<!-- ══════════════════════════════════════════ -->
<div id="s10" class="slide">
  <div class="slide-wrap">
    <div class="tag">Módulo 2 · Framework</div>
    <h2 class="slide-h">El Framework <span class="grad-text">ROCOF</span></h2>
    <p class="slide-sub" style="margin-bottom:36px;">
      5 componentes. Cualquier herramienta. Cualquier tarea.<br/>
      Una sola vez aprendido, no lo olvidas.
    </p>
    <div class="g5">
      <div class="rocof-card rc1">
        <div class="rl">R</div>
        <div class="rw">Rol</div>
        <div class="rd">"Actúa como experto en [campo específico]"</div>
      </div>
      <div class="rocof-card rc2">
        <div class="rl">O</div>
        <div class="rw">Objetivo</div>
        <div class="rd">¿Qué resultado concreto y medible necesitas?</div>
      </div>
      <div class="rocof-card rc3">
        <div class="rl">C</div>
        <div class="rw">Contexto</div>
        <div class="rd">Situación actual, audiencia, antecedentes clave</div>
      </div>
      <div class="rocof-card rc4">
        <div class="rl">O</div>
        <div class="rw">Output</div>
        <div class="rd">Formato exacto: tabla, email, bullets, informe…</div>
      </div>
      <div class="rocof-card rc5">
        <div class="rl">F</div>
        <div class="rw">Filtros</div>
        <div class="rd">Tono, extensión, restricciones, estilo</div>
      </div>
    </div>
    <div class="sdivider"></div>
    <div class="g2">
      <div class="prompt-block bad">
        <div class="pb-label bad">✗ Sin ROCOF</div>
        "Escríbeme algo para motivar a mi equipo"
      </div>
      <div class="prompt-block good">
        <div class="pb-label good">✓ Con ROCOF completo</div>
        <strong>R:</strong> "Actúa como director de comunicación interna. <strong>O:</strong> Necesito motivar a mi equipo de ventas que tuvo un mes difícil. <strong>C:</strong> Son 8 personas, resultados 15% bajo meta, sin justificación externa. <strong>O:</strong> Mensaje de máx. 200 palabras. <strong>F:</strong> Tono humano y directo, sin lenguaje corporativo vacío."
      </div>
    </div>
  </div>
  <div class="slide-num">10 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 11 — ITERACIÓN INTELIGENTE -->
<!-- ══════════════════════════════════════════ -->
<div id="s11" class="slide alt">
  <div class="slide-wrap">
    <div class="tag">Módulo 2 · Iteración</div>
    <h2 class="slide-h">La primera respuesta<br/>no es el destino.</h2>
    <p class="slide-sub" style="margin-bottom:36px;">
      El poder real está en saber cómo mejorar sin borrar y empezar de cero.
    </p>
    <div class="g2">
      <div>
        <h3 class="slide-h" style="font-size:20px;margin-bottom:18px;">Frases de iteración que funcionan</h3>
        <div class="rule-row">
          <div class="rule safe">
            <span class="ri">→</span>
            <div><p>"La respuesta anterior es útil pero necesito que <strong style='color:var(--accl);'>[ajuste específico]</strong>"</p></div>
          </div>
          <div class="rule safe">
            <span class="ri">→</span>
            <div><p>"Sé más específico en <strong style='color:var(--accl);'>[sección X]</strong> y reduce <strong style='color:var(--accl);'>[parte Y]</strong>"</p></div>
          </div>
          <div class="rule safe">
            <span class="ri">→</span>
            <div><p>"Reescribe el punto 3 con tono más <strong style='color:var(--accl);'>[X]</strong> y agrega un ejemplo de <strong style='color:var(--accl);'>[industria]</strong>"</p></div>
          </div>
          <div class="rule safe">
            <span class="ri">→</span>
            <div><p>"Asume el rol de alguien que critica esta propuesta. ¿Qué objeciones tendría?"</p></div>
          </div>
        </div>
      </div>
      <div class="card hi" style="display:flex;flex-direction:column;justify-content:center;">
        <div style="font-size:40px;margin-bottom:20px;text-align:center;">💡</div>
        <h4 style="text-align:center;margin-bottom:14px;">La regla de oro de la iteración</h4>
        <p style="text-align:center;">Nunca empieces de cero si puedes<br/>
        <strong style="color:var(--accl);">construir sobre lo que ya tienes.</strong><br/><br/>
        Cada iteración lleva la respuesta más cerca<br/>del entregable que necesitas.</p>
      </div>
    </div>
  </div>
  <div class="slide-num">11 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 12 — EJERCICIO 2 -->
<!-- ══════════════════════════════════════════ -->
<div id="s12" class="slide exercise">
  <div class="slide-wrap">
    <div class="ex-header">
      <div class="ex-badge">✏️ Ejercicio 2</div>
      <div class="ex-timer">⏱ 15 minutos</div>
      <div class="tag gold" style="margin:0;">El más importante del día</div>
    </div>
    <div class="ex-box">
      <h3>Del prompt malo al prompt ganador</h3>
      <p class="ex-desc">
        Toma el prompt que escribiste al inicio del curso — o uno real de tu trabajo de esta semana.<br/>
        Aplica ROCOF completo. Ejecuta. Compara. Eso es todo.
      </p>
      <div class="steps" style="margin-bottom:22px;">
        <div class="step">
          <div class="step-n gold">1</div>
          <div class="step-body"><h6>Identifica qué componentes de ROCOF le faltan a tu prompt original</h6></div>
        </div>
        <div class="step">
          <div class="step-n gold">2</div>
          <div class="step-body"><h6>Reconstruye el prompt completo aplicando los 5 componentes</h6></div>
        </div>
        <div class="step">
          <div class="step-n gold">3</div>
          <div class="step-body"><h6>Ejecuta ambas versiones y observa la diferencia de resultado</h6></div>
        </div>
        <div class="step">
          <div class="step-n gold">4</div>
          <div class="step-body"><h6>Comparte tu "antes y después" con el grupo</h6></div>
        </div>
      </div>
      <div class="prompt-block" style="border-color:rgba(245,200,66,.3);background:rgba(245,200,66,.04);">
        <strong style="color:var(--gold);">Meta del ejercicio:</strong> que tu prompt reconstruido produzca algo que no necesita edición manual para ser útil hoy mismo.
      </div>
    </div>
  </div>
  <div class="slide-num">12 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 13 — CAMBIO DE MENTALIDAD -->
<!-- ══════════════════════════════════════════ -->
<div id="s13" class="slide" style="background:linear-gradient(135deg,rgba(0,212,170,.06),transparent),var(--bg);">
  <div class="slide-wrap">
    <div class="tag teal">Módulo 3 · El cambio real</div>
    <h2 class="slide-h">
      Dejar de<br/><span style="color:var(--tm);text-decoration:line-through;">preguntarle a la IA.</span><br/>
      Empezar a <span class="teal-text">trabajar con ella.</span>
    </h2>
    <p class="slide-sub" style="margin-bottom:40px;">
      La diferencia entre usar IA y dominarla es exactamente esta.
    </p>
    <div class="ba-wrap">
      <div class="ba-col">
        <div class="ba-head bad">✗ Uso reactivo</div>
        <div class="ba-body">
          <div class="ba-item">Una pregunta → una respuesta → copiar y pegar</div>
          <div class="ba-item">La IA como buscador inteligente</div>
          <div class="ba-item">Resultado genérico, requiere mucha edición</div>
          <div class="ba-item">Ahorra poco tiempo real</div>
          <div class="ba-item">No hay aprendizaje acumulado</div>
        </div>
      </div>
      <div class="ba-arrow">→</div>
      <div class="ba-col">
        <div class="ba-head good">✓ Uso estratégico</div>
        <div class="ba-body">
          <div class="ba-item">Flujo dirigido: Idea → Entregable</div>
          <div class="ba-item">La IA como copiloto — tú pilotas</div>
          <div class="ba-item">Resultado aplicable con criterio propio</div>
          <div class="ba-item">5× más velocidad de producción real</div>
          <div class="ba-item">El sistema mejora con cada uso</div>
        </div>
      </div>
    </div>
  </div>
  <div class="slide-num">13 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 14 — EL FLUJO DE 5 FASES -->
<!-- ══════════════════════════════════════════ -->
<div id="s14" class="slide alt">
  <div class="slide-wrap">
    <div class="tag teal">Módulo 3 · El flujo</div>
    <h2 class="slide-h">El flujo de 5 fases.</h2>
    <p class="slide-sub" style="margin-bottom:40px;">
      Aplica a cualquier entregable, para cualquier audiencia, desde hoy.
    </p>
    <div class="g5" style="margin-bottom:32px;">
      <div class="rocof-card rc4" style="padding:24px 16px;">
        <div class="rl" style="font-size:36px;">01</div>
        <div class="rw">Claridad</div>
        <div class="rd">Define el objetivo del entregable con un prompt de arranque</div>
      </div>
      <div class="rocof-card rc4" style="padding:24px 16px;opacity:.9;">
        <div class="rl" style="font-size:36px;">02</div>
        <div class="rw">Estructura</div>
        <div class="rd">Pide a la IA el esquema completo con mensajes clave por sección</div>
      </div>
      <div class="rocof-card rc4" style="padding:24px 16px;opacity:.8;">
        <div class="rl" style="font-size:36px;">03</div>
        <div class="rw">Desarrollo</div>
        <div class="rd">Desarrolla cada sección con prompts específicos por bloque</div>
      </div>
      <div class="rocof-card rc4" style="padding:24px 16px;opacity:.7;">
        <div class="rl" style="font-size:36px;">04</div>
        <div class="rw">Revisión</div>
        <div class="rd">Pide a la IA que identifique inconsistencias y proponga mejoras</div>
      </div>
      <div class="rocof-card rc4" style="padding:24px 16px;opacity:.6;">
        <div class="rl" style="font-size:36px;">05</div>
        <div class="rw">Entregable</div>
        <div class="rd">Exportas, formateas y editas con tu criterio profesional</div>
      </div>
    </div>
    <div class="prompt-block good">
      <div class="pb-label good">Prompt de arranque (Fase 1)</div>
      <strong>Actúa como [experto relevante].</strong> Voy a construir [tipo de entregable] para [audiencia]. Objetivo: [resultado esperado]. Contexto: [situación actual en 2 líneas]. <strong>Empieza por la estructura completa con el mensaje clave de cada sección en una oración.</strong>
    </div>
  </div>
  <div class="slide-num">14 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 15 — CONSTRUCCIÓN EN VIVO -->
<!-- ══════════════════════════════════════════ -->
<div id="s15" class="slide" style="background:linear-gradient(135deg,rgba(0,212,170,.05),rgba(124,92,252,.04)),var(--bg);">
  <div class="slide-wrap">
    <div class="tag teal">Módulo 3 · Demo</div>
    <h2 class="slide-h">Ahora lo<br/><span class="teal-text">construimos en vivo.</span></h2>
    <p class="slide-sub" style="margin-bottom:40px;">
      En los próximos 25 minutos vas a ver cómo un entregable real<br/>
      se construye de cero — con IA — en tiempo real.
    </p>
    <div class="g3">
      <div class="card tealhi" style="text-align:center;">
        <div style="font-size:36px;margin-bottom:12px;">⏱</div>
        <h4>20 minutos</h4>
        <p>Para construir algo que antes tomaba 2 días. No es exageración — es el método.</p>
      </div>
      <div class="card tealhi" style="text-align:center;">
        <div style="font-size:36px;margin-bottom:12px;">5×</div>
        <h4>Más velocidad</h4>
        <p>En documentos clave: propuestas, informes, presentaciones ejecutivas.</p>
      </div>
      <div class="card tealhi" style="text-align:center;">
        <div style="font-size:36px;margin-bottom:12px;">0</div>
        <h4>Líneas de código</h4>
        <p>Solo lenguaje natural. Sin tecnicismos. Sin instalaciones. Solo tu herramienta abierta.</p>
      </div>
    </div>
    <p style="margin-top:28px;font-size:16px;color:var(--t2);">
      👉 Sigue el proceso en tu propia herramienta mientras lo vemos en pantalla.
    </p>
  </div>
  <div class="slide-num">15 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 16 — PROYECTO FINAL -->
<!-- ══════════════════════════════════════════ -->
<div id="s16" class="slide exercise">
  <div class="slide-wrap">
    <div class="ex-header">
      <div class="ex-badge">🏆 Proyecto Final</div>
      <div class="ex-timer">⏱ 20 minutos</div>
      <div class="tag teal" style="margin:0;">Módulo 3</div>
    </div>
    <div class="ex-box" style="border-color:rgba(0,212,170,.4);">
      <h3>Construye tu entregable real</h3>
      <p class="ex-desc">
        Usa el flujo de 5 fases. Elige uno de estos proyectos y construye algo
        que puedas compartir con tu jefe o cliente <strong>mañana mismo.</strong>
      </p>
      <div class="ex-options">
        <div class="ex-opt">
          <strong>Opción A</strong>
          Plan de trabajo de 30 días para un objetivo actual de tu rol profesional
        </div>
        <div class="ex-opt">
          <strong>Opción B</strong>
          Propuesta de mejora de proceso para tu área con diagnóstico y plan de acción
        </div>
        <div class="ex-opt">
          <strong>Opción C</strong>
          Propuesta comercial para un cliente ideal con propuesta de valor y alcance
        </div>
        <div class="ex-opt">
          <strong>Opción D</strong>
          Tu guía personal de 10 prompts maestros para tus tareas más repetitivas
        </div>
      </div>
      <div class="prompt-block good" style="margin-top:20px;">
        <div class="pb-label good">Criterio de éxito</div>
        Al terminar, pregúntate: <strong>¿Puedo compartir esto con mi jefe o cliente mañana sin editarlo demasiado?</strong> Si la respuesta es sí, lo lograste.
      </div>
    </div>
  </div>
  <div class="slide-num">16 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 17 — LO QUE CAMBIA DESDE MAÑANA -->
<!-- ══════════════════════════════════════════ -->
<div id="s17" class="slide alt">
  <div class="slide-wrap">
    <div class="tag teal">Transformación</div>
    <h2 class="slide-h">Esto es lo que<br/><span class="teal-text">cambia desde mañana.</span></h2>
    <div class="g2" style="margin-top:10px;">
      <div class="card tealhi">
        <div class="card-ico">⚡</div>
        <h4>5+ horas semanales recuperadas</h4>
        <p>Comunicación, análisis y documentación — las tareas que más tiempo consumen — ahora fluyen con IA como copiloto.</p>
      </div>
      <div class="card tealhi">
        <div class="card-ico">🧠</div>
        <h4>Piensas más claro, más rápido</h4>
        <p>La IA se convierte en tu espejo de pensamiento. Estructura ideas, organiza prioridades y aclara decisiones complejas.</p>
      </div>
      <div class="card tealhi">
        <div class="card-ico">📄</div>
        <h4>Entregables en minutos, no en horas</h4>
        <p>Propuestas, informes, presentaciones y planes: construidos con IA, revisados con tu criterio. En una fracción del tiempo.</p>
      </div>
      <div class="card tealhi">
        <div class="card-ico">🏆</div>
        <h4>Eres el profesional que va adelante</h4>
        <p>Quien sabe trabajar con IA produce más, con mayor calidad, en menos tiempo. Esa brecha se abre cada día más.</p>
      </div>
    </div>
    <div style="margin-top:32px;padding:24px;background:rgba(0,212,170,.08);border:1px solid rgba(0,212,170,.3);border-radius:16px;text-align:center;">
      <p style="font-size:18px;color:var(--t1);font-weight:600;line-height:1.65;">
        La IA no reemplaza a los profesionales.<br/>
        <span class="teal-text">Reemplaza a los que no saben usarla.</span>
      </p>
    </div>
  </div>
  <div class="slide-num">17 / 18</div>
</div>

<!-- ══════════════════════════════════════════ -->
<!-- SLIDE 18 — CIERRE -->
<!-- ══════════════════════════════════════════ -->
<div id="s18" class="slide center" style="background:linear-gradient(135deg,rgba(124,92,252,.08),rgba(0,212,170,.06)),var(--bg);padding:96px 60px;">
  <div class="slide-wrap">
    <div class="close-banner">
      <div class="tag" style="justify-content:center;margin-bottom:24px;">El reto final</div>
      <h2 class="slide-h" style="margin-bottom:18px;">
        Un solo uso.<br/>Antes del mediodía<br/><span class="teal-text">de mañana.</span>
      </h2>
      <p class="slide-sub" style="margin:0 auto 36px;">
        La única forma en que este curso cambia algo real en tu vida profesional<br/>
        es si aplicas al menos una de estas técnicas mañana.<br/>
        <strong style="color:var(--t1);">No la semana que viene. Mañana.</strong>
      </p>
      <div class="g3" style="margin-bottom:36px;text-align:left;">
        <div class="card goldhi" style="text-align:center;">
          <div style="font-size:32px;margin-bottom:10px;">📐</div>
          <h5>Framework ROCOF</h5>
          <p style="font-size:13px;">Llévate el PDF. Úsalo en tu próximo prompt.</p>
        </div>
        <div class="card goldhi" style="text-align:center;">
          <div style="font-size:32px;margin-bottom:10px;">📚</div>
          <h5>Biblioteca de prompts</h5>
          <p style="font-size:13px;">+20 prompts listos para tu trabajo. Sin excusas.</p>
        </div>
        <div class="card goldhi" style="text-align:center;">
          <div style="font-size:32px;margin-bottom:10px;">💬</div>
          <h5>Comunidad WhatsApp</h5>
          <p style="font-size:13px;">Comparte tu primer resultado. Aprende del grupo.</p>
        </div>
      </div>
      <a href="https://wa.me/573175122182?text=Hola%20Pablo%21%20Quiero%20unirme%20a%20la%20comunidad%20de%20%2ADe%20Prompts%20a%20Resultados%2A%20%F0%9F%9A%80" target="_blank" class="btn-p">
        Unirme a la comunidad →
      </a>
    </div>
  </div>
  <div class="slide-num">18 / 18</div>
</div>

<!-- FOOTER -->
<div class="foot">
  <div class="flogo">De Prompts a Resultados</div>
  <p>Masterclass de IA Aplicada · Profesionales · Medellín, Colombia</p>
  <p style="margin-top:6px;">Presentación en clase — uso exclusivo de participantes</p>
</div>

<script>
document.querySelectorAll('a[href^="#"]').forEach(function(a){
  a.addEventListener('click',function(e){
    var id=this.getAttribute('href').slice(1);
    var el=document.getElementById(id);
    if(el){e.preventDefault();el.scrollIntoView({behavior:'smooth',block:'start'});}
  });
});
</script>
</body>
</html>
