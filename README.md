<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Peak Forge | Train Hard. Track Reps. Transform.</title>
  <!-- Google Fonts + simple reset -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 (free) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background-color: #0a0c0f;
      color: #eef2f5;
      scroll-behavior: smooth;
      line-height: 1.4;
    }

    /* custom scrollbar */
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: #1e1f22;
    }
    ::-webkit-scrollbar-thumb {
      background: #f0542c;
      border-radius: 10px;
    }

    .container {
      max-width: 1280px;
      margin: 0 auto;
      padding: 0 2rem;
    }

    /* NAVBAR */
    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.25rem 2rem;
      background: rgba(10, 12, 15, 0.95);
      backdrop-filter: blur(8px);
      position: sticky;
      top: 0;
      z-index: 100;
      border-bottom: 1px solid rgba(240, 84, 44, 0.3);
    }
    .logo {
      font-size: 1.8rem;
      font-weight: 800;
      letter-spacing: -1px;
      background: linear-gradient(135deg, #f0542c, #ff8c42);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }
    .nav-links a {
      text-decoration: none;
      color: #eef2f5;
      font-weight: 500;
      transition: 0.2s;
      font-size: 1rem;
    }
    .nav-links a:hover, .nav-links a.active {
      color: #f0542c;
    }
    .btn-outline {
      border: 1.5px solid #f0542c;
      background: transparent;
      padding: 0.5rem 1.25rem;
      border-radius: 40px;
      color: #f0542c;
      font-weight: 600;
      transition: 0.2s;
      cursor: pointer;
    }
    .btn-outline:hover {
      background: #f0542c;
      color: #0a0c0f;
    }
    .btn-solid {
      background: #f0542c;
      border: none;
      padding: 0.7rem 1.5rem;
      border-radius: 40px;
      font-weight: 700;
      color: white;
      cursor: pointer;
      transition: 0.2s;
      font-size: 0.9rem;
    }
    .btn-solid:hover {
      background: #c13d1b;
      transform: scale(1.02);
    }

    /* HERO */
    .hero {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      padding: 3rem 0 4rem 0;
      gap: 2rem;
    }
    .hero-content {
      flex: 1;
    }
    .hero-content h1 {
      font-size: 3.5rem;
      font-weight: 800;
      line-height: 1.2;
      margin-bottom: 1.2rem;
    }
    .hero-highlight {
      color: #f0542c;
      border-bottom: 3px solid #f0542c;
    }
    .hero-content p {
      font-size: 1.2rem;
      color: #bdc3cf;
      margin-bottom: 2rem;
      max-width: 500px;
    }
    .hero-stats {
      display: flex;
      gap: 2rem;
      margin-top: 1.5rem;
    }
    .stat {
      text-align: left;
    }
    .stat-number {
      font-size: 2rem;
      font-weight: 800;
      color: #f0542c;
    }
    .hero-image {
      flex: 1;
      text-align: center;
    }
    .hero-image img {
      max-width: 100%;
      filter: drop-shadow(0 20px 25px -12px rgba(0,0,0,0.5));
      border-radius: 20px;
    }
    /* REP TRACKER SECTION (CORE INTERACTIVE) */
    .tracker-section {
      background: #111317;
      border-radius: 40px;
      padding: 2rem 2rem 2.5rem;
      margin: 3rem 0;
      box-shadow: 0 25px 35px -12px rgba(0,0,0,0.4);
      border: 1px solid #292e36;
    }
    .section-title {
      font-size: 2rem;
      font-weight: 700;
      margin-bottom: 1rem;
      text-align: center;
    }
    .section-desc {
      text-align: center;
      color: #a0a7b5;
      margin-bottom: 2rem;
    }
    .tracker-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: center;
    }
    .exercise-card {
      background: #1a1e24;
      border-radius: 28px;
      padding: 1.5rem;
      width: 280px;
      transition: transform 0.2s;
      border: 1px solid #2c323b;
    }
    .exercise-card:hover {
      transform: translateY(-5px);
      border-color: #f0542c;
    }
    .exercise-name {
      font-size: 1.5rem;
      font-weight: 700;
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 1rem;
    }
    .exercise-name i {
      color: #f0542c;
      font-size: 1.6rem;
    }
    .rep-control {
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: #0f1116;
      padding: 0.6rem 1rem;
      border-radius: 60px;
      margin: 1.2rem 0;
    }
    .rep-count {
      font-size: 2rem;
      font-weight: 800;
      font-family: monospace;
      background: #00000066;
      padding: 0 0.8rem;
      border-radius: 40px;
    }
    .rep-buttons button {
      background: #2c323d;
      border: none;
      font-size: 1.3rem;
      font-weight: bold;
      width: 40px;
      height: 40px;
      border-radius: 40px;
      margin: 0 5px;
      color: white;
      cursor: pointer;
      transition: 0.1s;
    }
    .rep-buttons button:hover {
      background: #f0542c;
    }
    .set-log {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      font-size: 0.85rem;
      background: #0b0d10;
      padding: 0.6rem;
      border-radius: 20px;
      margin-top: 0.8rem;
    }
    .log-btn {
      background: #f0542c;
      border: none;
      padding: 0.3rem 0.9rem;
      border-radius: 30px;
      font-weight: 600;
      font-size: 0.75rem;
      cursor: pointer;
      color: white;
    }
    .log-btn:active {
      transform: scale(0.96);
    }
    .total-reps {
      font-weight: 700;
      color: #ffb347;
    }
    /* PROGRESS & MOTIVATION */
    .progress-summary {
      margin-top: 2rem;
      background: #0e1015;
      border-radius: 28px;
      padding: 1.2rem 1.8rem;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
    }
    .total-stats {
      display: flex;
      gap: 1.5rem;
      flex-wrap: wrap;
    }
    .total-card {
      background: #1e222a;
      padding: 0.5rem 1.2rem;
      border-radius: 40px;
    }
    .reset-tracker {
      background: none;
      border: 1px solid #f0542c;
      color: #f0542c;
      padding: 0.5rem 1.2rem;
      border-radius: 40px;
      font-weight: 600;
      cursor: pointer;
      transition: 0.2s;
    }
    .reset-tracker:hover {
      background: #f0542c20;
    }
    /* PROGRAMS SECTION */
    .programs {
      margin: 4rem 0;
    }
    .program-cards {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: center;
      margin-top: 2rem;
    }
    .program-card {
      background: #111317;
      border-radius: 28px;
      padding: 2rem 1.5rem;
      width: 280px;
      text-align: center;
      transition: all 0.2s;
      border: 1px solid #292e36;
    }
    .program-card i {
      font-size: 2.8rem;
      color: #f0542c;
      margin-bottom: 1rem;
    }
    .program-card h3 {
      font-size: 1.5rem;
      margin-bottom: 1rem;
    }
    .program-card p {
      color: #b4bccc;
    }
    /* trainers / community */
    .testimonial {
      background: linear-gradient(145deg, #111317, #0c0e12);
      border-radius: 32px;
      padding: 2rem;
      margin: 3rem 0;
      text-align: center;
    }
    .testimonial i {
      font-size: 2rem;
      color: #f0542c;
      margin-bottom: 1rem;
    }
    /* FOOTER */
    footer {
      border-top: 1px solid #1e222a;
      padding: 2rem 0;
      margin-top: 3rem;
      text-align: center;
      color: #7c838f;
    }
    @media (max-width: 780px) {
      .navbar {
        flex-direction: column;
        gap: 1rem;
      }
      .hero {
        flex-direction: column;
        text-align: center;
      }
      .hero-content h1 {
        font-size: 2.5rem;
      }
      .hero-stats {
        justify-content: center;
      }
      .tracker-grid {
        gap: 1rem;
      }
    }
    button {
      font-family: inherit;
    }
    .motivation-tag {
      background: #f0542c20;
      border-left: 4px solid #f0542c;
      padding: 0.6rem 1rem;
      border-radius: 16px;
      margin-top: 1rem;
    }
  </style>
</head>
<body>

<nav class="navbar">
  <div class="logo"><i class="fas fa-dumbbell"></i> PEAK FORGE</div>
  <ul class="nav-links">
    <li><a href="#" class="active">Home</a></li>
    <li><a href="#">Training</a></li>
    <li><a href="#">Programs</a></li>
    <li><a href="#">Community</a></li>
  </ul>
  <button class="btn-outline" id="joinBtn">Join The Grind <i class="fas fa-arrow-right"></i></button>
</nav>

<main class="container">
  <!-- Hero section -->
  <div class="hero">
    <div class="hero-content">
      <h1>Elevate <span class="hero-highlight">Strength</span><br> Dominate Every Rep</h1>
      <p>Track your sets, log your reps, and break personal records with our interactive rep tracker. Precision meets passion.</p>
      <button class="btn-solid" id="scrollToTracker"><i class="fas fa-chart-line"></i> Start Tracking Now</button>
      <div class="hero-stats">
        <div class="stat"><span class="stat-number">500+</span><br>Active Athletes</div>
        <div class="stat"><span class="stat-number">120+</span><br>Programs</div>
        <div class="stat"><span class="stat-number">10k+</span><br>Daily Reps</div>
      </div>
    </div>
    <div class="hero-image">
      <!-- SVG style hero illustration (abstract gym) -->
      <svg viewBox="0 0 400 320" fill="none" xmlns="http://www.w3.org/2000/svg" style="max-width:100%">
        <rect x="30" y="150" width="80" height="120" rx="16" fill="#2A2F39" stroke="#f0542c" stroke-width="2"/>
        <rect x="130" y="100" width="80" height="170" rx="16" fill="#2A2F39" stroke="#f0542c" stroke-width="2"/>
        <rect x="230" y="50" width="80" height="220" rx="16" fill="#2A2F39" stroke="#f0542c" stroke-width="2"/>
        <circle cx="70" cy="280" r="12" fill="#f0542c"/>
        <circle cx="170" cy="280" r="12" fill="#f0542c"/>
        <circle cx="270" cy="280" r="12" fill="#f0542c"/>
        <path d="M340 210 L380 210 L360 250 Z" fill="#f0542c" opacity="0.9"/>
        <text x="40" y="60" fill="#f0542c" font-size="14" font-weight="bold">REPS MATTER</text>
        <text x="260" y="200" fill="#eef2f5" font-size="12">#FOCUS</text>
      </svg>
    </div>
  </div>

  <!-- REP TRACKER - CORE INTERACTIVE SECTION (Training & Reps) -->
  <div class="tracker-section" id="repTracker">
    <h2 class="section-title"><i class="fas fa-stopwatch"></i> LIVE REP COUNTER</h2>
    <p class="section-desc">Log your working sets, increase reps, and build momentum. Every rep counts toward your total volume.</p>
    
    <div class="tracker-grid" id="exercisesContainer">
      <!-- exercises injected via JS but we provide static fallback structure, yet we generate dynamic for better control -->
    </div>

    <!-- Summary & reset -->
    <div class="progress-summary" id="progressPanel">
      <div class="total-stats">
        <div class="total-card"><i class="fas fa-weight-hanging"></i> Total Reps: <span id="totalRepsAll">0</span></div>
        <div class="total-card"><i class="fas fa-list"></i> Completed Sets: <span id="totalSetsLogged">0</span></div>
      </div>
      <button class="reset-tracker" id="resetAllData"><i class="fas fa-trash-alt"></i> Reset All Reps</button>
    </div>
    <div class="motivation-tag" id="motivationMsg">
      <i class="fas fa-fire"></i> “Rep by rep, you’re becoming unstoppable.”
    </div>
  </div>

  <!-- Training Programs Section -->
  <div class="programs">
    <h2 class="section-title">Signature Training Plans</h2>
    <div class="program-cards">
      <div class="program-card"><i class="fas fa-dumbbell"></i><h3>Strength Builder</h3><p>3x/week · progressive overload · 5–8 rep range</p></div>
      <div class="program-card"><i class="fas fa-heartbeat"></i><h3>Hypertrophy Peak</h3><p>Volume focus · 8–12 reps · 4 sets each</p></div>
      <div class="program-card"><i class="fas fa-bolt"></i><h3>Power & Explosion</h3><p>Olympic lifts · 3–5 reps · explosive tempo</p></div>
    </div>
  </div>

  <!-- Community / Coach -->
  <div class="testimonial">
    <i class="fas fa-quote-right"></i>
    <p style="font-size: 1.2rem; max-width: 700px; margin:0.5rem auto;">"Using Peak Forge’s rep tracker pushed me to add 45lbs to my bench in 8 weeks. Consistency + data = real gains."</p>
    <h4 style="margin-top: 1rem;">— Marcus Chen, Elite Coach</h4>
    <div style="margin-top: 1rem;"><i class="fas fa-star" style="color:#f0542c;"></i><i class="fas fa-star" style="color:#f0542c;"></i><i class="fas fa-star" style="color:#f0542c;"></i><i class="fas fa-star" style="color:#f0542c;"></i><i class="fas fa-star" style="color:#f0542c;"></i></div>
  </div>
</main>

<footer>
  <p><i class="fas fa-dumbbell"></i> Peak Forge Gym — Train with intention. Every rep, every set, every day.</p>
  <p style="margin-top: 0.5rem;">© 2025 | #ForgeYourPeak</p>
</footer>

<script>
  // ---------- GYM REP TRACKER DATA ----------
  // Define exercises with initial reps per set, and sets array (dynamic)
  let exercises = [
    { id: 0, name: "Barbell Bench Press", icon: "fas fa-chest", currentReps: 8, setsHistory: [8, 7, 8] },   // last logged sets (3 default)
    { id: 1, name: "Pull-ups (Weighted)", icon: "fas fa-hand-peace", currentReps: 6, setsHistory: [6, 5, 6] },
    { id: 2, name: "Leg Press", icon: "fas fa-walking", currentReps: 12, setsHistory: [12, 12, 10] },
    { id: 3, name: "Dumbbell Shoulder Press", icon: "fas fa-fist-raised", currentReps: 10, setsHistory: [10, 9, 8] }
  ];
  
  // helper to compute total reps from all setsHistory
  function computeTotalReps() {
    let total = 0;
    exercises.forEach(ex => {
      total += ex.setsHistory.reduce((acc, val) => acc + val, 0);
    });
    return total;
  }
  
  function computeTotalSets() {
    let totalSets = 0;
    exercises.forEach(ex => {
      totalSets += ex.setsHistory.length;
    });
    return totalSets;
  }
  
  // update UI total display & motivation message
  function updateSummaryUI() {
    const totalRepsSpan = document.getElementById('totalRepsAll');
    const totalSetsSpan = document.getElementById('totalSetsLogged');
    if (totalRepsSpan) totalRepsSpan.innerText = computeTotalReps();
    if (totalSetsSpan) totalSetsSpan.innerText = computeTotalSets();
    
    // dynamic motivation based on total reps
    const totalReps = computeTotalReps();
    const msgDiv = document.getElementById('motivationMsg');
    if (totalReps > 120) {
      msgDiv.innerHTML = `<i class="fas fa-crown"></i> LEGEND MODE: ${totalReps} total reps! You're on fire 🔥`;
    } else if (totalReps > 60) {
      msgDiv.innerHTML = `<i class="fas fa-chart-simple"></i> Strong volume: ${totalReps} total reps! Keep pushing.`;
    } else if (totalReps > 20) {
      msgDiv.innerHTML = `<i class="fas fa-fire"></i> Great start: ${totalReps} total reps — consistency wins.`;
    } else {
      msgDiv.innerHTML = `<i class="fas fa-dumbbell"></i> Log your first set — every rep builds momentum.`;
    }
  }
  
  // render all exercise cards dynamically
  function renderExercises() {
    const container = document.getElementById('exercisesContainer');
    if (!container) return;
    container.innerHTML = '';
    exercises.forEach((ex, idx) => {
      const card = document.createElement('div');
      card.className = 'exercise-card';
      card.dataset.id = ex.id;
      
      // Header with icon
      const nameDiv = document.createElement('div');
      nameDiv.className = 'exercise-name';
      nameDiv.innerHTML = `<i class="${ex.icon}"></i> ${ex.name}`;
      
      // Rep control area
      const repControl = document.createElement('div');
      repControl.className = 'rep-control';
      const repValueSpan = document.createElement('span');
      repValueSpan.className = 'rep-count';
      repValueSpan.id = `repValue-${ex.id}`;
      repValueSpan.innerText = ex.currentReps;
      
      const btnGroup = document.createElement('div');
      btnGroup.className = 'rep-buttons';
      const minusBtn = document.createElement('button');
      minusBtn.innerText = '-';
      minusBtn.addEventListener('click', (e) => {
        e.stopPropagation();
        let newVal = ex.currentReps - 1;
        if (newVal < 1) newVal = 1;
        ex.currentReps = newVal;
        document.getElementById(`repValue-${ex.id}`).innerText = ex.currentReps;
      });
      const plusBtn = document.createElement('button');
      plusBtn.innerText = '+';
      plusBtn.addEventListener('click', (e) => {
        e.stopPropagation();
        let newVal = ex.currentReps + 1;
        if (newVal > 50) newVal = 50;
        ex.currentReps = newVal;
        document.getElementById(`repValue-${ex.id}`).innerText = ex.currentReps;
      });
      btnGroup.appendChild(minusBtn);
      btnGroup.appendChild(plusBtn);
      repControl.appendChild(repValueSpan);
      repControl.appendChild(btnGroup);
      
      // Set log area: shows last sets and log button
      const setLogDiv = document.createElement('div');
      setLogDiv.className = 'set-log';
      const historySpan = document.createElement('span');
      historySpan.id = `history-${ex.id}`;
      const lastSets = ex.setsHistory.slice(-3).reverse().join(', ') || 'none';
      historySpan.innerHTML = `<i class="fas fa-history"></i> recent: ${lastSets}`;
      const logBtn = document.createElement('button');
      logBtn.className = 'log-btn';
      logBtn.innerHTML = '<i class="fas fa-check-circle"></i> Log Set';
      logBtn.addEventListener('click', () => {
        // log current reps as a new set
        const repsToLog = ex.currentReps;
        ex.setsHistory.push(repsToLog);
        // update history display (show last 3)
        const recent = ex.setsHistory.slice(-3).reverse().join(', ');
        document.getElementById(`history-${ex.id}`).innerHTML = `<i class="fas fa-history"></i> recent: ${recent}`;
        // update total summary
        updateSummaryUI();
        // add small animation or optional confetti effect?
        logBtn.style.transform = 'scale(0.95)';
        setTimeout(() => { logBtn.style.transform = ''; }, 100);
        // optional: store data in localStorage? keep for session persistence
        saveToLocalStorage();
      });
      setLogDiv.appendChild(historySpan);
      setLogDiv.appendChild(logBtn);
      
      card.appendChild(nameDiv);
      card.appendChild(repControl);
      card.appendChild(setLogDiv);
      container.appendChild(card);
    });
    updateSummaryUI();
  }
  
  // reset all data (sets and current reps reset to default)
  function resetAllTrainingData() {
    // reset to initial data: setsHistory arrays as original
    exercises = [
      { id: 0, name: "Barbell Bench Press", icon: "fas fa-chest", currentReps: 8, setsHistory: [8, 7, 8] },
      { id: 1, name: "Pull-ups (Weighted)", icon: "fas fa-hand-peace", currentReps: 6, setsHistory: [6, 5, 6] },
      { id: 2, name: "Leg Press", icon: "fas fa-walking", currentReps: 12, setsHistory: [12, 12, 10] },
      { id: 3, name: "Dumbbell Shoulder Press", icon: "fas fa-fist-raised", currentReps: 10, setsHistory: [10, 9, 8] }
    ];
    renderExercises();  // re-render fresh
    updateSummaryUI();
    saveToLocalStorage();
  }
  
  // localStorage persistence for user progress
  function saveToLocalStorage() {
    const dataToStore = exercises.map(ex => ({
      id: ex.id,
      name: ex.name,
      icon: ex.icon,
      currentReps: ex.cur
