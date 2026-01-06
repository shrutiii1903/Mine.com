# Mine.com
<!--
Mine App - Single-file static website (index.html)

This is a fully functional, responsive landing page for the Mine app — your cognitive operating system to reduce decision fatigue and boost productivity.

Instructions:
1. Create a GitHub repo named `mine-app`.
2. Place this file as `index.html` in the root.
3. Enable GitHub Pages from the `main` branch (root). Site will be live at https://<username>.github.io/mine-app/
4. Replace placeholder logos, screenshots, and URLs as needed.

Quick Git commands:
  git init
  git add index.html
  git commit -m "Initial Mine App landing page"
  git branch -M main
  git remote add origin git@github.com:<your-username>/mine-app.git
  git push -u origin main

--><!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mine — Take Control of Your Day</title>
  <meta name="description" content="Mine turns your high-level goals into 3 prioritized daily tasks. Reduce decision fatigue, build routines, and regain focus without willpower.">
  <link rel="icon" href="data:;base64,iVBORw0KGgo=" />
  <style>
    body{margin:0;font-family:Arial,sans-serif;background:#0f172a;color:#e6eef8}
    .container{max-width:1100px;margin:0 auto;padding:24px}
    header{display:flex;justify-content:space-between;align-items:center;margin-bottom:32px}
    .logo{font-weight:700;font-size:24px;color:white}
    nav a{color:#94a3b8;text-decoration:none;margin-left:20px}
    .hero{display:flex;flex-wrap:wrap;gap:24px;align-items:center;margin-bottom:36px}
    .hero-text{flex:1;min-width:280px}
    h1{font-size:36px;margin-bottom:16px;color:white}
    p{color:#94a3b8;margin-bottom:18px;line-height:1.5}
    .btn{padding:12px 20px;border-radius:10px;border:none;font-weight:600;cursor:pointer}
    .btn-primary{background:#7c3aed;color:white}
    .btn-ghost{background:transparent;border:1px solid #94a3b8;color:#94a3b8}
    .features{display:flex;flex-wrap:wrap;gap:14px;margin-top:24px}
    .feature{flex:1;min-width:200px;background:rgba(255,255,255,0.03);padding:16px;border-radius:12px}
    footer{text-align:center;margin-top:40px;color:#94a3b8;font-size:13px}
    input,select,textarea{width:100%;padding:10px;border-radius:8px;margin-top:6px;border:1px solid rgba(255,255,255,0.1);background:transparent;color:white}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">Mine</div>
      <nav>
        <a href="#features">Features</a>
        <a href="#demo">Demo</a>
        <a href="#pricing">Pricing</a>
      </nav>
    </header><section class="hero">
  <div class="hero-text">
    <h1>Your day, decided.<br><span style="color:#7c3aed">Three actions. Zero overload.</span></h1>
    <p>Mine translates your high-level goals into three prioritized actions daily, scheduled directly into your calendar. Reduce decision fatigue, build routines, and regain focus without relying on willpower.</p>
    <div style="display:flex;gap:12px;margin-top:12px">
      <button class="btn btn-primary" onclick="document.getElementById('demo').scrollIntoView({behavior:'smooth'})">Try Demo</button>
      <a class="btn btn-ghost" href="#pricing">Pricing</a>
    </div>
  </div>

  <aside style="flex:1;min-width:280px">
    <div style="background:rgba(255,255,255,0.03);padding:16px;border-radius:12px">
      <h3>Interactive Demo</h3>
      <label for="goal">Add a goal</label>
      <input id="goal" placeholder="e.g. Finish thesis chapter 2">
      <button class="btn btn-ghost" style="margin-top:8px;width:100%" onclick="addGoal()">Save Goal</button>

      <div style="margin-top:12px">
        <label for="taskText">Add a micro-task</label>
        <input id="taskText" placeholder="e.g. Write 300 words">
        <button class="btn btn-primary" style="margin-top:8px;width:100%" onclick="addTask()">Add Task</button>
      </div>

      <div style="margin-top:12px">
        <h4>Tasks</h4>
        <div id="tasksList"></div>
        <button class="btn btn-ghost" onclick="generateTop3()">Generate Top 3</button>
      </div>

      <div style="margin-top:12px">
        <h4>Today's Top 3</h4>
        <div id="top3"></div>
      </div>

      <div style="margin-top:12px">
        <input id="email" placeholder="you@domain.com">
        <button class="btn btn-primary" style="margin-top:8px;width:100%" onclick="joinWaitlist()">Join Waitlist</button>
      </div>
    </div>
  </aside>
</section>

<section class="features" id="features">
  <div class="feature">
    <h4>Top-3 Daily Planner</h4>
    <p>Focus your executive attention on three clear priorities.</p>
  </div>
  <div class="feature">
    <h4>Context-aware scheduling</h4>
    <p>Schedule tasks when you're most alert using energy check-ins.</p>
  </div>
  <div class="feature">
    <h4>Behavioral scaffolding</h4>
    <p>Gradual fade-out so users internalize routines, not dependencies.</p>
  </div>
</section>

<section id="pricing" style="margin-top:36px">
  <div style="display:flex;gap:12px;flex-wrap:wrap">
    <div style="flex:1;min-width:220px;background:rgba(255,255,255,0.03);padding:16px;border-radius:12px">
      <h4>Early Access</h4>
      <p>₹599 / month</p>
      <ul>
        <li>Top-3 daily planner</li>
        <li>Calendar sync (Google)</li>
        <li>Energy & mood check-ins</li>
      </ul>
      <button class="btn btn-primary" style="width:100%">Subscribe</button>
    </div>
    <div style="flex:1;min-width:220px;background:rgba(255,255,255,0.03);padding:16px;border-radius:12px">
      <h4>Founder Beta</h4>
      <p>Limited seats</p>
      <ul>
        <li>Priority onboarding</li>
        <li>1:1 feedback session</li>
      </ul>
      <button class="btn btn-ghost" style="width:100%">Apply</button>
    </div>
  </div>
</section>

<footer>
  Built for focused humans · Mine · <span id="year"></span>
</footer>

  </div>  <script>
    const STORAGE_KEY='mine_demo_v1';
    function loadState(){const raw=localStorage.getItem(STORAGE_KEY);return raw?JSON.parse(raw):{goals:[],tasks:[],top3:[]};}
    function saveState(s){localStorage.setItem(STORAGE_KEY,JSON.stringify(s));}
    function renderGoals(){const s=loadState();}
    function renderTasks(){const s=loadState();const el=document.getElementById('tasksList');el.innerHTML=s.tasks.map((t,i)=>`<div>${t.text}</div>`).join('');}
    function renderTop3(){const s=loadState();const el=document.getElementById('top3');el.innerHTML=s.top3.map(t=>`<div>${t.text}</div>`).join('');}
    function addGoal(){const v=document.getElementById('goal').value.trim();if(!v)return;const s=loadState();s.goals.push(v);saveState(s);document.getElementById('goal').value='';renderGoals();}
    function addTask(){const t=document.getElementById('taskText').value.trim();if(!t)return;const s=loadState();s.tasks.push({text:t});saveState(s);document.getElementById('taskText').value='';renderTasks();}
    function generateTop3(){const s=loadState();s.top3=s.tasks.slice(0,3);saveState(s);renderTop3();}
    function joinWaitlist(){const e=document.getElementById('email').value.trim();if(!e)return;alert('Thanks — added to waitlist');}
    document.getElementById('year').textContent=new Date().getFullYear();
    renderGoals();renderTasks();renderTop3();
  </script></body>
</html>    
                        
