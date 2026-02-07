<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ylano | Portfolio</title>

  <!-- Google font -->
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Orbitron', sans-serif;
      background: #0b0f1a;
      color: white;
      scroll-behavior: smooth;
      overflow-x: hidden;
    }

    /* ===== Neon background glow ===== */
    body::before {
      content: "";
      position: fixed;
      width: 100%;
      height: 100%;
      background:
        radial-gradient(circle at 20% 20%, #00ffff22 0%, transparent 40%),
        radial-gradient(circle at 80% 60%, #ff00ff22 0%, transparent 40%);
      z-index: -1;
      pointer-events: none;
    }

    /* ===== Header ===== */
    header {
      text-align: center;
      padding: 120px 20px;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    header h1 {
      font-size: 4rem;
      color: #00ffff;
      text-shadow: 0 0 20px #00ffff, 0 0 40px #00ffff;
      animation: glow 3s ease-in-out infinite;
    }

    header p {
      margin-top: 15px;
      color: #ccc;
      font-size: 1.2rem;
      letter-spacing: 2px;
    }

    @keyframes glow {
      0%, 100% { text-shadow: 0 0 20px #00ffff, 0 0 40px #00ffff; }
      50% { text-shadow: 0 0 30px #00ffff, 0 0 60px #00ffff, 0 0 80px #00ffff; }
    }

    /* ===== Navbar ===== */
    nav {
      position: sticky;
      top: 0;
      background: rgba(11, 15, 26, 0.95);
      backdrop-filter: blur(8px);
      padding: 15px;
      text-align: center;
      z-index: 100;
      border-bottom: 1px solid #00ffff33;
    }

    nav a {
      color: white;
      margin: 0 20px;
      text-decoration: none;
      transition: 0.3s ease;
      font-weight: 600;
      position: relative;
    }

    nav a::after {
      content: '';
      position: absolute;
      bottom: -5px;
      left: 0;
      width: 0;
      height: 2px;
      background: #00ffff;
      transition: width 0.3s ease;
    }

    nav a:hover {
      color: #00ffff;
      text-shadow: 0 0 10px #00ffff;
    }

    nav a:hover::after {
      width: 100%;
    }

    /* ===== Sections ===== */
    section {
      max-width: 1000px;
      margin: 80px auto;
      padding: 0 20px;
      opacity: 0;
      transform: translateY(40px);
      transition: 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }

    section.show {
      opacity: 1;
      transform: translateY(0);
    }

    h2 {
      color: #ff00ff;
      margin-bottom: 40px;
      text-shadow: 0 0 10px #ff00ff;
      font-size: 2.5rem;
      position: relative;
      padding-bottom: 15px;
    }

    h2::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 50px;
      height: 3px;
      background: linear-gradient(90deg, #ff00ff, #00ffff);
    }

    h3 {
      color: #00ffff;
      margin-bottom: 12px;
      font-size: 1.3rem;
    }

    p {
      line-height: 1.8;
      color: #ddd;
      margin-bottom: 15px;
    }

    /* ===== Cards ===== */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
      margin-top: 30px;
    }

    .card {
      background: linear-gradient(135deg, #12172a 0%, #1a1f3a 100%);
      padding: 30px;
      border-radius: 20px;
      border: 2px solid #00ffff33;
      transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
      position: relative;
      overflow: hidden;
    }

    .card::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, #00ffff22, transparent);
      transition: left 0.5s ease;
    }

    .card:hover::before {
      left: 100%;
    }

    .card:hover {
      transform: translateY(-12px) scale(1.05);
      box-shadow: 0 15px 40px #00ffff55;
      border-color: #00ffff77;
    }

    .btn {
      display: inline-block;
      margin-top: 15px;
      padding: 12px 24px;
      border-radius: 12px;
      background: linear-gradient(135deg, #00ffff, #0099ff);
      color: black;
      text-decoration: none;
      font-weight: bold;
      transition: all 0.3s ease;
      border: none;
      cursor: pointer;
      box-shadow: 0 0 15px #00ffff44;
    }

    .btn:hover {
      background: linear-gradient(135deg, #ff00ff, #ff0080);
      box-shadow: 0 0 25px #ff00ff77;
      transform: translateY(-2px);
    }

    .btn:active {
      transform: translateY(0);
    }

    footer {
      text-align: center;
      padding: 50px 20px;
      color: #888;
      border-top: 1px solid #00ffff22;
      margin-top: 100px;
    }

    footer p {
      margin: 0;
    }

    /* ===== Mobile tweaks ===== */
    @media (max-width: 768px) {
      header h1 {
        font-size: 2.5rem;
      }

      h2 {
        font-size: 2rem;
      }

      nav a {
        margin: 0 10px;
        font-size: 0.95rem;
      }

      .grid {
        grid-template-columns: 1fr;
      }

      section {
        margin: 50px auto;
      }
    }

    @media (max-width: 480px) {
      header h1 {
        font-size: 2rem;
      }

      h2 {
        font-size: 1.5rem;
      }

      nav a {
        margin: 0 8px;
        font-size: 0.85rem;
      }
    }
  </style>
</head>

<body>

<header>
  <h1>Ylano.exe</h1>
  <p>3D Printing • Tech • Gaming • Creator</p>
</header>

<nav>
  <a href="#over">Over</a>
  <a href="#hobbies">Skills</a>
  <a href="#projecten">Portfolio</a>
  <a href="#contact">Contact</a>
</nav>

<section id="over">
  <h2>Over mij</h2>
  <p>
    Hé! Ik ben Ylano, een creativeling met een passie voor technologie en design. 
    Ik ontwerp en print mijn eigen 3D-projecten met mijn Anycubic printer en hou van het bouwen van dingen 
    van nul af aan. Of het nu gaat om gadgets, games of creatieve projecten – ik ga graag de grenzen op!
  </p>
</section>

<section id="hobbies">
  <h2>Skills & Hobby's</h2>
  <div class="grid">
    <div class="card">
      <div style="font-size: 2.5rem; margin-bottom: 10px;">🖨️</div>
      <h3>3D Printing</h3>
      <p>Ontwerpen en printen van custom onderdelen en prototypes</p>
    </div>
    <div class="card">
      <div style="font-size: 2.5rem; margin-bottom: 10px;">💻</div>
      <h3>Programmeren</h3>
      <p>Web development, scripting en automation projecten</p>
    </div>
    <div class="card">
      <div style="font-size: 2.5rem; margin-bottom: 10px;">🎮</div>
      <h3>Gaming</h3>
      <p>Gamer en gamedev enthusiast met oog voor design</p>
    </div>
    <div class="card">
      <div style="font-size: 2.5rem; margin-bottom: 10px;">🎨</div>
      <h3>Design</h3>
      <p>UI/UX, 3D-modeling en creatief probleemoplossen</p>
    </div>
  </div>
</section>

<section id="projecten">
  <h2>Portfolio</h2>

  <div class="grid">

    <div class="card">
      <h3>3D Print Case</h3>
      <p>Een custom ontworpen en geprinte case met gedetailleerd design. Dit project toont mijn vermogen om CAD te gebruiken en praktische onderdelen te creëren.</p>
      <a href="#" class="btn">Bekijk Project</a>
    </div>

    <div class="card">
      <h3>Robot Arm</h3>
      <p>Een mechanisch project met bewegende delen, ontworpen voor precisie. Dit combineert engineering, design en programmering.</p>
      <a href="#" class="btn">Bekijk Project</a>
    </div>

    <div class="card">
      <h3>Game Mod</h3>
      <p>Een eigen gaming project of mod die mijn programmeer- en designvaardigheden demonstreert in de gamedev-industrie.</p>
      <a href="#" class="btn">Bekijk Project</a>
    </div>

  </div>
</section>

<section id="contact">
  <h2>Contact</h2>
  <p>Interessant in samenwerking of wil je meer van mijn werk zien? Neem contact met me op!</p>
  <a href="https://github.com/libbrechtylano" class="btn">GitHub</a>
</section>

<footer>
  <p>© 2026 Ylano — Neon Mode Active ⚡</p>
</footer>

<!-- Scroll animation script -->
<script>
  const sections = document.querySelectorAll("section");

  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if(entry.isIntersecting){
        entry.target.classList.add("show");
      }
    });
  }, {
    threshold: 0.1
  });

  sections.forEach(section => observer.observe(section));
</script>

</body>
</html>
