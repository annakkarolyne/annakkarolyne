<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Anna Karolyne – Banner</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --navy: #0a0e1a;
    --blue: #0077B5;
    --sky: #00c4ff; 
    --gold: #f5c842;
    --white: #f0f4ff;
    --gray: #8899bb;
  }

  body {
    background: #06080f;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    font-family: 'Space Mono', monospace;
    padding: 40px 20px;
  }

  .banner {
    width: 900px;
    background: var(--navy);
    border: 1px solid rgba(0, 119, 181, 0.3);
    border-radius: 4px;
    overflow: hidden;
    position: relative;
    animation: fadeIn 1s ease both;
  }

  @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

  /* Grid lines background */
  .banner::before {
    content: '';
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,119,181,0.06) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,119,181,0.06) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  /* Top accent bar */
  .top-bar {
    height: 4px;
    background: linear-gradient(90deg, var(--blue), var(--sky), var(--gold));
  }

  .inner {
    padding: 50px 56px 44px;
    position: relative;
    z-index: 1;
  }

  /* Header row */
  .header {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    margin-bottom: 40px;
  }

  .name-block {}

  .label {
    font-size: 10px;
    letter-spacing: 4px;
    color: var(--sky);
    text-transform: uppercase;
    margin-bottom: 10px;
    animation: slideIn 0.8s 0.2s ease both;
  }

  @keyframes slideIn { from { opacity:0; transform:translateX(-12px); } to { opacity:1; transform:translateX(0); } }

  h1 {
    font-family: 'Playfair Display', serif;
    font-size: 68px;
    font-weight: 900;
    line-height: 1;
    color: var(--white);
    letter-spacing: -1px;
    animation: slideIn 0.8s 0.3s ease both;
  }

  h1 span {
    color: var(--sky);
  }

  .role {
    margin-top: 14px;
    font-size: 11px;
    letter-spacing: 3px;
    color: var(--gray);
    text-transform: uppercase;
    animation: slideIn 0.8s 0.4s ease both;
  }

  /* Accent circle */
  .circle-deco {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    border: 2px solid rgba(0,196,255,0.2);
    position: relative;
    flex-shrink: 0;
    animation: spin 20s linear infinite;
  }

  .circle-deco::before {
    content: '';
    position: absolute;
    inset: 8px;
    border-radius: 50%;
    border: 1px solid rgba(245,200,66,0.3);
    animation: spin 10s linear infinite reverse;
  }

  .circle-deco::after {
    content: 'AK';
    position: absolute;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--gold);
    animation: spin 20s linear infinite reverse;
  }

  @keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }

  /* Divider */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,119,181,0.5), transparent);
    margin-bottom: 36px;
  }

  /* About */
  .about {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 32px;
    margin-bottom: 40px;
  }

  .about-item {
    display: flex;
    gap: 14px;
    animation: fadeUp 0.7s ease both;
  }

  .about-item:nth-child(1) { animation-delay: 0.5s; }
  .about-item:nth-child(2) { animation-delay: 0.6s; }
  .about-item:nth-child(3) { animation-delay: 0.7s; }
  .about-item:nth-child(4) { animation-delay: 0.8s; }

  @keyframes fadeUp { from { opacity:0; transform:translateY(10px); } to { opacity:1; transform:translateY(0); } }

  .about-icon {
    font-size: 20px;
    flex-shrink: 0;
    margin-top: 2px;
  }

  .about-text {}
  .about-title {
    font-size: 9px;
    letter-spacing: 3px;
    color: var(--sky);
    text-transform: uppercase;
    margin-bottom: 4px;
  }
  .about-desc {
    font-size: 12px;
    color: var(--gray);
    line-height: 1.6;
  }
  .about-desc strong {
    color: var(--white);
    font-weight: 700;
  }

  /* Stack section */
  .stack-section {
    margin-bottom: 40px;
    animation: fadeUp 0.7s 0.9s ease both;
  }

  .section-title {
    font-size: 9px;
    letter-spacing: 4px;
    color: var(--sky);
    text-transform: uppercase;
    margin-bottom: 18px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: rgba(0,119,181,0.25);
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    padding: 6px 14px;
    font-size: 10px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    border-radius: 2px;
    transition: all 0.2s;
    cursor: default;
  }

  .tag:hover {
    transform: translateY(-2px);
  }

  .tag.primary {
    background: rgba(0,119,181,0.15);
    color: var(--sky);
    border: 1px solid rgba(0,119,181,0.4);
  }

  .tag.secondary {
    background: rgba(245,200,66,0.08);
    color: var(--gold);
    border: 1px solid rgba(245,200,66,0.25);
  }

  .tag.tertiary {
    background: rgba(240,244,255,0.05);
    color: var(--gray);
    border: 1px solid rgba(255,255,255,0.1);
  }

  /* Quote */
  .quote {
    border-left: 3px solid var(--gold);
    padding: 12px 20px;
    background: rgba(245,200,66,0.04);
    margin-bottom: 36px;
    animation: fadeUp 0.7s 1s ease both;
  }

  .quote p {
    font-size: 12px;
    font-style: italic;
    color: var(--gray);
    line-height: 1.7;
  }

  .quote p em {
    color: rgba(240,244,255,0.7);
    font-style: normal;
  }

  /* Footer */
  .footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    animation: fadeUp 0.7s 1.1s ease both;
  }

  .connect-label {
    font-size: 9px;
    letter-spacing: 3px;
    color: var(--gray);
    text-transform: uppercase;
  }

  .links {
    display: flex;
    gap: 12px;
  }

  .link-btn {
    padding: 9px 20px;
    font-size: 10px;
    font-family: 'Space Mono', monospace;
    letter-spacing: 2px;
    text-transform: uppercase;
    border-radius: 2px;
    text-decoration: none;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    gap: 7px;
  }

  .link-btn.linkedin {
    background: var(--blue);
    color: #fff;
    border: 1px solid var(--blue);
  }

  .link-btn.email {
    background: transparent;
    color: var(--gray);
    border: 1px solid rgba(255,255,255,0.12);
  }

  .link-btn:hover {
    transform: translateY(-2px);
    filter: brightness(1.15);
  }

  /* Corner accent */
  .corner {
    position: absolute;
    bottom: 0;
    right: 0;
    width: 120px;
    height: 120px;
    background: radial-gradient(ellipse at bottom right, rgba(0,119,181,0.12), transparent 70%);
    pointer-events: none;
  }

  /* Bottom bar */
  .bottom-bar {
    height: 3px;
    background: linear-gradient(90deg, var(--gold), var(--sky), var(--blue));
  }

  /* Glowing dot */
  .dot {
    display: inline-block;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--sky);
    box-shadow: 0 0 6px var(--sky);
    animation: pulse 2s ease-in-out infinite;
    vertical-align: middle;
    margin-right: 6px;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }
</style>
</head>
<body>
  <div class="banner">
    <div class="top-bar"></div>
    <div class="inner">

      <div class="header">
        <div class="name-block">
          <p class="label"><span class="dot"></span>Full Stack Developer</p>
          <h1>Anna <span>Karolyne</span></h1>
          <p class="role">Java &nbsp;·&nbsp; Spring Boot &nbsp;·&nbsp; RESTful APIs</p>
        </div>
        <div class="circle-deco"></div>
      </div>

      <div class="divider"></div>

      <div class="about">
        <div class="about-item">
          <div class="about-icon">🎓</div>
          <div class="about-text">
            <p class="about-title">Formação</p>
            <p class="about-desc">Desenvolvedora Full Stack Java — <strong>Generation Brasil</strong></p>
          </div>
        </div>
        <div class="about-item">
          <div class="about-icon">🛠️</div>
          <div class="about-text">
            <p class="about-title">Foco Atual</p>
            <p class="about-desc">APIs RESTful com <strong>Spring Boot</strong> & <strong>Spring Security</strong></p>
          </div>
        </div>
        <div class="about-item">
          <div class="about-icon">🌱</div>
          <div class="about-text">
            <p class="about-title">Aprendizado</p>
            <p class="about-desc"><strong>JUnit/Mockito</strong> e Arquitetura de Microserviços</p>
          </div>
        </div>
        <div class="about-item">
          <div class="about-icon">💬</div>
          <div class="about-text">
            <p class="about-title">Interesses</p>
            <p class="about-desc"><strong>Backend</strong>, Clean Code, Metodologias Ágeis</p>
          </div>
        </div>
      </div>

      <div class="stack-section">
        <p class="section-title">Stack Tecnológica</p>
        <div class="tags">
          <span class="tag primary">Java</span>
          <span class="tag primary">Spring Boot</span>
          <span class="tag primary">Spring Security</span>
          <span class="tag primary">MySQL</span>
          <span class="tag secondary">HTML5</span>
          <span class="tag secondary">CSS3</span>
          <span class="tag secondary">JavaScript</span>
          <span class="tag tertiary">Git</span>
          <span class="tag tertiary">Postman</span>
          <span class="tag tertiary">Insomnia</span>
          <span class="tag tertiary">JUnit</span>
          <span class="tag tertiary">Mockito</span>
        </div>
      </div>

      <div class="quote">
        <p><em>"A tecnologia move o mundo, mas são as pessoas que dão propósito ao código."</em></p>
      </div>

      <div class="footer">
        <p class="connect-label">Vamos nos conectar?</p>
        <div class="links">
          <a class="link-btn linkedin" href="https://www.linkedin.com/in/SEU_USUARIO_AQUI/" target="_blank">
            <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            LinkedIn
          </a>
          <a class="link-btn email" href="mailto:seuemail@exemplo.com">
            <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.910 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
            Email
          </a>
        </div>
      </div>

    </div>
    <div class="corner"></div>
    <div class="bottom-bar"></div>
  </div>
</body>
</html>
