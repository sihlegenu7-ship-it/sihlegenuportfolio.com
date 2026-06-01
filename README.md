<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sihle Genu — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,300;0,400;0,600;1,300&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #0a0a0a;
  --surface: #111;
  --card: #161616;
  --accent: #ff6b1a;
  --accent2: #ffd166;
  --text: #f0ede8;
  --muted: #888;
  --border: rgba(255,107,26,0.2);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'DM Sans', sans-serif;
  font-weight: 300;
  overflow-x: hidden;
}

/* NAV */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;
  display: flex; justify-content: space-between; align-items: center;
  padding: 1.2rem 6%;
  background: rgba(10,10,10,0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border);
}
.nav-logo {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.6rem;
  letter-spacing: 2px;
  color: var(--accent);
}
.nav-links a {
  color: var(--text);
  text-decoration: none;
  margin-left: 2rem;
  font-size: 0.85rem;
  letter-spacing: 1px;
  text-transform: uppercase;
  opacity: 0.7;
  transition: opacity .2s, color .2s;
}
.nav-links a:hover { opacity: 1; color: var(--accent); }

/* HERO */
#home {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  padding: 0 6%;
  gap: 4rem;
  padding-top: 80px;
  position: relative;
  overflow: hidden;
}
.hero-text { animation: fadeUp 0.9s ease both; }
.hero-label {
  font-size: 0.75rem;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: 1.2rem;
  display: flex; align-items: center; gap: 0.8rem;
}
.hero-label::before {
  content: '';
  display: inline-block;
  width: 30px; height: 1px;
  background: var(--accent);
}
h1 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(3.5rem, 8vw, 7rem);
  line-height: 0.92;
  letter-spacing: 1px;
  margin-bottom: 1.5rem;
}
h1 span { color: var(--accent); }
.hero-desc {
  font-size: 1rem;
  color: var(--muted);
  line-height: 1.7;
  max-width: 420px;
  margin-bottom: 2.5rem;
}
.hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }
.btn-primary {
  background: var(--accent);
  color: #fff;
  border: none;
  padding: 14px 32px;
  border-radius: 2px;
  cursor: pointer;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  font-weight: 600;
  transition: transform .2s, box-shadow .2s;
  text-decoration: none;
  display: inline-block;
}
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(255,107,26,0.4); }
.btn-ghost {
  background: transparent;
  color: var(--text);
  border: 1px solid rgba(240,237,232,0.3);
  padding: 13px 32px;
  border-radius: 2px;
  cursor: pointer;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  transition: border-color .2s, color .2s;
  text-decoration: none;
  display: inline-block;
}
.btn-ghost:hover { border-color: var(--accent); color: var(--accent); }

.hero-img-wrap {
  position: relative;
  animation: fadeUp 1.1s ease 0.2s both;
}
.hero-img-frame {
  width: 100%;
  max-width: 420px;
  aspect-ratio: 3/4;
  border-radius: 4px;
  overflow: hidden;
  position: relative;
  margin-left: auto;
  border: 1px solid var(--border);
  background: #1a1a1a;
  display: flex;
  align-items: center;
  justify-content: center;
}
.hero-img-frame::before {
  content: "✦";
  font-size: 4rem;
  color: var(--accent);
  opacity: 0.4;
}
.hero-badge {
  position: absolute;
  bottom: -18px; right: -18px;
  width: 110px; height: 110px;
  border-radius: 50%;
  background: var(--accent);
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  font-family: 'Bebas Neue', sans-serif;
  font-size: 0.85rem;
  letter-spacing: 2px;
  line-height: 1.3;
  text-align: center;
  color: #fff;
  z-index: 2;
  animation: spin 20s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }
.hero-badge-inner {
  animation: spin 20s linear infinite reverse;
  font-size: 0.75rem;
  letter-spacing: 1px;
}

/* ABOUT */
#about {
  padding: 120px 6%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 6rem;
  align-items: center;
}
.about-img-stack { position: relative; height: 480px; }
.about-img-back, .about-img-front {
  position: absolute;
  border-radius: 4px;
  border: 1px solid var(--border);
  background: #1a1a1a;
  display: flex;
  align-items: center;
  justify-content: center;
}
.about-img-back {
  width: 75%; height: 380px;
  bottom: 0; left: 0;
}
.about-img-back::before { content: "⟡"; font-size: 5rem; color: var(--accent); opacity: 0.3; }
.about-img-front {
  width: 60%; height: 300px;
  top: 0; right: 0;
  box-shadow: -8px 8px 40px rgba(0,0,0,0.6);
}
.about-img-front::before { content: "⚡"; font-size: 4rem; color: var(--accent); opacity: 0.3; }
.about-accent-box {
  position: absolute;
  bottom: 40px; right: -20px;
  background: var(--accent);
  color: #fff;
  padding: 16px 20px;
  border-radius: 2px;
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.8rem;
  line-height: 1;
  z-index: 2;
}
.about-accent-box small {
  display: block;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.65rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  font-weight: 400;
  margin-top: 4px;
}
.section-label {
  font-size: 0.7rem;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: 1rem;
}
h2 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(2.5rem, 5vw, 4rem);
  line-height: 1;
  margin-bottom: 1.5rem;
  letter-spacing: 1px;
}
.about-text p {
  color: var(--muted);
  line-height: 1.8;
  margin-bottom: 1.2rem;
  font-size: 0.95rem;
}

/* SKILLS */
#skills {
  padding: 100px 6%;
  background: var(--surface);
  position: relative;
}
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-top: 3rem;
}
.skill-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 4px;
  padding: 2rem 1.5rem;
  position: relative;
  overflow: hidden;
  transition: transform .3s, border-color .3s;
  cursor: default;
}
.skill-card:hover {
  transform: translateY(-4px);
  border-color: var(--accent);
}
.skill-card::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0;
  height: 2px;
  background: var(--accent);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform .3s;
}
.skill-card:hover::before { transform: scaleX(1); }
.skill-icon { font-size: 1.8rem; margin-bottom: 1rem; }
.skill-name {
  font-weight: 600;
  font-size: 1rem;
  margin-bottom: 0.4rem;
}
.skill-level {
  font-size: 0.75rem;
  color: var(--muted);
  letter-spacing: 2px;
  text-transform: uppercase;
}
.skill-bar {
  margin-top: 1rem;
  height: 2px;
  background: rgba(255,255,255,0.06);
  border-radius: 2px;
  overflow: hidden;
}
.skill-fill {
  height: 100%;
  background: var(--accent);
  border-radius: 2px;
  width: 0;
  transition: width 1.2s cubic-bezier(.4,0,.2,1);
}

/* EXPERIENCE */
#experience {
  padding: 100px 6%;
}
.exp-grid {
  display: grid;
  grid-template-columns: 2fr 1fr;
  grid-template-rows: auto auto;
  gap: 1.5rem;
  margin-top: 3rem;
}
.exp-card {
  border-radius: 4px;
  overflow: hidden;
  position: relative;
  border: 1px solid var(--border);
  background: var(--card);
  min-height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.exp-card.big { grid-row: span 2; min-height: 420px; }
.exp-card-label {
  position: absolute;
  bottom: 0; left: 0; right: 0;
  padding: 1.5rem;
  background: linear-gradient(to top, rgba(10,10,10,0.9) 0%, transparent 100%);
  font-size: 0.8rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--text);
  opacity: 0;
  transform: translateY(8px);
  transition: opacity .3s, transform .3s;
}
.exp-card:hover .exp-card-label { opacity: 1; transform: translateY(0); }
.exp-card-content { text-align: center; padding: 2rem; }
.exp-card-content .emoji { font-size: 3rem; margin-bottom: 1rem; display: block; }

/* PROJECTS */
#projects {
  padding: 100px 6%;
  background: var(--surface);
}
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}
.proj-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 4px;
  padding: 2.5rem 2rem;
  position: relative;
  overflow: hidden;
  transition: transform .3s, border-color .3s;
}
.proj-card:hover {
  transform: translateY(-4px);
  border-color: var(--accent);
}
.proj-number {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 4rem;
  color: rgba(255,107,26,0.08);
  position: absolute;
  top: 1rem; right: 1.5rem;
  line-height: 1;
  pointer-events: none;
}
.proj-tag {
  display: inline-block;
  font-size: 0.65rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--accent);
  background: rgba(255,107,26,0.1);
  border-radius: 2px;
  padding: 3px 8px;
  margin-bottom: 1.2rem;
}
.proj-card h3 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.8rem;
  letter-spacing: 1px;
  margin-bottom: 0.8rem;
}
.proj-card p {
  color: var(--muted);
  font-size: 0.9rem;
  line-height: 1.7;
  margin-bottom: 1.5rem;
}
.proj-link {
  font-size: 0.78rem;
  color: var(--accent);
  text-decoration: none;
  letter-spacing: 1px;
  text-transform: uppercase;
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  transition: gap .2s;
}
.proj-link:hover { gap: 0.8rem; }

/* CONTACT */
#contact {
  padding: 120px 6%;
  position: relative;
  overflow: hidden;
  text-align: center;
}
.contact-inner { max-width: 600px; margin: 0 auto; position: relative; }
.contact-inner h2 { font-size: clamp(3rem, 7vw, 6rem); margin-bottom: 1.2rem; }
.contact-inner p {
  color: var(--muted);
  font-size: 0.95rem;
  line-height: 1.8;
  margin-bottom: 3rem;
}
.contact-links {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}
.contact-link {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  padding: 14px 24px;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 2px;
  color: var(--text);
  text-decoration: none;
  font-size: 0.85rem;
  letter-spacing: 0.5px;
  transition: border-color .2s, color .2s, transform .2s;
}
.contact-link:hover {
  border-color: var(--accent);
  color: var(--accent);
  transform: translateY(-2px);
}

/* FOOTER */
footer {
  border-top: 1px solid var(--border);
  padding: 2rem 6%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.8rem;
  color: var(--muted);
}

/* ANIMATIONS */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}
.reveal {
  opacity: 0; transform: translateY(28px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible { opacity: 1; transform: none; }

/* RESPONSIVE */
@media (max-width: 768px) {
  #home { grid-template-columns: 1fr; padding-top: 100px; gap: 2rem; }
  .hero-img-wrap { order: -1; }
  .about-img-stack { height: 320px; }
  .exp-grid { grid-template-columns: 1fr; }
  .exp-card.big { grid-row: span 1; min-height: 260px; }
  nav .nav-links { display: none; }
  footer { flex-direction: column; gap: 0.5rem; text-align: center; }
}
</style>
</head>
<body>

<nav>
  <div class="nav-logo">SG</div>
  <div class="nav-links">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#experience">Journey</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<section id="home">
  <div class="hero-text">
    <div class="hero-label">Available for work</div>
    <h1>Sihle<br><span>Genu</span></h1>
    <p class="hero-desc">Systems Developer · Front-End Developer · UI Designer. Turning ideas into clean, engaging digital experiences at <strong style="color:var(--text)">Go Fourth Learning</strong>.</p>
    <div class="hero-btns">
      <a href="#projects" class="btn-primary">View My Work</a>
      <a href="#contact" class="btn-ghost">Let's Talk</a>
    </div>
  </div>
  <div class="hero-img-wrap">
    <div class="hero-img-frame"></div>
    <div class="hero-badge">
      <div class="hero-badge-inner">TECH<br>STUDENT<br>2026</div>
    </div>
  </div>
</section>

<section id="about">
  <div class="about-img-stack reveal">
    <div class="about-img-back"></div>
    <div class="about-img-front"></div>
    <div class="about-accent-box">
      AWS<br><small>Cloud + Tech</small>
    </div>
  </div>
  <div class="about-text reveal">
    <div class="section-label">Who I Am</div>
    <h2>Passionate<br>Builder &amp;<br>Learner</h2>
    <p>I'm a front-end developer and UI designer who enjoys turning ideas into engaging digital experiences. Currently sharpening my skills at the Go Fourth Learning Institute of Technology in Johannesburg.</p>
    <p>I believe in creating clean, user-friendly, and visually appealing websites that solve real-world problems. While still building my professional experience, I challenge myself every day through projects and learning opportunities.</p>
    <a href="#contact" class="btn-primary" style="margin-top:1rem">Get in Touch</a>
  </div>
</section>

<section id="skills">
  <div class="reveal">
    <div class="section-label">What I Bring</div>
    <h2>My Skills</h2>
  </div>
  <div class="skills-grid">
    <div class="skill-card reveal"><div class="skill-icon">⚡</div><div class="skill-name">HTML5</div><div class="skill-level">Solid Foundation</div><div class="skill-bar"><div class="skill-fill" style="width:85%"></div></div></div>
    <div class="skill-card reveal"><div class="skill-icon">🎨</div><div class="skill-name">CSS3</div><div class="skill-level">Intermediate</div><div class="skill-bar"><div class="skill-fill" style="width:78%"></div></div></div>
    <div class="skill-card reveal"><div class="skill-icon">🔧</div><div class="skill-name">JavaScript</div><div class="skill-level">Growing</div><div class="skill-bar"><div class="skill-fill" style="width:60%"></div></div></div>
    <div class="skill-card reveal"><div class="skill-icon">✏️</div><div class="skill-name">UI/UX Design</div><div class="skill-level">Intermediate</div><div class="skill-bar"><div class="skill-fill" style="width:72%"></div></div></div>
    <div class="skill-card reveal"><div class="skill-icon">☁️</div><div class="skill-name">AWS Cloud</div><div class="skill-level">Learning</div><div class="skill-bar"><div class="skill-fill" style="width:45%"></div></div></div>
    <div class="skill-card reveal"><div class="skill-icon">💡</div><div class="skill-name">Systems Dev</div><div class="skill-level">Core Strength</div><div class="skill-bar"><div class="skill-fill" style="width:90%"></div></div></div>
  </div>
</section>

<section id="experience">
  <div class="reveal">
    <div class="section-label">My Journey</div>
    <h2>Life at<br>Go Fourth</h2>
  </div>
  <div class="exp-grid">
    <div class="exp-card big reveal"><div class="exp-card-content"><span class="emoji">👥</span><h3 style="font-family:'Bebas Neue';">The Squad</h3><p style="color:var(--muted);">Collaboration & growth</p></div><div class="exp-card-label">The Squad — Go Fourth Learning</div></div>
    <div class="exp-card sm reveal"><div class="exp-card-content"><span class="emoji">🎤</span><h3 style="font-family:'Bebas Neue';">Presentations</h3></div><div class="exp-card-label">Presentations &amp; Storytelling</div></div>
    <div class="exp-card sm reveal"><div class="exp-card-content"><span class="emoji">☁️</span><h3 style="font-family:'Bebas Neue';">Cloud Computing</h3></div><div class="exp-card-label">Cloud Computing — Amazon FSx</div></div>
  </div>
</section>

<section id="projects">
  <div class="reveal">
    <div class="section-label">What I've Built</div>
    <h2>Projects</h2>
  </div>
  <div class="projects-grid">
    <div class="proj-card reveal"><div class="proj-number">01</div><span class="proj-tag">Web Design</span><h3>Real Deal Studios</h3><p>Artist management and music promotion website designed to showcase talent, build online presence, and connect artists with audiences.</p><a href="#" class="proj-link">View Project →</a></div>
    <div class="proj-card reveal"><div class="proj-number">02</div><span class="proj-tag">Portfolio</span><h3>Personal Portfolio</h3><p>This very website — a personal portfolio showcasing my skills, journey, and projects as a front-end developer and UI designer.</p><a href="#" class="proj-link">You're Here →</a></div>
  </div>
</section>

<section id="contact">
  <div class="contact-inner reveal">
    <div class="section-label">Let's Work Together</div>
    <h2>Get In<br>Touch</h2>
    <p>I'm open to opportunities, collaborations, and conversations. Reach out and let's build something great together.</p>
    <div class="contact-links">
      <a href="mailto:sihlegenu23@icloud.com" class="contact-link">✉️ sihlegenu23@icloud.com</a>
      <a href="https://wa.me/27732723384" target="_blank" class="contact-link">📱 073 272 3384</a>
    </div>
  </div>
</section>

<footer>
  <span class="nav-logo" style="font-family:'Bebas Neue',sans-serif;color:var(--accent);font-size:1.2rem;letter-spacing:2px;">Sihle Genu</span>
  <span>© 2026 — Front-End Developer · UI Designer</span>
</footer>

<script>
const reveals = document.querySelectorAll('.reveal');
const obs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); } });
}, { threshold: 0.12 });
reveals.forEach(r => obs.observe(r));

const bars = document.querySelectorAll('.skill-fill');
const barObs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.style.width = e.target.style.width; } });
}, { threshold: 0.3 });
bars.forEach(b => {
  const target = b.style.width;
  b.style.width = '0';
  barObs.observe(b);
  setTimeout(() => { b.style.width = target; }, 300);
});
</script>

</body>
</html>
