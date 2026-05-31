<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sales & Revenue Analysis Dashboard</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.44.0/tabler-icons.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/5.4.1/papaparse.min.js"></script>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; background: #f4f6f9; color: #1a1a2e; min-height: 100vh; }
  .topbar { background: #fff; border-bottom: 1px solid #e0e0e0; padding: 14px 28px; display: flex; align-items: center; justify-content: space-between; position: sticky; top: 0; z-index: 100; }
  .topbar-left h1 { font-size: 18px; font-weight: 600; color: #1a1a2e; }
  .topbar-left p { font-size: 13px; color: #888; }
  .topbar-right { display: flex; gap: 10px; }
  .btn { font-size: 13px; padding: 7px 16px; border-radius: 20px; border: 1px solid #ddd; background: #fff; color: #555; cursor: pointer; display: flex; align-items: center; gap: 6px; transition: background 0.15s; }
  .btn:hover { background: #f0f0f0; }
  .btn-primary { background: #2E75B6; color: #fff; border-color: #2E75B6; }
  .btn-primary:hover { background: #1F5A91; }
  .container { max-width: 1200px; margin: 0 auto; padding: 24px 28px; }
  .filter-bar { display: flex; gap: 10px; flex-wrap: wrap; align-items: center; margin-bottom: 20px; background: #fff; border-radius: 10px; border: 1px solid #e8e8e8; padding: 14px 18px; }
  .filter-bar label { font-size: 12px; color: #888; font-weight: 500; }
  .filter-bar select { font-size: 13px; padding: 6px 12px; border-radius: 8px; border: 1px solid #ddd; background: #fafafa; color: #333; cursor: pointer; }
  .filter-bar select:focus { outline: none; border-color: #2E75B6; }
  .filter-sep { width: 1px; height: 24px; background: #e0e0e0; margin: 0 4px; }
  .kpi-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 14px; margin-bottom: 20px; }
  .kpi { background: #fff; border-radius: 12px; border: 1px solid #e8e8e8; padding: 18px 20px; }
  .kpi-icon { width: 38px; height: 38px; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin-bottom: 12px; font-size: 18px; }
  .kpi-label { font-size: 12px; color: #999; margin-bottom: 4px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.05em; }
  .kpi-value { font-size: 26px; font-weight: 700; color: #1a1a2e; margin-bottom: 6px; }
  .kpi-delta { font-size: 12px; font-weight: 600; display: flex; align-items: center; gap: 4px; }
  .kpi-delta.up { color: #0F6E56; }
  .kpi-delta.down { color: #993C1D; }
  .charts-row { display: grid; grid-template-columns: 2fr 1fr; gap: 16px; margin-bottom: 20px; }
  .card { background: #fff; border-radius: 12px; border: 1px solid #e8e8e8; padding: 20px; }
  .card h3 { font-size: 14px; font-weight: 600; color: #1a1a2e; margin-bottom: 14px; }
  .bottom-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 20px; }
  .controls { display: flex; gap: 8px; margin-bottom: 18px; align-items: center; }
  .controls span { font-size: 12px; color: #aaa; margin-right: 4px; }
  .pill { font-size: 12px; padding: 5px 14px; border-radius: 20px; border: 1px solid #ddd; background: transparent; color: #666; cursor: pointer; transition: all 0.15s; }
  .pill:hover { background: #f4f6f9; }
  .pill.active { background: #2E75B6; color: #fff; border-color: #2E75B6; font-weight: 500; }
  .legend { display: flex; flex-wrap: wrap; gap: 14px; margin-bottom: 10px; font-size: 12px; color: #888; }
  .legend span { display: flex; align-items: center; gap: 5px; }
  .leg-dot { width: 10px; height: 10px; border-radius: 2px; }
  .leg-dash { width: 16px; height: 0; border-top: 2px dashed #D85A30; margin-top: 1px; }
  .product-row { display: flex; align-items: center; gap: 10px; padding: 9px 0; border-bottom: 1px solid #f0f0f0; }
  .product-row:last-child { border-bottom: none; }
  .product-rank { font-size: 12px; font-weight: 700; color: #bbb; width: 18px; text-align: center; }
  .product-name { font-size: 13px; color: #333; flex: 1; min-width: 0; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .product-bar-wrap { flex: 2; height: 6px; background: #f0f0f0; border-radius: 3px; overflow: hidden; }
  .product-bar { height: 100%; border-radius: 3px; transition: width 0.4s; }
  .product-rev { font-size: 12px; font-weight: 600; color: #333; min-width: 52px; text-align: right; }
  .insight-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; margin-bottom: 20px; }
  .insight { background: #fff; border-radius: 12px; border: 1px solid #e8e8e8; border-top: 3px solid #1D9E75; padding: 14px 16px; font-size: 13px; color: #666; line-height: 1.6; }
  .insight strong { color: #1a1a2e; }
  .upload-zone { border: 2px dashed #ddd; border-radius: 12px; padding: 32px; text-align: center; color: #aaa; font-size: 14px; cursor: pointer; transition: all 0.15s; margin-bottom: 20px; display: none; }
  .upload-zone:hover { border-color: #2E75B6; background: #f0f6ff; color: #2E75B6; }
  .upload-zone i { font-size: 36px; display: block; margin-bottom: 10px; }
  @media (max-width: 900px) {
    .kpi-grid { grid-template-columns: repeat(2, 1fr); }
    .charts-row, .bottom-row { grid-template-columns: 1fr; }
    .insight-row { grid-template-columns: 1fr; }
  }
  @media (max-width: 600px) {
    .kpi-grid { grid-template-columns: 1fr 1fr; }
    .container { padding: 16px; }
  }
</style>
</head>
<body>

<div class="topbar">
  <div class="topbar-left">
    <h1>Sales & Revenue</h1>
    <p>Interactive analysis dashboard</p>
  </div>
  <div class="topbar-right">
    <label class="btn" style="cursor:pointer;">
      <i class="ti ti-upload"></i> Import data
      <input type="file" id="fileInput" accept=".csv,.xlsx,.xls" style="display:none;">
    </label>
    <button class="btn btn-primary" onclick="alert('Connect to your AI or reporting tool here.')">
      <i class="ti ti-sparkles"></i> Get insights
    </button>
  </div>
</div>

<div class="container">

  <div class="filter-bar">
    <label>Period:</label>
    <select id="periodFilter" onchange="applyFilters()">
      <option value="all">All time</option>
      <option value="q1">Q1</option>
      <option value="q2">Q2</option>
      <option value="q3">Q3</option>
      <option value="q4" selected>Q4</option>
    </select>
    <div class="filter-sep"></div>
    <label>Region:</label>
    <select id="regionFilter" onchange="applyFilters()">
      <option value="all">All regions</option>
      <option value="north">North</option>
      <option value="south">South</option>
      <option value="east">East</option>
      <option value="west">West</option>
    </select>
    <div class="filter-sep"></div>
    <label>Category:</label>
    <select id="catFilter" onchange="applyFilters()">
      <option value="all">All categories</option>
      <option value="electronics">Electronics</option>
      <option value="apparel">Apparel</option>
      <option value="home">Home & Garden</option>
      <option value="sports">Sports</option>
    </select>
  </div>

  <div class="kpi-grid" id="kpiGrid"></div>

  <div class="controls">
    <span>Trend view:</span>
    <button class="pill active" onclick="setTrend('monthly', this)">Monthly</button>
    <button class="pill" onclick="setTrend('quarterly', this)">Quarterly</button>
    <button class="pill" onclick="setTrend('weekly', this)">Weekly</button>
  </div>

  <div class="charts-row">
    <div class="card">
      <h3>Revenue & sales trend</h3>
      <div class="legend">
        <span><span class="leg-dot" style="background:#3266ad;"></span>Revenue</span>
        <span><span class="leg-dot" style="background:#1D9E75;"></span>Units sold</span>
        <span><span class="leg-dash"></span>Target</span>
      </div>
      <div style="position:relative;width:100%;height:240px;">
        <canvas id="trendChart" role="img" aria-label="Revenue and units sold trend chart"></canvas>
      </div>
    </div>
    <div class="card">
      <h3>Sales by category</h3>
      <div style="position:relative;width:100%;height:240px;">
        <canvas id="donutChart" role="img" aria-label="Sales by category donut chart"></canvas>
      </div>
      <div class="legend" style="margin-top:10px;justify-content:center;">
        <span><span class="leg-dot" style="background:#3266ad;"></span>Electronics</span>
        <span><span class="leg-dot" style="background:#1D9E75;"></span>Apparel</span>
        <span><span class="leg-dot" style="background:#D85A30;"></span>Home</span>
        <span><span class="leg-dot" style="background:#B5D4F4;border:1px solid #ccc;"></span>Sports</span>
      </div>
    </div>
  </div>

  <div class="bottom-row">
    <div class="card">
      <h3>Top products by revenue</h3>
      <div id="productList"></div>
    </div>
    <div class="card">
      <h3>Regional performance</h3>
      <div style="position:relative;width:100%;height:220px;">
        <canvas id="regionChart" role="img" aria-label="Revenue by region bar chart"></canvas>
      </div>
    </div>
  </div>

  <div class="insight-row" id="insightRow"></div>

</div>

<script>
const MONTHLY = {
  labels: ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'],
  revenue: [142000,158000,135000,172000,189000,205000,198000,221000,214000,238000,255000,271000],
  units:   [1120,1340,1080,1450,1620,1780,1690,1920,1850,2040,2180,2310],
  target:  [150000,160000,145000,175000,190000,200000,205000,220000,215000,235000,250000,265000]
};
const QUARTERLY = {
  labels: ['Q1','Q2','Q3','Q4'],
  revenue: [435000,566000,633000,764000],
  units:   [3540,4850,5460,6530],
  target:  [455000,565000,640000,750000]
};
const WEEKLY = {
  labels: ['W1','W2','W3','W4','W5','W6','W7','W8'],
  revenue: [58000,63000,71000,55000,68000,79000,84000,91000],
  units:   [480,520,590,445,565,640,710,780],
  target:  [60000,65000,70000,60000,70000,80000,85000,90000]
};

const products = [
  { name: 'ProMax Laptop 15"',  rev: 284000, color: '#3266ad' },
  { name: 'Smart Hub 360',      rev: 198000, color: '#1D9E75' },
  { name: 'AirCore Headphones', rev: 156000, color: '#D85A30' },
  { name: 'FitBand Ultra',      rev: 134000, color: '#7F77DD' },
  { name: 'CloudDesk Chair',    rev: 112000, color: '#BA7517' },
];

const kpis = [
  { label: 'Total Revenue',    value: '$2.40M', delta: '+18.4% vs last year', up: true,  icon: 'ti-currency-dollar', iconBg: '#EBF3FC', iconColor: '#2E75B6' },
  { label: 'Units Sold',       value: '26,370', delta: '+22.1% vs last year', up: true,  icon: 'ti-package',         iconBg: '#E1F5EE', iconColor: '#1D9E75' },
  { label: 'Avg. Order Value', value: '$910',   delta: '-2.3% vs last year',  up: false, icon: 'ti-receipt',         iconBg: '#FAECE7', iconColor: '#993C1D' },
  { label: 'Conversion Rate',  value: '4.7%',   delta: '+0.8pp vs last year', up: true,  icon: 'ti-chart-line',      iconBg: '#F0EEFE', iconColor: '#534AB7' },
];

const insights = [
  { text: '<strong>Peak month:</strong> December led all months with $271K revenue — a 7% surge driven by holiday promotions.' },
  { text: '<strong>Best product:</strong> ProMax Laptop 15" generates 11.8% of total revenue, outpacing category average by 3×.' },
  { text: '<strong>Regional star:</strong> West region grew 31% YoY — fastest growing market, now 28% of total sales.' },
];

function buildKPIs() {
  document.getElementById('kpiGrid').innerHTML = kpis.map(k => `
    <div class="kpi">
      <div class="kpi-icon" style="background:${k.iconBg};color:${k.iconColor};">
        <i class="ti ${k.icon}"></i>
      </div>
      <div class="kpi-label">${k.label}</div>
      <div class="kpi-value">${k.value}</div>
      <div class="kpi-delta ${k.up ? 'up' : 'down'}">
        <i class="ti ${k.up ? 'ti-trending-up' : 'ti-trending-down'}"></i> ${k.delta}
      </div>
    </div>`).join('');
}

function buildProducts() {
  const maxRev = Math.max(...products.map(p => p.rev));
  document.getElementById('productList').innerHTML = products.map((p, i) => `
    <div class="product-row">
      <span class="product-rank">${i + 1}</span>
      <span class="product-name">${p.name}</span>
      <div class="product-bar-wrap">
        <div class="product-bar" style="width:${Math.round(p.rev / maxRev * 100)}%;background:${p.color};"></div>
      </div>
      <span class="product-rev">$${(p.rev / 1000).toFixed(0)}K</span>
    </div>`).join('');
}

function buildInsights() {
  document.getElementById('insightRow').innerHTML = insights.map(i =>
    `<div class="insight">${i.text}</div>`).join('');
}

let trendChart, donutChart, regionChart;

function buildTrendChart(data) {
  if (trendChart) trendChart.destroy();
  trendChart = new Chart(document.getElementById('trendChart'), {
    data: {
      labels: data.labels,
      datasets: [
        { type: 'bar',  label: 'Revenue',    data: data.revenue, backgroundColor: 'rgba(50,102,173,0.18)', borderColor: '#3266ad', borderWidth: 1.5, yAxisID: 'y',  order: 2 },
        { type: 'line', label: 'Units sold', data: data.units,   borderColor: '#1D9E75', backgroundColor: 'transparent', borderWidth: 2, pointRadius: 3, tension: 0.4, yAxisID: 'y2', order: 1 },
        { type: 'line', label: 'Target',     data: data.target,  borderColor: '#D85A30', borderDash: [5,4], backgroundColor: 'transparent', borderWidth: 1.5, pointRadius: 0, tension: 0.4, yAxisID: 'y', order: 0 }
      ]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      plugins: {
        legend: { display: false },
        tooltip: { mode: 'index', intersect: false,
          callbacks: { label: ctx => ctx.datasetIndex === 1
            ? ` Units: ${ctx.parsed.y.toLocaleString()}`
            : ` $${(ctx.parsed.y / 1000).toFixed(0)}K` }
        }
      },
      scales: {
        x:  { grid: { color: 'rgba(0,0,0,0.05)' }, ticks: { font: { size: 11 }, color: '#aaa' } },
        y:  { position: 'left',  grid: { color: 'rgba(0,0,0,0.05)' }, ticks: { font: { size: 11 }, color: '#aaa', callback: v => '$' + (v / 1000).toFixed(0) + 'K' } },
        y2: { position: 'right', grid: { display: false }, ticks: { font: { size: 11 }, color: '#1D9E75' } }
      }
    }
  });
}

function buildDonut() {
  if (donutChart) donutChart.destroy();
  donutChart = new Chart(document.getElementById('donutChart'), {
    type: 'doughnut',
    data: {
      labels: ['Electronics', 'Apparel', 'Home & Garden', 'Sports'],
      datasets: [{ data: [42, 28, 18, 12], backgroundColor: ['#3266ad','#1D9E75','#D85A30','#B5D4F4'], borderWidth: 2, borderColor: '#fff' }]
    },
    options: {
      responsive: true, maintainAspectRatio: false, cutout: '68%',
      plugins: { legend: { display: false }, tooltip: { callbacks: { label: ctx => ` ${ctx.label}: ${ctx.parsed}%` } } }
    }
  });
}

function buildRegionChart() {
  if (regionChart) regionChart.destroy();
  regionChart = new Chart(document.getElementById('regionChart'), {
    type: 'bar',
    data: {
      labels: ['North', 'South', 'East', 'West'],
      datasets: [{ label: 'Revenue', data: [520000, 410000, 680000, 790000],
        backgroundColor: ['#3266ad','#1D9E75','#D85A30','#7F77DD'], borderRadius: 5 }]
    },
    options: {
      indexAxis: 'y', responsive: true, maintainAspectRatio: false,
      plugins: { legend: { display: false }, tooltip: { callbacks: { label: ctx => ` $${(ctx.parsed.x / 1000).toFixed(0)}K` } } },
      scales: {
        x: { grid: { color: 'rgba(0,0,0,0.05)' }, ticks: { font: { size: 11 }, color: '#aaa', callback: v => '$' + (v / 1000) + 'K' } },
        y: { grid: { display: false }, ticks: { font: { size: 12 }, color: '#555' } }
      }
    }
  });
}

let currentTrend = MONTHLY;

function setTrend(key, btn) {
  document.querySelectorAll('.controls .pill').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  currentTrend = key === 'monthly' ? MONTHLY : key === 'quarterly' ? QUARTERLY : WEEKLY;
  buildTrendChart(currentTrend);
}

function applyFilters() {
  buildTrendChart(currentTrend);
}

document.getElementById('fileInput').addEventListener('change', function(e) {
  const file = e.target.files[0];
  if (!file) return;
  const ext = file.name.split('.').pop().toLowerCase();
  if (ext === 'csv') {
    Papa.parse(file, {
      header: true,
      complete: res => {
        const rows = res.data;
        alert('CSV loaded: ' + rows.length + ' rows detected.\nColumns: ' + Object.keys(rows[0] || {}).join(', ') + '\n\nMap your columns to revenue, units, date, and product to populate the dashboard.');
      }
    });
  } else {
    alert('Excel file "' + file.name + '" selected.\nTo fully parse .xlsx files, integrate SheetJS (xlsx) library and map your columns to the dashboard data arrays.');
  }
});

buildKPIs();
buildProducts();
buildInsights();
buildTrendChart(MONTHLY);
buildDonut();
buildRegionChart();
</script>
</body>
</html>
