<!DOCTYPE html><html lang="fa">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Crypto Smart Dashboard CMC</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
body { font-family:'Arial'; direction:rtl; margin:0; padding:20px; background:#f3f4f6; transition:background 0.3s; }
body.dark { background:#121212; color:#f0f0f0; }
.container { max-width:1200px; margin:auto; }
h2 { text-align:center; margin-bottom:15px; font-size:1.8rem; }
.select-box { background:white; padding:15px; border-radius:12px; margin-bottom:20px; box-shadow:0 3px 10px rgba(0,0,0,0.1); transition: background 0.3s; }
body.dark .select-box { background:#1f1f1f; }
#coinSearch { width:100%; padding:12px; border-radius:8px; border:1px solid #ccc; margin-bottom:10px; font-size:1rem; }
body.dark #coinSearch { border:1px solid #555; background:#333; color:#f0f0f0; }
.coin-list div { padding:8px; cursor:pointer; border-bottom:1px solid #eee; font-size:0.95rem; }
.coin-list div:hover { background:#e5e7eb; }
body.dark .coin-list div:hover { background:#333; }
.grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(200px,1fr)); gap:15px; }
.card { background:white; padding:10px; border-radius:12px; box-shadow:0 4px 12px rgba(0,0,0,0.15); transition: transform 0.2s, background-color 0.3s; position:relative; cursor:pointer; min-height:200px; }
.card.dragging { opacity:0.6; }
body.dark .card { background:#1f1f1f; }
.price { font-size:16px; font-weight:bold; margin-top:5px; }
.change-up { color:#00c853; }
.change-down { color:#d50000; }
.change-neutral { color:#ffb300; }
.delete-btn { position:absolute; top:8px; left:8px; background:red; color:white; border:none; border-radius:5px; padding:2px 6px; cursor:pointer; font-size:12px; z-index:2; }
.delete-btn:hover { background:darkred; }
.coin-logo { width:30px; height:30px; vertical-align:middle; margin-left:5px; }
.toggle-btn { margin-bottom:10px; padding:8px 15px; border:none; border-radius:8px; cursor:pointer; background:#333; color:white; font-size:1rem; }
.alert-input { width:50px; padding:3px; margin-top:5px; border-radius:5px; border:1px solid #ccc; }
#popup { position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.7); display:none; justify-content:center; align-items:center; z-index:10; overflow:auto; }
#popupContent { background:white; padding:20px; border-radius:12px; max-width:800px; width:90%; max-height:90%; overflow:auto; position:relative; }
body.dark #popupContent { background:#1f1f1f; color:white; }
#popupClose { position:absolute; top:10px; right:10px; font-size:20px; cursor:pointer; background:red; color:white; border:none; border-radius:5px; padding:2px 8px; }
@media(max-width:600px){ .grid { grid-template-columns:repeat(auto-fill,minmax(150px,1fr)); } .price { font-size:14px; } }
</style>
</head>
<body>
<div class="container">
<h2>Crypto Smart Dashboard CMC</h2>
<button class="toggle-btn" id="darkModeBtn">🌙 Dark Mode</button>
<div class="select-box">
    <b>🔍 جستجو و انتخاب ارز</b>
    <input id="coinSearch" type="text" placeholder="نام ارز را وارد کنید...">
    <div class="coin-list" id="coinList"></div>
</div>
<div class="grid" id="cryptoGrid"></div>
</div>
<div id="popup">
<div id="popupContent">
    <button id="popupClose">×</button>
    <h3 id="popupTitle"></h3>
    <img id="popupLogo" src="" alt="" style="width:40px;height:40px;">
    <p>قیمت فعلی: $<span id="popupPrice"></span></p>
    <p>تغییر ۱ ساعته: <span id="popupChange1h"></span></p>
    <p>تغییر ۲۴ ساعته: <span id="popupChange24h"></span></p>
    <canvas id="popupChart" width="700" height="300"></canvas>
</div>
</div>
<script>
// همان اسکریپت کامل نسخه شما اینجا قرار می‌گیرد
</script>
</body>
</html>
