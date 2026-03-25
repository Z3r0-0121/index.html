[index.html.html](https://github.com/user-attachments/files/26256793/index.html.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>WorkLog Planner Suite</title>
  <style>
    :root{
      --bg:#f4f4f4;
      --panel-bg: rgba(255,255,255,0.94);
      --card-bg: rgba(255,255,255,0.97);
      --text:#333;
      --line:#d8d8d8;
      --dark:#222;
      --green:#28a745;
      --red:#dc3545;
      --blue:#2563eb;
      --amber:#d97706;
      --muted:#666;
      --shadow:0 2px 6px rgba(0,0,0,.12);
      --radius:10px;
    }
    *{box-sizing:border-box}
    body{font-family:Arial,sans-serif;margin:0;background:var(--bg);color:var(--text)}
    body::before{
      content:"";
      position:fixed;
      inset:0;
      z-index:-1;
      pointer-events:none;
      background:url('IMG_2548.jpeg') no-repeat center 20%/min(85vw,900px) auto;
      opacity:.08;
    }
    header{background:var(--dark);color:#fff;padding:1em;text-align:center}
    header h1{margin:.15em 0}
    header p{margin:.2em 0 0;color:#ddd}
    .container{max-width:1220px;margin:20px auto;padding:0 20px}
    .toolbar,.tabbar{display:flex;gap:10px;flex-wrap:wrap;background:var(--panel-bg);padding:12px;border-radius:var(--radius);box-shadow:var(--shadow);margin-bottom:18px}
    .tabbar button{width:auto;min-width:130px;background:#fff;border:1px solid var(--line)}
    .tabbar button.active{background:var(--blue);color:#fff;border-color:var(--blue)}
    .toolbar{justify-content:flex-end}
    .card{background:var(--card-bg);padding:18px;border-radius:var(--radius);box-shadow:var(--shadow);margin-bottom:18px}
    .grid-2,.grid-3,.grid-4{display:grid;gap:12px}
    .grid-2{grid-template-columns:repeat(2,minmax(0,1fr))}
    .grid-3{grid-template-columns:repeat(3,minmax(0,1fr))}
    .grid-4{grid-template-columns:repeat(4,minmax(0,1fr))}
    @media (max-width:900px){.grid-4,.grid-3,.grid-2{grid-template-columns:1fr}}
    label{display:block;margin-top:10px;font-size:14px;font-weight:600}
    input,textarea,select,button{width:100%;padding:9px;margin-top:5px;border:1px solid #ccc;border-radius:7px;font:inherit}
    textarea{resize:vertical;min-height:84px}
    button{cursor:pointer;font-weight:700;background:#fff}
    .btn{background:var(--green);color:#fff;border:none}
    .btn-danger{background:var(--red);color:#fff;border:none}
    .btn-blue{background:var(--blue);color:#fff;border:none}
    .btn-amber{background:var(--amber);color:#fff;border:none}
    .inline-buttons{display:flex;gap:10px;flex-wrap:wrap;margin-top:12px}
    .inline-buttons button{width:auto;min-width:110px}
    .section{display:none}
    .section.active{display:block}
    table{width:100%;border-collapse:collapse;margin-top:12px;background:#fff}
    th,td{border:1px solid var(--line);padding:8px;text-align:left;vertical-align:top}
    th{background:#efefef}
    .actions-col button{width:auto;display:inline-block;margin-right:6px;margin-top:0;padding:6px 10px}
    .thumb img{max-width:80px;max-height:80px;border-radius:6px;cursor:pointer}
    dialog{border:none;border-radius:8px;padding:12px;max-width:95vw}
    #modalImg{max-width:90vw;max-height:80vh}
    #camVideo{max-width:90vw;max-height:70vh;display:block;margin-bottom:10px}
    .muted{color:var(--muted)}
    .pill{display:inline-block;padding:3px 8px;border-radius:999px;font-size:12px;font-weight:700}
    .pill.pending{background:#fef3c7;color:#92400e}
    .pill.bought,.pill.done,.pill.active,.pill.ok{background:#dcfce7;color:#166534}
    .pill.ordered,.pill.paused{background:#dbeafe;color:#1d4ed8}
    .pill.closed,.pill.cancelled,.pill.out{background:#fee2e2;color:#991b1b}
    .pill.low{background:#fef3c7;color:#92400e}
    .error-banner{position:fixed;left:0;right:0;bottom:0;background:#b91c1c;color:#fff;padding:8px 12px;font-size:14px;display:none;z-index:9999}
    .time-row{display:flex;gap:8px;flex-wrap:wrap}
    .time-row select{flex:1 1 120px;min-width:90px}
    .summary-grid{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:12px}
    @media (max-width:900px){.summary-grid{grid-template-columns:repeat(2,minmax(0,1fr))}}
    .summary-card{background:#fff;border:1px solid var(--line);border-radius:10px;padding:14px}
    .summary-card h4{margin:0 0 6px}
    .summary-card .big{font-size:24px;font-weight:800}
    .sticky-note{background:#fffbe6;border:1px solid #f3e6a2;padding:10px;border-radius:8px}
    .todo-due{color:#991b1b;font-weight:700}
    .today-box{border-left:4px solid var(--blue)}
    .project-block{margin-bottom:14px}
  
    :root{
      --brand1:#0f172a;
      --brand2:#1d4ed8;
      --brand3:#0ea5e9;
      --soft:#eef6ff;
      --ok:#16a34a;
      --warn:#d97706;
      --danger:#dc2626;
    }
    html{scroll-behavior:smooth}
    body{
      background:
        radial-gradient(circle at top right, rgba(59,130,246,.09), transparent 28%),
        linear-gradient(180deg, #f6f9ff 0%, #eef3f9 100%);
      -webkit-text-size-adjust:100%;
    }
    header{
      background:linear-gradient(135deg,var(--brand1),var(--brand2));
      box-shadow:0 10px 24px rgba(15,23,42,.18);
      position:sticky;
      top:0;
      z-index:100;
    }
    header h1{letter-spacing:.2px}
    .container{padding-bottom:34px}
    .toolbar,.tabbar,.card{
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
    }
    .tabbar{
      position:sticky;
      top:84px;
      z-index:95;
      overflow:auto hidden;
      flex-wrap:nowrap;
      scrollbar-width:thin;
      border:1px solid rgba(148,163,184,.25);
    }
    .tabbar button{
      white-space:nowrap;
      min-height:46px;
      border-radius:12px;
      font-weight:700;
      transition:transform .15s ease, box-shadow .15s ease, background .15s ease;
    }
    .tabbar button:hover{transform:translateY(-1px); box-shadow:0 6px 16px rgba(37,99,235,.12)}
    .tabbar button.active{
      background:linear-gradient(135deg,var(--brand2),var(--brand3));
      box-shadow:0 8px 18px rgba(37,99,235,.22);
    }
    .toolbar{
      border:1px solid rgba(148,163,184,.24);
      align-items:end;
    }
    .card{
      border:1px solid rgba(148,163,184,.2);
      box-shadow:0 10px 30px rgba(15,23,42,.08);
    }
    .summary-card{
      border:none;
      background:linear-gradient(180deg,#ffffff,#f8fbff);
      box-shadow:0 10px 20px rgba(15,23,42,.08);
    }
    .summary-card .big{color:var(--brand2)}
    input,textarea,select,button{
      min-height:44px;
    }
    input,textarea,select{
      background:#fff;
      border:1px solid #d7dfeb;
      transition:border-color .15s ease, box-shadow .15s ease;
    }
    input:focus,textarea:focus,select:focus{
      outline:none;
      border-color:#60a5fa;
      box-shadow:0 0 0 3px rgba(96,165,250,.18);
    }
    button{
      border:1px solid rgba(148,163,184,.25);
      transition:transform .15s ease, box-shadow .15s ease, opacity .15s ease;
    }
    button:hover{transform:translateY(-1px); box-shadow:0 8px 18px rgba(15,23,42,.10)}
    button:active{transform:translateY(0)}
    .btn{background:linear-gradient(135deg,#16a34a,#22c55e)}
    .btn-blue{background:linear-gradient(135deg,#2563eb,#38bdf8)}
    .btn-danger{background:linear-gradient(135deg,#dc2626,#ef4444)}
    .btn-amber{background:linear-gradient(135deg,#d97706,#f59e0b)}
    .pill{letter-spacing:.2px}
    .pill.low{background:#fff7d6;color:#9a6700}
    .pill.out{background:#ffe2e2;color:#b42318}
    .pill.ok{background:#dcfce7;color:#166534}
    .pill.pending{background:#fff7d6;color:#9a6700}
    .pill.bought,.pill.done,.pill.active{background:#dcfce7;color:#166534}
    .pill.ordered,.pill.paused{background:#dbeafe;color:#1d4ed8}
    .pill.closed,.pill.cancelled{background:#fee2e2;color:#991b1b}
    .today-box{
      background:linear-gradient(180deg,#ffffff,#f8fbff);
      border-left:4px solid var(--brand2);
    }
    .sticky-note{
      background:linear-gradient(180deg,#fffdea,#fff7cc);
      border-color:#f3dd6a;
    }
    table{
      display:block;
      overflow:auto;
      white-space:nowrap;
      border-radius:10px;
    }
    th{position:sticky; top:0; z-index:1}
    .section h3{
      margin-top:0;
      color:#0f172a;
    }
    .mobile-hint{
      display:none;
      font-size:12px;
      color:#64748b;
      margin-top:8px;
    }
    @media (max-width:900px){
      header{position:relative}
      .tabbar{top:0}
      .container{padding:0 12px 26px}
      .toolbar,.tabbar,.card{padding:12px}
      .summary-grid{grid-template-columns:1fr 1fr}
      .inline-buttons button{flex:1 1 calc(50% - 10px); min-width:0}
      .actions-col button{display:block; width:100%; margin:0 0 6px}
      table{font-size:14px}
      .mobile-hint{display:block}
      dialog{padding:8px; width:min(96vw,720px)}
    }
    @media (max-width:640px){
      body::before{background-size:min(100vw,620px) auto; opacity:.05}
      header{padding:14px 10px}
      header h1{font-size:22px}
      header p{font-size:13px}
      .summary-grid{grid-template-columns:1fr}
      .grid-4,.grid-3,.grid-2{grid-template-columns:1fr}
      .inline-buttons{gap:8px}
      .inline-buttons button{flex:1 1 100%}
      label{font-size:13px}
      input,textarea,select,button{font-size:16px}
      table{font-size:13px}
      th,td{padding:7px}
      .tabbar button{min-width:120px}
      .toolbar{justify-content:stretch}
      .toolbar > *{flex:1 1 100%}
      .actions-col button{padding:8px 10px}
    }

  </style>
</head>
<body>
  <header>
    <h1>WorkLog Planner Suite</h1>
    <p>Work log, projects, materials, reminders and printable weekly reports</p>
  </header>

  <div class="container">
    <div class="tabbar">
      <button class="tab-btn active" data-tab="dashboard" type="button">Dashboard</button>
      <button class="tab-btn" data-tab="worklog" type="button">Work Log</button>
      <button class="tab-btn" data-tab="projects" type="button">Projects</button>
      <button class="tab-btn" data-tab="materials" type="button">Materials</button>
      <button class="tab-btn" data-tab="inventory" type="button">Inventory</button>
      <button class="tab-btn" data-tab="reminders" type="button">Reminders</button>
      <button class="tab-btn" data-tab="reports" type="button">Reports / Search</button>
    </div>

    <section id="tab-dashboard" class="section active">
      <div class="summary-grid">
        <div class="summary-card"><h4>Active Projects</h4><div class="big" id="dashProjects">0</div></div>
        <div class="summary-card"><h4>Pending Materials</h4><div class="big" id="dashMaterials">0</div></div>
        <div class="summary-card"><h4>Today's Reminders</h4><div class="big" id="dashTodayReminders">0</div></div>
        <div class="summary-card"><h4>This Week Hours</h4><div class="big" id="dashWeekHours">0.00</div></div>
      </div>

      <div class="card today-box">
        <h3>Today / Overdue Reminders</h3>
        <div id="todayReminderList" class="muted">No reminders for now.</div>
      </div>

      <div class="card">
        <h3>Quick Notes</h3>
        <div class="sticky-note">Create the project first. Then attach work log, materials and reminders to the same project.</div>
      </div>
    </section>

    <section id="tab-worklog" class="section">
      <div class="toolbar">
        <label>View
          <select id="viewMode">
            <option value="week" selected>Week</option>
            <option value="day">Day</option>
            <option value="month">Month</option>
            <option value="year">Year</option>
          </select>
        </label>
        <label>Date
          <input id="calendarDate" type="date">
        </label>
        <button id="closeWeekBtn" class="btn" type="button">Close Week</button>
        <button id="printPeriodBtn" type="button">Print PDF</button>
      </div>

      <section class="card">
        <h3>Add / Edit Work Entry</h3>
        <div class="grid-3">
          <label>Date <input id="date" type="date"></label>
          <label>Project
            <select id="entryProjectId"></select>
          </label>
          <label>Hours worked <input id="hours" type="number" step="0.01" placeholder="auto if you set times"></label>
        </div>

        <div class="grid-2">
          <div>
            <label>Start time</label>
            <div class="time-row">
              <select id="startHour"></select>
              <select id="startMinute"></select>
              <select id="startAmpm">
                <option value="AM">AM</option>
                <option value="PM">PM</option>
              </select>
            </div>
          </div>
          <div>
            <label>End time</label>
            <div class="time-row">
              <select id="endHour"></select>
              <select id="endMinute"></select>
              <select id="endAmpm">
                <option value="AM">AM</option>
                <option value="PM">PM</option>
              </select>
            </div>
          </div>
        </div>

        <div class="grid-2">
          <label>Project / Location <input id="location" type="text" placeholder="project name / job site / address"></label>
          <label>Vendor <input id="vendor"></label>
        </div>
        <label>What was done <textarea id="task" rows="3"></textarea></label>
        <div class="grid-2">
          <label>Expense <input id="amount" type="number" step="0.01"></label>
          <label>Receipt photo
            <input id="receiptInput" type="file" accept="image/*" capture="environment">
          </label>
        </div>
        <div class="thumb" id="thumb"></div>
        <button class="btn" id="openCamBtn" type="button">Open Camera</button>

        <div class="inline-buttons">
          <button class="btn" id="saveBtn" type="button">Save</button>
          <button id="clearFormBtn" type="button">Clear</button>
          <button class="btn-danger" id="deleteBtn" type="button">Delete</button>
        </div>
        <p id="status"></p>
      </section>

      <section class="card">
        <h3>Quick Add Multiple Work Entries</h3>
        <div class="grid-3">
          <label>Date <input id="batchEntryDate" type="date"></label>
          <label>Project
            <select id="batchEntryProjectId"></select>
          </label>
          <label>Default Project / Location <input id="batchEntryLocation" type="text" placeholder="optional default location"></label>
        </div>

        <table>
          <thead>
            <tr>
              <th style="width:210px">Start</th>
              <th style="width:210px">End</th>
              <th style="width:90px">Hours</th>
              <th>Description</th>
              <th style="width:180px">Location</th>
              <th style="width:150px">Vendor</th>
              <th style="width:120px">Expense</th>
              <th style="width:120px">Action</th>
            </tr>
          </thead>
          <tbody id="batchWorklogTbody"></tbody>
        </table>

        <div class="inline-buttons">
          <button id="addBatchWorklogRowBtn" class="btn-amber" type="button">+ Add Row</button>
          <button id="saveBatchWorklogBtn" class="btn-blue" type="button">Save All Rows</button>
          <button id="clearBatchWorklogBtn" type="button">Clear Rows</button>
        </div>
        <p class="muted">Batch rows use AM / PM too.</p>
        <p id="batchWorklogStatusMsg"></p>
      </section>

      <section class="card">
        <h3>Work Entries</h3><div class="mobile-hint">Tip: swipe the table sideways on phone or tablet to see all columns.</div>
        <table>
          <thead>
            <tr>
              <th>Date</th>
              <th>Project</th>
              <th>Time</th>
              <th>Hours</th>
              <th>Description</th>
              <th>Project / Location</th>
              <th>Vendor</th>
              <th>Expense</th>
              <th>Receipt</th>
              <th>Actions</th>
            </tr>
          </thead>
          <tbody id="tbody"></tbody>
        </table>
      </section>

      <section class="card">
        <h3>History</h3>
        <ul id="historyList" style="max-height:160px;overflow:auto;margin:0;padding-left:18px"></ul>
        <button id="clearHistoryBtn" type="button" class="btn-danger" style="margin-top:8px">Clear History</button>
      </section>
    </section>

    <section id="tab-projects" class="section">
      <section class="card">
        <h3>Add / Edit Project</h3>
        <div class="grid-3">
          <label>Project name <input id="projectName" type="text" placeholder="Hotel room 214"></label>
          <label>Location <input id="projectLocation" type="text" placeholder="address / job site"></label>
          <label>Client <input id="projectClient" type="text" placeholder="client name"></label>
        </div>
        <div class="grid-2">
          <label>Status
            <select id="projectStatus">
              <option value="active">Active</option>
              <option value="paused">Paused</option>
              <option value="closed">Closed</option>
            </select>
          </label>
          <label>Start date <input id="projectStartDate" type="date"></label>
        </div>
        <label>Notes <textarea id="projectNotes"></textarea></label>
        <div class="inline-buttons">
          <button id="saveProjectBtn" class="btn-blue" type="button">Save Project</button>
          <button id="clearProjectBtn" type="button">Clear</button>
          <button id="deleteProjectBtn" class="btn-danger" type="button">Delete</button>
        </div>
        <p id="projectStatusMsg"></p>
      </section>

      <section class="card">
        <h3>Projects</h3>
        <table>
          <thead>
            <tr>
              <th>Name</th>
              <th>Location</th>
              <th>Client</th>
              <th>Status</th>
              <th>Start date</th>
              <th>Notes</th>
              <th>Actions</th>
            </tr>
          </thead>
          <tbody id="projectsTbody"></tbody>
        </table>
      </section>
    </section>

    <section id="tab-materials" class="section">
      <section class="card">
        <h3>Add / Edit Material</h3>
        <div class="grid-3">
          <label>Project
            <select id="materialProjectId"></select>
          </label>
          <label>Material <input id="materialName" type="text" placeholder="1/2 drywall"></label>
          <label>Quantity <input id="materialQty" type="number" step="0.01"></label>
        </div>
        <div class="grid-4">
          <label>Unit <input id="materialUnit" type="text" placeholder="sheets / pcs / ft"></label>
          <label>Store <input id="materialStore" type="text" placeholder="Home Depot / Lowe's"></label>
          <label>Estimated price <input id="materialPrice" type="number" step="0.01"></label>
          <label>Status
            <select id="materialStatus">
              <option value="pending">Pending</option>
              <option value="ordered">Ordered</option>
              <option value="bought">Bought</option>
            </select>
          </label>
        </div>
        <label>Notes <textarea id="materialNotes"></textarea></label>
        <div class="inline-buttons">
          <button id="saveMaterialBtn" class="btn-blue" type="button">Save Material</button>
          <button id="clearMaterialBtn" type="button">Clear</button>
          <button id="deleteMaterialBtn" class="btn-danger" type="button">Delete</button>
        </div>
        <p id="materialStatusMsg"></p>
      </section>

      <section class="card">
        <h3>Project Batch Entry</h3>
        <div class="grid-3">
          <label>Project
            <select id="batchMaterialProjectId"></select>
          </label>
          <label>Default Store <input id="batchMaterialStore" type="text" placeholder="optional default store"></label>
          <label>Default Status
            <select id="batchMaterialStatus">
              <option value="pending">Pending</option>
              <option value="ordered">Ordered</option>
              <option value="bought">Bought</option>
            </select>
          </label>
        </div>
        <table>
          <thead>
            <tr>
              <th style="width:120px">Qty</th>
              <th>Material</th>
              <th style="width:120px">Unit</th>
              <th style="width:160px">Store</th>
              <th style="width:130px">Price</th>
              <th>Notes</th>
              <th style="width:120px">Action</th>
            </tr>
          </thead>
          <tbody id="batchMaterialsTbody"></tbody>
        </table>
        <div class="inline-buttons">
          <button id="addBatchMaterialRowBtn" class="btn-amber" type="button">+ Add Row</button>
          <button id="saveBatchMaterialsBtn" class="btn-blue" type="button">Save All Rows</button>
          <button id="clearBatchMaterialsBtn" type="button">Clear Rows</button>
        </div>
        <p class="muted">Enter many products for the same project in one shot.</p>
        <p id="batchMaterialStatusMsg"></p>
      </section>

      <section class="card">
        <h3>Materials List</h3><div class="mobile-hint">Tip: swipe the table sideways on phone or tablet to see all columns.</div>
        <p class="muted">Grouped by project so each shopping list stays together.</p>
        <div id="materialsGroupedList"></div>
      </section>
    </section>

    <section id="tab-inventory" class="section">
      <section class="card">
        <h3>Add / Edit Inventory Item</h3>
        <div class="grid-4">
          <label>Project
            <select id="inventoryProjectId"></select>
          </label>
          <label>Piece name <input id="inventoryName" type="text" placeholder="Drywall screw 1-5/8"></label>
          <label>Code / SKU <input id="inventorySku" type="text" placeholder="optional"></label>
          <label>Category <input id="inventoryCategory" type="text" placeholder="screws / wire / tools"></label>
        </div>

        <div class="grid-4">
          <label>Initial quantity <input id="inventoryQty" type="number" step="0.01"></label>
          <label>Unit <input id="inventoryUnit" type="text" placeholder="pcs / box / ft / rolls"></label>
          <label>Min stock <input id="inventoryMinStock" type="number" step="0.01" placeholder="optional"></label>
          <label>Location <input id="inventoryLocation" type="text" placeholder="truck / room / shelf"></label>
        </div>

        <label>Notes <textarea id="inventoryNotes"></textarea></label>

        <div class="inline-buttons">
          <button id="saveInventoryBtn" class="btn-blue" type="button">Save Item</button>
          <button id="clearInventoryBtn" type="button">Clear</button>
          <button id="deleteInventoryBtn" class="btn-danger" type="button">Delete</button>
        </div>
        <p id="inventoryStatusMsg"></p>
      </section>

      <section class="card">
        <h3>Inventory Entry / Exit</h3>
        <div class="grid-4">
          <label>Item
            <select id="movementItemId"></select>
          </label>
          <label>Type
            <select id="movementType">
              <option value="in">Entry (+)</option>
              <option value="out">Exit (-)</option>
            </select>
          </label>
          <label>Quantity <input id="movementQty" type="number" step="0.01"></label>
          <label>Date <input id="movementDate" type="date"></label>
        </div>

        <div class="grid-3">
          <label>Reference <input id="movementRef" type="text" placeholder="invoice / used in room 202 / restock"></label>
          <label>Handled by <input id="movementUser" type="text" placeholder="optional"></label>
          <label>Project
            <select id="movementProjectId"></select>
          </label>
        </div>

        <label>Notes <textarea id="movementNotes"></textarea></label>

        <div class="inline-buttons">
          <button id="saveMovementBtn" class="btn-amber" type="button">Apply Movement</button>
          <button id="clearMovementBtn" type="button">Clear</button>
          <button id="printInventoryBtn" type="button">Print Inventory Sheet</button>
        </div>
        <p id="movementStatusMsg"></p>
      </section>

      <section class="card">
        <h3>Search Inventory</h3>
        <div class="grid-4">
          <label>Search <input id="inventorySearch" type="text" placeholder="piece / code / category / location"></label>
          <label>Project
            <select id="inventorySearchProjectId"></select>
          </label>
          <label>Stock filter
            <select id="inventoryStockFilter">
              <option value="">All</option>
              <option value="low">Low stock</option>
              <option value="out">Out of stock</option>
            </select>
          </label>
          <label>&nbsp;
            <button id="runInventorySearchBtn" class="btn-blue" type="button">Search</button>
          </label>
        </div>
      </section>

      <section class="card">
        <h3>Inventory List</h3><div class="mobile-hint">Tip: swipe the table sideways on phone or tablet to see all columns.</div>
        <table>
          <thead>
            <tr>
              <th>Piece</th>
              <th>Code</th>
              <th>Category</th>
              <th>Project</th>
              <th>Qty</th>
              <th>Unit</th>
              <th>Min</th>
              <th>Remaining</th>
              <th>Location</th>
              <th>Status</th>
              <th>Notes</th>
              <th>Actions</th>
            </tr>
          </thead>
          <tbody id="inventoryTbody"></tbody>
        </table>
      </section>

      <section class="card">
        <h3>Inventory Movement History</h3><div class="mobile-hint">Tip: swipe the table sideways on phone or tablet to see all columns.</div>
        <table>
          <thead>
            <tr>
              <th>Date</th>
              <th>Piece</th>
              <th>Type</th>
              <th>Qty</th>
              <th>Reference</th>
              <th>Handled by</th>
              <th>Project</th>
              <th>Notes</th>
            </tr>
          </thead>
          <tbody id="inventoryMovementsTbody"></tbody>
        </table>
      </section>
    </section>

    <section id="tab-reminders" class="section">
      <section class="card">
        <h3>Add / Edit Reminder</h3>
        <div class="grid-3">
          <label>Project
            <select id="reminderProjectId"></select>
          </label>
          <label>Title <input id="reminderTitle" type="text" placeholder="Buy screws"></label>
          <label>Priority
            <select id="reminderPriority">
              <option value="normal">Normal</option>
              <option value="high">High</option>
              <option value="urgent">Urgent</option>
            </select>
          </label>
        </div>
        <div class="grid-3">
          <label>Date <input id="reminderDate" type="date"></label>
          <label>Time <input id="reminderTime" type="time"></label>
          <label>Status
            <select id="reminderDone">
              <option value="false">Pending</option>
              <option value="true">Completed</option>
            </select>
          </label>
        </div>
        <label>Description <textarea id="reminderDescription"></textarea></label>
        <div class="inline-buttons">
          <button id="saveReminderBtn" class="btn-blue" type="button">Save Reminder</button>
          <button id="clearReminderBtn" type="button">Clear</button>
          <button id="deleteReminderBtn" class="btn-danger" type="button">Delete</button>
        </div>
        <p id="reminderStatusMsg"></p>
      </section>

      <section class="card">
        <h3>Reminders</h3>
        <table>
          <thead>
            <tr>
              <th>Project</th>
              <th>Title</th>
              <th>Description</th>
              <th>Date</th>
              <th>Time</th>
              <th>Priority</th>
              <th>Status</th>
              <th>Actions</th>
            </tr>
          </thead>
          <tbody id="remindersTbody"></tbody>
        </table>
      </section>
    </section>

    <section id="tab-reports" class="section">
      <div class="toolbar">
        <button id="openSearchBtn" type="button">Search Work Entries</button>
        <button id="exportBtn" type="button">Export Backup</button>
        <button id="importBtn" type="button">Import Backup</button>
        <input id="importFile" type="file" accept="application/json" style="display:none">
      </div>

      <div class="card">
        <h3>Backup & Restore <small id="backupLockStatus" class="muted">🔒 Locked</small></h3>
        <p class="muted">Backup includes work entries, history, projects, materials, reminders and inventory.</p>
      </div>

      <div class="card">
        <h3>Cloud Sync Ready Notes</h3>
        <p class="muted">This version saves data locally on each device. To share the same data between phone, tablet and computer, the next step is to connect the app to a cloud database such as Firebase.</p>
      </div>
    </section>
  </div>

  <dialog id="imgModal">
    <img id="modalImg" alt="Receipt">
    <button id="closeModalBtn" type="button">Close</button>
  </dialog>

  <dialog id="camModal">
    <video id="camVideo" autoplay playsinline></video>
    <button id="snapBtn" type="button">Snap</button>
    <button id="closeCamBtn" type="button">Close</button>
  </dialog>

  <dialog id="searchModal">
    <div>
      <h3>Search work entries</h3>
      <div class="grid-3">
        <label>Date <input id="searchDate" type="date"></label>
        <label>Project / Location <input id="searchLocation" type="text" placeholder="project name / address"></label>
        <label>Vendor <input id="searchVendor" type="text" placeholder="e.g., Home Depot"></label>
      </div>
      <div class="grid-3">
        <label>Description <input id="searchDesc" type="text" placeholder="keyword in description"></label>
        <label>Amount (exact) <input id="searchAmount" type="number" step="0.01" placeholder="e.g., 120"></label>
        <label>Project
          <select id="searchProjectId"></select>
        </label>
      </div>
      <div class="inline-buttons">
        <button id="runSearchBtn" type="button">Search</button>
        <button id="clearSearchBtn" type="button">Clear</button>
        <button id="printSearchBtn" type="button">Print results</button>
        <button id="closeSearchBtn" type="button">Close</button>
      </div>
      <table>
        <thead>
          <tr>
            <th>Date</th>
            <th>Project</th>
            <th>Hours</th>
            <th>Description</th>
            <th>Project / Location</th>
            <th>Vendor</th>
            <th>Expense</th>
          </tr>
        </thead>
        <tbody id="searchTbody"></tbody>
      </table>
    </div>
  </dialog>

  <dialog id="weekModal">
    <div>
      <h3>Weekly Summary</h3>
      <p id="weekRange"></p>
      <p><strong>Total hours:</strong> <span id="weekHours">0</span></p>
      <p><strong>Total expenses:</strong> <span id="weekExpenses">$0.00</span></p>
      <div class="inline-buttons">
        <button id="weekPrintBtn" class="btn" type="button">Print PDF</button>
        <button id="clearWeekBtn" class="btn-danger" type="button">Clear week</button>
        <button id="weekCloseBtn" type="button">Close</button>
      </div>
      <small>Note: clearing requires password.</small>
    </div>
  </dialog>

  <div id="errorBanner" class="error-banner"></div>

  <script>
    'use strict';

    function $(s){ return document.querySelector(s); }
    function $all(s){ return Array.from(document.querySelectorAll(s)); }
    function money(n){ return Number(n || 0).toLocaleString('en-US', {style:'currency',currency:'USD'}); }
    function escapeHtml(s){ return String(s == null ? '' : s).replace(/[&<>"']/g, function(c){ return {"&":"&amp;","<":"&lt;",">":"&gt;","\"":"&quot;","'":"&#39;"}[c]; }); }
    function nl2br(s){ return escapeHtml(s).replace(/\\n/g,'<br>'); }
    function localYYYYMMDD(d){ var dt=new Date(d); return dt.getFullYear()+'-'+String(dt.getMonth()+1).padStart(2,'0')+'-'+String(dt.getDate()).padStart(2,'0'); }
    function weekStartOf(date){ var d=new Date(date); var diff=(d.getDay()-5+7)%7; d.setDate(d.getDate()-diff); d.setHours(0,0,0,0); return d; }
    function weekEndOf(date){ var s=weekStartOf(date); s.setDate(s.getDate()+6); s.setHours(23,59,59,999); return s; }
    function checkPassword(){ var p=prompt('Enter password to confirm (hint: 123)'); return p==='123'; }
    function badgeClass(v){ return String(v || '').toLowerCase(); }
    function labelBadge(v){ return '<span class="pill '+badgeClass(v)+'">'+escapeHtml(v || '')+'</span>'; }

    function fillTimeSelects(){
      var startHour = $('#startHour');
      var startMinute = $('#startMinute');
      var endHour = $('#endHour');
      var endMinute = $('#endMinute');
      if(startHour && !startHour.options.length){
        startHour.innerHTML='<option value="">Hour</option>';
        endHour.innerHTML='<option value="">Hour</option>';
        for(var h=1; h<=12; h++){
          startHour.innerHTML += '<option value="'+h+'">'+h+'</option>';
          endHour.innerHTML += '<option value="'+h+'">'+h+'</option>';
        }
      }
      if(startMinute && !startMinute.options.length){
        startMinute.innerHTML='<option value="">Min</option>';
        endMinute.innerHTML='<option value="">Min</option>';
        for(var m=0; m<60; m++){
          var mm=String(m).padStart(2,'0');
          startMinute.innerHTML += '<option value="'+mm+'">'+mm+'</option>';
          endMinute.innerHTML += '<option value="'+mm+'">'+mm+'</option>';
        }
      }
    }

    function buildHourOptions(selected){
      var html='<option value="">Hr</option>';
      for(var h=1; h<=12; h++){
        html += '<option value="'+h+'"'+(String(selected)===String(h)?' selected':'')+'>'+h+'</option>';
      }
      return html;
    }
    function buildMinuteOptions(selected){
      var html='<option value="">Min</option>';
      for(var m=0; m<60; m++){
        var mm=String(m).padStart(2,'0');
        html += '<option value="'+mm+'"'+(String(selected)===mm?' selected':'')+'>'+mm+'</option>';
      }
      return html;
    }
    function buildAmpmOptions(selected){
      return '<option value="AM"'+(selected==='AM'?' selected':'')+'>AM</option><option value="PM"'+(selected==='PM'?' selected':'')+'>PM</option>';
    }

    function to24HourString(hour12, minute, ampm){
      if(!hour12 || minute === '' || !ampm) return '';
      var h=Number(hour12);
      if(ampm === 'AM'){ if(h===12) h=0; } else { if(h!==12) h+=12; }
      return String(h).padStart(2,'0')+':'+String(minute).padStart(2,'0');
    }
    function from24HourString(time24){
      if(!time24 || !time24.includes(':')) return {hour:'', minute:'', ampm:'AM'};
      var parts=time24.split(':');
      var h=Number(parts[0]);
      var m=String(parts[1]).padStart(2,'0');
      var ampm=h>=12 ? 'PM' : 'AM';
      h=h%12; if(h===0) h=12;
      return {hour:String(h), minute:m, ampm:ampm};
    }
    function setTimeFields(prefix, time24){
      var t=from24HourString(time24);
      var hourEl=$('#'+prefix+'Hour');
      var minuteEl=$('#'+prefix+'Minute');
      var ampmEl=$('#'+prefix+'Ampm');
      if(hourEl) hourEl.value=t.hour;
      if(minuteEl) minuteEl.value=t.minute;
      if(ampmEl) ampmEl.value=t.ampm;
    }
    function getTimeFields(prefix){
      var hourEl=$('#'+prefix+'Hour');
      var minuteEl=$('#'+prefix+'Minute');
      var ampmEl=$('#'+prefix+'Ampm');
      return to24HourString(hourEl ? hourEl.value : '', minuteEl ? minuteEl.value : '', ampmEl ? ampmEl.value : '');
    }
    function formatTime12(time24){
      if(!time24 || !time24.includes(':')) return '';
      var t=from24HourString(time24);
      return t.hour+':'+t.minute+' '+t.ampm;
    }
    function calculateHoursFrom24Range(start, end){
      if(!start || !end) return null;
      var a=start.split(':'), b=end.split(':');
      var sMin=Number(a[0])*60+Number(a[1]);
      var eMin=Number(b[0])*60+Number(b[1]);
      if(eMin < sMin) eMin += 24*60;
      return parseFloat(((eMin-sMin)/60).toFixed(2));
    }
    function recalcHoursFromTimeFields(){
      var start=getTimeFields('start');
      var end=getTimeFields('end');
      var hoursEl=$('#hours');
      if(!hoursEl || !start || !end) return;
      var calc=calculateHoursFrom24Range(start,end);
      if(calc !== null) hoursEl.value=calc.toFixed(2);
    }
    function bindTimeAutoRecalc(){
      ['startHour','startMinute','startAmpm','endHour','endMinute','endAmpm'].forEach(function(id){
        var el=document.getElementById(id);
        if(el) el.addEventListener('change', recalcHoursFromTimeFields);
      });
    }

    function getBatchTime24(prefix, row){
      var h = row.querySelector('.'+prefix+'-hour').value;
      var m = row.querySelector('.'+prefix+'-minute').value;
      var ap = row.querySelector('.'+prefix+'-ampm').value;
      return to24HourString(h,m,ap);
    }

    function createBatchWorklogRow(data){
      data = data || {};
      var s = from24HourString(data.start || '');
      var e = from24HourString(data.end || '');
      return '<tr>'+
        '<td><div class="time-row"><select class="batch-start-hour">'+buildHourOptions(s.hour)+'</select><select class="batch-start-minute">'+buildMinuteOptions(s.minute)+'</select><select class="batch-start-ampm">'+buildAmpmOptions(s.ampm)+'</select></div></td>'+
        '<td><div class="time-row"><select class="batch-end-hour">'+buildHourOptions(e.hour)+'</select><select class="batch-end-minute">'+buildMinuteOptions(e.minute)+'</select><select class="batch-end-ampm">'+buildAmpmOptions(e.ampm)+'</select></div></td>'+
        '<td><input class="batch-work-hours" type="number" step="0.01" value="'+escapeHtml(data.hours != null ? data.hours : '')+'" placeholder="auto"></td>'+
        '<td><input class="batch-work-task" type="text" value="'+escapeHtml(data.task || '')+'" placeholder="what was done"></td>'+
        '<td><input class="batch-work-location" type="text" value="'+escapeHtml(data.location || '')+'" placeholder="location"></td>'+
        '<td><input class="batch-work-vendor" type="text" value="'+escapeHtml(data.vendor || '')+'" placeholder="vendor"></td>'+
        '<td><input class="batch-work-amount" type="number" step="0.01" value="'+escapeHtml(data.amount != null ? data.amount : '')+'"></td>'+
        '<td class="actions-col"><button class="remove-batch-work-row-btn" type="button">Remove</button></td>'+
      '</tr>';
    }

    function initBatchWorklogRows(){
      var tbody=$('#batchWorklogTbody');
      if(!tbody) return;
      tbody.innerHTML='';
      for(var i=0;i<4;i++) tbody.insertAdjacentHTML('beforeend', createBatchWorklogRow());
    }

    function createBatchMaterialRow(data){
      data = data || {};
      return '<tr>'+
        '<td><input class="batch-qty" type="number" step="0.01" value="'+escapeHtml(data.qty != null ? data.qty : '')+'"></td>'+
        '<td><input class="batch-material" type="text" value="'+escapeHtml(data.material || '')+'" placeholder="material"></td>'+
        '<td><input class="batch-unit" type="text" value="'+escapeHtml(data.unit || '')+'" placeholder="unit"></td>'+
        '<td><input class="batch-store" type="text" value="'+escapeHtml(data.store || '')+'" placeholder="store"></td>'+
        '<td><input class="batch-price" type="number" step="0.01" value="'+escapeHtml(data.price != null ? data.price : '')+'"></td>'+
        '<td><input class="batch-notes" type="text" value="'+escapeHtml(data.notes || '')+'" placeholder="notes"></td>'+
        '<td class="actions-col"><button class="remove-batch-row-btn" type="button">Remove</button></td>'+
      '</tr>';
    }

    function initBatchMaterialRows(){
      var tbody=$('#batchMaterialsTbody');
      if(!tbody) return;
      tbody.innerHTML='';
      for(var i=0;i<4;i++) tbody.insertAdjacentHTML('beforeend', createBatchMaterialRow());
    }

    var DB_NAME='planner_suite_db';
    var DB_VERSION=6;
    var ENTRY_STORE='entries';
    var HISTORY_STORE='history';
    var PROJECT_STORE='projects';
    var MATERIAL_STORE='materials';
    var REMINDER_STORE='reminders';
    var INVENTORY_STORE='inventory';
    var INVENTORY_MOVEMENT_STORE='inventory_movements';
    var dbPromise=null;
    var lastSearchHTML='';
    var reminderTicker=null;

    function openDB(){
      if(dbPromise) return dbPromise;
      dbPromise = new Promise(function(resolve,reject){
        var request=indexedDB.open(DB_NAME, DB_VERSION);
        request.onupgradeneeded=function(event){
          var db=event.target.result;
          var tx=event.target.transaction;

          if(!db.objectStoreNames.contains(ENTRY_STORE)){
            var entryStore=db.createObjectStore(ENTRY_STORE,{keyPath:'id'});
            entryStore.createIndex('date','date',{unique:false});
            entryStore.createIndex('updatedAt','updatedAt',{unique:false});
          } else {
            var upgradedEntryStore=tx.objectStore(ENTRY_STORE);
            if(!upgradedEntryStore.indexNames.contains('updatedAt')) upgradedEntryStore.createIndex('updatedAt','updatedAt',{unique:false});
          }

          if(!db.objectStoreNames.contains(HISTORY_STORE)){
            var historyStore=db.createObjectStore(HISTORY_STORE,{keyPath:'ts'});
            historyStore.createIndex('date','date',{unique:false});
          }

          if(!db.objectStoreNames.contains(PROJECT_STORE)){
            var projectStore=db.createObjectStore(PROJECT_STORE,{keyPath:'id'});
            projectStore.createIndex('name','name',{unique:false});
            projectStore.createIndex('status','status',{unique:false});
          }

          if(!db.objectStoreNames.contains(MATERIAL_STORE)){
            var materialStore=db.createObjectStore(MATERIAL_STORE,{keyPath:'id'});
            materialStore.createIndex('projectId','projectId',{unique:false});
            materialStore.createIndex('status','status',{unique:false});
          }

          if(!db.objectStoreNames.contains(REMINDER_STORE)){
            var reminderStore=db.createObjectStore(REMINDER_STORE,{keyPath:'id'});
            reminderStore.createIndex('projectId','projectId',{unique:false});
            reminderStore.createIndex('dueDate','dueDate',{unique:false});
            reminderStore.createIndex('completed','completed',{unique:false});
          }

          if(!db.objectStoreNames.contains(INVENTORY_STORE)){
            var inventoryStore=db.createObjectStore(INVENTORY_STORE,{keyPath:'id'});
            inventoryStore.createIndex('name','name',{unique:false});
            inventoryStore.createIndex('projectId','projectId',{unique:false});
            inventoryStore.createIndex('sku','sku',{unique:false});
            inventoryStore.createIndex('updatedAt','updatedAt',{unique:false});
          }

          if(!db.objectStoreNames.contains(INVENTORY_MOVEMENT_STORE)){
            var movementStore=db.createObjectStore(INVENTORY_MOVEMENT_STORE,{keyPath:'id'});
            movementStore.createIndex('itemId','itemId',{unique:false});
            movementStore.createIndex('date','date',{unique:false});
            movementStore.createIndex('type','type',{unique:false});
          }
        };
        request.onsuccess=function(){ resolve(request.result); };
        request.onerror=function(){ reject(request.error); };
      });
      return dbPromise;
    }

    async function getAllFromStore(storeName){
      var db=await openDB();
      return new Promise(function(resolve,reject){
        var tx=db.transaction(storeName,'readonly');
        var req=tx.objectStore(storeName).getAll();
        req.onsuccess=function(){ resolve(req.result || []); };
        req.onerror=function(){ reject(req.error); };
      });
    }
    async function putInStore(storeName, value){
      var db=await openDB();
      return new Promise(function(resolve,reject){
        var tx=db.transaction(storeName,'readwrite');
        tx.objectStore(storeName).put(value);
        tx.oncomplete=function(){ resolve(true); };
        tx.onerror=function(){ reject(tx.error); };
      });
    }
    async function deleteFromStore(storeName, key){
      var db=await openDB();
      return new Promise(function(resolve,reject){
        var tx=db.transaction(storeName,'readwrite');
        tx.objectStore(storeName).delete(key);
        tx.oncomplete=function(){ resolve(true); };
        tx.onerror=function(){ reject(tx.error); };
      });
    }
    async function clearStore(storeName){
      var db=await openDB();
      return new Promise(function(resolve,reject){
        var tx=db.transaction(storeName,'readwrite');
        tx.objectStore(storeName).clear();
        tx.oncomplete=function(){ resolve(true); };
        tx.onerror=function(){ reject(tx.error); };
      });
    }
    async function replaceStore(storeName, items){
      var db=await openDB();
      return new Promise(function(resolve,reject){
        var tx=db.transaction(storeName,'readwrite');
        var store=tx.objectStore(storeName);
        store.clear();
        (items || []).forEach(function(item){ store.put(item); });
        tx.oncomplete=function(){ resolve(true); };
        tx.onerror=function(){ reject(tx.error); };
      });
    }

    async function loadAllEntries(){
      var rows=await getAllFromStore(ENTRY_STORE);
      rows.sort(function(a,b){
        return String(b.date || '').localeCompare(String(a.date || '')) || Number(b.updatedAt || 0)-Number(a.updatedAt || 0);
      });
      return rows;
    }
    async function loadHistory(){
      var rows=await getAllFromStore(HISTORY_STORE);
      rows.sort(function(a,b){ return Number(a.ts || 0)-Number(b.ts || 0); });
      return rows;
    }
    async function loadProjects(){
      var rows=await getAllFromStore(PROJECT_STORE);
      rows.sort(function(a,b){ return String(a.name || '').localeCompare(String(b.name || '')); });
      return rows;
    }
    async function loadMaterials(){
      var rows=await getAllFromStore(MATERIAL_STORE);
      rows.sort(function(a,b){ return Number(b.createdAt || 0)-Number(a.createdAt || 0); });
      return rows;
    }
    async function loadReminders(){
      var rows=await getAllFromStore(REMINDER_STORE);
      rows.sort(function(a,b){
        return String(a.dueDate || '').localeCompare(String(b.dueDate || '')) || String(a.dueTime || '').localeCompare(String(b.dueTime || ''));
      });
      return rows;
    }
    async function loadInventory(){
      var rows=await getAllFromStore(INVENTORY_STORE);
      rows.sort(function(a,b){
        return String(a.name || '').localeCompare(String(b.name || '')) || Number(b.updatedAt || 0)-Number(a.updatedAt || 0);
      });
      return rows;
    }
    async function loadInventoryMovements(){
      var rows=await getAllFromStore(INVENTORY_MOVEMENT_STORE);
      rows.sort(function(a,b){
        return String(b.date || '').localeCompare(String(a.date || '')) || Number(b.createdAt || 0)-Number(a.createdAt || 0);
      });
      return rows;
    }

    async function addHistory(item){
      var hist=await loadHistory();
      hist.push(item);
      if(hist.length > 100){
        hist=hist.slice(hist.length-100);
        await replaceStore(HISTORY_STORE, hist);
        return;
      }
      await putInStore(HISTORY_STORE, item);
    }

    function getSelectedBaseDate(){ return $('#calendarDate') && $('#calendarDate').value ? new Date($('#calendarDate').value+'T00:00:00') : new Date(); }
    function inSelectedView(entryDateStr){
      if(!entryDateStr) return false;
      var base=getSelectedBaseDate();
      var mode=$('#viewMode') ? $('#viewMode').value : 'week';
      var d=new Date(entryDateStr+'T00:00:00');
      if(mode==='day') return localYYYYMMDD(d)===localYYYYMMDD(base);
      if(mode==='week') return d>=weekStartOf(base) && d<=weekEndOf(base);
      if(mode==='month') return d.getFullYear()===base.getFullYear() && d.getMonth()===base.getMonth();
      if(mode==='year') return d.getFullYear()===base.getFullYear();
      return true;
    }

    function showError(err){
      console.error(err);
      var b=document.getElementById('errorBanner');
      if(!b) return;
      b.style.display='block';
      b.textContent='Error: '+(err && err.message ? err.message : err);
    }
    window.addEventListener('error', function(e){ showError(e.error || e.message); });

    function projectNameById(projects, id){
      var item=projects.find(function(p){ return String(p.id)===String(id); });
      return item ? item.name : '';
    }

    function inventoryStatusLabel(item){
      var qty=Number(item.qty || 0);
      var min=Number(item.minStock || 0);
      if(qty <= 0) return 'out';
      if(min > 0 && qty <= min) return 'low';
      return 'ok';
    }

    function inventoryItemLabel(item){
      return (item.name || '') + ' — ' + (Number(item.qty || 0)) + ' ' + (item.unit || '');
    }

    function populateProjectSelect(selectId, projects, includeBlankLabel){
      var el=document.getElementById(selectId);
      if(!el) return;
      var html='';
      html += '<option value="">'+escapeHtml(includeBlankLabel || 'No project')+'</option>';
      projects.forEach(function(p){ html += '<option value="'+p.id+'">'+escapeHtml(p.name || '')+'</option>'; });
      el.innerHTML=html;
    }

    function switchTab(tabName){
      $all('.tab-btn').forEach(function(btn){ btn.classList.toggle('active', btn.getAttribute('data-tab')===tabName); });
      $all('.section').forEach(function(sec){ sec.classList.toggle('active', sec.id==='tab-'+tabName); });
    }

    function openPrintHTML(htmlString){
      var iframe=document.createElement('iframe');
      iframe.style.position='fixed'; iframe.style.right='0'; iframe.style.bottom='0'; iframe.style.width='0'; iframe.style.height='0'; iframe.style.border='0';
      document.body.appendChild(iframe);
      var doc=iframe.contentDocument || iframe.contentWindow.document;
      doc.open(); doc.write(htmlString); doc.close();
      setTimeout(function(){ try{ iframe.contentWindow.focus(); iframe.contentWindow.print(); }catch(_){} },250);
      setTimeout(function(){ if(document.body.contains(iframe)) document.body.removeChild(iframe); },3000);
    }

    function printShoppingListForProject(projectName, items){
      var totalEstimate = items.reduce(function(t,m){ return t + (Number(m.price)||0); },0);
      var rows = items.map(function(m){
        return '<tr>'+
          '<td>'+escapeHtml(m.material || '')+'</td>'+
          '<td>'+escapeHtml(m.qty != null ? m.qty : '')+'</td>'+
          '<td>'+escapeHtml(m.unit || '')+'</td>'+
          '<td>'+escapeHtml(m.store || '')+'</td>'+
          '<td>'+(m.price ? money(m.price) : '')+'</td>'+
          '<td>'+escapeHtml(m.notes || '')+'</td>'+
          '<td>'+escapeHtml(m.status || '')+'</td>'+
        '</tr>';
      }).join('');

      var html='<!DOCTYPE html><html><head><meta charset="utf-8"><title>Shopping List</title><style>@page{size:portrait;margin:12mm;} body{font-family:Arial;margin:16px;color:#222} table{width:100%;border-collapse:collapse} th,td{border:1px solid #999;padding:6px;vertical-align:top} th{background:#eee} .head{display:flex;justify-content:space-between;align-items:flex-end;border-bottom:2px solid #333;padding-bottom:8px;margin-bottom:12px}</style></head><body>'+
      '<div class="head"><div><h2 style="margin:0">Shopping List</h2><div><b>Project:</b> '+escapeHtml(projectName)+'</div></div><div><b>Items:</b> '+items.length+'<br><b>Est. total:</b> '+money(totalEstimate)+'</div></div>'+
      '<table><thead><tr><th>Material</th><th>Qty</th><th>Unit</th><th>Store</th><th>Est. price</th><th>Notes</th><th>Status</th></tr></thead><tbody>'+rows+'</tbody></table>'+
      '</body></html>';

      openPrintHTML(html);
    }

    async function printInventorySheet(){
      var projects=await loadProjects();
      var items=await loadInventory();

      var rows=items.map(function(i){
        return '<tr>'+
          '<td>'+escapeHtml(i.name || '')+'</td>'+
          '<td>'+escapeHtml(i.sku || '')+'</td>'+
          '<td>'+escapeHtml(i.category || '')+'</td>'+
          '<td>'+escapeHtml(projectNameById(projects, i.projectId) || '')+'</td>'+
          '<td>'+escapeHtml(i.qty != null ? i.qty : '')+'</td>'+
          '<td>'+escapeHtml(i.unit || '')+'</td>'+
          '<td>'+escapeHtml(i.location || '')+'</td>'+
          '<td>'+escapeHtml(inventoryStatusLabel(i))+'</td>'+
          '<td>'+escapeHtml(i.notes || '')+'</td>'+
        '</tr>';
      }).join('');

      var html='<!DOCTYPE html><html><head><meta charset="utf-8"><title>Inventory Sheet</title><style>@page{size:landscape;margin:10mm;} body{font-family:Arial;margin:16px;color:#222} table{width:100%;border-collapse:collapse} th,td{border:1px solid #999;padding:6px;vertical-align:top} th{background:#eee} .head{display:flex;justify-content:space-between;align-items:flex-end;border-bottom:2px solid #333;padding-bottom:8px;margin-bottom:12px}</style></head><body>'+
      '<div class="head"><div><h2 style="margin:0">Inventory Sheet</h2><div><b>Generated:</b> '+new Date().toLocaleString()+'</div></div><div><b>Total items:</b> '+items.length+'</div></div>'+
      '<table><thead><tr><th>Piece</th><th>Code</th><th>Category</th><th>Project</th><th>Remaining</th><th>Unit</th><th>Location</th><th>Status</th><th>Notes</th></tr></thead><tbody>'+rows+'</tbody></table>'+
      '</body></html>';

      openPrintHTML(html);
    }

    var editingEntryId=null, editingProjectId=null, editingMaterialId=null, editingReminderId=null, editingInventoryId=null;

    async function renderAll(){
      var projects=await loadProjects();
      populateProjectSelect('entryProjectId', projects, 'No project');
      populateProjectSelect('batchEntryProjectId', projects, 'No project');
      populateProjectSelect('materialProjectId', projects, 'Choose project');
      populateProjectSelect('batchMaterialProjectId', projects, 'Choose project');
      populateProjectSelect('reminderProjectId', projects, 'No project');
      populateProjectSelect('searchProjectId', projects, 'All projects');
      populateProjectSelect('inventoryProjectId', projects, 'No project');
      populateProjectSelect('movementProjectId', projects, 'No project');
      populateProjectSelect('inventorySearchProjectId', projects, 'All projects');
      await Promise.all([
        renderDashboard(), renderEntries(projects), renderHistory(), renderProjects(), renderMaterials(projects), renderReminders(projects), renderInventory(projects)
      ]);
    }

    async function renderDashboard(){
      var projects=await loadProjects();
      var materials=await loadMaterials();
      var reminders=await loadReminders();
      var entries=await loadAllEntries();
      var today=localYYYYMMDD(new Date());
      var weekStart=weekStartOf(new Date()), weekEnd=weekEndOf(new Date());
      var activeProjects=projects.filter(function(p){ return String(p.status||'').toLowerCase()==='active'; }).length;
      var pendingMaterials=materials.filter(function(m){ return String(m.status||'').toLowerCase()!=='bought'; }).length;
      var todayReminders=reminders.filter(function(r){ return !r.completed && r.dueDate && r.dueDate<=today; }).length;
      var weekHours=entries.filter(function(e){ var d=new Date((e.date||'')+'T00:00:00'); return d>=weekStart && d<=weekEnd; }).reduce(function(t,e){ return t+(Number(e.hours)||0); },0);
      $('#dashProjects').textContent=activeProjects;
      $('#dashMaterials').textContent=pendingMaterials;
      $('#dashTodayReminders').textContent=todayReminders;
      $('#dashWeekHours').textContent=weekHours.toFixed(2);

      var list=$('#todayReminderList');
      var dueList=reminders.filter(function(r){ return !r.completed && r.dueDate && r.dueDate<=today; });
      if(!dueList.length){ list.innerHTML='<div class="muted">No reminders for now.</div>'; return; }
      list.innerHTML = dueList.map(function(r){
        var project=projectNameById(projects, r.projectId);
        var overdue = r.dueDate < today ? 'Overdue' : 'Today';
        return '<div style="padding:8px 0;border-bottom:1px solid #eee"><div class="todo-due">'+escapeHtml(overdue)+' - '+escapeHtml(r.title || '')+'</div><div>'+escapeHtml(project || 'No project')+(r.dueTime ? ' • '+escapeHtml(r.dueTime) : '')+'</div><div class="muted">'+escapeHtml(r.description || '')+'</div></div>';
      }).join('');
    }

    async function renderEntries(projects){
      var tbody=$('#tbody');
      var rows=(await loadAllEntries()).filter(function(e){ return inSelectedView(e.date); });
      tbody.innerHTML='';
      var frag=document.createDocumentFragment();
      rows.forEach(function(e){
        var tr=document.createElement('tr');
        var timeRange=(e.start || e.end) ? escapeHtml(formatTime12(e.start || ''))+'–'+escapeHtml(formatTime12(e.end || '')) : '';
        tr.innerHTML='<td>'+escapeHtml(e.date || '')+'</td>'+
          '<td>'+escapeHtml(projectNameById(projects, e.projectId) || '')+'</td>'+
          '<td>'+timeRange+'</td>'+
          '<td>'+escapeHtml(e.hours != null ? e.hours : '')+'</td>'+
          '<td>'+nl2br(e.task || '')+'</td>'+
          '<td>'+escapeHtml(e.location || '')+'</td>'+
          '<td>'+escapeHtml(e.vendor || '')+'</td>'+
          '<td>'+(e.amount ? money(e.amount) : '')+'</td>'+
          '<td>'+(e.receipt ? '<img src="'+e.receipt+'" style="max-width:60px;cursor:pointer">' : '')+'</td>'+
          '<td class="actions-col"><button class="edit-entry-btn" data-id="'+e.id+'" type="button">Edit</button><button class="delete-entry-btn" data-id="'+e.id+'" type="button">Delete</button></td>';
        frag.appendChild(tr);
      });
      if(!rows.length){
        var trEmpty=document.createElement('tr');
        trEmpty.innerHTML='<td colspan="10" style="text-align:center;color:#666">No entries for selected view</td>';
        frag.appendChild(trEmpty);
      }
      tbody.appendChild(frag);
    }

    async function renderHistory(){
      var list=$('#historyList');
      var h=await loadHistory();
      list.innerHTML='';
      var frag=document.createDocumentFragment();
      for(var i=h.length-1;i>=0;i--){
        var li=document.createElement('li');
        var e=h[i];
        li.textContent=(e.date || '')+' • '+(e.vendor || '')+' • '+(e.hours || 0)+'h • '+(e.amount ? money(e.amount) : '$0.00');
        frag.appendChild(li);
      }
      list.appendChild(frag);
    }

    async function renderProjects(){
      var tbody=$('#projectsTbody');
      var rows=await loadProjects();
      tbody.innerHTML=rows.map(function(p){
        return '<tr>'+
          '<td>'+escapeHtml(p.name || '')+'</td>'+
          '<td>'+escapeHtml(p.location || '')+'</td>'+
          '<td>'+escapeHtml(p.client || '')+'</td>'+
          '<td>'+labelBadge(p.status || '')+'</td>'+
          '<td>'+escapeHtml(p.startDate || '')+'</td>'+
          '<td>'+nl2br(p.notes || '')+'</td>'+
          '<td class="actions-col"><button class="edit-project-btn" data-id="'+p.id+'" type="button">Edit</button><button class="delete-project-row-btn" data-id="'+p.id+'" type="button">Delete</button></td>'+
        '</tr>';
      }).join('') || '<tr><td colspan="7" style="text-align:center;color:#666">No projects yet</td></tr>';
    }

    async function renderMaterials(projects){
      var wrap=$('#materialsGroupedList');
      var rows=await loadMaterials();
      if(!rows.length){
        wrap.innerHTML='<div class="muted">No materials yet</div>';
        return;
      }

      var grouped={};
      rows.forEach(function(m){
        var key=String(m.projectId || '');
        if(!grouped[key]) grouped[key]=[];
        grouped[key].push(m);
      });

      var projectKeys=Object.keys(grouped).sort(function(a,b){
        return String(projectNameById(projects,a) || 'No project').localeCompare(String(projectNameById(projects,b) || 'No project'));
      });

      wrap.innerHTML=projectKeys.map(function(projectId){
        var items=grouped[projectId];
        var projectLabel=projectNameById(projects, projectId) || 'No project';
        var totalEstimate=items.reduce(function(t,m){ return t + (Number(m.price)||0); },0);
        return '<div class="card project-block">'+
          '<div style="display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap;align-items:center">'+
            '<div><h4 style="margin:0">'+escapeHtml(projectLabel)+'</h4><div class="muted"><b>Items:</b> '+items.length+' &nbsp; | &nbsp; <b>Est. total:</b> '+money(totalEstimate)+'</div></div>'+
            '<div class="inline-buttons" style="margin-top:0"><button class="btn-amber print-shopping-btn" data-project="'+escapeHtml(projectId)+'" type="button">Print Shopping List</button></div>'+
          '</div>'+
          '<table>'+
            '<thead>'+
              '<tr>'+
                '<th>Material</th>'+
                '<th>Qty</th>'+
                '<th>Unit</th>'+
                '<th>Store</th>'+
                '<th>Est. price</th>'+
                '<th>Status</th>'+
                '<th>Notes</th>'+
                '<th>Actions</th>'+
              '</tr>'+
            '</thead>'+
            '<tbody>'+
              items.map(function(m){
                return '<tr>'+
                  '<td>'+escapeHtml(m.material || '')+'</td>'+
                  '<td>'+escapeHtml(m.qty != null ? m.qty : '')+'</td>'+
                  '<td>'+escapeHtml(m.unit || '')+'</td>'+
                  '<td>'+escapeHtml(m.store || '')+'</td>'+
                  '<td>'+(m.price ? money(m.price) : '')+'</td>'+
                  '<td>'+labelBadge(m.status || '')+'</td>'+
                  '<td>'+nl2br(m.notes || '')+'</td>'+
                  '<td class="actions-col"><button class="edit-material-btn" data-id="'+m.id+'" type="button">Edit</button><button class="delete-material-row-btn" data-id="'+m.id+'" type="button">Delete</button></td>'+
                '</tr>';
              }).join('')+
            '</tbody>'+
          '</table>'+
        '</div>';
      }).join('');
    }

    async function renderInventory(projects){
      var allItems=await loadInventory();
      var movements=await loadInventoryMovements();
      var items=allItems.slice();
      var searchTerm=($('#inventorySearch') ? $('#inventorySearch').value.trim().toLowerCase() : '');
      var projectFilter=($('#inventorySearchProjectId') ? $('#inventorySearchProjectId').value : '');
      var stockFilter=($('#inventoryStockFilter') ? $('#inventoryStockFilter').value : '');

      if(projectFilter){
        items=items.filter(function(i){ return String(i.projectId || '')===String(projectFilter); });
      }

      if(searchTerm){
        items=items.filter(function(i){
          return String(i.name || '').toLowerCase().indexOf(searchTerm)!==-1 ||
                 String(i.sku || '').toLowerCase().indexOf(searchTerm)!==-1 ||
                 String(i.category || '').toLowerCase().indexOf(searchTerm)!==-1 ||
                 String(i.location || '').toLowerCase().indexOf(searchTerm)!==-1;
        });
      }

      if(stockFilter==='low'){
        items=items.filter(function(i){ return inventoryStatusLabel(i)==='low'; });
      }
      if(stockFilter==='out'){
        items=items.filter(function(i){ return inventoryStatusLabel(i)==='out'; });
      }

      var invTbody=$('#inventoryTbody');
      invTbody.innerHTML=items.map(function(i){
        var status=inventoryStatusLabel(i);
        return '<tr>'+
          '<td>'+escapeHtml(i.name || '')+'</td>'+
          '<td>'+escapeHtml(i.sku || '')+'</td>'+
          '<td>'+escapeHtml(i.category || '')+'</td>'+
          '<td>'+escapeHtml(projectNameById(projects, i.projectId) || '')+'</td>'+
          '<td>'+escapeHtml(i.initialQty != null ? i.initialQty : '')+'</td>'+
          '<td>'+escapeHtml(i.unit || '')+'</td>'+
          '<td>'+escapeHtml(i.minStock != null ? i.minStock : '')+'</td>'+
          '<td><b>'+escapeHtml(i.qty != null ? i.qty : '')+'</b></td>'+
          '<td>'+escapeHtml(i.location || '')+'</td>'+
          '<td>'+labelBadge(status)+'</td>'+
          '<td>'+nl2br(i.notes || '')+'</td>'+
          '<td class="actions-col"><button class="edit-inventory-btn" data-id="'+i.id+'" type="button">Edit</button><button class="delete-inventory-row-btn" data-id="'+i.id+'" type="button">Delete</button></td>'+
        '</tr>';
      }).join('') || '<tr><td colspan="12" style="text-align:center;color:#666">No inventory items yet</td></tr>';

      var movementSelect=$('#movementItemId');
      if(movementSelect){
        movementSelect.innerHTML='<option value="">Choose item</option>' + allItems.map(function(i){
          return '<option value="'+i.id+'">'+escapeHtml(inventoryItemLabel(i))+'</option>';
        }).join('');
      }

      var movTbody=$('#inventoryMovementsTbody');
      movTbody.innerHTML=movements.map(function(m){
        var item=(allItems.find(function(i){ return String(i.id)===String(m.itemId); }) || {});
        return '<tr>'+
          '<td>'+escapeHtml(m.date || '')+'</td>'+
          '<td>'+escapeHtml(m.itemName || item.name || '')+'</td>'+
          '<td>'+labelBadge(m.type === 'in' ? 'active' : 'pending')+' '+escapeHtml(m.type || '')+'</td>'+
          '<td>'+escapeHtml(m.qty != null ? m.qty : '')+'</td>'+
          '<td>'+escapeHtml(m.reference || '')+'</td>'+
          '<td>'+escapeHtml(m.user || '')+'</td>'+
          '<td>'+escapeHtml(projectNameById(projects, m.projectId) || '')+'</td>'+
          '<td>'+nl2br(m.notes || '')+'</td>'+
        '</tr>';
      }).join('') || '<tr><td colspan="8" style="text-align:center;color:#666">No inventory movements yet</td></tr>';
    }

    async function renderReminders(projects){
      var tbody=$('#remindersTbody');
      var rows=await loadReminders();
      tbody.innerHTML=rows.map(function(r){
        return '<tr>'+
          '<td>'+escapeHtml(projectNameById(projects, r.projectId) || '')+'</td>'+
          '<td>'+escapeHtml(r.title || '')+'</td>'+
          '<td>'+nl2br(r.description || '')+'</td>'+
          '<td>'+escapeHtml(r.dueDate || '')+'</td>'+
          '<td>'+escapeHtml(r.dueTime || '')+'</td>'+
          '<td>'+escapeHtml(r.priority || '')+'</td>'+
          '<td>'+labelBadge(r.completed ? 'done' : 'pending')+'</td>'+
          '<td class="actions-col"><button class="edit-reminder-btn" data-id="'+r.id+'" type="button">Edit</button><button class="toggle-reminder-btn" data-id="'+r.id+'" type="button">'+(r.completed ? 'Undo' : 'Done')+'</button><button class="delete-reminder-row-btn" data-id="'+r.id+'" type="button">Delete</button></td>'+
        '</tr>';
      }).join('') || '<tr><td colspan="8" style="text-align:center;color:#666">No reminders yet</td></tr>';
    }

    function resetEntryForm(){
      editingEntryId=null;
      $('#date').value=localYYYYMMDD(new Date());
      $('#entryProjectId').value='';
      $('#hours').value='';
      $('#startHour').value=''; $('#startMinute').value=''; $('#startAmpm').value='AM';
      $('#endHour').value=''; $('#endMinute').value=''; $('#endAmpm').value='AM';
      $('#location').value=''; $('#task').value=''; $('#vendor').value=''; $('#amount').value=''; $('#thumb').innerHTML=''; $('#receiptInput').value=''; $('#status').textContent='';
      $('#batchEntryDate').value=localYYYYMMDD(new Date());
      $('#batchEntryProjectId').value='';
      $('#batchEntryLocation').value='';
      $('#batchWorklogStatusMsg').textContent='';
      initBatchWorklogRows();
    }
    function resetProjectForm(){ editingProjectId=null; $('#projectName').value=''; $('#projectLocation').value=''; $('#projectClient').value=''; $('#projectStatus').value='active'; $('#projectStartDate').value=''; $('#projectNotes').value=''; $('#projectStatusMsg').textContent=''; }
    function resetMaterialForm(){ editingMaterialId=null; $('#materialProjectId').value=''; $('#materialName').value=''; $('#materialQty').value=''; $('#materialUnit').value=''; $('#materialStore').value=''; $('#materialPrice').value=''; $('#materialStatus').value='pending'; $('#materialNotes').value=''; $('#batchMaterialProjectId').value=''; $('#batchMaterialStore').value=''; $('#batchMaterialStatus').value='pending'; $('#materialStatusMsg').textContent=''; $('#batchMaterialStatusMsg').textContent=''; initBatchMaterialRows(); }
    function resetReminderForm(){ editingReminderId=null; $('#reminderProjectId').value=''; $('#reminderTitle').value=''; $('#reminderDescription').value=''; $('#reminderDate').value=''; $('#reminderTime').value=''; $('#reminderPriority').value='normal'; $('#reminderDone').value='false'; $('#reminderStatusMsg').textContent=''; }
    function resetInventoryForm(){
      editingInventoryId=null;
      $('#inventoryProjectId').value='';
      $('#inventoryName').value='';
      $('#inventorySku').value='';
      $('#inventoryCategory').value='';
      $('#inventoryQty').value='';
      $('#inventoryUnit').value='';
      $('#inventoryMinStock').value='';
      $('#inventoryLocation').value='';
      $('#inventoryNotes').value='';
      $('#inventoryStatusMsg').textContent='';

      $('#movementItemId').value='';
      $('#movementType').value='in';
      $('#movementQty').value='';
      $('#movementDate').value=localYYYYMMDD(new Date());
      $('#movementRef').value='';
      $('#movementUser').value='';
      $('#movementProjectId').value='';
      $('#movementNotes').value='';
      $('#movementStatusMsg').textContent='';
      $('#inventorySearch').value='';
      $('#inventorySearchProjectId').value='';
      $('#inventoryStockFilter').value='';
    }

    function notifyReminder(title, body){
      try{
        if('Notification' in window && Notification.permission === 'granted'){
          new Notification(title, { body: body || '' });
          return;
        }
      }catch(_){}
      alert(title + (body ? '\\n\\n'+body : ''));
    }

    async function reminderWatcher(){
      var reminders=await loadReminders();
      var now=new Date();
      var today=localYYYYMMDD(now);
      var hh=String(now.getHours()).padStart(2,'0');
      var mm=String(now.getMinutes()).padStart(2,'0');
      var current=hh+':'+mm;
      var projects=await loadProjects();
      for(var i=0;i<reminders.length;i++){
        var r=reminders[i];
        if(r.completed) continue;
        if(!r.dueDate || !r.dueTime) continue;
        if(r.dueDate !== today) continue;
        if(r.dueTime !== current) continue;
        if(r.lastAlertAt === today+' '+current) continue;
        r.lastAlertAt=today+' '+current;
        await putInStore(REMINDER_STORE, r);
        notifyReminder('Reminder: '+(r.title || ''), (projectNameById(projects, r.projectId) || 'No project') + (r.description ? '\\n'+r.description : ''));
      }
      await renderDashboard();
    }

    function startReminderWatcher(){
      if('Notification' in window && Notification.permission === 'default'){
        Notification.requestPermission().catch(function(){});
      }
      if(reminderTicker) clearInterval(reminderTicker);
      reminderTicker=setInterval(function(){ reminderWatcher().catch(showError); }, 30000);
      reminderWatcher().catch(showError);
    }

    async function doSearch(){
      var all=await loadAllEntries();
      var projects=await loadProjects();
      var d=$('#searchDate').value;
      var loc=$('#searchLocation').value.trim().toLowerCase();
      var v=$('#searchVendor').value.trim().toLowerCase();
      var desc=$('#searchDesc').value.trim().toLowerCase();
      var amtStr=$('#searchAmount').value.trim();
      var searchProjectId=$('#searchProjectId').value;
      var amt=amtStr ? Number(amtStr) : null;
      var hrs=0, exp=0;
      var filtered=all.filter(function(e){
        var ok=true;
        if(d) ok=ok && e.date===d;
        if(loc) ok=ok && String(e.location || '').toLowerCase().indexOf(loc)!==-1;
        if(v) ok=ok && String(e.vendor || '').toLowerCase().indexOf(v)!==-1;
        if(desc) ok=ok && String(e.task || '').toLowerCase().indexOf(desc)!==-1;
        if(searchProjectId) ok=ok && String(e.projectId || '')===String(searchProjectId);
        if(amt!==null && !Number.isNaN(amt)) ok=ok && Number(e.amount || 0)===amt;
        return ok;
      });
      filtered.forEach(function(e){ hrs += Number(e.hours)||0; exp += Number(e.amount)||0; });
      var rows=filtered.map(function(e){
        return '<tr>'+
          '<td>'+escapeHtml(e.date || '')+'</td>'+
          '<td>'+escapeHtml(projectNameById(projects, e.projectId) || '')+'</td>'+
          '<td>'+escapeHtml(e.hours || '')+'</td>'+
          '<td>'+nl2br(e.task || '')+'</td>'+
          '<td>'+escapeHtml(e.location || '')+'</td>'+
          '<td>'+escapeHtml(e.vendor || '')+'</td>'+
          '<td>'+(e.amount ? money(e.amount) : '')+'</td>'+
        '</tr>';
      }).join('');
      $('#searchTbody').innerHTML = (rows || '<tr><td colspan="7" style="text-align:center;padding:8px;border:1px solid #ccc">No results</td></tr>') + (filtered.length ? '<tr><td colspan="7" style="text-align:right;padding:6px;border:1px solid #ccc"><b>Total hours:</b> '+hrs.toFixed(2)+' | <b>Total expenses:</b> '+money(exp)+'</td></tr>' : '');
      lastSearchHTML='<table style="width:100%;border-collapse:collapse"><thead><tr><th style="border:1px solid #ccc;padding:6px">Date</th><th style="border:1px solid #ccc;padding:6px">Project</th><th style="border:1px solid #ccc;padding:6px">Hours</th><th style="border:1px solid #ccc;padding:6px">Description</th><th style="border:1px solid #ccc;padding:6px">Project / Location</th><th style="border:1px solid #ccc;padding:6px">Vendor</th><th style="border:1px solid #ccc;padding:6px">Expense</th></tr></thead><tbody>'+rows+'</tbody></table><p><b>Total hours:</b> '+hrs.toFixed(2)+' | <b>Total expenses:</b> '+money(exp)+'</p>';
    }

    async function printSelectedPeriodToPdf(){
      var entries=(await loadAllEntries()).filter(function(e){ return inSelectedView(e.date); });
      var projects=await loadProjects();
      var base=getSelectedBaseDate();
      var mode=$('#viewMode').value;
      var byDate={}; var totalH=0, totalA=0;
      entries.forEach(function(e){ var k=e.date || ''; (byDate[k]=byDate[k] || []).push(e); totalH += Number(e.hours)||0; totalA += Number(e.amount)||0; });
      var dates=Object.keys(byDate).sort();
      var compactWeekRows=dates.map(function(d){
        return byDate[d].map(function(e){
          var time=(e.start || e.end) ? (escapeHtml(formatTime12(e.start || ''))+'–'+escapeHtml(formatTime12(e.end || ''))) : '';
          return '<tr><td>'+escapeHtml(d)+'</td><td>'+time+'</td><td>'+escapeHtml(e.hours != null ? e.hours : '')+'</td><td>'+escapeHtml(projectNameById(projects, e.projectId) || '')+'</td><td>'+nl2br(e.task || '')+'</td><td>'+escapeHtml(e.location || '')+'</td><td>'+escapeHtml(e.vendor || '')+'</td><td>'+(e.amount ? money(e.amount) : '')+'</td></tr>';
        }).join('');
      }).join('');
      var weekTableHtml='<table class="week-table"><thead><tr><th style="width:90px">Date</th><th style="width:130px">Time</th><th style="width:60px">Hours</th><th style="width:140px">Project</th><th>Description</th><th style="width:170px">Project / Location</th><th style="width:130px">Vendor</th><th style="width:90px">Expense</th></tr></thead><tbody>'+compactWeekRows+'</tbody><tfoot><tr><td colspan="2" style="text-align:right"><b>Totals</b></td><td><b>'+totalH.toFixed(2)+'</b></td><td colspan="4"></td><td><b>'+money(totalA)+'</b></td></tr></tfoot></table>';
      function getViewRangeLabel(base, mode){ if(mode==='day') return localYYYYMMDD(base); if(mode==='week') return localYYYYMMDD(weekStartOf(base))+' – '+localYYYYMMDD(weekEndOf(base)); if(mode==='month') return base.getFullYear()+'-'+String(base.getMonth()+1).padStart(2,'0'); if(mode==='year') return String(base.getFullYear()); return ''; }
      var html='<!DOCTYPE html><html><head><meta charset="utf-8"><title>WorkLog Report</title><style>@page{size:landscape;margin:10mm;}body{font-family:Arial,Helvetica,sans-serif;margin:10px;color:#222;font-size:11px}.header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:10px;border-bottom:2px solid #333;padding-bottom:6px}.brand{font-size:18px;font-weight:bold}.meta{font-size:11px;text-align:right}table{width:100%;border-collapse:collapse;table-layout:fixed}th,td{border:1px solid #999;padding:4px 5px;vertical-align:top;word-wrap:break-word;overflow-wrap:break-word}th{background:#eee}</style></head><body><div class="header"><div class="brand">WorkLog Planner</div><div class="meta">Range: <b>'+escapeHtml(getViewRangeLabel(base, mode))+'</b><br>Generated: '+new Date().toLocaleString()+'</div></div>'+weekTableHtml+'</body></html>';
      openPrintHTML(html);
    }

    async function initApp(){
      try{
        await openDB();
        fillTimeSelects();
        bindTimeAutoRecalc();
        initBatchWorklogRows();
        initBatchMaterialRows();

        var todayStr=localYYYYMMDD(new Date());
        $('#date').value=todayStr;
        $('#calendarDate').value=todayStr;
        $('#batchEntryDate').value=todayStr;
        $('#projectStartDate').value=todayStr;
        $('#reminderDate').value=todayStr;
        $('#movementDate').value=todayStr;

        $all('.tab-btn').forEach(function(btn){
          btn.addEventListener('click', function(){ switchTab(btn.getAttribute('data-tab')); });
        });

        $('#saveBtn').addEventListener('click', async function(){
          try{
            var start=getTimeFields('start');
            var end=getTimeFields('end');
            var hoursInputStr=$('#hours').value.trim();
            var hoursInput=hoursInputStr === '' ? null : parseFloat(hoursInputStr);
            var hours=0;
            if(start && end){
              var calcHours=calculateHoursFrom24Range(start, end);
              hours = calcHours === null ? 0 : calcHours;
            } else { hours = (hoursInput === null || Number.isNaN(hoursInput)) ? 0 : hoursInput; }

            var obj={
              id: editingEntryId || String(Date.now()),
              date: $('#date').value || todayStr,
              projectId: $('#entryProjectId').value || '',
              start: start,
              end: end,
              hours: hours,
              task: $('#task').value || '',
              amount: parseFloat($('#amount').value || 0),
              location: $('#location').value || '',
              vendor: $('#vendor').value || '',
              receipt: $('#thumb img') ? $('#thumb img').src : '',
              updatedAt: Date.now()
            };
            await putInStore(ENTRY_STORE, obj);
            await addHistory({id:obj.id,date:obj.date,vendor:obj.vendor,hours:obj.hours,amount:obj.amount,ts:Date.now()});
            resetEntryForm();
            $('#status').textContent='Saved work entry.';
            await renderAll();
          }catch(err){ showError(err); }
        });

        $('#clearFormBtn').addEventListener('click', resetEntryForm);
        $('#deleteBtn').addEventListener('click', async function(){
          try{
            if(!editingEntryId) return;
            if(!checkPassword()) return;
            await deleteFromStore(ENTRY_STORE, editingEntryId);
            resetEntryForm();
            await renderAll();
          }catch(err){ showError(err); }
        });

        $('#tbody').addEventListener('click', async function(e){
          try{
            if(e.target && e.target.tagName === 'IMG'){
              $('#modalImg').src=e.target.src;
              $('#imgModal').showModal();
              return;
            }
            var editBtn=e.target.closest('.edit-entry-btn');
            var delBtn=e.target.closest('.delete-entry-btn');
            if(editBtn){
              var all=await loadAllEntries();
              var item=all.find(function(x){ return String(x.id)===String(editBtn.getAttribute('data-id')); });
              if(!item) return;
              editingEntryId=item.id;
              $('#date').value=item.date || '';
              $('#entryProjectId').value=item.projectId || '';
              setTimeFields('start', item.start || '');
              setTimeFields('end', item.end || '');
              $('#hours').value=item.hours != null ? item.hours : '';
              $('#task').value=item.task || '';
              $('#amount').value=item.amount != null ? item.amount : '';
              $('#location').value=item.location || '';
              $('#vendor').value=item.vendor || '';
              $('#thumb').innerHTML=item.receipt ? '<img src="'+item.receipt+'" style="max-width:60px">' : '';
              recalcHoursFromTimeFields();
              switchTab('worklog');
              window.scrollTo({top:0,behavior:'smooth'});
              $('#status').textContent='Editing work entry #'+item.id;
              return;
            }
            if(delBtn){
              if(!checkPassword()) return;
              await deleteFromStore(ENTRY_STORE, delBtn.getAttribute('data-id'));
              if(editingEntryId === delBtn.getAttribute('data-id')) resetEntryForm();
              await renderAll();
            }
          }catch(err){ showError(err); }
        });

        $('#addBatchWorklogRowBtn').addEventListener('click', function(){
          $('#batchWorklogTbody').insertAdjacentHTML('beforeend', createBatchWorklogRow());
        });

        $('#batchWorklogTbody').addEventListener('click', function(e){
          var btn=e.target.closest('.remove-batch-work-row-btn');
          if(!btn) return;
          var rows=$all('#batchWorklogTbody tr');
          if(rows.length <= 1){
            btn.closest('tr').querySelectorAll('input, select').forEach(function(inp){ inp.value=''; });
            btn.closest('tr').querySelector('.batch-start-ampm').value='AM';
            btn.closest('tr').querySelector('.batch-end-ampm').value='AM';
            return;
          }
          btn.closest('tr').remove();
        });

        $('#saveBatchWorklogBtn').addEventListener('click', async function(){
          try{
            var batchDate=$('#batchEntryDate').value || localYYYYMMDD(new Date());
            var batchProjectId=$('#batchEntryProjectId').value || '';
            var defaultLocation=$('#batchEntryLocation').value.trim();
            var rows=$all('#batchWorklogTbody tr');
            var created=0;

            for(var i=0;i<rows.length;i++){
              var row=rows[i];
              var start=getBatchTime24('batch-start', row);
              var end=getBatchTime24('batch-end', row);
              var hoursRaw=((row.querySelector('.batch-work-hours') || {}).value || '').trim();
              var task=((row.querySelector('.batch-work-task') || {}).value || '').trim();
              var location=((row.querySelector('.batch-work-location') || {}).value || '').trim() || defaultLocation;
              var vendor=((row.querySelector('.batch-work-vendor') || {}).value || '').trim();
              var amount=parseFloat(((row.querySelector('.batch-work-amount') || {}).value || 0));

              if(!task && !start && !end && !hoursRaw && !location && !vendor && !amount) continue;

              var hours=0;
              if(start && end){
                var calc=calculateHoursFrom24Range(start, end);
                hours = calc === null ? 0 : calc;
              } else {
                var parsedHours=parseFloat(hoursRaw || 0);
                hours = Number.isNaN(parsedHours) ? 0 : parsedHours;
              }

              await putInStore(ENTRY_STORE, {
                id: String(Date.now()) + '_work_' + i,
                date: batchDate,
                projectId: batchProjectId,
                start: start,
                end: end,
                hours: hours,
                task: task,
                amount: Number.isNaN(amount) ? 0 : amount,
                location: location,
                vendor: vendor,
                receipt: '',
                updatedAt: Date.now() + i
              });
              await addHistory({id:String(Date.now()) + '_hist_' + i,date:batchDate,vendor:vendor,hours:hours,amount:Number.isNaN(amount) ? 0 : amount,ts:Date.now() + i});
              created++;
            }

            if(!created) throw new Error('Add at least one work row with data');
            $('#batchWorklogStatusMsg').textContent='Added '+created+' work entry row(s).';
            await renderAll();
            initBatchWorklogRows();
          }catch(err){ showError(err); }
        });

        $('#clearBatchWorklogBtn').addEventListener('click', function(){
          initBatchWorklogRows();
          $('#batchWorklogStatusMsg').textContent='';
        });

        $('#saveProjectBtn').addEventListener('click', async function(){
          try{
            var obj={
              id: editingProjectId || String(Date.now()),
              name: $('#projectName').value.trim(),
              location: $('#projectLocation').value.trim(),
              client: $('#projectClient').value.trim(),
              status: $('#projectStatus').value,
              startDate: $('#projectStartDate').value || '',
              notes: $('#projectNotes').value || '',
              createdAt: Date.now()
            };
            if(!obj.name) throw new Error('Project name is required');
            await putInStore(PROJECT_STORE, obj);
            resetProjectForm();
            $('#projectStatusMsg').textContent='Project saved.';
            await renderAll();
          }catch(err){ showError(err); }
        });
        $('#clearProjectBtn').addEventListener('click', resetProjectForm);
        $('#deleteProjectBtn').addEventListener('click', async function(){
          try{
            if(!editingProjectId) return;
            if(!checkPassword()) return;
            await deleteFromStore(PROJECT_STORE, editingProjectId);
            resetProjectForm();
            await renderAll();
          }catch(err){ showError(err); }
        });
        $('#projectsTbody').addEventListener('click', async function(e){
          try{
            var editBtn=e.target.closest('.edit-project-btn');
            var delBtn=e.target.closest('.delete-project-row-btn');
            if(editBtn){
              var all=await loadProjects();
              var item=all.find(function(x){ return String(x.id)===String(editBtn.getAttribute('data-id')); });
              if(!item) return;
              editingProjectId=item.id;
              $('#projectName').value=item.name || '';
              $('#projectLocation').value=item.location || '';
              $('#projectClient').value=item.client || '';
              $('#projectStatus').value=item.status || 'active';
              $('#projectStartDate').value=item.startDate || '';
              $('#projectNotes').value=item.notes || '';
              switchTab('projects');
              $('#projectStatusMsg').textContent='Editing project #'+item.id;
              return;
            }
            if(delBtn){
              if(!checkPassword()) return;
              await deleteFromStore(PROJECT_STORE, delBtn.getAttribute('data-id'));
              if(editingProjectId === delBtn.getAttribute('data-id')) resetProjectForm();
              await renderAll();
            }
          }catch(err){ showError(err); }
        });

        $('#saveMaterialBtn').addEventListener('click', async function(){
          try{
            var obj={
              id: editingMaterialId || String(Date.now()),
              projectId: $('#materialProjectId').value || '',
              material: $('#materialName').value.trim(),
              qty: parseFloat($('#materialQty').value || 0),
              unit: $('#materialUnit').value.trim(),
              store: $('#materialStore').value.trim(),
              price: parseFloat($('#materialPrice').value || 0),
              status: $('#materialStatus').value,
              notes: $('#materialNotes').value || '',
              createdAt: Date.now()
            };
            if(!obj.material) throw new Error('Material name is required');
            await putInStore(MATERIAL_STORE, obj);
            resetMaterialForm();
            $('#materialStatusMsg').textContent='Material saved.';
            await renderAll();
          }catch(err){ showError(err); }
        });
        $('#clearMaterialBtn').addEventListener('click', resetMaterialForm);
        $('#deleteMaterialBtn').addEventListener('click', async function(){
          try{
            if(!editingMaterialId) return;
            if(!checkPassword()) return;
            await deleteFromStore(MATERIAL_STORE, editingMaterialId);
            resetMaterialForm();
            await renderAll();
          }catch(err){ showError(err); }
        });

        $('#addBatchMaterialRowBtn').addEventListener('click', function(){
          $('#batchMaterialsTbody').insertAdjacentHTML('beforeend', createBatchMaterialRow());
        });

        $('#batchMaterialsTbody').addEventListener('click', function(e){
          var btn=e.target.closest('.remove-batch-row-btn');
          if(!btn) return;
          var rows=$all('#batchMaterialsTbody tr');
          if(rows.length <= 1){
            btn.closest('tr').querySelectorAll('input').forEach(function(inp){ inp.value=''; });
            return;
          }
          btn.closest('tr').remove();
        });

        $('#saveBatchMaterialsBtn').addEventListener('click', async function(){
          try{
            var projectId=$('#batchMaterialProjectId').value || '';
            var defaultStore=$('#batchMaterialStore').value.trim();
            var defaultStatus=$('#batchMaterialStatus').value;
            var rows=$all('#batchMaterialsTbody tr');
            var created=0;
            for(var i=0;i<rows.length;i++){
              var row=rows[i];
              var qty=parseFloat((row.querySelector('.batch-qty') || {}).value || 0);
              var material=((row.querySelector('.batch-material') || {}).value || '').trim();
              var unit=((row.querySelector('.batch-unit') || {}).value || '').trim();
              var store=((row.querySelector('.batch-store') || {}).value || '').trim() || defaultStore;
              var price=parseFloat((row.querySelector('.batch-price') || {}).value || 0);
              var notes=((row.querySelector('.batch-notes') || {}).value || '').trim();
              if(!material) continue;
              await putInStore(MATERIAL_STORE, {
                id: String(Date.now()) + '_mat_' + i,
                projectId: projectId,
                material: material,
                qty: Number.isNaN(qty) ? 0 : qty,
                unit: unit,
                store: store,
                price: Number.isNaN(price) ? 0 : price,
                status: defaultStatus,
                notes: notes,
                createdAt: Date.now() + i
              });
              created++;
            }
            if(!created) throw new Error('Add at least one material row with a name');
            $('#batchMaterialStatusMsg').textContent='Added '+created+' material item(s).';
            await renderAll();
            initBatchMaterialRows();
          }catch(err){ showError(err); }
        });

        $('#clearBatchMaterialsBtn').addEventListener('click', function(){
          initBatchMaterialRows();
          $('#batchMaterialStatusMsg').textContent='';
        });

        $('#materialsGroupedList').addEventListener('click', async function(e){
          try{
            var editBtn=e.target.closest('.edit-material-btn');
            var delBtn=e.target.closest('.delete-material-row-btn');
            var printBtn=e.target.closest('.print-shopping-btn');

            if(printBtn){
              var projectId=printBtn.getAttribute('data-project');
              var projects=await loadProjects();
              var materials=await loadMaterials();
              var items=materials.filter(function(m){ return String(m.projectId || '')===String(projectId || ''); });
              printShoppingListForProject(projectNameById(projects, projectId) || 'No project', items);
              return;
            }

            if(editBtn){
              var all=await loadMaterials();
              var item=all.find(function(x){ return String(x.id)===String(editBtn.getAttribute('data-id')); });
              if(!item) return;
              editingMaterialId=item.id;
              $('#materialProjectId').value=item.projectId || '';
              $('#materialName').value=item.material || '';
              $('#materialQty').value=item.qty != null ? item.qty : '';
              $('#materialUnit').value=item.unit || '';
              $('#materialStore').value=item.store || '';
              $('#materialPrice').value=item.price != null ? item.price : '';
              $('#materialStatus').value=item.status || 'pending';
              $('#materialNotes').value=item.notes || '';
              switchTab('materials');
              $('#materialStatusMsg').textContent='Editing material #'+item.id;
              return;
            }
            if(delBtn){
              if(!checkPassword()) return;
              await deleteFromStore(MATERIAL_STORE, delBtn.getAttribute('data-id'));
              if(editingMaterialId === delBtn.getAttribute('data-id')) resetMaterialForm();
              await renderAll();
            }
          }catch(err){ showError(err); }
        });

        $('#saveInventoryBtn').addEventListener('click', async function(){
          try{
            var initialQty=parseFloat($('#inventoryQty').value || 0);
            var obj={
              id: editingInventoryId || String(Date.now()),
              projectId: $('#inventoryProjectId').value || '',
              name: $('#inventoryName').value.trim(),
              sku: $('#inventorySku').value.trim(),
              category: $('#inventoryCategory').value.trim(),
              initialQty: Number.isNaN(initialQty) ? 0 : initialQty,
              qty: Number.isNaN(initialQty) ? 0 : initialQty,
              unit: $('#inventoryUnit').value.trim(),
              minStock: parseFloat($('#inventoryMinStock').value || 0),
              location: $('#inventoryLocation').value.trim(),
              notes: $('#inventoryNotes').value || '',
              updatedAt: Date.now()
            };

            if(!obj.name) throw new Error('Piece name is required');

            if(editingInventoryId){
              var allInventory=await loadInventory();
              var existing=allInventory.find(function(x){ return String(x.id)===String(editingInventoryId); });
              if(existing){
                obj.qty = Number(existing.qty || 0);
                obj.initialQty = existing.initialQty != null ? existing.initialQty : obj.initialQty;
              }
            }

            await putInStore(INVENTORY_STORE, obj);
            $('#inventoryStatusMsg').textContent='Inventory item saved.';
            resetInventoryForm();
            await renderAll();
          }catch(err){ showError(err); }
        });

        $('#clearInventoryBtn').addEventListener('click', resetInventoryForm);

        $('#deleteInventoryBtn').addEventListener('click', async function(){
          try{
            if(!editingInventoryId) return;
            if(!checkPassword()) return;
            await deleteFromStore(INVENTORY_STORE, editingInventoryId);
            resetInventoryForm();
            await renderAll();
          }catch(err){ showError(err); }
        });

        $('#saveMovementBtn').addEventListener('click', async function(){
          try{
            var itemId=$('#movementItemId').value;
            var type=$('#movementType').value;
            var qty=parseFloat($('#movementQty').value || 0);
            var date=$('#movementDate').value || localYYYYMMDD(new Date());

            if(!itemId) throw new Error('Choose an inventory item');
            if(!qty || qty <= 0) throw new Error('Quantity must be greater than zero');

            var allItems=await loadInventory();
            var item=allItems.find(function(x){ return String(x.id)===String(itemId); });
            if(!item) throw new Error('Inventory item not found');

            var currentQty=Number(item.qty || 0);
            var newQty=currentQty;

            if(type==='in'){
              newQty=currentQty + qty;
            }else{
              if(qty > currentQty) throw new Error('Not enough pieces in stock');
              newQty=currentQty - qty;
            }

            item.qty=parseFloat(newQty.toFixed(2));
            item.updatedAt=Date.now();
            await putInStore(INVENTORY_STORE, item);

            await putInStore(INVENTORY_MOVEMENT_STORE, {
              id: String(Date.now()),
              itemId: item.id,
              itemName: item.name,
              type: type,
              qty: qty,
              date: date,
              reference: $('#movementRef').value.trim(),
              user: $('#movementUser').value.trim(),
              projectId: $('#movementProjectId').value || item.projectId || '',
              notes: $('#movementNotes').value || '',
              createdAt: Date.now()
            });

            $('#movementStatusMsg').textContent='Movement applied. Remaining: ' + item.qty + ' ' + (item.unit || '');
            $('#movementQty').value='';
            $('#movementRef').value='';
            $('#movementUser').value='';
            $('#movementNotes').value='';
            await renderAll();
          }catch(err){ showError(err); }
        });

        $('#clearMovementBtn').addEventListener('click', function(){
          $('#movementItemId').value='';
          $('#movementType').value='in';
          $('#movementQty').value='';
          $('#movementDate').value=localYYYYMMDD(new Date());
          $('#movementRef').value='';
          $('#movementUser').value='';
          $('#movementProjectId').value='';
          $('#movementNotes').value='';
          $('#movementStatusMsg').textContent='';
        });

        $('#runInventorySearchBtn').addEventListener('click', function(){
          renderInventoryFromUI().catch(showError);
        });

        $('#printInventoryBtn').addEventListener('click', function(){
          printInventorySheet().catch(showError);
        });

        async function renderInventoryFromUI(){
          var projects=await loadProjects();
          await renderInventory(projects);
        }

        $('#inventoryTbody').addEventListener('click', async function(e){
          try{
            var editBtn=e.target.closest('.edit-inventory-btn');
            var delBtn=e.target.closest('.delete-inventory-row-btn');

            if(editBtn){
              var all=await loadInventory();
              var item=all.find(function(x){ return String(x.id)===String(editBtn.getAttribute('data-id')); });
              if(!item) return;

              editingInventoryId=item.id;
              $('#inventoryProjectId').value=item.projectId || '';
              $('#inventoryName').value=item.name || '';
              $('#inventorySku').value=item.sku || '';
              $('#inventoryCategory').value=item.category || '';
              $('#inventoryQty').value=item.initialQty != null ? item.initialQty : item.qty;
              $('#inventoryUnit').value=item.unit || '';
              $('#inventoryMinStock').value=item.minStock != null ? item.minStock : '';
              $('#inventoryLocation').value=item.location || '';
              $('#inventoryNotes').value=item.notes || '';
              $('#inventoryStatusMsg').textContent='Editing inventory item #' + item.id;
              switchTab('inventory');
              return;
            }

            if(delBtn){
              if(!checkPassword()) return;
              await deleteFromStore(INVENTORY_STORE, delBtn.getAttribute('data-id'));
              if(editingInventoryId === delBtn.getAttribute('data-id')) resetInventoryForm();
              await renderAll();
            }
          }catch(err){ showError(err); }
        });

        $('#saveReminderBtn').addEventListener('click', async function(){
          try{
            var obj={
              id: editingReminderId || String(Date.now()),
              projectId: $('#reminderProjectId').value || '',
              title: $('#reminderTitle').value.trim(),
              description: $('#reminderDescription').value || '',
              dueDate: $('#reminderDate').value || '',
              dueTime: $('#reminderTime').value || '',
              priority: $('#reminderPriority').value,
              completed: $('#reminderDone').value === 'true',
              lastAlertAt: '',
              createdAt: Date.now()
            };
            if(!obj.title) throw new Error('Reminder title is required');
            await putInStore(REMINDER_STORE, obj);
            resetReminderForm();
            $('#reminderStatusMsg').textContent='Reminder saved.';
            await renderAll();
          }catch(err){ showError(err); }
        });
        $('#clearReminderBtn').addEventListener('click', resetReminderForm);
        $('#deleteReminderBtn').addEventListener('click', async function(){
          try{
            if(!editingReminderId) return;
            if(!checkPassword()) return;
            await deleteFromStore(REMINDER_STORE, editingReminderId);
            resetReminderForm();
            await renderAll();
          }catch(err){ showError(err); }
        });
        $('#remindersTbody').addEventListener('click', async function(e){
          try{
            var editBtn=e.target.closest('.edit-reminder-btn');
            var toggleBtn=e.target.closest('.toggle-reminder-btn');
            var delBtn=e.target.closest('.delete-reminder-row-btn');
            if(editBtn){
              var all=await loadReminders();
              var item=all.find(function(x){ return String(x.id)===String(editBtn.getAttribute('data-id')); });
              if(!item) return;
              editingReminderId=item.id;
              $('#reminderProjectId').value=item.projectId || '';
              $('#reminderTitle').value=item.title || '';
              $('#reminderDescription').value=item.description || '';
              $('#reminderDate').value=item.dueDate || '';
              $('#reminderTime').value=item.dueTime || '';
              $('#reminderPriority').value=item.priority || 'normal';
              $('#reminderDone').value=item.completed ? 'true' : 'false';
              switchTab('reminders');
              $('#reminderStatusMsg').textContent='Editing reminder #'+item.id;
              return;
            }
            if(toggleBtn){
              var allT=await loadReminders();
              var itemT=allT.find(function(x){ return String(x.id)===String(toggleBtn.getAttribute('data-id')); });
              if(!itemT) return;
              itemT.completed=!itemT.completed;
              await putInStore(REMINDER_STORE, itemT);
              await renderAll();
              return;
            }
            if(delBtn){
              if(!checkPassword()) return;
              await deleteFromStore(REMINDER_STORE, delBtn.getAttribute('data-id'));
              if(editingReminderId === delBtn.getAttribute('data-id')) resetReminderForm();
              await renderAll();
            }
          }catch(err){ showError(err); }
        });

        $('#clearHistoryBtn').addEventListener('click', async function(){
          try{
            if(!confirm('Clear all history?')) return;
            await clearStore(HISTORY_STORE);
            await renderHistory();
          }catch(err){ showError(err); }
        });

        $('#receiptInput').addEventListener('change', function(e){
          var f=e.target.files && e.target.files[0];
          if(!f) return;
          var r=new FileReader();
          r.onload=function(){ $('#thumb').innerHTML='<img src="'+r.result+'">'; };
          r.readAsDataURL(f);
        });

        $('#openCamBtn').addEventListener('click', function(){
          if(!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia){ alert('Camera not supported'); return; }
          navigator.mediaDevices.getUserMedia({video:true}).then(function(stream){
            var camVideo=$('#camVideo');
            camVideo.srcObject=stream;
            $('#camModal').showModal();
          }).catch(showError);
        });
        $('#snapBtn').addEventListener('click', function(){
          var camVideo=$('#camVideo');
          if(!camVideo.videoWidth) return;
          var c=document.createElement('canvas'); c.width=camVideo.videoWidth; c.height=camVideo.videoHeight;
          c.getContext('2d').drawImage(camVideo,0,0);
          $('#thumb').innerHTML='<img src="'+c.toDataURL('image/jpeg',0.9)+'" style="max-width:60px">';
          if(camVideo.srcObject){ camVideo.srcObject.getTracks().forEach(function(t){ t.stop(); }); camVideo.srcObject=null; }
          $('#camModal').close();
        });
        $('#closeCamBtn').addEventListener('click', function(){
          var camVideo=$('#camVideo');
          if(camVideo.srcObject){ camVideo.srcObject.getTracks().forEach(function(t){ t.stop(); }); camVideo.srcObject=null; }
          $('#camModal').close();
        });
        $('#closeModalBtn').addEventListener('click', function(){ $('#imgModal').close(); });

        $('#viewMode').addEventListener('change', function(){ renderEntriesFromUI().catch(showError); });
        $('#calendarDate').addEventListener('change', function(){ renderEntriesFromUI().catch(showError); });
        async function renderEntriesFromUI(){ var projects=await loadProjects(); await renderEntries(projects); }

        $('#printPeriodBtn').addEventListener('click', function(){ printSelectedPeriodToPdf().catch(showError); });
        $('#closeWeekBtn').addEventListener('click', async function(){
          try{
            var base=getSelectedBaseDate();
            var entries=(await loadAllEntries()).filter(function(e){ var d=new Date((e.date || '')+'T00:00:00'); return d>=weekStartOf(base) && d<=weekEndOf(base); });
            var hours=entries.reduce(function(t,e){ return t+(Number(e.hours)||0); },0);
            var exp=entries.reduce(function(t,e){ return t+(Number(e.amount)||0); },0);
            $('#weekRange').textContent='Range: '+weekStartOf(base).toLocaleDateString()+' – '+weekEndOf(base).toLocaleDateString();
            $('#weekHours').textContent=hours.toFixed(2);
            $('#weekExpenses').textContent=money(exp);
            $('#weekModal').showModal();
          }catch(err){ showError(err); }
        });
        $('#weekPrintBtn').addEventListener('click', function(){ printSelectedPeriodToPdf().catch(showError); });
        $('#weekCloseBtn').addEventListener('click', function(){ $('#weekModal').close(); });
        $('#clearWeekBtn').addEventListener('click', async function(){
          try{
            if(!checkPassword()) return;
            var base=getSelectedBaseDate();
            var entries=await loadAllEntries();
            var weekEntries=entries.filter(function(e){ var d=new Date((e.date || '')+'T00:00:00'); return d>=weekStartOf(base) && d<=weekEndOf(base); });
            for(var i=0;i<weekEntries.length;i++) await deleteFromStore(ENTRY_STORE, weekEntries[i].id);
            $('#weekModal').close();
            await renderAll();
          }catch(err){ showError(err); }
        });

        $('#openSearchBtn').addEventListener('click', function(){ $('#searchModal').showModal(); });
        $('#runSearchBtn').addEventListener('click', function(){ doSearch().catch(showError); });
        $('#clearSearchBtn').addEventListener('click', function(){ $('#searchDate').value=''; $('#searchLocation').value=''; $('#searchVendor').value=''; $('#searchDesc').value=''; $('#searchAmount').value=''; $('#searchProjectId').value=''; $('#searchTbody').innerHTML=''; lastSearchHTML=''; });
        $('#closeSearchBtn').addEventListener('click', function(){ $('#searchModal').close(); });
        $('#printSearchBtn').addEventListener('click', async function(){ if(!lastSearchHTML) await doSearch(); var html='<!DOCTYPE html><html><head><meta charset="utf-8"><title>Search Results</title><style>@page{size:landscape;margin:10mm;} body{font-family:Arial;margin:16px} table{width:100%;border-collapse:collapse;table-layout:fixed} th,td{border:1px solid #999;padding:6px;vertical-align:top;word-wrap:break-word;overflow-wrap:break-word} th{background:#eee}</style></head><body><h2>Search Results</h2>'+lastSearchHTML+'</body></html>'; openPrintHTML(html); });

        var backupUnlocked=false;
        function setBackupLockLabel(){ $('#backupLockStatus').textContent = backupUnlocked ? '🔓 Unlocked' : '🔒 Locked'; }
        function ensureBackupUnlocked(){ if(backupUnlocked) return true; if(checkPassword()){ backupUnlocked=true; setBackupLockLabel(); return true; } return false; }
        setBackupLockLabel();
        document.addEventListener('visibilitychange', function(){ if(document.hidden){ backupUnlocked=false; setBackupLockLabel(); } });
        window.addEventListener('beforeunload', function(){ backupUnlocked=false; setBackupLockLabel(); });

        $('#exportBtn').addEventListener('click', async function(){
          try{
            if(!ensureBackupUnlocked()) return;
            var payload={
              entries: await loadAllEntries(),
              history: await loadHistory(),
              projects: await loadProjects(),
              materials: await loadMaterials(),
              reminders: await loadReminders(),
              inventory: await loadInventory(),
              inventoryMovements: await loadInventoryMovements(),
              exportedAt: new Date().toISOString(),
              version: DB_VERSION
            };
            var blob=new Blob([JSON.stringify(payload,null,2)], {type:'application/json'});
            var url=URL.createObjectURL(blob);
            var a=document.createElement('a');
            a.href=url; a.download='planner_suite_backup_'+localYYYYMMDD(new Date())+'.json';
            document.body.appendChild(a); a.click();
            setTimeout(function(){ URL.revokeObjectURL(url); a.remove(); },0);
          }catch(err){ showError(err); }
        });
        $('#importBtn').addEventListener('click', function(){ if(!ensureBackupUnlocked()) return; $('#importFile').click(); });
        $('#importFile').addEventListener('change', function(e){
          var f=e.target.files && e.target.files[0];
          if(!f) return;
          var r=new FileReader();
          r.onload=async function(){
            try{
              var data=JSON.parse(r.result || '{}');
              if(!confirm('This will replace current data. Continue?')) return;
              await replaceStore(ENTRY_STORE, Array.isArray(data.entries) ? data.entries : []);
              await replaceStore(HISTORY_STORE, Array.isArray(data.history) ? data.history : []);
              await replaceStore(PROJECT_STORE, Array.isArray(data.projects) ? data.projects : []);
              await replaceStore(MATERIAL_STORE, Array.isArray(data.materials) ? data.materials : []);
              await replaceStore(REMINDER_STORE, Array.isArray(data.reminders) ? data.reminders : []);
              await replaceStore(INVENTORY_STORE, Array.isArray(data.inventory) ? data.inventory : []);
              await replaceStore(INVENTORY_MOVEMENT_STORE, Array.isArray(data.inventoryMovements) ? data.inventoryMovements : []);
              resetEntryForm(); resetProjectForm(); resetMaterialForm(); resetReminderForm(); resetInventoryForm();
              await renderAll();
              alert('Import completed.');
            }catch(err){ showError(err); }
            finally{ $('#importFile').value=''; }
          };
          r.readAsText(f);
        });

        await renderAll();
        startReminderWatcher();
      }catch(err){ showError(err); }
    }

    initApp();
  </script>
</body>
</html>
