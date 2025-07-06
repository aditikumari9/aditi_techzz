<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Student ERP Portal</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(to right, #e0eafc, #cfdef3);
      display: flex;
      height: 100vh;
      overflow: hidden;
    }
    aside {
      width: 230px;
      background-color: #2f3c7e;
      color: white;
      display: flex;
      flex-direction: column;
      padding-top: 40px;
    }
    aside h2 {
      text-align: center;
      margin-bottom: 30px;
      font-size: 20px;
      font-weight: 600;
    }
    aside button {
      background: none;
      border: none;
      color: white;
      text-align: left;
      padding: 15px 20px;
      font-size: 16px;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    aside button:hover {
      background-color: #3e4c92;
    }
    main {
      flex: 1;
      padding: 25px;
      overflow-y: auto;
    }
    header {
      background: #364f6b;
      color: white;
      padding: 20px;
      font-size: 24px;
      text-align: center;
      border-radius: 10px;
      margin-bottom: 20px;
    }
    .card {
      background: white;
      padding: 20px;
      margin-bottom: 20px;
      border-radius: 12px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.1);
    }
    .tab {
      display: none;
    }
    .tab.active {
      display: block;
    }
    .alert {
      color: #d32f2f;
      font-weight: bold;
    }
    .badge {
      padding: 4px 10px;
      font-size: 12px;
      background-color: #f50057;
      color: white;
      border-radius: 10px;
      margin-left: 10px;
    }
    .progress-bar {
      background-color: #eee;
      border-radius: 20px;
      height: 18px;
      margin-bottom: 10px;
    }
    .progress {
      height: 100%;
      border-radius: 20px;
      background: linear-gradient(90deg, #36d1dc, #5b86e5);
      width: 0;
      animation: fillProgress 2s ease forwards;
    }
    @keyframes fillProgress {
      to {
        width: var(--width);
      }
    }
    .clock {
      float: right;
      font-size: 16px;
      color: #ffeb3b;
    }
    ul {
      padding-left: 20px;
    }
    li {
      margin-bottom: 8px;
    }
  </style>
</head>
<body>
  <aside>
    <h2>Student Portal</h2>
    <button onclick="showTab('dashboard')">🏠 Dashboard</button>
    <button onclick="showTab('alerts')">🚨 Alerts</button>
    <button onclick="showTab('internship')">🎓 Internships</button>
    <button onclick="showTab('placements')">💼 Placements</button>
    <button onclick="showTab('analytics')">📊 Performance</button>
  </aside>

  <main>
    <header>Welcome to Student ERP <span class="clock" id="clock"></span></header>

    <div id="dashboard" class="tab active">
      <div class="card">
        <h3>Hello, Student!</h3>
        <p>This is your smart dashboard. Use the menu to explore your academic and career details.</p>
      </div>
    </div>

    <div id="alerts" class="tab">
      <div class="card">
        <h3>Low Attendance <span class="badge">Critical</span></h3>
        <p class="alert">⚠️ Less than 75% attendance in: Math, Java</p>
      </div>
      <div class="card">
        <h3>Assignments <span class="badge">2 Due</span></h3>
        <ul>
          <li>Java OOP Project - Due: 10th July</li>
          <li>Database Report - Due: 12th July</li>
        </ul>
      </div>
    </div>

    <div id="internship" class="tab">
      <div class="card">
        <h3>Internship Status</h3>
        <ul>
          <li>TCS - <span class="badge">Applied</span></li>
          <li>Infosys - <span class="badge" style="background:#4caf50;">Interview Scheduled</span></li>
        </ul>
      </div>
    </div>

    <div id="placements" class="tab">
      <div class="card">
        <h3>Placement Tracker</h3>
        <ul>
          <li>Wipro Drive - 15th July <span class="badge">Upcoming</span></li>
          <li>Amazon Coding Round - 18th July <span class="badge" style="background:#4caf50;">In Prep</span></li>
        </ul>
      </div>
    </div>

    <div id="analytics" class="tab">
      <div class="card">
        <h3>Performance Overview</h3>
        <p>CGPA: 8.3</p>
        <p>Java: 85%</p>
        <div class="progress-bar"><div class="progress" style="--width: 85%;"></div></div>
        <p>Maths: 74%</p>
        <div class="progress-bar"><div class="progress" style="--width: 74%; background: orange;"></div></div>
        <p>OS: 92%</p>
        <div class="progress-bar"><div class="progress" style="--width: 92%;"></div></div>
      </div>
    </div>
  </main>

  <script>
    function showTab(id) {
      document.querySelectorAll('.tab').forEach(tab => tab.classList.remove('active'));
      document.getElementById(id).classList.add('active');
    }

    function updateClock() {
      const now = new Date();
      document.getElementById('clock').textContent = now.toLocaleTimeString();
    }
    setInterval(updateClock, 1000);
    updateClock();
  </script>
</body>
</html>
