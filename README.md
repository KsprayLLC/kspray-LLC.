[kspray_readme_app.html](https://github.com/user-attachments/files/26101273/kspray_readme_app.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Kspray – README</title>
<style>
  :root {
    --bg: #0d0f14;
    --bg2: #13161e;
    --bg3: #1a1e28;
    --border: rgba(255,255,255,0.07);
    --text: #e8eaf0;
    --muted: #8b90a0;
    --accent: #6c63ff;
    --accent2: #a78bfa;
    --green: #34d399;
    --amber: #fbbf24;
    --red: #f87171;
    --blue: #60a5fa;
    --teal: #2dd4bf;
    --radius: 12px;
    --mono: 'Courier New', monospace;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { background: var(--bg); color: var(--text); font-family: system-ui, -apple-system, sans-serif; font-size: 15px; line-height: 1.7; }

  /* Layout */
  .sidebar { position: fixed; top: 0; left: 0; width: 240px; height: 100vh; background: var(--bg2); border-right: 1px solid var(--border); padding: 28px 0; overflow-y: auto; z-index: 10; }
  .main { margin-left: 240px; padding: 48px 56px; max-width: 900px; }

  /* Sidebar */
  .sidebar-logo { padding: 0 24px 24px; border-bottom: 1px solid var(--border); margin-bottom: 16px; }
  .sidebar-logo .pill { display: inline-block; background: linear-gradient(135deg, var(--accent), var(--accent2)); color: #fff; font-weight: 700; font-size: 18px; padding: 6px 14px; border-radius: 8px; letter-spacing: .5px; }
  .sidebar-logo p { font-size: 11px; color: var(--muted); margin-top: 6px; }
  .nav-section { padding: 6px 24px; font-size: 10px; font-weight: 700; text-transform: uppercase; letter-spacing: 1.2px; color: var(--muted); margin-top: 12px; }
  .nav-item { display: block; padding: 7px 24px; font-size: 13px; color: var(--muted); text-decoration: none; transition: all .15s; border-left: 2px solid transparent; }
  .nav-item:hover, .nav-item.active { color: var(--text); background: rgba(108,99,255,.08); border-left-color: var(--accent); }

  /* Hero */
  .hero { background: var(--bg2); border: 1px solid var(--border); border-radius: var(--radius); padding: 40px; margin-bottom: 40px; position: relative; overflow: hidden; }
  .hero::before { content: ''; position: absolute; top: -60px; right: -60px; width: 220px; height: 220px; background: radial-gradient(circle, rgba(108,99,255,.15) 0%, transparent 70%); pointer-events: none; }
  .hero-badge { display: inline-flex; align-items: center; gap: 6px; background: rgba(108,99,255,.15); border: 1px solid rgba(108,99,255,.3); color: var(--accent2); font-size: 12px; font-weight: 600; padding: 4px 12px; border-radius: 20px; margin-bottom: 16px; }
  .hero h1 { font-size: 36px; font-weight: 800; letter-spacing: -1px; background: linear-gradient(135deg, #fff 40%, var(--accent2)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
  .hero p { color: var(--muted); margin-top: 10px; font-size: 15px; max-width: 520px; }
  .badges { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 20px; }
  .badge { font-size: 11px; font-weight: 600; padding: 4px 10px; border-radius: 6px; }
  .badge.green { background: rgba(52,211,153,.12); color: var(--green); border: 1px solid rgba(52,211,153,.25); }
  .badge.blue  { background: rgba(96,165,250,.12); color: var(--blue);  border: 1px solid rgba(96,165,250,.25); }
  .badge.amber { background: rgba(251,191,36,.12); color: var(--amber); border: 1px solid rgba(251,191,36,.25); }
  .badge.purple{ background: rgba(167,139,250,.12);color: var(--accent2);border: 1px solid rgba(167,139,250,.25); }

  /* Sections */
  section { margin-bottom: 48px; scroll-margin-top: 32px; }
  .section-title { font-size: 20px; font-weight: 700; color: #fff; margin-bottom: 20px; display: flex; align-items: center; gap: 10px; padding-bottom: 10px; border-bottom: 1px solid var(--border); }
  .section-title .icon { font-size: 20px; }

  /* Feature grid */
  .feature-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 14px; }
  .feature-card { background: var(--bg2); border: 1px solid var(--border); border-radius: 10px; padding: 18px; transition: border-color .2s, transform .2s; }
  .feature-card:hover { border-color: rgba(108,99,255,.4); transform: translateY(-2px); }
  .feature-card .f-icon { font-size: 22px; margin-bottom: 10px; }
  .feature-card h4 { font-size: 13px; font-weight: 700; color: #fff; margin-bottom: 4px; }
  .feature-card p { font-size: 12px; color: var(--muted); line-height: 1.5; }

  /* Steps */
  .steps { display: flex; flex-direction: column; gap: 12px; }
  .step { display: flex; gap: 16px; align-items: flex-start; background: var(--bg2); border: 1px solid var(--border); border-radius: 10px; padding: 18px 20px; }
  .step-num { min-width: 28px; height: 28px; border-radius: 50%; background: linear-gradient(135deg, var(--accent), var(--accent2)); color: #fff; font-size: 12px; font-weight: 800; display: flex; align-items: center; justify-content: center; margin-top: 1px; }
  .step-body h4 { font-size: 14px; font-weight: 700; color: #fff; margin-bottom: 3px; }
  .step-body p { font-size: 13px; color: var(--muted); }

  /* Code blocks */
  .code-block { background: #0a0c10; border: 1px solid var(--border); border-radius: 10px; overflow: hidden; margin: 16px 0; }
  .code-header { display: flex; align-items: center; justify-content: space-between; padding: 10px 16px; background: var(--bg3); border-bottom: 1px solid var(--border); }
  .code-header span { font-size: 12px; color: var(--muted); font-family: var(--mono); }
  .copy-btn { font-size: 11px; color: var(--muted); background: rgba(255,255,255,.05); border: 1px solid var(--border); padding: 3px 10px; border-radius: 5px; cursor: pointer; transition: all .15s; }
  .copy-btn:hover { color: var(--text); border-color: rgba(255,255,255,.2); }
  .copy-btn.copied { color: var(--green); border-color: rgba(52,211,153,.3); }
  pre { padding: 18px 20px; font-size: 13px; font-family: var(--mono); line-height: 1.75; overflow-x: auto; color: #c9d1d9; }
  .kw { color: var(--accent2); } .str { color: var(--green); } .cm { color: #555; } .vr { color: var(--blue); } .nm { color: var(--amber); }

  /* File tree */
  .tree { background: #0a0c10; border: 1px solid var(--border); border-radius: 10px; padding: 20px 24px; font-family: var(--mono); font-size: 13px; line-height: 2; }
  .tree .dir { color: var(--blue); font-weight: 600; }
  .tree .file { color: var(--muted); }
  .tree .comment { color: #555; }

  /* Compliance cards */
  .compliance-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .c-card { background: var(--bg2); border: 1px solid var(--border); border-radius: 10px; padding: 18px 20px; display: flex; gap: 14px; }
  .c-card .c-icon { font-size: 24px; }
  .c-card h4 { font-size: 13px; font-weight: 700; color: #fff; margin-bottom: 4px; }
  .c-card p { font-size: 12px; color: var(--muted); line-height: 1.5; }

  /* Env table */
  .env-table { width: 100%; border-collapse: collapse; font-size: 13px; }
  .env-table th { text-align: left; padding: 10px 14px; font-size: 11px; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--muted); border-bottom: 1px solid var(--border); }
  .env-table td { padding: 11px 14px; border-bottom: 1px solid rgba(255,255,255,.04); vertical-align: top; }
  .env-table tr:last-child td { border-bottom: none; }
  .env-table td:first-child { font-family: var(--mono); color: var(--blue); font-size: 12px; }
  .env-table td:last-child { color: var(--muted); }

  /* Warning */
  .warn { background: rgba(251,191,36,.06); border: 1px solid rgba(251,191,36,.2); border-radius: 8px; padding: 12px 16px; font-size: 13px; color: var(--amber); margin: 12px 0; display: flex; gap: 10px; align-items: flex-start; }

  /* Contact */
  .contact-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 12px; }
  .contact-card { background: var(--bg2); border: 1px solid var(--border); border-radius: 10px; padding: 16px 18px; }
  .contact-card h4 { font-size: 12px; font-weight: 700; color: var(--muted); text-transform: uppercase; letter-spacing: .8px; margin-bottom: 6px; }
  .contact-card a { color: var(--accent2); font-size: 13px; text-decoration: none; }
  .contact-card a:hover { text-decoration: underline; }

  /* Disclaimer */
  .disclaimer { background: rgba(248,113,113,.05); border: 1px solid rgba(248,113,113,.15); border-radius: 10px; padding: 16px 20px; font-size: 13px; color: #fca5a5; line-height: 1.6; margin-top: 48px; }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 5px; height: 5px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 4px; }

  @media(max-width:768px) {
    .sidebar { display: none; }
    .main { margin-left: 0; padding: 24px 20px; }
    .compliance-grid, .contact-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- Sidebar -->
<nav class="sidebar">
  <div class="sidebar-logo">
    <div class="pill">💊 Kspray</div>
    <p>Patient App · v1.0.0</p>
  </div>
  <div class="nav-section">Overview</div>
  <a class="nav-item active" href="#features">Features</a>
  <a class="nav-item" href="#getting-started">Getting Started</a>
  <div class="nav-section">Usage</div>
  <a class="nav-item" href="#patient-flow">Patient Flow</a>
  <a class="nav-item" href="#env">Environment Vars</a>
  <a class="nav-item" href="#structure">Project Structure</a>
  <div class="nav-section">Compliance</div>
  <a class="nav-item" href="#privacy">Privacy & HIPAA</a>
  <a class="nav-item" href="#contributing">Contributing</a>
  <div class="nav-section">Info</div>
  <a class="nav-item" href="#contact">Contact</a>
</nav>

<!-- Main Content -->
<main class="main">

  <!-- Hero -->
  <div class="hero">
    <div class="hero-badge">💊 Pharma Telehealth Platform</div>
    <h1>Kspray</h1>
    <p>Telehealth-powered ketamine nasal spray therapy — built for patients, by clinicians. From intake to prescription to progress tracking, all in one place.</p>
    <div class="badges">
      <span class="badge green">✓ HIPAA Compliant</span>
      <span class="badge blue">React + TypeScript</span>
      <span class="badge amber">⚕ Clinician-Reviewed</span>
      <span class="badge purple">AES-256 Encrypted</span>
    </div>
  </div>

  <!-- Features -->
  <section id="features">
    <div class="section-title"><span class="icon">🌟</span> Features</div>
    <div class="feature-grid">
      <div class="feature-card"><div class="f-icon">🧾</div><h4>Patient Onboarding</h4><p>Simple eligibility screening and secure account creation.</p></div>
      <div class="feature-card"><div class="f-icon">📋</div><h4>Clinical Intake</h4><p>Encrypted health questionnaires reviewed by licensed providers.</p></div>
      <div class="feature-card"><div class="f-icon">🎥</div><h4>Telehealth Consults</h4><p>Live video visits with prescribing clinicians.</p></div>
      <div class="feature-card"><div class="f-icon">💊</div><h4>Prescription Management</h4><p>Track and manage your ketamine nasal spray prescription end-to-end.</p></div>
      <div class="feature-card"><div class="f-icon">🗓️</div><h4>Treatment Scheduling</h4><p>Guided session reminders and personalized dosing schedules.</p></div>
      <div class="feature-card"><div class="f-icon">💬</div><h4>Secure Messaging</h4><p>Communicate directly with your care team, privately.</p></div>
      <div class="feature-card"><div class="f-icon">📈</div><h4>Progress Tracking</h4><p>Log mood, symptoms, and treatment responses over time.</p></div>
      <div class="feature-card"><div class="f-icon">🔒</div><h4>HIPAA-Compliant</h4><p>All data encrypted and handled per federal health privacy standards.</p></div>
    </div>
  </section>

  <!-- Getting Started -->
  <section id="getting-started">
    <div class="section-title"><span class="icon">🚀</span> Getting Started</div>

    <p style="color:var(--muted);margin-bottom:16px">Prerequisites: Node.js v18+, npm v9+ or Yarn, and a modern browser.</p>

    <div class="code-block">
      <div class="code-header"><span>bash — clone & install</span><button class="copy-btn" onclick="copyCode(this)">Copy</button></div>
      <pre><span class="cm"># Clone the repository</span>
<span class="kw">git</span> clone https://github.com/your-org/kspray.git

<span class="cm"># Navigate into the project</span>
<span class="kw">cd</span> kspray

<span class="cm"># Install dependencies</span>
<span class="kw">npm</span> install</pre>
    </div>

    <div class="code-block">
      <div class="code-header"><span>bash — run</span><button class="copy-btn" onclick="copyCode(this)">Copy</button></div>
      <pre><span class="kw">npm</span> run dev       <span class="cm"># Development server → http://localhost:5173</span>
<span class="kw">npm</span> run build     <span class="cm"># Production build</span>
<span class="kw">npm</span> run preview   <span class="cm"># Preview production build</span>
<span class="kw">npm</span> run test      <span class="cm"># Run test suite</span>
<span class="kw">npm</span> run lint      <span class="cm"># Lint source files</span></pre>
    </div>
  </section>

  <!-- Env Vars -->
  <section id="env">
    <div class="section-title"><span class="icon">⚙️</span> Environment Variables</div>
    <div class="warn">⚠️ Never commit your <code>.env</code> file. Copy from <code>.env.example</code> and fill in your values.</div>
    <div class="code-block">
      <div class="code-header"><span>.env</span><button class="copy-btn" onclick="copyCode(this)">Copy</button></div>
      <pre><span class="vr">VITE_API_BASE_URL</span>=<span class="str">https://api.kspray.com</span>
<span class="vr">VITE_TELEHEALTH_KEY</span>=<span class="str">your_telehealth_api_key</span>
<span class="vr">VITE_ANALYTICS_ID</span>=<span class="str">your_analytics_id</span>
<span class="vr">HIPAA_COMPLIANCE_MODE</span>=<span class="nm">true</span></pre>
    </div>
    <table class="env-table" style="margin-top:16px">
      <thead><tr><th>Variable</th><th>Description</th></tr></thead>
      <tbody>
        <tr><td>VITE_API_BASE_URL</td><td>Base URL for the Kspray backend API</td></tr>
        <tr><td>VITE_TELEHEALTH_KEY</td><td>API key for the video consultation provider</td></tr>
        <tr><td>VITE_ANALYTICS_ID</td><td>Analytics tracking ID (no PHI is ever sent)</td></tr>
        <tr><td>HIPAA_COMPLIANCE_MODE</td><td>Enables strict PHI handling and audit logging</td></tr>
      </tbody>
    </table>
  </section>

  <!-- Patient Flow -->
  <section id="patient-flow">
    <div class="section-title"><span class="icon">🏥</span> Patient Flow</div>
    <div class="steps">
      <div class="step"><div class="step-num">1</div><div class="step-body"><h4>Create an Account</h4><p>Sign up with your email, verify your identity, and complete eligibility screening.</p></div></div>
      <div class="step"><div class="step-num">2</div><div class="step-body"><h4>Complete Intake</h4><p>Answer secure health and symptom questionnaires reviewed by a licensed clinician.</p></div></div>
      <div class="step"><div class="step-num">3</div><div class="step-body"><h4>Schedule a Consultation</h4><p>Book a video visit with a licensed prescribing provider at a time that works for you.</p></div></div>
      <div class="step"><div class="step-num">4</div><div class="step-body"><h4>Receive Your Prescription</h4><p>If approved, your ketamine nasal spray prescription is sent to a compounding pharmacy.</p></div></div>
      <div class="step"><div class="step-num">5</div><div class="step-body"><h4>Begin Treatment</h4><p>Follow your personalized dosing schedule guided by in-app reminders and instructions.</p></div></div>
      <div class="step"><div class="step-num">6</div><div class="step-body"><h4>Track Your Progress</h4><p>Log mood, symptoms, and session notes before and after each treatment.</p></div></div>
    </div>
  </section>

  <!-- Project Structure -->
  <section id="structure">
    <div class="section-title"><span class="icon">🗂️</span> Project Structure</div>
    <div class="tree">
      <div><span class="dir">kspray/</span></div>
      <div>&nbsp;&nbsp;├── <span class="dir">public/</span>               <span class="comment"># Static assets</span></div>
      <div>&nbsp;&nbsp;├── <span class="dir">src/</span></div>
      <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="dir">components/</span>       <span class="comment"># Reusable UI components</span></div>
      <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="dir">pages/</span>            <span class="comment"># Route-level page components</span></div>
      <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="dir">features/</span>         <span class="comment"># Auth, intake, telehealth</span></div>
      <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="dir">hooks/</span>            <span class="comment"># Custom React hooks</span></div>
      <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="dir">services/</span>         <span class="comment"># API service layer</span></div>
      <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="dir">store/</span>            <span class="comment"># Global state (Zustand)</span></div>
      <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;└── <span class="dir">utils/</span>            <span class="comment"># Helper functions</span></div>
      <div>&nbsp;&nbsp;├── <span class="dir">docs/</span>                 <span class="comment"># Developer & compliance docs</span></div>
      <div>&nbsp;&nbsp;├── <span class="file">.env.example</span>          <span class="comment"># Env variable template</span></div>
      <div>&nbsp;&nbsp;├── <span class="file">CONTRIBUTING.md</span></div>
      <div>&nbsp;&nbsp;├── <span class="file">LICENSE</span></div>
      <div>&nbsp;&nbsp;└── <span class="file">README.md</span></div>
    </div>
  </section>

  <!-- Privacy -->
  <section id="privacy">
    <div class="section-title"><span class="icon">🔒</span> Privacy & Compliance</div>
    <div class="compliance-grid">
      <div class="c-card"><div class="c-icon">🛡️</div><div><h4>AES-256 Encryption</h4><p>All patient data is encrypted at rest and in transit. Zero exceptions.</p></div></div>
      <div class="c-card"><div class="c-icon">⚕️</div><div><h4>HIPAA Compliant</h4><p>Built to HIPAA standards with full PHI audit logging and access controls.</p></div></div>
      <div class="c-card"><div class="c-icon">✅</div><div><h4>SOC 2 Type II</h4><p>Infrastructure and processes audited annually against SOC 2 Type II criteria.</p></div></div>
      <div class="c-card"><div class="c-icon">🚫</div><div><h4>No Ad Tracking</h4><p>Zero patient health information is ever shared with advertisers or data brokers.</p></div></div>
    </div>
  </section>

  <!-- Contributing -->
  <section id="contributing">
    <div class="section-title"><span class="icon">🤝</span> Contributing</div>
    <p style="color:var(--muted);margin-bottom:16px">All contributors must complete a HIPAA training acknowledgment before merging to <code style="color:var(--blue)">main</code>. Read <code style="color:var(--blue)">CONTRIBUTING.md</code> before submitting a PR.</p>
    <div class="code-block">
      <div class="code-header"><span>bash</span><button class="copy-btn" onclick="copyCode(this)">Copy</button></div>
      <pre><span class="cm"># Run tests before submitting a PR</span>
<span class="kw">npm</span> run test

<span class="cm"># Lint your code</span>
<span class="kw">npm</span> run lint</pre>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <div class="section-title"><span class="icon">📬</span> Contact & Support</div>
    <div class="contact-grid">
      <div class="contact-card"><h4>Patient Support</h4><a href="mailto:support@kspray.com">support@kspray.com</a></div>
      <div class="contact-card"><h4>Clinical Questions</h4><a href="mailto:care@kspray.com">care@kspray.com</a></div>
      <div class="contact-card"><h4>Engineering</h4><a href="mailto:eng@kspray.com">eng@kspray.com</a></div>
      <div class="contact-card"><h4>Website</h4><a href="https://www.kspray.com" target="_blank">www.kspray.com</a></div>
    </div>
  </section>

  <!-- Disclaimer -->
  <div class="disclaimer">
    ⚕️ <strong>Medical Disclaimer:</strong> Kspray is intended for use only by patients under the care of a licensed prescriber. Ketamine therapy carries risks — please consult your provider with any questions or concerns about your treatment plan.
  </div>

</main>

<script>
  // Copy button
  function copyCode(btn) {
    const pre = btn.closest('.code-block').querySelector('pre');
    navigator.clipboard.writeText(pre.innerText).then(() => {
      btn.textContent = 'Copied!';
      btn.classList.add('copied');
      setTimeout(() => { btn.textContent = 'Copy'; btn.classList.remove('copied'); }, 2000);
    });
  }

  // Active nav highlight on scroll
  const sections = document.querySelectorAll('section[id], div[id]');
  const navItems = document.querySelectorAll('.nav-item');
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        navItems.forEach(n => n.classList.remove('active'));
        const match = document.querySelector(`.nav-item[href="#${e.target.id}"]`);
        if (match) match.classList.add('active');
      }
    });
  }, { threshold: 0.4 });
  sections.forEach(s => obs.observe(s));

  // Smooth scroll for nav
  navItems.forEach(item => {
    item.addEventListener('click', e => {
      e.preventDefault();
      const target = document.querySelector(item.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth' });
    });
  });
</script>
</body>
</html>
