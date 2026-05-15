<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Modern Work Dashboard</title>

  <script src="https://cdn.tailwindcss.com"></script>

  <style>
    body {
      background: #081120;
      color: white;
      font-family: Arial, sans-serif;
    }

    .glass {
      background: #101c2e;
      border: 1px solid #1e293b;
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    }

    .status-badge {
      padding: 6px 12px;
      border-radius: 999px;
      font-size: 12px;
      font-weight: bold;
    }

    .waiting {
      background: rgba(234,179,8,0.2);
      color: #fde047;
    }

    .review {
      background: rgba(59,130,246,0.2);
      color: #93c5fd;
    }

    .blocked {
      background: rgba(239,68,68,0.2);
      color: #fca5a5;
    }

    .completed {
      background: rgba(34,197,94,0.2);
      color: #86efac;
    }

    table {
      border-collapse: separate;
      border-spacing: 0 12px;
    }

    tbody tr {
      background: #172437;
      transition: 0.2s;
    }

    tbody tr:hover {
      background: #20314d;
    }

    .chart-bar {
      height: 10px;
      border-radius: 999px;
      background: #22d3ee;
    }
  </style>
</head>

<body>

  <div class="max-w-7xl mx-auto p-6">

    <!-- HEADER -->
    <div class="flex flex-col lg:flex-row justify-between items-start lg:items-center mb-8 gap-4">
      <div>
        <h1 class="text-4xl font-bold">WORK STATUS DASHBOARD</h1>
        <p class="text-slate-400 mt-2">
          Production & Engineering Task Tracking
        </p>
      </div>

      <div class="glass rounded-2xl px-5 py-3">
        <p class="text-slate-400 text-sm">Last Update</p>
        <p id="lastUpdate" class="font-semibold"></p>
      </div>
    </div>

    <!-- KPI -->
    <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 gap-5 mb-8">

      <div class="glass rounded-3xl p-6">
        <p class="text-slate-400 text-sm">TOTAL TASKS</p>
        <h2 id="totalTask" class="text-5xl font-bold mt-4">0</h2>
      </div>

      <div class="glass rounded-3xl p-6">
        <p class="text-slate-400 text-sm">IN PROGRESS</p>
        <h2 id="inProgress" class="text-5xl font-bold mt-4">0</h2>
      </div>

      <div class="glass rounded-3xl p-6">
        <p class="text-slate-400 text-sm">COMPLETED</p>
        <h2 id="completed" class="text-5xl font-bold mt-4">0</h2>
      </div>

      <div class="glass rounded-3xl p-6">
        <p class="text-slate-400 text-sm">BLOCKED</p>
        <h2 id="blocked" class="text-5xl font-bold mt-4">0</h2>
      </div>

    </div>

    <!-- MAIN CONTENT -->
    <div class="grid grid-cols-1 xl:grid-cols-3 gap-6">

      <!-- TABLE -->
      <div class="xl:col-span-2 glass rounded-3xl p-6">

        <div class="flex justify-between items-center mb-6">
          <h2 class="text-2xl font-semibold">Task Overview</h2>

          <input
            type="text"
            id="searchInput"
            placeholder="Search..."
            class="bg-slate-800 border border-slate-700 rounded-xl px-4 py-2 outline-none"
          />
        </div>

        <div class="overflow-x-auto">

          <table class="w-full">

            <thead>
              <tr class="text-slate-400 text-sm text-left">
                <th class="pb-3">TOPIC</th>
                <th class="pb-3">ACTIVITY</th>
                <th class="pb-3">MEMBER</th>
                <th class="pb-3">LEADTIME</th>
                <th class="pb-3">STATUS</th>
              </tr>
            </thead>

            <tbody id="taskTable"></tbody>

          </table>

        </div>
      </div>

      <!-- SIDE -->
      <div class="space-y-6">

        <!-- WORKLOAD -->
        <div class="glass rounded-3xl p-6">

          <h2 class="text-xl font-semibold mb-6">Team Workload</h2>

          <div id="workloadContainer" class="space-y-5"></div>

        </div>

        <!-- STATUS SUMMARY -->
        <div class="glass rounded-3xl p-6">

          <h2 class="text-xl font-semibold mb-5">
            Status Summary
          </h2>

          <div id="statusSummary" class="space-y-4"></div>

        </div>

      </div>

    </div>

  </div>

  <script>

    // =========================================
    // REPLACE THIS URL WITH YOUR APPS SCRIPT
    // =========================================

    const API_URL =
      "https://script.google.com/macros/s/AKfycbxVfyD_YfCHLNbrokqUflFZUs4mz6_76et9AVJlhOV9htMlnxQ8rezq_1rhF_7tPjc4/exec";

    let tasks = [];

    async function loadData() {

      try {

        const response = await fetch(API_URL);

        tasks = await response.json();

        renderDashboard(tasks);

      } catch (error) {

        console.error(error);

      }
    }

    function renderDashboard(data) {

      document.getElementById("lastUpdate").innerText =
        new Date().toLocaleString();

      // KPI
      const total = data.length;

      const completed =
        data.filter(t => t.STATUS === "Completed").length;

      const blocked =
        data.filter(t => t.STATUS === "Blocked").length;

      const progress =
        data.filter(t =>
          t.STATUS === "Waiting" ||
          t.STATUS === "Review" ||
          t.STATUS === "In Progress"
        ).length;

      document.getElementById("totalTask").innerText = total;
      document.getElementById("completed").innerText = completed;
      document.getElementById("blocked").innerText = blocked;
      document.getElementById("inProgress").innerText = progress;

      renderTable(data);
      renderWorkload(data);
      renderStatus(data);
    }

    function renderTable(data) {

      const table = document.getElementById("taskTable");

      table.innerHTML = "";

      data.forEach(task => {

        const statusClass =
          task.STATUS === "Waiting" ? "waiting" :
          task.STATUS === "Review" ? "review" :
          task.STATUS === "Blocked" ? "blocked" :
          "completed";

        table.innerHTML += `
          <tr>
            <td class="py-4 px-3 rounded-l-2xl font-medium">
              ${task.TOPIC || "-"}
            </td>

            <td class="px-3">
              ${task.ACTIVITY || "-"}
            </td>

            <td class="px-3">
              ${task.MEMBER || "-"}
            </td>

            <td class="px-3">
              ${task["LEAD DAYS"] || 0} Days
            </td>

            <td class="px-3 rounded-r-2xl">
              <span class="status-badge ${statusClass}">
                ${task.STATUS || "-"}
              </span>
            </td>
          </tr>
        `;
      });
    }

    function renderWorkload(data) {

      const workload = {};

      data.forEach(task => {

        const member = task.MEMBER || "Unknown";

        workload[member] =
          (workload[member] || 0) + 1;
      });

      const container =
        document.getElementById("workloadContainer");

      container.innerHTML = "";

      Object.keys(workload).forEach(member => {

        const value = workload[member] * 20;

        container.innerHTML += `
          <div>
            <div class="flex justify-between mb-2">
              <span>${member}</span>
              <span class="text-slate-400">
                ${value}%
              </span>
            </div>

            <div class="w-full h-3 bg-slate-700 rounded-full overflow-hidden">
              <div
                class="chart-bar"
                style="width:${value}%"
              ></div>
            </div>
          </div>
        `;
      });
    }

    function renderStatus(data) {

      const statusMap = {
        Waiting: 0,
        Review: 0,
        Blocked: 0,
        Completed: 0
      };

      data.forEach(task => {

        if (statusMap[task.STATUS] !== undefined) {

          statusMap[task.STATUS]++;
        }
      });

      const colors = {
        Waiting: "bg-yellow-400",
        Review: "bg-blue-400",
        Blocked: "bg-red-400",
        Completed: "bg-green-400"
      };

      const container =
        document.getElementById("statusSummary");

      container.innerHTML = "";

      Object.keys(statusMap).forEach(status => {

        container.innerHTML += `
          <div class="flex justify-between items-center">

            <div class="flex items-center gap-3">

              <div class="w-3 h-3 rounded-full ${colors[status]}"></div>

              <span>${status}</span>

            </div>

            <span class="font-semibold">
              ${statusMap[status]}
            </span>

          </div>
        `;
      });
    }

    // SEARCH
    document.getElementById("searchInput")
      .addEventListener("input", function(e) {

        const keyword =
          e.target.value.toLowerCase();

        const filtered =
          tasks.filter(task => {

            return JSON.stringify(task)
              .toLowerCase()
              .includes(keyword);
          });

        renderTable(filtered);
      });

    loadData();

    // AUTO REFRESH
    setInterval(loadData, 30000);

  </script>

</body>
</html>
