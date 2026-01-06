# Mine.com
<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Mine — Cognitive operating system for focused humans</title>
  <meta name="description" content="Mine translates your vague goals into 3 specific, high-impact daily tasks. Reduce decision fatigue, build routines, and get momentum." />
  <meta property="og:title" content="Mine — Cognitive operating system for focused humans" />
  <meta property="og:description" content="Translate vague goals into 3 specific, high-impact daily tasks. Reduce decision fatigue and build momentum." />
  <meta property="og:type" content="website" />
  <meta name="theme-color" content="#0f172a" />
  <link rel="icon" href="data:;base64,iVBORw0KGgo=" />
  <style>
    :root{--bg:#0f172a;--card:#0b1220;--muted:#94a3b8;--accent:#7c3aed;--glass:rgba(255,255,255,0.03)}
    *{box-sizing:border-box}
    html,body{height:100%}
    body{margin:0;font-family:Inter,ui-sans-serif,system-ui,-apple-system,'Segoe UI',Roboto,'Helvetica Neue',Arial;background:linear-gradient(180deg,#071022 0%, #071b2e 60%);color:#e6eef8;-webkit-font-smoothing:antialiased}
    .container{max-width:1100px;margin:32px auto;padding:24px}
    header{display:flex;align-items:center;justify-content:space-between;margin-bottom:28px}
    .logo{display:flex;gap:12px;align-items:center}
    .logo-mark{width:44px;height:44px;border-radius:10px;background:linear-gradient(135deg,var(--accent),#06b6d4);display:flex;align-items:center;justify-content:center;font-weight:700;color:white}
    nav a{color:var(--muted);text-decoration:none;margin-left:18px}
    .hero{display:grid;grid-template-columns:1.1fr .9fr;gap:28px;align-items:center}
    h1{font-size:34px;margin:0 0 12px 0}
    p.lead{color:var(--muted);margin:0 0 18px 0;line-height:1.5}
    .cta{display:flex;gap:12px}
    .btn{padding:12px 18px;border-radius:10px;border:0;cursor:pointer;font-weight:600}
    .btn-primary{background:linear-gradient(90deg,var(--accent),#06b6d4);color:white}
    .btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--muted)}
    .card{background:var(--card);padding:18px;border-radius:14px;box-shadow:0 6px 20px rgba(2,6,23,0.6)}
    .features{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:18px}
    .feature{padding:12px;border-radius:10px;background:var(--glass);}
    .muted{color:var(--muted)}
    .small{font-size:13px}
    /* Demo app UI */
    .demo{padding:18px;border-radius:12px;background:linear-gradient(180deg,#041226, #04203a);}
    label{display:block;margin-bottom:8px;font-size:14px}
    input,textarea,select{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:inherit}
    .row{display:flex;gap:10px}
    .tasks{margin-top:12px}
    .task{display:flex;align-items:center;justify-content:space-between;padding:10px;border-radius:8px;margin-bottom:8px;background:rgba(255,255,255,0.02)}
    .task .meta{color:var(--muted);font-size:13px}
    footer{margin-top:36px;padding:20px;color:var(--muted);text-align:center;font-size:13px}
    @media (max-width:880px){.hero{grid-template-columns:1fr;}.features{grid-template-columns:1fr}.logo-mark{width:40px;height:40px}.container{padding:16px}}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">
        <div class="logo-mark">M</div>
        <div>
          <div style="font-weight:700">Mine</div>
          <div class="small muted">Cognitive operating system for focused humans</div>
        </div>
      </div>
      <nav>
        <a href="#features">Features</a>
        <a href="#demo">Demo</a>
        <a href="#pricing">Pricing</a>
      </nav>
    </header><section class="hero">
  <div>
    <h1>Your day, decided.<br/><span style="color:var(--accent)">Three actions. Zero overload.</span></h1>
    <p class="lead">Mine translates your high-level goals into three prioritized actions each day, scheduled into your calendar. Reduce decision fatigue, build routines, and regain focus—without willpower.</p>
    <div class="cta">
      <button class="btn btn-primary" onclick="document.getElementById('demo').scrollIntoView({behavior:'smooth'})">Try the demo</button>
      <a class="btn btn-ghost" href="#pricing">Pricing</a>
    </div>

    <div class="card" style="margin-top:18px">
      <div style="display:flex;align-items:center;justify-content:space-between">
        <div>
          <div style="font-weight:700">Target users</div>
          <div class="muted small">Students · Professionals · Early-stage creators</div>
        </div>
        <div style="text-align:right">
          <div style="font-weight:700">₹599</div>
          <div class="small muted">monthly (early access)</div>
        </div>
      </div>
    </div>

    <div class="features" id="features">
      <div class="feature card">
        <div style="font-weight:700">Top-3 Daily Planner</div>
        <div class="muted small">Focus your executive attention on three clear priorities.</div>
      </div>
      <div class="feature card">
        <div style="font-weight:700">Context-aware scheduling</div>
        <div class="muted small">Schedule tasks when you're most alert using energy check-ins.</div>
      </div>
      <div class="feature card">
        <div style="font-weight:700">Behavioral scaffolding</div>
        <div class="muted small">Gradual fade-out so users internalize routines, not dependencies.</div>
      </div>
    </div>
  </div>

  <aside>
    <div class="card demo" id="demo">
      <div style="font-weight:700;margin-bottom:10px">Interactive demo</div>
      <div class="small muted">This client-side demo uses localStorage. It shows how Mine turns goals into 3 daily tasks.</div>

      <label for="goal">Add a long-term goal</label>
      <input id="goal" placeholder="e.g. Finish thesis chapter 2" />
      <button class="btn btn-ghost" style="margin-top:8px;width:100%" onclick="addGoal()">Save Goal</button>

      <div style="margin-top:12px">
        <label for="taskText">Add a micro-task</label>
        <div class="row">
          <input id="taskText" placeholder="e.g. Write 300 words" />
          <select id="taskGoal" style="width:160px">
            <option value="">(choose goal)</option>
          </select>
        </div>
        <button class="btn btn-primary" style="margin-top:8px;width:100%" onclick="addTask()">Add Task</button>
      </div>

      <div class="tasks" style="margin-top:14px">
        <div style="display:flex;justify-content:space-between;align-items:center">
          <div style="font-weight:700">Tasks</div>
          <button class="btn btn-ghost small" onclick="generateTop3()">Generate Top 3</button>
        </div>
        <div id="tasksList" style="margin-top:8px"></div>

        <div style="margin-top:14px">
          <div style="font-weight:700">Today's Top 3</div>
          <div id="top3" style="margin-top:8px"></div>
        </div>
      </div>

    </div>

    <div class="card" style="margin-top:12px">
      <div style="font-weight:700">Early access</div>
      <div class="muted small">Join the waitlist for early access and feedback sessions.</div>
      <input id="email" placeholder="you@domain.com" style="margin-top:8px" />
      <button class="btn btn-primary" style="margin-top:8px;width:100%" onclick="joinWaitlist()">Join Waitlist</button>
    </div>
  </aside>
</section>

<section style="margin-top:26px">
  <div class="card" id="pricing">
    <h3 style="margin:0 0 8px 0">Pricing</h3>
    <div class="muted small">Simple, founder-friendly pricing during early access.</div>
    <div style="display:flex;gap:12px;margin-top:12px;flex-wrap:wrap">
      <div class="card" style="flex:1;min-width:220px">
        <div style="font-weight:700">Early Access</div>
        <div class="small muted">₹599 / month</div>
        <ul class="muted small">
          <li>Top-3 daily planner</li>
          <li>Calendar sync (Google)</li>
          <li>Energy & mood check-ins</li>
        </ul>
        <button class="btn btn-primary" style="width:100%" onclick="alert('Demo purchase flow - replace with Stripe server code')">Subscribe</button>
      </div>
      <div class="card" style="flex:1;min-width:220px">
        <div style="font-weight:700">Founder</div>
        <div class="small muted">Beta partnership — limited seats</div>
        <ul class="muted small">
          <li>Priority onboarding</li>
          <li>1:1 product feedback session</li>
        </ul>
        <button class="btn btn-ghost" style="width:100%" onclick="alert('Contact founder@mindos.example')">Apply</button>
      </div>
    </div>
  </div>
</section>

<footer>
  Built for focused humans · Mine · <span id="year"></span>
</footer>

  </div>  <script>
    // Small client-side demo logic. All data is stored in localStorage.
    const STORAGE_KEY = 'mindos_demo_v1'
    function loadState(){
      const raw = localStorage.getItem(STORAGE_KEY)
      return raw ? JSON.parse(raw) : {goals:[], tasks:[], top3:[]}
    }
    function saveState(s){ localStorage.setItem(STORAGE_KEY, JSON.stringify(s)) }
    function renderGoals(){
      const s = loadState()
      const sel = document.getElementById('taskGoal')
      sel.innerHTML = '<option value="">(choose goal)</option>' + s.goals.map((g,i)=>`<option value="${i}">${g}</option>`).join('')
    }
    function renderTasks(){
      const s = loadState()
      const el = document.getElementById('tasksList')
      el.innerHTML = s.tasks.map((t,i)=>`<div class="task"><div><div style="font-weight:700">${escapeHtml(t.text)}</div><div class="meta">${escapeHtml(t.goal||'No goal')}</div></div><div style="display:flex;gap:8px"><button class="btn btn-ghost small" onclick="markDone(${i})">Done</button><button class="btn btn-ghost small" onclick="deleteTask(${i})">Delete</button></div></div>`).join('')
    }
    function renderTop3(){
      const s = loadState()
      const el = document.getElementById('top3')
      if(!s.top3 || s.top3.length===0){ el.innerHTML = '<div class="muted small">No top-3 yet. Click Generate Top 3.</div>'; return }
      el.innerHTML = s.top3.map((t,i)=>`<div class="task"><div><div style="font-weight:700">${escapeHtml(t.text)}</div><div class="meta">${escapeHtml(t.goal||'No goal')}</div></div><div style="display:flex;gap:8px"><button class="btn btn-ghost small" onclick="addToCalendar(${i})">Block</button></div></div>`).join('')
    }
    function addGoal(){
      const v = document.getElementById('goal').value.trim(); if(!v) return alert('Enter a goal')
      const s = loadState(); s.goals.push(v); saveState(s); document.getElementById('goal').value=''; renderGoals()
    }
    function addTask(){
      const t = document.getElementById('taskText').value.trim(); const gIdx = document.getElementById('taskGoal').value
      if(!t) return alert('Enter a task')
      const s = loadState(); s.tasks.push({text:t,goal:gIdx? s.goals[gIdx] : ''}); saveState(s); document.getElementById('taskText').value=''; renderTasks()
    }
    function markDone(i){
      const s = loadState(); s.tasks.splice(i,1); saveState(s); renderTasks()
    }
    function deleteTask(i){ const s = loadState(); s.tasks.splice(i,1); saveState(s); renderTasks() }
    function generateTop3(){
      const s = loadState();
      // naive selection: pick first 3 tasks; in real product this uses priority model
      s.top3 = s.tasks.slice(0,3)
      saveState(s); renderTop3()
    }
    function addToCalendar(i){
      const s = loadState(); const t = s.top3[i];
      if(!t) return
      // open Google Calendar event creation (user must be logged in)
      const start = new Date(); start.setHours(start.getHours()+1)
      const end = new Date(start.getTime()+25*60000) // 25 minute block
      const fmt = d=>encodeURIComponent(d.toISOString().replace(/-|:|\.\d+/g,''))
      const url = `https://calendar.google.com/calendar/u/0/r/eventedit?text=${encodeURIComponent(t.text)}&dates=${fmt(start)}/${fmt(end)}&details=${encodeURIComponent('From Mine demo')}`
      window.open(url,'_blank')
    }
    function joinWaitlist(){
      const e = document.getElementById('email').value.trim(); if(!e) return alert('Enter email')
      // demo: store email locally. Replace with API call to save to mailing list.
      const s = loadState(); s.waitlist = s.waitlist || []; s.waitlist.push(e); saveState(s); alert('Thanks — you are on the demo waitlist')
    }
    function escapeHtml(s){ return (s+'').replace(/[&<>\"]/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c])) }

    // initialization
    document.getElementById('year').textContent = new Date().getFullYear()
    renderGoals(); renderTasks(); renderTop3();
  </script></body>
</html>
