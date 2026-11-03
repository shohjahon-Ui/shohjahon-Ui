
<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shohjahon | Creative Developer</title>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

<style>
:root {
  --bg: #070914;
  --blue: #5c7cff;
  --purple: #a855f7;
  --cyan: #36d9ff;
  --text: #f4f6ff;
  --muted: #9da5bd;
  --glass: rgba(255,255,255,.055);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', sans-serif;
  background: var(--bg);
  color: var(--text);
  overflow-x: hidden;
}

body::before {
  content: "";
  position: fixed;
  inset: 0;
  z-index: -5;
  background:
    radial-gradient(ellipse at 15% 20%, #30206b55, transparent 40%),
    radial-gradient(ellipse at 85% 30%, #064b7250, transparent 40%),
    radial-gradient(ellipse at 50% 90%, #54217a40, transparent 45%);
}

/* ANIMATSIYALI ORQA FON */

.background {
  position: fixed;
  inset: 0;
  z-index: -2;
  overflow: hidden;
  pointer-events: none;
  perspective: 900px;
}

.cube {
  position: absolute;
  width: 90px;
  height: 90px;
  border: 1px solid #7c91ff65;
  background: linear-gradient(135deg, #667aff12, #a855f710);
  box-shadow: 0 0 35px #637bff15,
              inset 0 0 30px #637bff12;
  animation: cubeFloat 14s ease-in-out infinite;
  transform-style: preserve-3d;
}

.cube:nth-child(1) {
  left: 8%;
  top: 18%;
  animation-duration: 17s;
}

.cube:nth-child(2) {
  left: 78%;
  top: 13%;
  width: 130px;
  height: 130px;
  animation-delay: -4s;
}

.cube:nth-child(3) {
  left: 65%;
  top: 65%;
  width: 65px;
  height: 65px;
  animation-delay: -7s;
}

.cube:nth-child(4) {
  left: 20%;
  top: 75%;
  width: 115px;
  height: 115px;
  animation-delay: -9s;
}

.cube:nth-child(5) {
  left: 48%;
  top: 40%;
  width: 45px;
  height: 45px;
  animation-delay: -2s;
}

@keyframes cubeFloat {
  0% {
    transform: rotateX(0deg) rotateY(0deg) translateY(0);
  }
  50% {
    transform: rotateX(180deg) rotateY(180deg) translateY(-90px);
  }
  100% {
    transform: rotateX(360deg) rotateY(360deg) translateY(0);
  }
}

.glow {
  position: fixed;
  width: 350px;
  height: 350px;
  border-radius: 50%;
  background: #596fff18;
  filter: blur(100px);
  top: 20%;
  left: 35%;
  z-index: -3;
  animation: glowMove 9s ease-in-out infinite alternate;
}

@keyframes glowMove {
  to {
    transform: translate(180px, 100px) scale(1.4);
  }
}

.particles {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: -1;
}

.particle {
  position: absolute;
  width: 3px;
  height: 3px;
  background: #8ca8ff;
  border-radius: 50%;
  box-shadow: 0 0 12px #8ca8ff;
  animation: particleMove 8s linear infinite;
}

@keyframes particleMove {
  0% { transform: translateY(100vh); opacity: 0; }
  20% { opacity: 1; }
  100% { transform: translateY(-100px); opacity: 0; }
}

/* NAVBAR */

nav {
  width: 100%;
  padding: 24px 8%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: fixed;
  top: 0;
  z-index: 100;
  backdrop-filter: blur(18px);
  background: #080b18a8;
  border-bottom: 1px solid #ffffff0c;
}

.logo {
  font-size: 23px;
  font-weight: 900;
  letter-spacing: -1px;
}

.logo span {
  color: var(--blue);
}

nav ul {
  display: flex;
  gap: 32px;
  list-style: none;
}

nav a {
  color: #b8bfd5;
  text-decoration: none;
  font-size: 13px;
  transition: .3s;
}

nav a:hover {
  color: white;
}

.contact-btn {
  padding: 12px 22px;
  border-radius: 10px;
  background: linear-gradient(120deg, var(--blue), var(--purple));
  color: white;
  text-decoration: none;
  font-size: 13px;
  font-weight: 700;
  box-shadow: 0 0 25px #697bff50;
}

/* HERO */

.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 130px 10% 70px;
  position: relative;
}

.hero-content {
  max-width: 750px;
  animation: appear 1.2s ease both;
}

.status {
  display: inline-flex;
  align-items: center;
  gap: 9px;
  padding: 10px 16px;
  background: #ffffff0b;
  border: 1px solid #ffffff18;
  border-radius: 30px;
  color: #b9c2df;
  font-size: 12px;
  margin-bottom: 30px;
}

.status span {
  width: 8px;
  height: 8px;
  background: #4dffac;
  border-radius: 50%;
  box-shadow: 0 0 12px #4dffac;
}

h1 {
  font-size: clamp(48px, 8vw, 92px);
  line-height: 1.05;
  font-weight: 900;
  letter-spacing: -5px;
}

.gradient-text {
  background: linear-gradient(100deg, #77a1ff, #bd7cff, #39dcff);
  -webkit-background-clip: text;
  color: transparent;
  background-size: 200%;
  animation: gradientMove 5s linear infinite;
}

@keyframes gradientMove {
  to { background-position: 200%; }
}

.hero p {
  margin-top: 28px;
  max-width: 590px;
  color: var(--muted);
  line-height: 1.9;
  font-size: 16px;
}

.hero-buttons {
  display: flex;
  gap: 16px;
  margin-top: 38px;
  flex-wrap: wrap;
}

.primary-btn, .secondary-btn {
  text-decoration: none;
  padding: 16px 25px;
  border-radius: 12px;
  font-weight: 700;
  font-size: 13px;
  transition: .3s;
}

.primary-btn {
  background: linear-gradient(120deg, var(--blue), var(--purple));
  color: white;
  box-shadow: 0 10px 35px #6c6cff35;
}

.secondary-btn {
  color: white;
  border: 1px solid #ffffff30;
  background: #ffffff08;
}

.primary-btn:hover, .secondary-btn:hover {
  transform: translateY(-5px);
}

/* SECTIONS */

section {
  padding: 100px 10%;
}

.section-label {
  color: var(--blue);
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 3px;
  margin-bottom: 15px;
}

.section-title {
  font-size: clamp(32px, 5vw, 48px);
  font-weight: 900;
  letter-spacing: -2px;
  margin-bottom: 20px;
}

.section-description {
  color: var(--muted);
  line-height: 1.8;
  max-width: 650px;
  margin-bottom: 45px;
}

/* GLASS CARDS */

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
  gap: 20px;
}

.card {
  padding: 30px;
  background: var(--glass);
  border: 1px solid #ffffff12;
  border-radius: 20px;
  backdrop-filter: blur(15px);
  transition: .4s;
  position: relative;
  overflow: hidden;
}

.card::before {
  content: "";
  position: absolute;
  width: 150px;
  height: 150px;
  background: #637bff18;
  filter: blur(50px);
  top: -80px;
  right: -70px;
}

.card:hover {
  transform: translateY(-10px);
  border-color: #718bff80;
  box-shadow: 0 20px 50px #0006, 0 0 25px #647cff18;
}

.card-icon {
  font-size: 34px;
  margin-bottom: 22px;
}

.card h3 {
  font-size: 19px;
  margin-bottom: 14px;
}

.card p {
  color: var(--muted);
  font-size: 13px;
  line-height: 1.8;
}

/* ABOUT */

.about-box {
  display: grid;
  grid-template-columns: 1.2fr .8fr;
  gap: 30px;
  align-items: center;
}

.about-text {
  color: var(--muted);
  line-height: 2;
  font-size: 15px;
}

.about-visual {
  min-height: 300px;
  border-radius: 25px;
  border: 1px solid #ffffff18;
  background: radial-gradient(circle, #526cff35, #17132c80, #090b17);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  perspective: 700px;
}

.big-cube {
  width: 110px;
  height: 110px;
  border: 2px solid #7c9dff;
  background: #718aff12;
  box-shadow: 0 0 60px #667bff80,
              inset 0 0 30px #667bff50;
  animation: cubeFloat 8s linear infinite;
}

/* SKILLS */

.skill {
  margin-bottom: 25px;
}

.skill-info {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
  font-size: 13px;
}

.skill-info span:last-child {
  color: #a9b5ff;
}

.skill-bar {
  height: 7px;
  background: #ffffff12;
  border-radius: 20px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  width: var(--width);
  background: linear-gradient(90deg, var(--blue), var(--cyan));
  border-radius: 20px;
  animation: progress 2s ease both;
}

@keyframes progress {
  from { width: 0; }
}

/* PROJECTS */

.project-card {
  min-height: 250px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.project-number {
  color: #7289ff;
  font-size: 12px;
  letter-spacing: 3px;
}

.project-card a {
  color: #a9b9ff;
  text-decoration: none;
  font-size: 13px;
  margin-top: 20px;
}

/* EXPERIENCE */

.timeline {
  border-left: 2px solid #647cff55;
  padding-left: 30px;
}

.timeline-item {
  position: relative;
  margin-bottom: 40px;
}

.timeline-item::before {
  content: "";
  position: absolute;
  left: -38px;
  top: 5px;
  width: 13px;
  height: 13px;
  background: var(--blue);
  border-radius: 50%;
  box-shadow: 0 0 20px var(--blue);
}

.timeline-item h3 {
  margin-bottom: 10px;
}

.timeline-item p {
  color: var(--muted);
  line-height: 1.8;
  font-size: 14px;
}

/* CONTACT */

.contact-box {
  text-align: center;
  padding: 65px 25px;
  border-radius: 30px;
  background: linear-gradient(135deg, #222b6155, #55246a40);
  border: 1px solid #ffffff20;
}

.contact-box h2 {
  font-size: clamp(30px, 5vw, 48px);
  margin-bottom: 20px;
}

.contact-box p {
  color: var(--muted);
  margin-bottom: 30px;
  line-height: 1.8;
}

footer {
  padding: 35px 10%;
  border-top: 1px solid #ffffff12;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 15px;
  color: var(--muted);
  font-size: 12px;
}

.reveal {
  opacity: 0;
  transform: translateY(35px);
  transition: 1s;
}

.reveal.show {
  opacity: 1;
  transform: translateY(0);
}

@keyframes appear {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

@media(max-width: 750px) {
  nav { padding: 20px 6%; }
  nav ul { display: none; }
  .hero { padding-left: 7%; padding-right: 7%; }
  section { padding: 75px 7%; }
  .about-box { grid-template-columns: 1fr; }
  h1 { letter-spacing: -3px; }
  footer { padding: 30px 7%; }
}
</style>
</head>

<body>

<div class="background">
  <div class="cube"></div>
  <div class="cube"></div>
  <div class="cube"></div>
  <div class="cube"></div>
  <div class="cube"></div>
</div>

<div class="glow"></div>
<div class="particles" id="particles"></div>

<nav>
  <div class="logo">SHOH<span>JAHON.</span></div>

  <ul>
    <li><a href="#about">Men haqimda</a></li>
    <li><a href="#skills">Ko‘nikmalar</a></li>
    <li><a href="#projects">Loyihalar</a></li>
    <li><a href="#experience">Tajriba</a></li>
  </ul>

  <a class="contact-btn" href="https://t.me/Shojahon2015">Bog‘lanish ↗</a>
</nav>

<header class="hero">
  <div class="hero-content">
    <div class="status">
      <span></span>
      CREATIVE DEVELOPER
    </div>

    <h1>
      Salom, men<br>
      <span class="gradient-text">Shohjahon.</span>
    </h1>

    <p>
      Men zamonaviy web-saytlar, raqamli mahsulotlar
      va kreativ dizaynlar yaratadigan veb dasturchi va dizaynerman.
      G‘oyalarni haqiqiy loyihalarga aylantiraman.
    </p>

    <div class="hero-buttons">
      <a href="#projects" class="primary-btn">Loyihalarimni ko‘r ↗</a>
      <a href="https://t.me/Shojahon2015" class="secondary-btn">Men bilan bog‘lan</a>
    </div>
  </div>
</header>

<section id="about" class="reveal">
  <div class="section-label">01 / ABOUT ME</div>
  <h2 class="section-title">Men haqimda</h2>

  <div class="about-box">
    <div class="about-text">
      <p>
        Dasturlash va veb-dizayn — mening asosiy yo‘nalishlarim.
        Men toza kod, qulay interfeys va zamonaviy ko‘rinishga
        katta e’tibor beraman.
      </p>
      <br>
      <p>
        HTML, CSS, JavaScript, React va Python kabi texnologiyalar
        bilan ishlayman. Shuningdek, Telegram botlar va turli
        raqamli platformalar yarataman.
      </p>
      <br>
      <p>
        Yangi g‘oyalarni sinab ko‘rish, muammolarga kreativ
        yechim topish va foydali mahsulotlar yaratish menga yoqadi.
      </p>
    </div>

    <div class="about-visual">
      <div class="big-cube"></div>
    </div>
  </div>
</section>

<section id="skills" class="reveal">
  <div class="section-label">02 / MY SKILLS</div>
  <h2 class="section-title">Texnologiyalar</h2>
  <p class="section-description">
    Loyihalarimda foydalanadigan texnologiyalar va vositalar.
  </p>

  <div class="card-grid">
    <div class="card">
      <div class="card-icon">🌐</div>
      <h3>Frontend</h3>
      <p>HTML, CSS, JavaScript, Bootstrap, React, Tilda</p>
    </div>

    <div class="card">
      <div class="card-icon">⚙️</div>
      <h3>Backend</h3>
      <p>Python, Django, Node.js va server texnologiyalari</p>
    </div>

    <div class="card">
      <div class="card-icon">🎨</div>
      <h3>UI/UX Design</h3>
      <p>Figma, Canva va zamonaviy interfeys dizayni</p>
    </div>

    <div class="card">
      <div class="card-icon">🤖</div>
      <h3>Automation</h3>
      <p>Telegram botlar va avtomatlashtirilgan yechimlar</p>
    </div>

    <div class="card">
      <div class="card-icon">🔧</div>
      <h3>Developer Tools</h3>
      <p>Git, GitHub va dasturchilar uchun vositalar</p>
    </div>
  </div>
</section>

<section class="reveal">
  <div class="section-label">03 / TECHNOLOGY LEVEL</div>
  <h2 class="section-title">Mening yo‘nalishlarim</h2>
  <p class="section-description">
    Doimiy o‘rganish va amaliy loyihalar orqali rivojlanib boraman.
  </p>

  <div class="card">
    <div class="skill">
      <div class="skill-info"><span>HTML / CSS</span><span>Web</span></div>
      <div class="skill-bar"><div class="skill-progress" style="--width:90%"></div></div>
    </div>

    <div class="skill">
      <div class="skill-info"><span>JavaScript</span><span>Web</span></div>
      <div class="skill-bar"><div class="skill-progress" style="--width:75%"></div></div>
    </div>

    <div class="skill">
      <div class="skill-info"><span>React / Bootstrap</span><span>Frontend</span></div>
      <div class="skill-bar"><div class="skill-progress" style="--width:70%"></div></div>
    </div>

    <div class="skill">
      <div class="skill-info"><span>Python / Django</span><span>Backend</span></div>
      <div class="skill-bar"><div class="skill-progress" style="--width:65%"></div></div>
    </div>

    <div class="skill">
      <div class="skill-info"><span>Figma / Canva</span><span>Design</span></div>
      <div class="skill-bar"><div class="skill-progress" style="--width:65%"></div></div>
    </div>
  </div>
</section>

<section id="projects" class="reveal">
  <div class="section-label">04 / SELECTED WORKS</div>
  <h2 class="section-title">Mening loyihalarim</h2>
  <p class="section-description">
    Men yaratgan va hozirda ishlab chiqayotgan raqamli mahsulotlar.
  </p>

  <div class="card-grid">
    <div class="card project-card">
      <div>
        <div class="project-number">PROJECT 01</div>
        <div class="card-icon">📅</div>
        <h3>Kundalik</h3>
        <p>
          Kunlik rejalar, budilnik va eslatmalar uchun
          yetti tilli platforma. Telefonga o‘rnatish mumkin.
        </p>
      </div>
      <a href="#">Loyiha haqida ↗</a>
    </div>

    <div class="card project-card">
      <div>
        <div class="project-number">PROJECT 02</div>
        <div class="card-icon">🏢</div>
        <h3>Kelajak Markazi</h3>
        <p>
          Uch tilli, zamonaviy dizayn va 3D elementlarga
          ega portfolio veb-sayt.
        </p>
      </div>
      <a href="#">Loyiha haqida ↗</a>
    </div>

    <div class="card project-card">
      <div>
        <div class="project-number">PROJECT 03</div>
        <div class="card-icon">🌍</div>
        <h3>World</h3>
        <p>
          Bolalar uchun IT va chet tillarini o‘rganish
          platformasi. Ishlab chiqilmoqda.
        </p>
      </div>
      <a href="#">Ishlab chiqilmoqda ↗</a>
    </div>

    <div class="card project-card">
      <div>
        <div class="project-number">PROJECT 04</div>
        <div class="card-icon">💼</div>
        <h3>Abron.uz</h3>
        <p>
          Bizneslar uchun qulay band qilish platformasi.
          Ishlab chiqilmoqda.
        </p>
      </div>
      <a href="#">Ishlab chiqilmoqda ↗</a>
    </div>
  </div>
</section>

<section id="experience" class="reveal">
  <div class="section-label">05 / EXPERIENCE</div>
  <h2 class="section-title">Tajriba va ta’lim</h2>

  <div class="timeline">
    <div class="timeline-item">
      <h3>IT va AI koordinatori</h3>
      <p>Maktabda IT va sun’iy intellekt yo‘nalishida faoliyat.</p>
    </div>

    <div class="timeline-item">
      <h3>Junior IT Academy</h3>
      <p>Bir yillik dasturlash kursi va grafik dizayn ta’limi.</p>
    </div>

    <div class="timeline-item">
      <h3>IT Startup Qarshi 2026</h3>
      <p>Startap yo‘nalishidagi tadbir ishtirokchisi.</p>
    </div>
  </div>
</section>

<section class="reveal">
  <div class="contact-box">
    <div class="section-label">06 / CONTACT</div>
    <h2>Birgalikda nimadir<br><span class="gradient-text">ajoyib yaratamiz!</span></h2>
    <p>
      Loyihangiz yoki hamkorlik bo‘yicha taklifingiz bormi?
      Telegram orqali bog‘lanishingiz mumkin.
    </p>
    <a href="https://t.me/Shojahon2015" class="primary-btn">
      Telegram orqali yozish ↗
    </a>
  </div>
</section>

<footer>
  <div>© 2026 Shohjahon. Barcha huquqlar himoyalangan.</div>
  <div>Designed & Developed with 💙</div>
</footer>

<script>
// ANIMATSIYALI ZARRALAR

const particles = document.getElementById("particles");

for (let i = 0; i < 45; i++) {
  const particle = document.createElement("div");
  particle.className = "particle";
  particle.style.left = Math.random() * 100 + "%";
  particle.style.animationDelay = Math.random() * 8 + "s";
  particle.style.animationDuration = (5 + Math.random() * 9) + "s";
  particles.appendChild(particle);
}

// SCROLL ANIMATION

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add("show");
    }
  });
}, { threshold: 0.12 });

document.querySelectorAll(".reveal").forEach(el => {
  observer.observe(el);
});
</script>

</body>
</html>
