<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NOcean</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 20px; background: #f9fafb; }
    h1 { font-size: 2em; margin-bottom: 20px; }
    .container { display: grid; grid-template-columns: 1fr; gap: 20px; }
    .card { background: white; padding: 15px; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
    ul { list-style: none; padding: 0; }
    li { padding: 8px; border: 1px solid #ddd; border-radius: 5px; margin-bottom: 8px; cursor: pointer; }
    li.done { background: #d1fae5; text-decoration: line-through; }
    textarea { width: 100%; height: 120px; padding: 8px; border: 1px solid #ccc; border-radius: 5px; }
    .bites-list li { cursor: default; border-left: 5px solid #a5b4fc; }
    .bite-status { display: inline-block; padding: 2px 8px; border-radius: 4px; font-size: 0.85em; margin-right: 4px; }
    .status-new { background: #fef08a; }
    .status-inprogress { background: #bae6fd; }
    .status-done { background: #bbf7d0; text-decoration: line-through; }
    .bite-category { font-size: 0.9em; color: #6366f1; font-weight: bold; }
    .bite-meta { font-size: 0.85em; color: #6b7280; }
    .bites-form-row { display: flex; gap: 8px; margin-bottom: 8px; }
    .bites-form-row input, .bites-form-row select { flex: 1; padding: 6px 8px; border-radius: 4px; border: 1px solid #ccc; }
    .bites-form-row button { flex: none; padding: 6px 14px; border-radius: 4px; background: #6366f1; color: white; border: none; font-weight: bold; cursor: pointer; }
    .bites-form-row button:hover { background: #4f46e5; }
    .options-edit-section { margin: 10px 0; }
    .options-list { display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 4px; }
    .option-pill { background: #e0e7ff; color: #3730a3; border-radius: 16px; padding: 2px 12px; font-size: 0.93em; display: flex; align-items: center; }
    .edit-btn, .del-btn { background: none; border: none; color: #6366f1; margin-left: 6px; font-size: 1em; cursor: pointer; padding: 0; }
    .del-btn { color: #dc2626; }
    .add-new-row { display: flex; gap: 4px; margin-top: 4px; }
    .add-new-row input { flex: 1; padding: 3px 6px; font-size: 1em; border: 1px solid #ccc; border-radius: 4px; }
    .add-new-row button { padding: 2px 10px; font-size: 1em; background: #6366f1; color: white; border: none; border-radius: 4px; }
    .add-new-row button:hover { background: #4f46e5; }
  </style>
</head>
<body>
  <h1>NOcean</h1>
  <div class="container">
    <div class="card">
      <h2>Bites</h2>
      <div class="options-edit-section">
        <strong>Status options:</strong>
        <div id="statusOptions" class="options-list"></div>
        <div class="add-new-row">
          <input type="text" id="newStatusInput" placeholder="Add new status">
          <button type="button" onclick="addStatusOption()">+</button>
        </div>
      </div>
      <div class="options-edit-section">
        <strong>Category options:</strong>
        <div id="categoryOptions" class="options-list"></div>
        <div class="add-new-row">
          <input type="text" id="newCategoryInput" placeholder="Add new category">
          <button type="button" onclick="addCategoryOption()">+</button>
        </div>
      </div>
      <ul id="biteList" class="bites-list"></ul>
      <form id="biteForm" autocomplete="off">
        <div class="bites-form-row">
          <input type="text" id="biteContent" placeholder="Bite note (smallest object)" required>
          <input type="text" id="biteResponsible" placeholder="Responsible (person or group)" required>
          <select id="biteStatus"></select>
          <select id="biteCategory"></select>
          <button type="submit">Add Bite</button>
        </div>
      </form>
    </div>

    <div class="card">
      <h2>Tasks</h2>
      <ul id="taskList">
        <li onclick="toggleTask(this)">Design homepage</li>
        <li onclick="toggleTask(this)" class="done">Plan marketing strategy</li>
      </ul>
    </div>

    <div class="card">
      <h2>Calendar</h2>
      <p style="color: gray;">Upcoming events will appear here.</p>
    </div>

    <div class="card">
      <h2>Notes</h2>
      <textarea placeholder="Write your notes here..."></textarea>
    </div>
  </div>

  <script>
    // Task toggling
    function toggleTask(element) {
      element.classList.toggle("done");
    }

    // Bites logic
    const bites = [];

    // Editable status and category options
    let statusOptions = [
      { value: "new", label: "New" },
      { value: "in progress", label: "In Progress" },
      { value: "done", label: "Done" }
    ];
    let categoryOptions = [
      { value: "Solstice Rooms and Restaurant", label: "Solstice Rooms and Restaurant" },
      { value: "Atrium project for Solstice", label: "Atrium project for Solstice" },
      { value: "Safeway Current Operations", label: "Safeway Current Operations" }
    ];

    // --- Status & Category Options Rendering/Editing ---
    function renderStatusOptions() {
      const container = document.getElementById('statusOptions');
      container.innerHTML = '';
      statusOptions.forEach((opt, i) => {
        const pill = document.createElement('span');
        pill.className = 'option-pill';
        pill.innerHTML = `<span>${opt.label}</span>
          <button class="edit-btn" title="Edit" onclick="editStatusOption(${i})">&#9998;</button>
          <button class="del-btn" title="Delete" onclick="deleteStatusOption(${i})">&times;</button>`;
        container.appendChild(pill);
      });
      populateStatusSelect();
    }

    function renderCategoryOptions() {
      const container = document.getElementById('categoryOptions');
      container.innerHTML = '';
      categoryOptions.forEach((opt, i) => {
        const pill = document.createElement('span');
        pill.className = 'option-pill';
        pill.innerHTML = `<span>${opt.label}</span>
          <button class="edit-btn" title="Edit" onclick="editCategoryOption(${i})">&#9998;</button>
          <button class="del-btn" title="Delete" onclick="deleteCategoryOption(${i})">&times;</button>`;
        container.appendChild(pill);
      });
      populateCategorySelect();
    }

    function populateStatusSelect() {
      const sel = document.getElementById('biteStatus');
      sel.innerHTML = '';
      statusOptions.forEach(opt => {
        sel.innerHTML += `<option value="${opt.value}">${opt.label}</option>`;
      });
    }

    function populateCategorySelect() {
      const sel = document.getElementById('biteCategory');
      sel.innerHTML = '';
      categoryOptions.forEach(opt => {
        sel.innerHTML += `<option value="${opt.value}">${opt.label}</option>`;
      });
    }

    // --- Adding new status/category options ---
    function addStatusOption() {
      const inp = document.getElementById('newStatusInput');
      const val = inp.value.trim();
      if (val && !statusOptions.some(opt => opt.label.toLowerCase() === val.toLowerCase())) {
        statusOptions.push({ value: val.toLowerCase(), label: val });
        renderStatusOptions();
      }
      inp.value = '';
    }
    function addCategoryOption() {
      const inp = document.getElementById('newCategoryInput');
      const val = inp.value.trim();
      if (val && !categoryOptions.some(opt => opt.label.toLowerCase() === val.toLowerCase())) {
        categoryOptions.push({ value: val, label: val });
        renderCategoryOptions();
      }
      inp.value = '';
    }

    // --- Editing/deleting status/category options ---
    function editStatusOption(i) {
      const newLabel = prompt("Edit status label:", statusOptions[i].label);
      if (newLabel && newLabel.trim()) {
        statusOptions[i].label = newLabel.trim();
        statusOptions[i].value = newLabel.trim().toLowerCase();
        renderStatusOptions();
      }
    }
    function deleteStatusOption(i) {
      if (statusOptions.length <= 1) return alert('Must have at least one status option.');
      if (confirm(`Delete status "${statusOptions[i].label}"?`)) {
        statusOptions.splice(i, 1);
        renderStatusOptions();
      }
    }
    function editCategoryOption(i) {
      const newLabel = prompt("Edit category label:", categoryOptions[i].label);
      if (newLabel && newLabel.trim()) {
        categoryOptions[i].label = newLabel.trim();
        categoryOptions[i].value = newLabel.trim();
        renderCategoryOptions();
      }
    }
    function deleteCategoryOption(i) {
      if (categoryOptions.length <= 1) return alert('Must have at least one category option.');
      if (confirm(`Delete category "${categoryOptions[i].label}"?`)) {
        categoryOptions.splice(i, 1);
        renderCategoryOptions();
      }
    }

    // --- Bites adding/display ---
    const biteForm = document.getElementById('biteForm');
    const biteList = document.getElementById('biteList');
    const contentInput = document.getElementById('biteContent');
    const responsibleInput = document.getElementById('biteResponsible');
    const statusInput = document.getElementById('biteStatus');
    const categoryInput = document.getElementById('biteCategory');

    biteForm.onsubmit = function(e) {
      e.preventDefault();
      const content = contentInput.value.trim();
      const responsible = responsibleInput.value.trim();
      const status = statusInput.value;
      const statusLabel = statusOptions.find(opt => opt.value === status)?.label || status;
      const category = categoryInput.value;
      const categoryLabel = categoryOptions.find(opt => opt.value === category)?.label || category;
      if(content && responsible && status && category){
        bites.push({ content, responsible, status, statusLabel, category, categoryLabel });
        renderBites();
        biteForm.reset();
      }
    };

    function renderBites() {
      biteList.innerHTML = bites.map(bite => {
        let statusClass = "status-new";
        if (bite.status === "in progress") statusClass = "status-inprogress";
        if (bite.status === "done") statusClass = "status-done";
        return `<li>
          <span class="bite-status ${statusClass}">${bite.statusLabel}</span>
          <span class="bite-category">${bite.categoryLabel}</span><br>
          <strong>${bite.content}</strong><br>
          <span class="bite-meta">Responsible: ${bite.responsible}</span>
        </li>`;
      }).join('');
    }

    // --- Initial Render ---
    renderStatusOptions();
    renderCategoryOptions();
    // Optionally, render starter bites here
