<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="theme-color" content="#111827">
<title>StudyMate UK</title>

<style>
*{box-sizing:border-box}
:root{
  --bg:#f4f7fb;
  --card:#fff;
  --text:#172033;
  --muted:#6b7280;
  --line:#e5e7eb;
  --primary:#172033;
  --soft:#eef2f7;
  --gold:#f2c94c;
  --danger:#ef4444;
}
body.dark{
  --bg:#0d1117;
  --card:#171d27;
  --text:#f7f8fa;
  --muted:#aab2c0;
  --line:#2c3441;
  --primary:#f7f8fa;
  --soft:#252d39;
}
body{
  margin:0;
  background:var(--bg);
  color:var(--text);
  font-family:Inter,Arial,sans-serif;
  transition:.2s;
}
button,input,select{font:inherit}
button{cursor:pointer}

.app{display:flex;min-height:100vh}

.sidebar{
  width:245px;
  background:var(--card);
  border-right:1px solid var(--line);
  padding:20px 14px;
  position:fixed;
  inset:0 auto 0 0;
  z-index:20;
}
.brand{
  font-size:22px;
  font-weight:800;
  padding:10px;
  margin-bottom:20px;
}
.brand span{color:#7180ff}

.nav-btn{
  width:100%;
  text-align:left;
  border:0;
  background:transparent;
  color:var(--text);
  padding:13px 14px;
  border-radius:12px;
  margin:3px 0;
}
.nav-btn.active,.nav-btn:hover{background:var(--soft)}

.main{
  margin-left:245px;
  width:calc(100% - 245px);
  min-height:100vh;
}

.topbar{
  height:70px;
  border-bottom:1px solid var(--line);
  background:var(--card);
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0 24px;
  position:sticky;
  top:0;
  z-index:10;
}

.icon-btn{
  border:0;
  background:var(--soft);
  color:var(--text);
  border-radius:10px;
  padding:10px 13px;
}

.content{
  max-width:1100px;
  margin:auto;
  padding:25px;
}

.page{display:none}
.page.active{display:block}

.hero{
  background:linear-gradient(135deg,#172033,#35415b);
  color:white;
  border-radius:24px;
  padding:30px;
  margin-bottom:18px;
}
.hero h1{font-size:34px;margin:0 0 8px}
.hero p{margin:0;opacity:.85}

.grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:14px;
}

.card{
  background:var(--card);
  border:1px solid var(--line);
  border-radius:18px;
  padding:20px;
  margin-bottom:16px;
}

.stat{text-align:center}
.stat-icon{font-size:27px}
.stat-number{font-size:30px;font-weight:800;margin:6px 0}

.muted{color:var(--muted)}

.row{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:10px;
}

.form-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
}

input,select{
  width:100%;
  padding:12px;
  margin:5px 0;
  border-radius:11px;
  border:1px solid var(--line);
  background:var(--card);
  color:var(--text);
}

.primary{
  background:#172033;
  color:white;
  border:0;
  padding:11px 15px;
  border-radius:10px;
}

.dark .primary{
  background:#f7f8fa;
  color:#111827;
}

.secondary{
  background:var(--soft);
  color:var(--text);
  border:0;
  padding:11px 15px;
  border-radius:10px;
}

.danger{
  background:var(--danger);
  color:white;
  border:0;
  padding:8px 10px;
  border-radius:9px;
}

.task{
  display:flex;
  align-items:center;
  gap:12px;
  padding:14px 0;
  border-bottom:1px solid var(--line);
}
.task:last-child{border-bottom:0}
.check{width:auto!important}
.task-info{flex:1}
.done{text-decoration:line-through;opacity:.5}

.badge{
  display:inline-block;
  background:var(--soft);
  color:var(--text);
  padding:4px 8px;
  border-radius:20px;
  font-size:11px;
  margin-left:5px;
}

.progress-bg{
  height:14px;
  background:var(--soft);
  border-radius:20px;
  overflow:hidden;
}

.progress{
  height:100%;
  width:0;
  background:#172033;
  transition:.3s;
}

.dark .progress{background:#fff}

.timer{
  font-size:72px;
  font-weight:800;
  text-align:center;
  letter-spacing:2px;
}

.center{text-align:center}

.reminder{
  padding:15px 0;
  border-bottom:1px solid var(--line);
}
.reminder:last-child{border:0}

.calendar{
  display:grid;
  grid-template-columns:repeat(7,1fr);
  gap:6px;
}

.day{
  min-height:55px;
  padding:8px;
  background:var(--soft);
  border-radius:9px;
}

.day.today{outline:2px solid #7180ff}

.reminder-dot{
  width:7px;
  height:7px;
  border-radius:50%;
  background:#7180ff;
  display:inline-block;
}

.empty{
  padding:25px;
  text-align:center;
  color:var(--muted);
}

/* PREMIUM */

.premium-page{
  max-width:700px;
  margin:auto;
}

.premium-header{
  background:#111827;
  color:white;
  border-radius:24px;
  padding:28px;
  margin-bottom:20px;
}

.premium-back{
  border:none;
  background:rgba(255,255,255,.12);
  color:white;
  width:42px;
  height:42px;
  border-radius:50%;
  font-size:20px;
}

.premium-logo{
  margin-top:20px;
  font-size:30px;
  font-weight:800;
}

.premium-subtitle{
  margin-top:8px;
  color:#cbd5e1;
}

.premium-card{
  background:linear-gradient(135deg,#fff7d6,#ffffff);
  border-radius:24px;
  padding:22px;
  box-shadow:0 12px 35px rgba(17,24,39,.12);
  border:1px solid #f3e8b0;
  margin-bottom:20px;
}

.premium-badge{
  display:inline-block;
  background:#111827;
  color:#ffd84d;
  padding:7px 12px;
  border-radius:20px;
  font-size:13px;
  font-weight:700;
}

.premium-title{
  margin-top:14px;
  font-size:27px;
  font-weight:800;
}

.premium-description{
  margin-top:7px;
  color:#6b7280;
  line-height:1.5;
}

.feature{
  display:flex;
  align-items:center;
  background:var(--card);
  padding:15px;
  margin-bottom:10px;
  border-radius:16px;
  border:1px solid var(--line);
}

.feature-icon{
  width:43px;
  height:43px;
  display:flex;
  align-items:center;
  justify-content:center;
  background:var(--soft);
  border-radius:13px;
  font-size:21px;
}

.feature-text{margin-left:13px}
.feature-title{font-weight:700}
.feature-description{
  color:var(--muted);
  font-size:13px;
  margin-top:3px;
}

.plan{
  background:var(--card);
  border:2px solid transparent;
  border-radius:20px;
  padding:18px;
  margin-bottom:12px;
  cursor:pointer;
  transition:.2s;
}

.plan.selected{
  border-color:#111827;
  box-shadow:0 7px 20px rgba(17,24,39,.10);
}

.dark .plan.selected{border-color:#fff}

.plan-header{
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.plan-name{
  font-weight:800;
  font-size:17px;
}

.price{
  font-size:22px;
  font-weight:800;
}

.period{
  color:var(--muted);
  font-size:13px;
}

.save{
  display:inline-block;
  margin-top:7px;
  background:#dcfce7;
  color:#166534;
  padding:5px 9px;
  border-radius:10px;
  font-size:12px;
  font-weight:700;
}

.subscribe{
  width:100%;
  border:none;
  border-radius:16px;
  padding:17px;
  background:#111827;
  color:white;
  font-size:17px;
  font-weight:800;
  cursor:pointer;
  margin-top:8px;
}

.restore{
  display:block;
  margin:10px auto;
  border:none;
  background:transparent;
  color:var(--muted);
  font-size:14px;
  padding:10px;
  cursor:pointer;
}

.premium-status{
  padding:15px;
  background:#dcfce7;
  color:#166534;
  border-radius:14px;
  margin-bottom:15px;
  font-weight:700;
}

.dark .premium-status{
  background:#143522;
  color:#86efac;
}

.premium-footer{
  text-align:center;
  color:var(--muted);
  font-size:12px;
  padding:20px;
  line-height:1.5;
}

.mobile-menu{display:none}

@media(max-width:900px){
  .grid{grid-template-columns:repeat(2,1fr)}
}

@media(max-width:700px){
  .sidebar{
    transform:translateX(-100%);
    transition:.2s;
  }

  .sidebar.open{transform:translateX(0)}

  .main{
    margin-left:0;
    width:100%;
  }

  .mobile-menu{display:block}

  .content{padding:14px}

  .form-grid{grid-template-columns:1fr}

  .grid{grid-template-columns:1fr 1fr}

  .hero h1{font-size:27px}

  .timer{font-size:54px}
}

@media(max-width:450px){
  .grid{grid-template-columns:1fr}
}
</style>
</head>

<body>

<div class="app">

<aside class="sidebar" id="sidebar">

  <div class="brand">
    📚 Study<span>Mate</span>
  </div>

  <button class="nav-btn active" data-page="dashboard">🏠 Dashboard</button>
  <button class="nav-btn" data-page="tasks">📝 Tasks</button>
  <button class="nav-btn" data-page="calendar">📅 Calendar</button>
  <button class="nav-btn" data-page="reminders">🔔 Reminders</button>
  <button class="nav-btn" data-page="focus">⏱️ Focus</button>
  <button class="nav-btn" data-page="goals">🎯 Goals</button>
  <button class="nav-btn" data-page="statistics">📊 Statistics</button>
  <button class="nav-btn" data-page="premium">⭐ Premium</button>
  <button class="nav-btn" data-page="profile">👤 Profile</button>
  <button class="nav-btn" data-page="settings">⚙️ Settings</button>

</aside>

<section class="main">

<header class="topbar">

  <button class="icon-btn mobile-menu" onclick="toggleMenu()">☰</button>

  <strong id="topTitle">Dashboard</strong>

  <button class="icon-btn" onclick="toggleTheme()">🌙</button>

</header>

<main class="content">

<!-- DASHBOARD -->

<section class="page active" id="dashboard">

<div class="hero">

  <h1 id="heroTitle">
    Study smarter. Achieve more. 🚀
  </h1>

  <p>
    Everything you need to organise your study routine.
  </p>

</div>

<div class="grid">

  <div class="card stat">
    <div class="stat-icon">📝</div>
    <div class="stat-number" id="dashTotal">0</div>
    <span class="muted">Total tasks</span>
  </div>

  <div class="card stat">
    <div class="stat-icon">✅</div>
    <div class="stat-number" id="dashDone">0</div>
    <span class="muted">Completed</span>
  </div>

  <div class="card stat">
    <div class="stat-icon">📈</div>
    <div class="stat-number" id="dashProgress">0%</div>
    <span class="muted">Progress</span>
  </div>

  <div class="card stat">
    <div class="stat-icon">🔥</div>
    <div class="stat-number" id="dashStreak">0</div>
    <span class="muted">Day streak</span>
  </div>

</div>

<div class="card">

  <div class="row">
    <h2>Today's progress</h2>
    <span id="todayGoalLabel">0/0</span>
  </div>

  <div class="progress-bg">
    <div class="progress" id="dashProgressBar"></div>
  </div>

</div>

<div class="card">

  <h2>Upcoming tasks</h2>

  <div id="upcoming"></div>

</div>

</section>


<!-- TASKS -->

<section class="page" id="tasks">

<div class="card">

<h2>📝 Homework Tracker</h2>

<div class="form-grid">

  <input id="taskSubject" placeholder="Subject">

  <select id="taskCategory">
    <option>Maths</option>
    <option>English</option>
    <option>Science</option>
    <option>History</option>
    <option>Geography</option>
    <option>Computer Science</option>
    <option>Other</option>
  </select>

</div>

<input id="taskText" placeholder="What do you need to do?">

<input id="taskDate" type="date">

<button class="primary" onclick="addTask()">
  ➕ Add Task
</button>

</div>


<div class="card">

<div class="row">

<h2>Your tasks</h2>

<select id="taskFilter"
        style="width:auto"
        onchange="renderTasks()">

<option value="all">All</option>
<option value="active">Active</option>
<option value="done">Completed</option>

</select>

</div>

<div id="taskList"></div>

</div>

</section>


<!-- CALENDAR -->

<section class="page" id="calendar">

<div class="card">

<h2>📅 Study Calendar</h2>

<p class="muted" id="monthLabel"></p>

<div class="calendar" id="calendarGrid"></div>

</div>

<div class="card">

<h2>Deadlines</h2>

<div id="calendarTasks"></div>

</div>

</section>


<!-- REMINDERS -->

<section class="page" id="reminders">

<div class="card">

<h2>🔔 Study Reminders</h2>

<p class="muted">
Create reminders for homework, revision or study sessions.
</p>

<input id="reminderTitle" placeholder="Reminder title">

<input id="reminderDate" type="datetime-local">

<button class="primary" onclick="addReminder()">
🔔 Add Reminder
</button>

<button class="secondary" onclick="requestNotifications()">
Allow Notifications
</button>

</div>

<div class="card">

<h2>Your reminders</h2>

<div id="reminderList"></div>

</div>

</section>


<!-- FOCUS -->

<section class="page" id="focus">

<div class="card center">

<h2>⏱️ Focus Timer</h2>

<div class="timer" id="timer">25:00</div>

<button class="primary" onclick="startTimer()">▶ Start</button>

<button class="secondary" onclick="pauseTimer()">⏸ Pause</button>

<button class="secondary" onclick="resetTimer()">🔄 Reset</button>

<p class="muted">
25 minutes of focus followed by a short break.
</p>

</div>

</section>


<!-- GOALS -->

<section class="page" id="goals">

<div class="card">

<h2>🎯 Daily Goal</h2>

<input id="goalInput"
       type="number"
       min="1"
       placeholder="Tasks to complete today">

<button class="primary" onclick="setGoal()">
Set Goal
</button>

<h3 id="goalText">
No goal set.
</h3>

<div class="progress-bg">

<div class="progress"
     id="goalBar">
</div>

</div>

</div>

</section>


<!-- STATISTICS -->

<section class="page" id="statistics">

<div class="grid">

<div class="card stat">

<div class="stat-icon">📝</div>

<div class="stat-number" id="statTotal">
0
</div>

<span class="muted">
Tasks
</span>

</div>


<div class="card stat">

<div class="stat-icon">✅</div>

<div class="stat-number" id="statDone">
0
</div>

<span class="muted">
Completed
</span>

</div>


<div class="card stat">

<div class="stat-icon">⏱️</div>

<div class="stat-number" id="statSessions">
0
</div>

<span class="muted">
Focus sessions
</span>

</div>


<div class="card stat">

<div class="stat-icon">🔥</div>

<div class="stat-number" id="statStreak">
0
</div>

<span class="muted">
Streak
</span>

</div>

</div>


<div class="card">

<h2>Completion rate</h2>

<div class="progress-bg">

<div class="progress"
     id="statBar">
</div>

</div>

<p id="statPercent">
0%
</p>

</div>

</section>


<!-- PREMIUM -->

<section class="page" id="premium">

<div class="premium-page">

<header class="premium-header">

<button class="premium-back"
        onclick="showPage('dashboard')">
←
</button>

<div class="premium-logo">
StudyMate ⭐
</div>

<div class="premium-subtitle">
Unlock your full study potential
</div>

</header>


<div id="premiumActive"
     class="premium-status"
     style="display:none">

⭐ Premium is active on this device.

</div>


<section class="premium-card">

<span class="premium-badge">
⭐ PREMIUM
</span>

<h1 class="premium-title">
Study smarter.
</h1>

<p class="premium-description">
Get access to all StudyMate features
and take your studying to the next level.
</p>

</section>


<h2 class="section-title">
What's included
</h2>


<div class="feature">

<div class="feature-icon">📚</div>

<div class="feature-text">

<div class="feature-title">
Unlimited Subjects
</div>

<div class="feature-description">
Add as many subjects as you need.
</div>

</div>

</div>


<div class="feature">

<div class="feature-icon">📝</div>

<div class="feature-text">

<div class="feature-title">
Unlimited Homework
</div>

<div class="feature-description">
Keep all your assignments organised.
</div>

</div>

</div>


<div class="feature">

<div class="feature-icon">⏱️</div>

<div class="feature-text">

<div class="feature-title">
Advanced Focus Timer
</div>

<div class="feature-description">
More options for focused study sessions.
</div>

</div>

</div>


<div class="feature">

<div class="feature-icon">📊</div>

<div class="feature-text">

<div class="feature-title">
Detailed Progress
</div>

<div class="feature-description">
Understand your study progress.
</div>

</div>

</div>


<div class="feature">

<div class="feature-icon">☁️</div>

<div class="feature-text">

<div class="feature-title">
Cloud Sync
</div>

<div class="feature-description">
Keep your data synced across devices.
</div>

</div>

</div>


<div class="feature">

<div class="feature-icon">🎨</div>

<div class="feature-text">

<div class="feature-title">
Premium Themes
</div>

<div class="feature-description">
Unlock additional StudyMate themes.
</div>

</div>

</div>


<div class="pricing">

<h2 class="section-title">
Choose your plan
</h2>


<div class="plan selected"
     onclick="selectPlan('monthly')"
     id="monthly">

<div class="plan-header">

<div>

<div class="plan-name">
Monthly
</div>

<div class="period">
Cancel anytime
</div>

</div>

<div>

<span class="price">
£2.99
</span>

<span class="period">
/month
</span>

</div>

</div>

</div>


<div class="plan"
     onclick="selectPlan('yearly')"
     id="yearly">

<div class="plan-header">

<div>

<div class="plan-name">
Yearly
</div>

<span class="save">
SAVE ~30%
</span>

</div>

<div>

<span class="price">
£24.99
</span>

<span class="period">
/year
</span>

</div>

</div>

</div>


<button class="subscribe"
        onclick="startPremium()">

Continue with Premium

</button>


<button class="restore"
        onclick="restorePurchase()">

Restore Purchase

</button>

<div class="premium-footer">

Demo payment only — real payments are not connected yet.<br>
Your demo Premium status is stored locally on this device.

</div>

</div>

</div>

</section>


<!-- PROFILE -->

<section class="page" id="profile">

<div class="card">

<h2>👤 Student Profile</h2>

<input id="profileName"
       placeholder="Your name">

<button class="primary"
        onclick="saveProfile()">

Save Profile

</button>

<h3 id="profileWelcome">
Welcome to StudyMate! 👋
</h3>

</div>

</section>


<!-- SETTINGS -->

<section class="page" id="settings">

<div class="card">

<h2>⚙️ Settings</h2>


<div class="setting">

<strong>
Theme
</strong>

<p class="muted">
Switch between light and dark mode.
</p>

<button class="secondary"
        onclick="toggleTheme()">

Toggle theme

</button>

</div>


<div class="setting">

<strong>
Notifications
</strong>

<p class="muted">
Allow StudyMate to request browser notifications.
</p>

<button class="secondary"
        onclick="requestNotifications()">

Enable notifications

</button>

</div>


<div class="setting">

<strong>
Premium
</strong>

<p class="muted"
   id="settingsPremiumStatus">

Free plan

</p>

<button class="secondary"
        onclick="showPage('premium')">

View Premium

</button>

</div>


<div class="setting">

<strong>
Reset data
</strong>

<p class="muted">
Delete tasks, goals, reminders and profile data.
</p>

<button class="danger"
        onclick="resetAll()">

Reset StudyMate

</button>

</div>

</div>

</section>

</main>

</section>

</div>


<script>

const KEY="studymate_final";

let data=JSON.parse(
 localStorage.getItem(KEY)||"null"
)||{
 tasks:[],
 reminders:[],
 goal:0,
 name:"",
 focusSessions:0,
 dark:false,
 premium:false,
 premiumPlan:null
};

let seconds=1500;
let timerInterval=null;

let selectedPlan=data.premiumPlan||"monthly";


/* STORAGE */

function save(){

 localStorage.setItem(
  KEY,
  JSON.stringify(data)
 );

}


/* NAVIGATION */

document.querySelectorAll(".nav-btn")
.forEach(btn=>{

 btn.addEventListener("click",()=>{

   showPage(btn.dataset.page);

   document
   .getElementById("sidebar")
   .classList.remove("open");

 });

});


function showPage(page){

 document
 .querySelectorAll(".page")
 .forEach(p=>p.classList.remove("active"));

 document
 .getElementById(page)
 .classList.add("active");


 document
 .querySelectorAll(".nav-btn")
 .forEach(b=>{

   b.classList.toggle(
    "active",
    b.dataset.page===page
   );

 });


 const names={

  dashboard:"Dashboard",
  tasks:"Tasks",
  calendar:"Calendar",
  reminders:"Reminders",
  focus:"Focus Timer",
  goals:"Goals",
  statistics:"Statistics",
  premium:"Premium",
  profile:"Profile",
  settings:"Settings"

 };


 document
 .getElementById("topTitle")
 .textContent=names[page];


 renderAll();

}


function toggleMenu(){

 document
 .getElementById("sidebar")
 .classList.toggle("open");

}


/* THEME */

function toggleTheme(){

 data.dark=!data.dark;

 document
 .body
 .classList
 .toggle("dark",data.dark);

 save();

}


/* TASKS */

function addTask(){

 const subject=
 document.getElementById("taskSubject")
 .value.trim();

 const category=
 document.getElementById("taskCategory")
 .value;

 const text=
 document.getElementById("taskText")
 .value.trim();

 const date=
 document.getElementById("taskDate")
 .value;


 if(!subject||!text){

   alert(
    "Please enter a subject and task."
   );

   return;

 }


 data.tasks.push({

   id:Date.now(),

   subject,
   category,
   text,
   date,

   done:false,

   created:
    new Date().toISOString()

 });


 document.getElementById(
  "taskSubject"
 ).value="";

 document.getElementById(
  "taskText"
 ).value="";

 document.getElementById(
  "taskDate"
 ).value="";


 save();

 renderAll();

}


function toggleTask(id){

 const task=
 data.tasks.find(t=>t.id===id);

 if(task){

   task.done=!task.done;

   save();

   renderAll();

 }

}


function deleteTask(id){

 data.tasks=
 data.tasks.filter(t=>t.id!==id);

 save();

 renderAll();

}


function renderTasks(){

 const list=
 document.getElementById("taskList");

 if(!list)return;


 const filter=
 document.getElementById("taskFilter")
 .value;


 let tasks=[...data.tasks];


 if(filter==="active")
 tasks=tasks.filter(t=>!t.done);

 if(filter==="done")
 tasks=tasks.filter(t=>t.done);


 if(!tasks.length){

   list.innerHTML=
   '<div class="empty">No tasks here yet.</div>';

   return;

 }


 tasks.sort(
  (a,b)=>
  (a.date||"9999")
  .localeCompare(b.date||"9999")
 );


 list.innerHTML=
 tasks.map(t=>`

 <div class="task">

   <input
    class="check"
    type="checkbox"
    ${t.done?"checked":""}
    onchange="toggleTask(${t.id})">

   <div class="task-info ${t.done?"done":""}">

     <strong>
       ${safe(t.subject)}
     </strong>

     <span class="badge">
       ${safe(t.category)}
     </span>

     <br>

     ${safe(t.text)}

     ${t.date?
     `<br>
      <span class="muted">
       📅 ${safe(t.date)}
      </span>`
     :""}

   </div>

   <button
    class="danger"
    onclick="deleteTask(${t.id})">

    🗑

   </button>

 </div>

 `).join("");

}


/* DASHBOARD */

function renderDashboard(){

 const total=data.tasks.length;

 const done=
 data.tasks.filter(t=>t.done).length;

 const percent=
 total?
 Math.round(done/total*100):
 0;


 document.getElementById(
  "dashTotal"
 ).textContent=total;


 document.getElementById(
  "dashDone"
 ).textContent=done;


 document.getElementById(
  "dashProgress"
 ).textContent=
 percent+"%";


 document.getElementById(
  "dashStreak"
 ).textContent=
 calculateStreak();


 document.getElementById(
  "dashProgressBar"
 ).style.width=
 percent+"%";


 const goalDone=
 Math.min(done,data.goal||0);


 document.getElementById(
  "todayGoalLabel"
 ).textContent=
 data.goal?
 `${goalDone}/${data.goal}`:
 `${done}/0`;


 const upcoming=
 document.getElementById("upcoming");


 const future=
 data.tasks
 .filter(t=>!t.done&&t.date)
 .sort((a,b)=>
  a.date.localeCompare(b.date)
 )
 .slice(0,5);


 if(!future.length){

   upcoming.innerHTML=
   '<div class="empty">No upcoming tasks.</div>';

 }else{

   upcoming.innerHTML=
   future.map(t=>`

    <div class="task">

      <div class="task-info">

       <strong>
        ${safe(t.subject)}
       </strong>

       <span class="badge">
        ${safe(t.category)}
       </span>

       <br>

       ${safe(t.text)}

       <br>

       <span class="muted">
        📅 ${safe(t.date)}
       </span>

      </div>

    </div>

   `).join("");

 }

}


/* GOAL */

function setGoal(){

 const value=
 Number(
  document.getElementById("goalInput").value
 );


 if(value<1){

   alert(
    "Please enter a valid goal."
   );

   return;

 }


 data.goal=value;

 save();

 renderAll();

}


function renderGoal(){

 const done=
 data.tasks.filter(t=>t.done).length;


 if(!data.goal){

   document.getElementById(
    "goalText"
   ).textContent=
   "No goal set.";

   document.getElementById(
    "goalBar"
   ).style.width="0%";

   return;

 }


 const p=
 Math.min(
  100,
  Math.round(done/data.goal*100)
 );


 document.getElementById(
  "goalText"
 ).textContent=
 `🎯 ${Math.min(done,data.goal)}/${data.goal} tasks completed`;


 document.getElementById(
  "goalBar"
 ).style.width=
 p+"%";

}


/* CALENDAR */

function renderCalendar(){

 const grid=
 document.getElementById(
  "calendarGrid"
 );

 const now=new Date();

 const year=now.getFullYear();

 const month=now.getMonth();


 document.getElementById(
  "monthLabel"
 ).textContent=
 now.toLocaleDateString(
  "en-GB",
  {
   month:"long",
   year:"numeric"
  }
 );


 const first=
 new Date(year,month,1);

 const last=
 new Date(year,month+1,0);


 const mondayIndex=
 (first.getDay()+6)%7;


 grid.innerHTML="";


 [
  "Mon",
  "Tue",
  "Wed",
  "Thu",
  "Fri",
  "Sat",
  "Sun"
 ]
 .forEach(d=>{

  grid.innerHTML+=
  `<div class="day">
   <strong>${d}</strong>
  </div>`;

 });


 for(
  let i=0;
  i<mondayIndex;
  i++
 ){

  grid.innerHTML+=
  `<div></div>`;

 }


 for(
  let d=1;
  d<=last.getDate();
  d++
 ){

  const date=
  `${year}-${
   String(month+1).padStart(2,"0")
  }-${
   String(d).padStart(2,"0")
  }`;


  const has=
  data.tasks.some(
   t=>t.date===date
  );


  const today=new Date();


  const isToday=
   today.getFullYear()===year&&
   today.getMonth()===month&&
   today.getDate()===d;


  grid.innerHTML+=`

   <div class="day ${isToday?"today":""}">

    <strong>${d}</strong>

    ${
     has?
     '<br><span class="reminder-dot"></span>':
     ""
    }

   </div>

  `;

 }


 const ct=
 document.getElementById(
  "calendarTasks"
 );


 const tasks=
 data.tasks.filter(t=>t.date);


 if(!tasks.length){

  ct.innerHTML=
  '<div class="empty">No deadlines added.</div>';

 }else{

  ct.innerHTML=
  tasks
  .sort((a,b)=>
   a.date.localeCompare(b.date)
  )
  .map(t=>`

   <div class="task">

    <div class="task-info">

     <strong>
      ${safe(t.subject)}
     </strong>

     <br>

     ${safe(t.text)}

     <br>

     <span class="muted">
      📅 ${safe(t.date)}
     </span>

    </div>

   </div>

  `).join("");

 }

}


/* REMINDERS */

function addReminder(){

 const title=
 document.getElementById(
  "reminderTitle"
 ).value.trim();


 const date=
 document.getElementById(
  "reminderDate"
 ).value;


 if(!title||!date){

   alert(
    "Please enter a title and time."
   );

   return;

 }


 data.reminders.push({

  id:Date.now(),

  title,
  date,

  notified:false

 });


 document.getElementById(
  "reminderTitle"
 ).value="";


 document.getElementById(
  "reminderDate"
 ).value="";


 save();

 renderAll();

}


function deleteReminder(id){

 data.reminders=
 data.reminders.filter(
  r=>r.id!==id
 );

 save();

 renderAll();

}


function renderReminders(){

 const box=
 document.getElementById(
  "reminderList"
 );


 if(!data.reminders.length){

  box.innerHTML=
  '<div class="empty">No reminders yet.</div>';

  return;

 }


 data.reminders.sort(
  (a,b)=>
  a.date.localeCompare(b.date)
 );


 box.innerHTML=
 data.reminders.map(r=>`

  <div class="reminder">

   <div class="row">

    <div>

     <strong>
      🔔 ${safe(r.title)}
     </strong>

     <br>

     <span class="muted">
      ${formatDateTime(r.date)}
     </span>

    </div>

    <button
     class="danger"
     onclick="deleteReminder(${r.id})">

     🗑

    </button>

   </div>

  </div>

 `).join("");

}


function requestNotifications(){

 if(!("Notification" in window)){

  alert(
   "Notifications are not supported by this browser."
  );

  return;

 }


 Notification
 .requestPermission()
 .then(permission=>{

  if(permission==="granted"){

   alert(
    "Notifications enabled."
   );

  }else{

   alert(
    "Notifications were not enabled."
   );

  }

 });

}


function checkReminders(){

 const now=Date.now();


 data.reminders.forEach(r=>{

  const time=
  new Date(r.date).getTime();


  if(!r.notified&&time<=now){

   r.notified=true;


   if(
    "Notification" in window &&
    Notification.permission==="granted"
   ){

    new Notification(
     "StudyMate Reminder",
     {
      body:r.title
     }
    );

   }

  }

 });


 save();

}


/* TIMER */

function showTimer(){

 const m=
 String(
  Math.floor(seconds/60)
 )
 .padStart(2,"0");


 const s=
 String(
  seconds%60
 )
 .padStart(2,"0");


 document.getElementById(
  "timer"
 ).textContent=
 `${m}:${s}`;

}


function startTimer(){

 if(timerInterval)return;


 timerInterval=
 setInterval(()=>{

  if(seconds>0){

   seconds--;

   showTimer();

  }else{

   pauseTimer();

   data.focusSessions++;

   save();

   renderAll();

   alert(
    "🎉 Focus session complete!"
   );

  }

 },1000);

}


function pauseTimer(){

 clearInterval(timerInterval);

 timerInterval=null;

}


function resetTimer(){

 pauseTimer();

 seconds=1500;

 showTimer();

}


/* STATISTICS */

function renderStats(){

 const total=
 data.tasks.length;

 const done=
 data.tasks.filter(
  t=>t.done
 ).length;


 const p=
 total?
 Math.round(done/total*100):
 0;


 document.getElementById(
  "statTotal"
 ).textContent=total;


 document.getElementById(
  "statDone"
 ).textContent=done;


 document.getElementById(
  "statSessions"
 ).textContent=
 data.focusSessions;


 document.getElementById(
  "statStreak"
 ).textContent=
 calculateStreak();


 document.getElementById(
  "statBar"
 ).style.width=
 p+"%";


 document.getElementById(
  "statPercent"
 ).textContent=
 p+"% completion rate";

}


/* PROFILE */

function saveProfile(){

 const name=
 document.getElementById(
  "profileName"
 ).value.trim();


 if(!name)return;


 data.name=name;

 save();

 renderAll();

}


function renderProfile(){

 document.getElementById(
  "profileName"
 ).value=
 data.name;


 document.getElementById(
  "profileWelcome"
 ).textContent=
 data.name?
 `Welcome back, ${data.name}! 👋`:
 "Welcome to StudyMate! 👋";


 document.getElementById(
  "heroTitle"
 ).textContent=
 data.name?
 `Welcome back, ${data.name}! 🚀`:
 "Study smarter. Achieve more. 🚀";

}


/* STREAK */

function calculateStreak(){

 const dates=
 [
  ...new Set(
   data.tasks
   .filter(t=>t.done&&t.created)
   .map(t=>t.created.slice(0,10))
  )
 ];


 if(!dates.length)return 0;


 dates.sort().reverse();


 let streak=0;

 let current=new Date();


 for(
  const date of dates
 ){

  const d=
  current.toISOString()
  .slice(0,10);


  if(date===d){

   streak++;

   current.setDate(
    current.getDate()-1
   );

  }else{

   break;

  }

 }


 return streak;

}


/* PREMIUM */

function selectPlan(plan){

 selectedPlan=plan;


 document
 .getElementById("monthly")
 .classList
 .remove("selected");


 document
 .getElementById("yearly")
 .classList
 .remove("selected");


 document
 .getElementById(plan)
 .classList
 .add("selected");

}


function startPremium(){

 /*
   DEMO ONLY.

   This does NOT process real money.

   Later this function can be connected
   to a real payment/subscription system.
 */


 data.premium=true;

 data.premiumPlan=
 selectedPlan;


 save();

 renderAll();


 alert(
  selectedPlan==="monthly"
  ?
  "⭐ Premium activated in DEMO mode.\n\n£2.99/month selected."
  :
  "⭐ Premium activated in DEMO mode.\n\n£24.99/year selected."
 );

}


function restorePurchase(){

 if(data.premium){

  alert(
   "⭐ Your StudyMate Premium demo is already active."
  );

  return;

 }


 alert(
  "No Premium purchase was found on this device."
 );

}


function renderPremium(){

 const active=
 document.getElementById(
  "premiumActive"
 );


 const settings=
 document.getElementById(
  "settingsPremiumStatus"
 );


 if(data.premium){

  active.style.display="block";

  settings.textContent=
  data.premiumPlan==="yearly"
  ?
  "⭐ Premium — Yearly plan"
  :
  "⭐ Premium — Monthly plan";

 }else{

  active.style.display="none";

  settings.textContent=
  "Free plan";

 }


 selectPlan(
  data.premiumPlan||"monthly"
 );

}


/* RESET */

function resetAll(){

 if(
  !confirm(
   "Delete all StudyMate data?"
  )
 )return;


 localStorage.removeItem(KEY);

 location.reload();

}


/* HELPERS */

function safe(text){

 return String(text)
 .replace(
  /[&<>"']/g,
  c=>({

   "&":"&amp;",
   "<":"&lt;",
   ">":"&gt;",
   '"':"&quot;",
   "'":"&#39;"

  }[c])
 );

}


function formatDateTime(value){

 const d=new Date(value);


 if(isNaN(d))
 return value;


 return d.toLocaleString(
  "en-GB",
  {
   dateStyle:"medium",
   timeStyle:"short"
  }
 );

}


/* RENDER ALL */

function renderAll(){

 renderTasks();

 renderDashboard();

 renderGoal();

 renderCalendar();

 renderReminders();

 renderStats();

 renderProfile();

 renderPremium();

 showTimer();

}


/* INIT */

document.body
.classList
.toggle("dark",data.dark);

renderAll();

setInterval(
 checkReminders,
 30000
);

</script>

</body>
</html>
