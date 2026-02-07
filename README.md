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
      margin: 5;
      padding: 5;
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
    }

    /* ===== Header ===== */
    header {
      text-align: center;
      padding: 120px 20px;
    }

    header h1 {
      font-size: 3rem;
      color: #00ffff;
      text-shadow: 0 0 20px #00ffff;
    }

    header p {
      margin-top: 15px;
      color: #ccc;
    }

    /* ===== Navbar ===== */
    nav {
      position: sticky;
      top: 0;
      background: #0b0f1acc;
      backdrop-filter: blur(8px);
      padding: 15px;
      text-align: center;
    }

    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      transition: 0.3s;
    }

    nav a:hover {
      color: #00ffff;
      text-shadow: 0 0 10px #00ffff;
    }

    /* ===== Sections ===== */
    section {
      max-width: 1000px;
      margin: 80px auto;
      padding: 0 20px;
      opacity: 0;
      transform: translateY(40px);
      transition: 0.6s;
    }

    section.show {
      opacity: 1;
      transform: translateY(0);
    }

    h2 {
      color: #ff00ff;
      margin-bottom: 25px;
      text-shadow: 0 0 10px #ff00ff;
    }

    /* ===== Cards ===== */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 25px;
    }

    .card {
      background: #12172a;
      padding: 25px;
      border-radius: 18px;
      border: 1px solid #00ffff33;
      transition: 0.3s;
    }

    .card:hover {
      transform: translateY(-8px) scale(1.03);
      box-shadow: 0 0 20px #00ffff55;
    }

    .btn {
      display: inline-block;
      margin-top: 15px;
      padding: 10px 18px;
      border-radius: 10px;
      background: #00ffff;
      color: black;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }

    .btn:hover {
      background: #ff00ff;
      box-shadow: 0 0 15px #ff00ff;
    }

    footer {
      text-align: center;
      padding: 40px;
      color: #aaa;
    }

    /* ===== Mobile tweaks ===== */
    @media (max-width: 600px) {
      header h1 {
        font-size: 2rem;
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
    Hey! Ik ben Ylano.  
    Ik ontwerp en print mijn eigen 3D-projecten met mijn Anycubic printer
    en hou van technologie, games en bouwen.
  </p>
</section>

<section id="hobbies">
  <h2>Skills & Hobby's</h2>
  <div class="grid">
    <div class="card">🖨️ 3D Printing</div>
    <div class="card">💻 Programmeren</div>
    <div class="card">🎮 Gaming</div>
    <div class="card">🎨 Design</div>
  </div>
</section>

<section id="projecten">
  <h2>Portfolio</h2>

  <div class="grid">

    <div class="card">
      <h3>3D Print Case</h3>
      <p>Zelf ontworpen en geprint onderdeel.</p>
      <a href="#" class="btn">Bekijk</a>
    </div>

    <div class="card">
      <h3>Robot Arm</h3>
      <p>Mechanisch project met bewegende delen.</p>
      <a href="#" class="btn">Bekijk</a>
    </div>

    <div class="card">
      <h3>Game Mod</h3>
      <p>Eigen gaming project of mod.</p>
      <a href="#" class="btn">Bekijk</a>
    </div>

  </div>
</section>

<section id="contact">
  <h2>Contact</h2>
  <p>Stuur me een bericht of check mijn GitHub!</p>
  <a href="https://github.com/" class="btn">GitHub</a>
</section>

<footer>
  © 2026 Ylano — Neon Mode Active ⚡
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
  });

  sections.forEach(section => observer.observe(section));
</script>

</body>
</html>

