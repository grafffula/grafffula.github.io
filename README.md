<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>С Днём Рождения, Артём! 🎉</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;600;700&family=Montserrat:wght@800;900&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-dark: #070714;
      --card-bg: rgba(18, 20, 44, 0.62);
      --card-border: rgba(255, 255, 255, 0.14);
      --text-main: #f8fafc;
      --text-muted: #cbd5e1;
      --accent-1: #ff2a85;
      --accent-2: #7928ca;
      --accent-3: #00dfd8;
      --accent-4: #ffb800;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Manrope', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      background-color: var(--bg-dark);
      color: var(--text-main);
      min-height: 100vh;
      overflow-x: hidden;
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    /* Animated Aurora Mesh Layer behind Canvas */
    .aurora-bg {
      position: fixed;
      inset: 0;
      z-index: 0;
      overflow: hidden;
      pointer-events: none;
      background: radial-gradient(circle at 20% 20%, #160d35 0%, #070714 60%);
    }

    .aurora-orb {
      position: absolute;
      border-radius: 50%;
      filter: blur(90px);
      opacity: 0.55;
      mix-blend-mode: screen;
      animation: floatOrb 18s ease-in-out infinite alternate;
    }

    .orb-1 {
      width: 520px;
      height: 520px;
      background: radial-gradient(circle, #ff2a85, transparent 70%);
      top: -120px;
      left: -100px;
      animation-duration: 16s;
    }

    .orb-2 {
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, #00dfd8, transparent 70%);
      bottom: -180px;
      right: -120px;
      animation-duration: 21s;
      animation-delay: -5s;
    }

    .orb-3 {
      width: 460px;
      height: 460px;
      background: radial-gradient(circle, #7928ca, transparent 70%);
      top: 40%;
      left: 55%;
      animation-duration: 19s;
      animation-delay: -9s;
    }

    .orb-4 {
      width: 380px;
      height: 380px;
      background: radial-gradient(circle, #ffb800, transparent 70%);
      bottom: 20%;
      left: 10%;
      opacity: 0.35;
      animation-duration: 23s;
      animation-delay: -3s;
    }

    @keyframes floatOrb {
      0% {
        transform: translate3d(0, 0, 0) scale(1) rotate(0deg);
      }
      50% {
        transform: translate3d(80px, -60px, 0) scale(1.18) rotate(120deg);
      }
      100% {
        transform: translate3d(-60px, 90px, 0) scale(0.92) rotate(240deg);
      }
    }

    /* Interactive Particle & Fireworks Canvas */
    #fx-canvas {
      position: fixed;
      inset: 0;
      width: 100%;
      height: 100%;
      z-index: 1;
      pointer-events: none;
    }

    /* Main Content Container */
    .wrapper {
      position: relative;
      z-index: 2;
      max-width: 1040px;
      margin: 0 auto;
      padding: 40px 20px 80px;
    }

    /* Hero Section */
    .hero {
      text-align: center;
      padding: 48px 16px 36px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .age-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 18px;
      border-radius: 999px;
      background: rgba(255, 255, 255, 0.08);
      border: 1px solid rgba(255, 255, 255, 0.2);
      backdrop-filter: blur(12px);
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: #ffd166;
      margin-bottom: 22px;
      box-shadow: 0 0 25px rgba(255, 184, 0, 0.25);
      animation: pulseBadge 3s ease-in-out infinite;
    }

    @keyframes pulseBadge {
      0%, 100% { transform: translateY(0) scale(1); }
      50% { transform: translateY(-4px) scale(1.03); }
    }

    h1 {
      font-family: 'Montserrat', sans-serif;
      font-weight: 900;
      font-size: clamp(2.4rem, 7vw, 4.8rem);
      line-height: 1.06;
      letter-spacing: -0.02em;
      text-transform: uppercase;
      margin-bottom: 20px;
      background: linear-gradient(
        110deg,
        #ffffff 10%,
        #00dfd8 30%,
        #ff2a85 55%,
        #ffb800 80%,
        #ffffff 95%
      );
      background-size: 250% auto;
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: shineText 5s linear infinite;
      filter: drop-shadow(0 8px 30px rgba(255, 42, 133, 0.35));
    }

    @keyframes shineText {
      to {
        background-position: 250% center;
      }
    }

    .hero-sub {
      max-width: 640px;
      font-size: clamp(1.05rem, 2.3vw, 1.25rem);
      color: var(--text-muted);
      margin-bottom: 32px;
    }

    /* Neon Button */
    .btn-firework {
      position: relative;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 16px 32px;
      font-family: 'Montserrat', sans-serif;
      font-weight: 800;
      font-size: 1rem;
      letter-spacing: 0.03em;
      color: #fff;
      background: linear-gradient(135deg, #ff2a85 0%, #7928ca 50%, #00dfd8 100%);
      background-size: 200% 200%;
      border: none;
      border-radius: 16px;
      cursor: pointer;
      box-shadow: 0 10px 35px rgba(255, 42, 133, 0.45), 0 0 0 1px rgba(255, 255, 255, 0.25) inset;
      transition: transform 0.25s cubic-bezier(0.34, 1.56, 0.64, 1), box-shadow 0.25s ease;
      animation: gradientShift 4s ease infinite;
      user-select: none;
    }

    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .btn-firework:hover {
      transform: translateY(-4px) scale(1.04);
      box-shadow: 0 16px 45px rgba(0, 223, 216, 0.55), 0 0 0 2px rgba(255, 255, 255, 0.5) inset;
    }

    .btn-firework:active {
      transform: translateY(1px) scale(0.97);
    }

    /* Achievement Strip */
    .stats-strip {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px;
      margin: 12px 0 48px;
    }

    .stat-pill {
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 10px 18px;
      border-radius: 14px;
      background: rgba(255, 255, 255, 0.06);
      border: 1px solid rgba(255, 255, 255, 0.12);
      backdrop-filter: blur(10px);
      font-size: 0.92rem;
      font-weight: 600;
      color: #f1f5f9;
      transition: transform 0.3s ease, border-color 0.3s ease, background 0.3s ease;
    }

    .stat-pill:hover {
      transform: translateY(-3px);
      border-color: var(--accent-3);
      background: rgba(0, 223, 216, 0.12);
    }

    /* Cards Grid */
    .section-label {
      text-align: center;
      font-family: 'Montserrat', sans-serif;
      font-weight: 800;
      font-size: 0.85rem;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: var(--accent-3);
      margin-bottom: 24px;
    }

    .cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(290px, 1fr));
      gap: 22px;
      margin-bottom: 56px;
      perspective: 1200px;
    }

    .card {
      position: relative;
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: 24px;
      padding: 28px 26px;
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.45);
      overflow: hidden;
      transform-style: preserve-3d;
      transition: transform 0.18s ease-out, border-color 0.3s ease, box-shadow 0.3s ease;
      opacity: 0;
      transform: translateY(35px) scale(0.96);
    }

    .card.visible {
      opacity: 1;
      transform: translateY(0) scale(1);
      transition: opacity 0.65s cubic-bezier(0.22, 1, 0.36, 1),
                  transform 0.65s cubic-bezier(0.34, 1.56, 0.64, 1),
                  border-color 0.3s ease,
                  box-shadow 0.3s ease;
    }

    .card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(
        420px circle at var(--mouse-x, 50%) var(--mouse-y, 50%),
        rgba(255, 255, 255, 0.14),
        transparent 60%
      );
      opacity: 0;
      transition: opacity 0.3s ease;
      pointer-events: none;
    }

    .card:hover::before {
      opacity: 1;
    }

    .card:hover {
      border-color: rgba(255, 255, 255, 0.35);
      box-shadow: 0 24px 60px rgba(121, 40, 202, 0.35);
    }

    .card-accent-bar {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 4px;
      background: linear-gradient(90deg, var(--c1, #ff2a85), var(--c2, #00dfd8));
    }

    .card-icon {
      width: 52px;
      height: 52px;
      border-radius: 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.7rem;
      margin-bottom: 18px;
      background: rgba(255, 255, 255, 0.08);
      border: 1px solid rgba(255, 255, 255, 0.14);
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
    }

    .card h2 {
      font-family: 'Montserrat', sans-serif;
      font-weight: 800;
      font-size: 1.25rem;
      line-height: 1.25;
      margin-bottom: 12px;
      color: #ffffff;
    }

    .card p {
      font-size: 0.98rem;
      color: var(--text-muted);
      line-height: 1.62;
    }

    .highlight {
      color: #fff;
      font-weight: 700;
    }

    .rainbow-pill {
      display: inline-block;
      padding: 1px 8px;
      border-radius: 8px;
      background: linear-gradient(90deg, #ff2a85, #ff8a00, #ffd166, #06d6a0, #118ab2, #9b5de5);
      color: #070714;
      font-weight: 800;
      font-size: 0.9em;
    }

    /* Wishes Section */
    .wishes-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 20px;
      margin-bottom: 52px;
    }

    .wish-card {
      position: relative;
      padding: 26px 24px;
      border-radius: 22px;
      background: linear-gradient(155deg, rgba(255, 255, 255, 0.09), rgba(255, 255, 255, 0.03));
      border: 1px solid rgba(255, 255, 255, 0.14);
      backdrop-filter: blur(14px);
      transition: transform 0.35s cubic-bezier(0.34, 1.56, 0.64, 1), border-color 0.3s ease;
      opacity: 0;
      transform: translateY(30px);
    }

    .wish-card.visible {
      opacity: 1;
      transform: translateY(0);
    }

    .wish-card:hover {
      transform: translateY(-6px) scale(1.02);
      border-color: var(--accent-4);
    }

    .wish-emoji {
      font-size: 2rem;
      margin-bottom: 12px;
      display: inline-block;
      animation: bounceEmoji 2.8s ease-in-out infinite;
    }

    @keyframes bounceEmoji {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-6px); }
    }

    .wish-card h3 {
      font-family: 'Montserrat', sans-serif;
      font-weight: 800;
      font-size: 1.15rem;
      margin-bottom: 10px;
      color: #ffd166;
    }

    .wish-card p {
      font-size: 0.96rem;
      color: var(--text-muted);
    }

    /* Interactive Toast Box */
    .toast-box {
      position: relative;
      text-align: center;
      padding: 36px 24px;
      border-radius: 28px;
      background: linear-gradient(135deg, rgba(255, 42, 133, 0.16), rgba(121, 40, 202, 0.2), rgba(0, 223, 216, 0.16));
      border: 1px solid rgba(255, 255, 255, 0.22);
      backdrop-filter: blur(20px);
      box-shadow: 0 24px 60px rgba(0, 0, 0, 0.5);
    }

    .toast-title {
      font-family: 'Montserrat', sans-serif;
      font-weight: 900;
      font-size: clamp(1.35rem, 3.2vw, 1.9rem);
      margin-bottom: 12px;
      color: #fff;
    }

    .toast-dynamic {
      min-height: 58px;
      max-width: 620px;
      margin: 0 auto 24px;
      font-size: 1.05rem;
      color: #f8fafc;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: opacity 0.25s ease, transform 0.25s ease;
    }

    .toast-dynamic.switching {
      opacity: 0;
      transform: scale(0.95);
    }

    .hint-tap {
      margin-top: 28px;
      text-align: center;
      font-size: 0.84rem;
      color: rgba(203, 213, 225, 0.65);
    }

    @media (max-width: 600px) {
      .wrapper {
        padding: 24px 14px 64px;
      }
      .hero {
        padding: 28px 8px 24px;
      }
      .card {
        padding: 24px 20px;
      }
    }
  </style>
</head>
<body>

  <!-- Animated Aurora Background -->
  <div class="aurora-bg" aria-hidden="true">
    <div class="aurora-orb orb-1"></div>
    <div class="aurora-orb orb-2"></div>
    <div class="aurora-orb orb-3"></div>
    <div class="aurora-orb orb-4"></div>
  </div>

  <!-- Interactive Particles & Fireworks Canvas -->
  <canvas id="fx-canvas" aria-hidden="true"></canvas>

  <main class="wrapper">
    <!-- Hero -->
    <section class="hero">
      <div class="age-badge">🎂 LEVEL 28–29 • ПОЛЁТ НОРМАЛЬНЫЙ</div>
      <h1>С Днём Рождения,<br>Артём!</h1>
      <p class="hero-sub">
        Главный поздравительный сайт для человека-титана, который умудряется вывозить всё и сразу. Сегодня весь этот неоновый движ работает исключительно в твою честь!
      </p>
      <button class="btn-firework" id="hero-burst-btn" type="button">
        <span>🎆 Бахнуть салют за именинника</span>
      </button>
    </section>

    <!-- Achievement Strip -->
    <div class="stats-strip">
      <div class="stat-pill">👨‍👩‍👦‍👦 Папа двух богатырей</div>
      <div class="stat-pill">🏠 Своя крепость</div>
      <div class="stat-pill">🚘 Тачка тянет как зверь</div>
      <div class="stat-pill">🧖‍♂️ Мастер банного релакса</div>
    </div>

    <!-- Main Story Blocks (2-3 sentences max per block) -->
    <div class="section-label">⚡ Хроники твоих побед</div>
    <section class="cards-grid">
      <article class="card tilt-card" style="--c1: #ff2a85; --c2: #ffb800;">
        <div class="card-accent-bar"></div>
        <div class="card-icon">👑</div>
        <h2>Семейный уровень «Хардкор»</h2>
        <p>
          Дома тебя ждёт любимая жена <span class="highlight">Аня</span> и сразу два наследника — старшему уже 4 года, а младший только недавно ворвался в этот мир. Воспитывать двоих пацанов без кнопки «пауза» — задачка со звёздочкой, но ты тащишь её как настоящий батя-легенда!
        </p>
      </article>

      <article class="card tilt-card" style="--c1: #00dfd8; --c2: #3b82f6;">
        <div class="card-accent-bar"></div>
        <div class="card-icon">🏰</div>
        <h2>Свои стены и бодрый конь</h2>
        <p>
          Квартира в ипотеку — шаг мощный: теперь стены свои, а банк стал почти родным человеком. Плюс тачка в строю, которая хоть и с характером, но тянет ого-го как крепко и вывозит любые марш-броски!
        </p>
      </article>

      <article class="card tilt-card" style="--c1: #a855f7; --c2: #ff2a85;">
        <div class="card-accent-bar"></div>
        <div class="card-icon">🧖‍♂️</div>
        <h2>Респект за баньку и Егора</h2>
        <p>
          Огромное спасибо, что в таком графике нашёл время, силы и средства собрать нас с друзьями в бане! Заодно ты так душевно утешил <span class="highlight">Егора</span> после расставания, что я уже начал подозревать у вас крепкую <span class="rainbow-pill">голубую дружбу</span> 🏳️‍🌈👀.
        </p>
      </article>

      <article class="card tilt-card" style="--c1: #10b981; --c2: #00dfd8;">
        <div class="card-accent-bar"></div>
        <div class="card-icon">💘</div>
        <h2>Банная терапия сработала</h2>
        <p>
          Правда, твой секретный метод поддержки оказался настолько мощным, что Егор почти сразу нашёл новую даму сердца. Так что «голубая лагуна» отменяется, но за ту легендарную посиделку лично от меня тебе пожизненный почёт!
        </p>
      </article>
    </section>

    <!-- Wishes Section -->
    <div class="section-label">🚀 Апгрейды на новый год жизни</div>
    <section class="wishes-grid">
      <div class="wish-card">
        <span class="wish-emoji">⚡</span>
        <h3>Железных сил</h3>
        <p>
          Пусть внутренняя батарейка никогда не садится, даже после самых бодрых ночных смен с младшим. Богатырского здоровья тебе с запасом на все дела!
        </p>
      </div>

      <div class="wish-card">
        <span class="wish-emoji">💸</span>
        <h3>Финансового взлёта</h3>
        <p>
          Желаю, чтобы доходы росли быстрее процентов по ипотеке, а бюджет всегда радовал жирным плюсом. Пусть деньги приходят легко и красиво!
        </p>
      </div>

      <div class="wish-card">
        <span class="wish-emoji">🏝️</span>
        <h3>Времени на отдых</h3>
        <p>
          Желаю побольше часов лично для себя — без суеты, гонки и лишних нервов. Ты заслужил качественный чилл и ещё не одну крутую баньку!
        </p>
      </div>
    </section>

    <!-- Interactive Toast Generator -->
    <section class="toast-box">
      <h2 class="toast-title">🍻 Генератор тостов за Артёма</h2>
      <p class="toast-dynamic" id="toast-text">
        Поднимаю бокал за то, чтобы тачка тянула, ипотека таяла, пацаны радовали, а Аня всегда гордилась своим героем!
      </p>
      <button class="btn-firework" id="next-toast-btn" type="button">
        <span>🔥 Следующий тост + мега-залп</span>
      </button>
    </section>

    <p class="hint-tap">✨ Лайфхак: кликай или тапай в любое место экрана, чтобы запускать салюты</p>
  </main>

  <script>
    (() => {
      const canvas = document.getElementById('fx-canvas');
      const ctx = canvas.getContext('2d');

      let width = (canvas.width = window.innerWidth);
      let height = (canvas.height = window.innerHeight);

      window.addEventListener('resize', () => {
        width = canvas.width = window.innerWidth;
        height = canvas.height = window.innerHeight;
      });

      const palette = [
        '#ff2a85',
        '#00dfd8',
        '#ffb800',
        '#9b5de5',
        '#00f5d4',
        '#fee440',
        '#ff5e5b',
        '#38bdf8'
      ];

      const mouse = { x: -9999, y: -9999, active: false };

      window.addEventListener('pointermove', (e) => {
        mouse.x = e.clientX;
        mouse.y = e.clientY;
        mouse.active = true;
        spawnTrail(e.clientX, e.clientY);
      });

      window.addEventListener('pointerleave', () => {
        mouse.active = false;
      });

      /* Ambient Constellation Particles */
      const ambientCount = Math.min(85, Math.floor((width * height) / 14000));
      const ambientParticles = [];

      class AmbientParticle {
        constructor() {
          this.reset(true);
        }
        reset(randomY = false) {
          this.x = Math.random() * width;
          this.y = randomY ? Math.random() * height : height + 10;
          this.vx = (Math.random() - 0.5) * 0.65;
          this.vy = -0.25 - Math.random() * 0.55;
          this.radius = 1.6 + Math.random() * 2.6;
          this.color = palette[Math.floor(Math.random() * palette.length)];
          this.alpha = 0.35 + Math.random() * 0.55;
          this.pulse = Math.random() * Math.PI * 2;
        }
        update() {
          this.pulse += 0.04;
          this.x += this.vx;
          this.y += this.vy;

          if (mouse.active) {
            const dx = this.x - mouse.x;
            const dy = this.y - mouse.y;
            const dist = Math.hypot(dx, dy);
            if (dist < 140 && dist > 0) {
              const force = (140 - dist) / 140;
              this.x += (dx / dist) * force * 2.4;
              this.y += (dy / dist) * force * 2.4;
            }
          }

          if (this.y < -20 || this.x < -20 || this.x > width + 20) {
            this.reset(false);
          }
        }
        draw() {
          const r = this.radius + Math.sin(this.pulse) * 0.6;
          ctx.save();
          ctx.globalAlpha = this.alpha;
          ctx.beginPath();
          ctx.arc(this.x, this.y, Math.max(0.6, r), 0, Math.PI * 2);
          ctx.fillStyle = this.color;
          ctx.shadowBlur = 12;
          ctx.shadowColor = this.color;
          ctx.fill();
          ctx.restore();
        }
      }

      for (let i = 0; i < ambientCount; i++) {
        ambientParticles.push(new AmbientParticle());
      }

      /* Fireworks & Confetti Sparks */
      const sparks = [];

      class Spark {
        constructor(x, y, color, speedScale = 1, isConfetti = false) {
          this.x = x;
          this.y = y;
          const angle = Math.random() * Math.PI * 2;
          const speed = (1.8 + Math.random() * 6.5) * speedScale;
          this.vx = Math.cos(angle) * speed;
          this.vy = Math.sin(angle) * speed - (isConfetti ? 2 : 0.8);
          this.gravity = isConfetti ? 0.11 : 0.08;
          this.drag = 0.965;
          this.color = color;
          this.alpha = 1;
          this.decay = 0.012 + Math.random() * 0.015;
          this.size = isConfetti ? 4 + Math.random() * 5 : 2 + Math.random() * 2.8;
          this.isConfetti = isConfetti;
          this.rotation = Math.random() * Math.PI * 2;
          this.rotSpeed = (Math.random() - 0.5) * 0.25;
        }
        update() {
          this.vx *= this.drag;
          this.vy *= this.drag;
          this.vy += this.gravity;
          this.x += this.vx;
          this.y += this.vy;
          this.alpha -= this.decay;
          this.rotation += this.rotSpeed;
        }
        draw() {
          if (this.alpha <= 0) return;
          ctx.save();
          ctx.globalAlpha = Math.max(0, this.alpha);
          ctx.translate(this.x, this.y);
          ctx.rotate(this.rotation);
          ctx.fillStyle = this.color;
          ctx.shadowBlur = 10;
          ctx.shadowColor = this.color;

          if (this.isConfetti) {
            ctx.fillRect(-this.size / 2, -this.size / 4, this.size, this.size / 2);
          } else {
            ctx.beginPath();
            ctx.arc(0, 0, this.size, 0, Math.PI * 2);
            ctx.fill();
          }
          ctx.restore();
        }
      }

      function spawnTrail(x, y) {
        if (sparks.length > 550) return;
        const color = palette[Math.floor(Math.random() * palette.length)];
        const s = new Spark(x, y, color, 0.22, false);
        s.decay = 0.035;
        s.gravity = 0.02;
        sparks.push(s);
      }

      function launchFirework(x, y, count = 65, scale = 1.15) {
        const baseColor = palette[Math.floor(Math.random() * palette.length)];
        for (let i = 0; i < count; i++) {
          const color = Math.random() > 0.35
            ? palette[Math.floor(Math.random() * palette.length)]
            : baseColor;
          sparks.push(new Spark(x, y, color, scale, i % 3 === 0));
        }
      }

      function megaSalvo() {
        const bursts = 5;
        for (let i = 0; i < bursts; i++) {
          setTimeout(() => {
            const rx = width * (0.18 + Math.random() * 0.64);
            const ry = height * (0.16 + Math.random() * 0.45);
            launchFirework(rx, ry, 75, 1.3);
          }, i * 210);
        }
      }

      /* Click anywhere for fireworks */
      window.addEventListener('pointerdown', (e) => {
        launchFirework(e.clientX, e.clientY, 55, 1.05);
      });

      document.getElementById('hero-burst-btn').addEventListener('click', (e) => {
        e.stopPropagation();
        megaSalvo();
      });

      /* Rotating Toasts */
      const toasts = [
        'Поднимаю бокал за то, чтобы тачка тянула, ипотека таяла, пацаны радовали, а Аня всегда гордилась своим героем!',
        'За крепкую мужскую дружбу — такую надёжную, что даже Егор после твоей баньки мгновенно вернулся в строй!',
        'За железный запас энергии: чтобы хватало и на работу, и на двоих сыновей, и на душевный отдых!',
        'За финансовый турбо-режим: пусть купюры липнут к рукам быстрее, чем ты успеваешь их тратить!'
      ];
      let toastIndex = 0;
      const toastEl = document.getElementById('toast-text');

      document.getElementById('next-toast-btn').addEventListener('click', (e) => {
        e.stopPropagation();
        megaSalvo();
        toastEl.classList.add('switching');
        setTimeout(() => {
          toastIndex = (toastIndex + 1) % toasts.length;
          toastEl.textContent = toasts[toastIndex];
          toastEl.classList.remove('switching');
        }, 220);
      });

      /* Animation Loop */
      function animate() {
        ctx.clearRect(0, 0, width, height);

        for (let i = 0; i < ambientParticles.length; i++) {
          const p = ambientParticles[i];
          p.update();
          p.draw();

          for (let j = i + 1; j < ambientParticles.length; j++) {
            const p2 = ambientParticles[j];
            const dx = p.x - p2.x;
            const dy = p.y - p2.y;
            const dist = Math.hypot(dx, dy);
            if (dist < 115) {
              ctx.save();
              ctx.globalAlpha = (1 - dist / 115) * 0.18;
              ctx.strokeStyle = p.color;
              ctx.lineWidth = 1;
              ctx.beginPath();
              ctx.moveTo(p.x, p.y);
              ctx.lineTo(p2.x, p2.y);
              ctx.stroke();
              ctx.restore();
            }
          }
        }

        for (let i = sparks.length - 1; i >= 0; i--) {
          sparks[i].update();
          sparks[i].draw();
          if (sparks[i].alpha <= 0) {
            sparks.splice(i, 1);
          }
        }

        requestAnimationFrame(animate);
      }

      animate();

      /* Opening Celebration Burst */
      setTimeout(megaSalvo, 350);

      /* 3D Tilt & Spotlight on Cards */
      document.querySelectorAll('.tilt-card').forEach((card) => {
        card.addEventListener('pointermove', (e) => {
          const rect = card.getBoundingClientRect();
          const x = e.clientX - rect.left;
          const y = e.clientY - rect.top;
          card.style.setProperty('--mouse-x', `${x}px`);
          card.style.setProperty('--mouse-y', `${y}px`);

          const rotateY = ((x / rect.width) - 0.5) * 10;
          const rotateX = ((y / rect.height) - 0.5) * -10;
          card.style.transform = `perspective(900px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) translateY(-4px)`;
        });

        card.addEventListener('pointerleave', () => {
          card.style.transform = '';
        });
      });

      /* Scroll Reveal */
      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry, idx) => {
            if (entry.isIntersecting) {
              setTimeout(() => {
                entry.target.classList.add('visible');
              }, idx * 90);
              observer.unobserve(entry.target);
            }
          });
        },
        { threshold: 0.12 }
      );

      document.querySelectorAll('.card, .wish-card').forEach((el) => observer.observe(el));
    })();
  </script>
</body>
</html>
