# yashkshirsagar.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Yash Kshirsagar – Portfolio</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
:root {
  --bg: #f6f6f6;
  --card-bg: #ffffff;
  --text: #222222;
  --accent: #2563eb;
  --accent-soft: #dbeafe;
  --border: #e5e7eb;
}

body.dark {
  --bg: #020617;
  --card-bg: #0f172a;
  --text: #e5e7eb;
  --accent: #3b82f6;
  --accent-soft: #1e293b;
  --border: #1f2937;
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Inter", sans-serif;
  background: var(--bg);
  color: var(--text);
  transition: background 0.3s ease, color 0.3s ease;
}

/* Navbar */
nav {
  position: sticky;
  top: 0;
  z-index: 20;
  backdrop-filter: blur(10px);
  background: linear-gradient(to right, rgba(15,23,42,0.92), rgba(30,64,175,0.92));
  color: white;
  padding: 10px 8%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav .brand {
  font-weight: 800;
  letter-spacing: 0.08em;
  font-size: 1.05rem;
}

nav .nav-links a {
  margin-left: 20px;
  text-decoration: none;
  color: #e5e7eb;
  font-size: 0.95rem;
  position: relative;
}

nav .nav-links a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -3px;
  width: 0%;
  height: 2px;
  background: #facc15;
  transition: width 0.2s ease-out;
}

nav .nav-links a:hover::after {
  width: 100%;
}

nav .nav-links a:hover {
  color: white;
}

button#themeToggle {
  border: 1px solid rgba(148,163,184,0.7);
  background: transparent;
  color: #e5e7eb;
  padding: 6px 10px;
  border-radius: 999px;
  cursor: pointer;
  font-size: 0.8rem;
  margin-left: 16px;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  transition: background 0.2s ease, transform 0.1s ease;
}

button#themeToggle:hover {
  background: rgba(15,23,42,0.4);
  transform: translateY(-1px);
}

/* Hero */
header.hero {
  padding: 60px 8% 40px 8%;
  background: radial-gradient(circle at top left, #1d4ed8 0, #020617 45%, #020617 100%);
  color: white;
}

.hero-inner {
  max-width: 900px;
  margin: 0 auto;
  opacity: 0;
  transform: translateY(20px);
  animation: heroFadeUp 0.8s ease-out forwards;
}

.hero-title {
  font-size: 2.6rem;
  margin-bottom: 4px;
}

.hero-tagline {
  font-size: 1.05rem;
  font-weight: 500;
  margin-bottom: 8px;
  color: #e5e7eb;
}

.hero-subtitle {
  font-size: 0.98rem;
  opacity: 0.92;
}

.hero-tags {
  margin-top: 14px;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.hero-tags span {
  border-radius: 999px;
  border: 1px solid rgba(148,163,184,0.8);
  padding: 4px 10px;
  font-size: 0.78rem;
  background: rgba(15,23,42,0.35);
}

.hero-actions {
  margin-top: 22px;
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.hero-actions a {
  text-decoration: none;
  font-size: 0.9rem;
  border-radius: 999px;
  padding: 9px 18px;
  transition: transform 0.15s ease, box-shadow 0.15s ease, background 0.15s ease;
}

.hero-primary {
  background: #facc15;
  color: #111827;
  font-weight: 600;
  box-shadow: 0 8px 18px rgba(15,23,42,0.4);
}

.hero-primary:hover {
  transform: translateY(-1px);
  box-shadow: 0 10px 25px rgba(15,23,42,0.6);
}

.hero-secondary {
  border: 1px solid rgba(209,213,219,0.9);
  color: white;
}

.hero-secondary:hover {
  background: rgba(15,23,42,0.55);
}

/* Sections */
section {
  padding: 40px 8%;
}

section h2 {
  color: var(--accent);
  border-bottom: 2px solid var(--accent);
  display: inline-block;
  margin-bottom: 14px;
}

/* Cards & layout */
.card {
  background: var(--card-bg);
  border-radius: 12px;
  padding: 20px;
  margin: 12px 0;
  border: 1px solid var(--border);
  box-shadow: 0 10px 25px rgba(15,23,42,0.05);
  transition: transform 0.15s ease, box-shadow 0.15s ease, background 0.2s ease, border-color 0.2s ease;
}

.card:hover {
  transform: translateY(-3px);
  box-shadow: 0 16px 40px rgba(15,23,42,0.12);
  border-color: rgba(37,99,235,0.5);
}

.card h3 {
  margin-top: 0;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 16px;
}

/* Reveal animation */
.reveal {
  opacity: 0;
  transform: translateY(18px);
  transition: opacity 0.5s ease-out, transform 0.5s ease-out;
}

.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Timeline */
.timeline {
  border-left: 2px solid var(--accent);
  padding-left: 20px;
  margin-top: 10px;
}

.timeline-item {
  margin-bottom: 18px;
  position: relative;
  padding-left: 2px;
}

.timeline-item::before {
  content: "";
  position: absolute;
  left: -11px;
  top: 4px;
  width: 10px;
  height: 10px;
  background: var(--accent);
  border-radius: 999px;
}

.timeline-item span {
  font-size: 0.8rem;
  opacity: 0.75;
}

/* Skills chips */
.skills-list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.skills-list span {
  font-size: 0.8rem;
  padding: 6px 10px;
  border-radius: 999px;
  background: var(--accent-soft);
}

body.dark .skills-list span {
  background: rgba(15,23,42,0.8);
  border: 1px solid rgba(55,65,81,0.9);
}

/* Contact */
.contact-links a {
  display: inline-block;
  margin-right: 12px;
  margin-bottom: 8px;
  text-decoration: none;
  font-size: 0.9rem;
  color: var(--accent);
}

.contact-links a:hover {
  text-decoration: underline;
}

/* Footer */
footer {
  text-align: center;
  padding: 18px;
  font-size: 0.8rem;
  color: #9ca3af;
}

/* Keyframes */
@keyframes heroFadeUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive */
@media (max-width: 600px) {
  .hero-title {
    font-size: 1.9rem;
  }
  nav {
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
  }
}
</style>
</head>
<body>

<nav>
  <div class="brand">YK</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#experience">Experience</a>
    <a href="#skills">Skills</a>
    <a href="#contact">Contact</a>
    <button id="themeToggle">🌙 <span>Dark</span></button>
  </div>
</nav>

<header class="hero">
  <div class="hero-inner">
    <div class="hero-title">Yash Kshirsagar</div>
    <div class="hero-tagline">Aspiring Software Engineer & Tech-Driven Leader</div>
    <div class="hero-subtitle">
      Computer Science student with a strong blend of <strong>technical skills</strong>,
      <strong>entrepreneurial mindset</strong>, and <strong>leadership experience</strong>.
      I enjoy building practical solutions, leading high-impact events, and collaborating with
      diverse stakeholders to turn ideas into execution-ready outcomes.
    </div>
    <div class="hero-tags">
      <span>Computer Science</span>
      <span>Cybersecurity Fundamentals</span>
      <span>Event Tech & Ops</span>
      <span>Entrepreneurship</span>
      <span>Public Speaking</span>
      <span>Team Leadership</span>
    </div>
    <div class="hero-actions">
      <a class="hero-primary" href="#contact">Contact Me</a>
      <!-- Replace resume.pdf with your actual resume link -->
      <a class="hero-secondary" href="resume.pdf" target="_blank" rel="noopener noreferrer">Download Resume</a>
    </div>
  </div>
</header>

<section id="about">
  <h2>About Me</h2>
  <div class="card reveal">
    <p>
      I am a <strong>Computer Science engineering student from Nashik</strong>, actively building my profile at the
      intersection of <strong>technology, strategy, and execution</strong>. Over the past few years, I have:
    </p>
    <ul>
      <li>Led <strong>technical operations and teams</strong> for large-scale conferences with 300+ participants.</li>
      <li>Won an <strong>entrepreneurship flagship competition (E-Verse 2023)</strong> with an implementation-ready startup plan.</li>
      <li>Collaborated closely with <strong>school leadership, government initiatives, and industry mentors</strong>.</li>
    </ul>
    <p>
      I’m particularly interested in <strong>software development, tech-enabled business solutions, and cybersecurity</strong>.
      I’m currently exploring opportunities in <strong>SDE, product, and tech strategy roles</strong> where I can contribute
      both technically and through strong communication and leadership.
    </p>
  </div>
</section>

<section id="projects">
  <h2>Projects</h2>
  <div class="grid">
    <div class="card reveal">
      <h3>Smart Bus Tracking System</h3>
      <p>
        A web-based interface that displays real-time bus locations using mapping APIs and a clean, intuitive UI.
        Built to improve urban navigation and reduce uncertainty for daily commuters.
      </p>
      <ul>
        <li>Developed using <strong>HTML, CSS, JavaScript</strong> and mapping APIs.</li>
        <li>Designed responsive front-end and route visualization for better user experience.</li>
      </ul>
    </div>
    <div class="card reveal">
      <h3>Library Management System</h3>
      <p>
        A database-backed system for managing book issue/return and inventory at an institutional level, with a focus on reliability and ease of use.
      </p>
      <ul>
        <li>Implemented using <strong>MySQL, HTML/CSS, JavaScript</strong>.</li>
        <li>Supports essential CRUD operations with structured and secure data handling.</li>
      </ul>
    </div>
    <div class="card reveal">
      <h3>Startup Business Plan – Real Estate & Daily Living</h3>
      <p>
        A full-scale business plan developed as part of <strong>E-Verse 2023</strong>, targeting real estate and daily living needs with tech-enabled solutions.
      </p>
      <ul>
        <li>Focused on simplifying daily living needs in a real estate context through a scalable model.</li>
        <li>Included financial modeling, go-to-market strategy, and a polished pitch deck.</li>
        <li>Presented and defended in a live competition setting, leading to a <strong>winning outcome</strong>.</li>
      </ul>
    </div>
  </div>
</section>

<section id="experience">
  <h2>Experience & Leadership</h2>

  <div class="card reveal">
    <h3>Timeline</h3>
    <div class="timeline">

      <div class="timeline-item reveal">
        <strong>Technical Head & Secretariat Member – WHISMUN</strong>
        <span> | 2022–2023</span>
        <p>
          Led end-to-end technical operations for two high-scale Model United Nations conferences with
          <strong>300+ participants</strong>, heading a team of <strong>6+ members</strong> and ensuring seamless event execution.
          Worked in close coordination with the <strong>Director and Principal of Wisdom High International School & Junior College</strong>,
          aligning strategy, logistics, and quality standards. Built strong <strong>business, academic, and institutional connections</strong>,
          and fostered a collaborative, high-performance team culture.
        </p>
      </div>

      <div class="timeline-item reveal">
        <strong>Marketing & Social Media Lead – E-Cell GESCOE</strong>
        <span> | 2022–2023</span>
        <p>
          Drove strategic marketing and social media initiatives to strengthen the campus entrepreneurship ecosystem.
          Collaborated with <strong>NIMA, Startup India, and Government of Maharashtra</strong> to design and execute
          brand-building activities and engagement-driven campaigns that increased participation and visibility.
        </p>
      </div>

      <div class="timeline-item reveal">
        <strong>Winner – E-Verse 2023 (Entrepreneurship Cell GESCOE)</strong>
        <span> | 2023</span>
        <p>
          Won the flagship entrepreneurship competition by presenting a high-potential, implementation-ready startup
          plan in real estate and daily living solutions. Created <strong>on-the-spot pitch decks</strong>, delivered
          impactful presentations to judges and participants, and built valuable connections with mentors and industry experts.
        </p>
      </div>

      <div class="timeline-item reveal">
        <strong>Cybersecurity Analyst Simulation – Tata Consultancy Services (TCS)</strong>
        <span> | 2023</span>
        <p>
          Completed a structured cybersecurity job simulation, working through <strong>SIEM analysis, incident investigation,
          log review, and documentation</strong>. Gained exposure to Security Operations Center (SOC) workflows and
          foundational threat analysis practices.
        </p>
      </div>

    </div>
  </div>
</section>

<section id="skills">
  <h2>Skills</h2>
  <div class="card reveal">
    <h3>Technical Skills</h3>
    <div class="skills-list">
      <span>Java</span><span>Python</span><span>C/C++</span><span>SQL</span>
      <span>JavaScript</span><span>HTML/CSS</span><span>React</span><span>Node.js</span>
      <span>MySQL</span><span>Git</span><span>Docker</span>
    </div>
  </div>
  <div class="card reveal">
    <h3>Core Strengths</h3>
    <div class="skills-list">
      <span>Leadership</span><span>Event Management</span><span>Cybersecurity Fundamentals</span>
      <span>Public Speaking</span><span>Problem Solving</span><span>Pitching & Communication</span>
      <span>Team Collaboration</span><span>Stakeholder Management</span>
    </div>
  </div>
</section>

<section id="contact">
  <h2>Contact</h2>
  <div class="card reveal">
    <p>
      I am actively looking for opportunities in <strong>software development, tech-enabled business roles,
      and cybersecurity-adjacent roles</strong>. If you’d like to connect about internships, projects, or collaborations, feel free to reach out:
    </p>
    <div class="contact-links">
      <a href="mailto:yashkshirsagar.yk@gmail.com">📧 Email</a>
      <a href="https://www.linkedin.com/in/yash-kshirsagar-b8ba4539a/" target="_blank" rel="noopener noreferrer">🔗 LinkedIn</a>
      <!-- Replace this with your actual GitHub once set -->
      <a href="https://github.com/YOUR_GITHUB_USERNAME" target="_blank" rel="noopener noreferrer">💻 GitHub</a>
    </div>
  </div>
</section>

<footer>
  © 2025 Yash Kshirsagar · Built with HTML, CSS & a lot of curiosity
</footer>

<script>
// Dark mode toggle with localStorage
const toggleBtn = document.getElementById('themeToggle');
const body = document.body;

if (localStorage.getItem('theme') === 'dark') {
  body.classList.add('dark');
  toggleBtn.innerHTML = '☀️ <span>Light</span>';
}

toggleBtn.addEventListener('click', () => {
  body.classList.toggle('dark');
  const isDark = body.classList.contains('dark');
  toggleBtn.innerHTML = isDark ? '☀️ <span>Light</span>' : '🌙 <span>Dark</span>';
  localStorage.setItem('theme', isDark ? 'dark' : 'light');
});

// Reveal on scroll
const revealElements = document.querySelectorAll('.reveal');

const onScrollReveal = () => {
  const triggerBottom = window.innerHeight * 0.88;
  revealElements.forEach(el => {
    const boxTop = el.getBoundingClientRect().top;
    if (boxTop < triggerBottom) {
      el.classList.add('visible');
    }
  });
};

window.addEventListener('scroll', onScrollReveal);
window.addEventListener('load', onScrollReveal);
</script>

</body>
</html>
