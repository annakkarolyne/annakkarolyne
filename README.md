<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Banner – Ana Caroline</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #0d0d0d;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    padding: 40px;
  }

  .banner {
    width: 860px;
    height: 200px;
    background: #0a0f1e;
    border: 1px solid rgba(0,119,181,0.25);
    border-radius: 6px;
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 48px;
    animation: appear 1s ease both;
  }

  @keyframes appear {
    from { opacity: 0; transform: scale(0.97); }
    to   { opacity: 1; transform: scale(1); }
  }

  /* ── background decoration ── */
  .bg-lines {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,119,181,0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,119,181,0.05) 1px, transparent 1px);
    background-size: 32px 32px;
  }

  .bg-glow {
    position: absolute;
    right: -40px;
    top: -60px;
    width: 340px;
    height: 340px;
    background: radial-gradient(circle, rgba(0,119,181,0.18) 0%, transparent 65%);
    pointer-events: none;
  }

  .bg-glow2 {
    position: absolute;
    left: 200px;
    bottom: -80px;
    width: 200px;
    height: 200px;
    background: radial-gradient(circle, rgba(0,196,255,0.07) 0%, transparent 65%);
    pointer-events: none;
  }

  /* ── top & bottom accent bars ── */
  .bar-top {
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, transparent, #0077B5, #00c4ff, transparent);
  }
  .bar-bottom {
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, rgba(0,119,181,0.4), transparent);
  }

  /* ── left: monogram ── */
  .monogram {
    position: relative;
    z-index: 2;
    flex-shrink: 0;
    width: 72px;
    height: 72px;
    border-radius: 50%;
    border: 1.5px solid rgba(0,196,255,0.35);
    display: flex;
    align-items: center;
    justify-content: center;
    background: rgba(0,119,181,0.08);
    animation: spin-ring 25s linear infinite;
  }

  .monogram::before {
    content: '';
    position: absolute;
    inset: 6px;
    border-radius: 50%;
    border: 1px dashed rgba(0,196,255,0.2);
    animation: spin-ring 12s linear infinite reverse;
  }

  @keyframes spin-ring {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
  }

  .monogram span {
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px;
    font-weight: 700;
    color: #00c4ff;
    letter-spacing: 1px;
    animation: spin-ring 25s linear infinite reverse;
    position: relative;
    z-index: 1;
  }

  /* ── center: name + info ── */
  .center {
    position: relative;
    z-index: 2;
    flex: 1;
    padding: 0 36px;
  }

  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 9px;
    letter-spacing: 4px;
    color: #00c4ff;
    text-transform: uppercase;
    margin-bottom: 8px;
    opacity: 0;
    animation: slide-up 0.6s 0.3s ease forwards;
  }

  .name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 46px;
    font-weight: 600;
    color: #f0f4ff;
    line-height: 1;
    letter-spacing: -0.5px;
    opacity: 0;
    animation: slide-up 0.6s 0.5s ease forwards;
  }

  .name em {
    font-style: normal;
    color: #00c4ff;
  }

  .role {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: #5577aa;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-top: 10px;
    opacity: 0;
    animation: slide-up 0.6s 0.7s ease forwards;
  }

  @keyframes slide-up {
    from { opacity: 0; transform: translateY(8px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ── right: stack ── */
  .stack {
    position: relative;
    z-index: 2;
    flex-shrink: 0;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 6px;
    opacity: 0;
    animation: fade-in 0.8s 0.9s ease forwards;
  }

  @keyframes fade-in {
    from { opacity: 0; }
    to   { opacity: 1; }
  }

  .stack-label {
    font-family: 'DM Mono', monospace;
    font-size: 8px;
    letter-spacing: 3px;
    color: #5577aa;
    text-transform: uppercase;
    margin-bottom: 4px;
  }

  .pills {
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-end;
    gap: 5px;
    max-width: 180px;
  }

  .pill {
    font-family: 'DM Mono', monospace;
    font-size: 9px;
    padding: 3px 9px;
    border-radius: 2px;
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  .pill.blue {
    background: rgba(0,119,181,0.15);
    border: 1px solid rgba(0,119,181,0.4);
    color: #00c4ff;
  }

  .pill.dim {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    color: #5577aa;
  }

  /* ── divider ── */
  .divider {
    position: relative;
    z-index: 2;
    width: 1px;
    height: 80px;
    background: linear-gradient(to bottom, transparent, rgba(0,119,181,0.3), transparent);
    flex-shrink: 0;
  }
</style>
</head>
<body>
  <div class="banner">
    <div class="bg-lines"></div>
    <div class="bg-glow"></div>
    <div class="bg-glow2"></div>
    <div class="bar-top"></div>
    <div class="bar-bottom"></div>

    <!-- Monogram -->
    <div class="monogram"><span>AC</span></div>

    <!-- Center -->
    <div class="center">
      <p class="tag">✦ Full Stack Developer</p>
      <h1 class="name">Ana <em>Caroline</em></h1>
      <p class="role">Java &nbsp;·&nbsp; Spring Boot &nbsp;·&nbsp; Fatec Americana</p>
    </div>

    <div class="divider"></div>

    <!-- Stack -->
    <div class="stack">
      <p class="stack-label">Stack</p>
      <div class="pills">
        <span class="pill blue">Java</span>
        <span class="pill blue">Spring</span>
        <span class="pill blue">MySQL</span>
        <span class="pill dim">HTML</span>
        <span class="pill dim">CSS</span>
        <span class="pill dim">JS</span>
      </div>
    </div>
  </div>
</body>
</html>
