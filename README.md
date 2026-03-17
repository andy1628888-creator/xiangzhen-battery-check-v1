<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>祥真一職人｜電池三項快檢系統</title>
<style>
*{box-sizing:border-box}
html,body{
  margin:0;
  padding:0;
}
body{
  font-family:Arial,"Noto Sans TC",sans-serif;
  background:#f3f6fb;
  color:#243447;
}
.wrap{
  max-width:580px;
  margin:20px auto;
  padding:14px;
}
.card{
  background:#fff;
  border-radius:20px;
  padding:22px 18px;
  box-shadow:0 10px 28px rgba(0,0,0,.08);
}
.title{
  text-align:center;
  font-size:25px;
  font-weight:800;
  color:#1265cf;
  margin-bottom:8px;
}
.sub{
  text-align:center;
  font-size:13px;
  color:#66788a;
  line-height:1.8;
  margin-bottom:10px;
}
.system-info{
  text-align:center;
  font-size:13px;
  color:#6b7280;
  line-height:1.8;
  margin-bottom:16px;
}
.tab-bar{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:10px;
  margin-bottom:18px;
}
.tab-btn{
  border:none;
  border-radius:18px;
  padding:16px 10px;
  background:#e9eef7;
  color:#1f4f95;
  font-weight:800;
  cursor:pointer;
  font-size:15px;
}
.tab-btn.active{
  background:linear-gradient(135deg,#1265cf,#4b95f4);
  color:#fff;
  box-shadow:0 10px 20px rgba(18,101,207,.18);
}
.hidden{display:none}
label{
  display:block;
  margin-top:18px;
  font-weight:800;
  font-size:14px;
  color:#2d3b4c;
}
select,input{
  width:100%;
  margin-top:7px;
  padding:15px 14px;
  border:1px solid #d4deea;
  border-radius:16px;
  font-size:15px;
  background:#fff;
  color:#243447;
  outline:none;
}
select:focus,input:focus{
  border-color:#6ea2f0;
  box-shadow:0 0 0 4px rgba(78,133,230,.12);
}
button.calc-btn{
  width:100%;
  margin-top:20px;
  padding:17px;
  border:none;
  border-radius:18px;
  background:linear-gradient(135deg,#1265cf,#4b95f4);
  color:#fff;
  font-size:17px;
  font-weight:800;
  cursor:pointer;
}
.result{
  margin-top:18px;
  padding:18px;
  border-radius:18px;
  background:#f6f9ff;
  border-left:6px solid #2db46f;
  line-height:1.95;
}
.result.result-green{border-left-color:#2db46f}
.result.result-yellow{border-left-color:#d9a700}
.result.result-orange{border-left-color:#ef7d23}
.result.result-red{border-left-color:#d84343}
.error-box{
  display:none;
  margin-top:14px;
  padding:12px;
  border-radius:12px;
  background:#fff1f1;
  color:#c62828;
  font-weight:800;
  border-left:5px solid #e53935;
  line-height:1.7;
}
.info-strong{
  color:#1265cf;
  font-weight:800;
  font-size:17px;
}
.notice-card{
  margin-top:14px;
  padding:14px;
  border-radius:14px;
  background:#eef5ff;
  border-left:5px solid #4a8ee8;
}
.notice-title{
  font-weight:800;
  color:#1d5fba;
  margin-bottom:6px;
}
.notice-text{
  font-size:14px;
  line-height:1.8;
  color:#41556b;
}
.notice-store{
  margin-top:8px;
  font-size:13px;
  color:#64778b;
  font-weight:700;
}
.small-note{
  margin-top:12px;
  font-size:13px;
  color:#66788a;
  line-height:1.8;
}
.result-title{
  font-size:16px;
  font-weight:800;
  color:#1c5fb9;
  margin-bottom:8px;
}
.inline-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:12px;
}
.bar{
  width:100%;
  height:18px;
  border-radius:999px;
  background:#dfe7f1;
  overflow:hidden;
  margin-top:10px;
  box-shadow:inset 0 1px 4px rgba(0,0,0,.08);
}
.bar-fill{
  height:100%;
  width:0%;
  background:linear-gradient(90deg,#22c55e,#84cc16);
  transition:width .4s ease;
}
.section-tip{
  margin-top:14px;
  padding:12px 14px;
  border-radius:14px;
  background:#f6f9ff;
  color:#5b6b7a;
  font-size:13px;
  line-height:1.8;
}
.action-box{
  margin-top:16px;
}
.action-intro{
  font-size:13px;
  margin-bottom:8px;
  color:#5b6b7a;
  line-height:1.8;
}
.line-btn{
  display:block;
  width:100%;
  padding:14px;
  border-radius:14px;
  background:#06c755;
  color:#fff;
  font-weight:800;
  text-align:center;
  text-decoration:none;
  margin-bottom:10px;
}
.call-btn{
  display:block;
  width:100%;
  padding:13px;
  border-radius:14px;
  background:#4a8ee8;
  color:#fff;
  font-weight:800;
  text-align:center;
  text-decoration:none;
}
.test-time{
  font-size:13px;
  color:#8a97a8;
  margin-bottom:8px;
}
.score-badge{
  display:inline-block;
  padding:6px 12px;
  border-radius:999px;
  font-size:13px;
  font-weight:800;
  margin-bottom:10px;
}
.score-green{
  background:#e8f8ee;
  color:#1f8f4d;
}
.score-yellow{
  background:#fff8df;
  color:#b88300;
}
.score-orange{
  background:#fff0e4;
  color:#d96a00;
}
.score-red{
  background:#ffe9e9;
  color:#c93838;
}
.footer-copyright{
  text-align:center;
  font-size:12px;
  color:#8a97a8;
  margin-top:25px;
  padding-bottom:15px;
}
@media (max-width:540px){
  .tab-bar{grid-template-columns:1fr}
  .inline-grid{grid-template-columns:1fr}
}
</style>
</head>
<body>
<div class="wrap">
  <div class="card">
    <div class="title">⚡ 祥真一職人</div>
    <div class="sub">
      電池三項快檢系統<br>
      回程快測｜健康度診斷｜負載掉壓檢測
    </div>

    <div class="system-info">
      <div id="systemTime">系統時間：讀取中...</div>
      <div id="viewCount">📊 本系統已完成 0 次檢測</div>
    </div>

    <div class="tab-bar">
      <button id="tabReturn" class="tab-btn active" onclick="switchTool('return')">🧭 回程快測</button>
      <button id="tabHealth" class="tab-btn" onclick="switchTool('health')">🔧 健康度診斷</button>
      <button id="tabSag" class="tab-btn" onclick="switchTool('sag')">📉 掉壓檢測</button>
    </div>

    <!-- 回程快測 -->
    <div id="returnBox">
      <label>電池類型</label>
      <select id="rt_batteryType" onchange="rt_updateConfig()">
        <option value="lithium">鋰電池</option>
        <option value="lead">鉛酸電池</option>
      </select>

      <label>電池電壓規格</label>
      <select id="rt_voltage" onchange="rt_updateCapacityOptions()"></select>

      <label>電池容量</label>
      <select id="rt_capacity"></select>

      <label>電池使用年齡</label>
      <select id="rt_age"></select>

      <label>騎乘環境</label>
      <select id="rt_road">
        <option value="1">平路通勤</option>
        <option value="0.92">市區走停</option>
        <option value="0.85">山路 / 坡道</option>
      </select>

      <label>騎乘載重類型</label>
      <select id="rt_weight">
        <option value="1.03">單人輕量</option>
        <option value="1">單人一般</option>
        <option value="0.9">單人偏重</option>
        <option value="0.82">雙載 / 載貨</option>
      </select>

      <label>目前靜置電壓</label>
      <input id="rt_nowVoltage" type="number" step="0.1" placeholder="例如 50、63、71">

      <div class="inline-grid">
        <div>
          <label>目的地距離（km）</label>
          <input id="rt_targetDistance" type="number" step="0.1" placeholder="例如 8">
        </div>
        <div>
          <label>行程模式</label>
          <select id="rt_tripMode">
            <option value="oneway">單程</option>
            <option value="round">來回</option>
          </select>
        </div>
      </div>

      <div class="section-tip">
        可不輸入目的地距離，只看剩餘續航估算。<br>
        若有輸入目的地距離，系統會進一步判斷是否可安全到達或來回。
      </div>

      <button class="calc-btn" onclick="rt_calculate()">立即判斷</button>

      <div id="rt_errorBox" class="error-box"></div>
      <div id="rt_result" class="result hidden"></div>
    </div>

    <!-- 健康度診斷 -->
    <div id="healthBox" class="hidden">
      <label>理論滿電續航（km）</label>
      <input id="ht_idealRange" type="number" step="1" placeholder="例如 40">

      <label>實際目前滿電續航（km）</label>
      <input id="ht_actualRange" type="number" step="1" placeholder="例如 15">

      <button class="calc-btn" onclick="ht_calculate()">開始診斷</button>

      <div id="ht_errorBox" class="error-box"></div>
      <div id="ht_result" class="result hidden"></div>
    </div>

    <!-- 掉壓檢測 -->
    <div id="sagBox" class="hidden">
      <label>電池類型</label>
      <select id="sg_batteryType" onchange="sg_updateVoltageOptions()">
        <option value="lithium">鋰電池</option>
        <option value="lead">鉛酸電池</option>
      </select>

      <label>電壓規格</label>
      <select id="sg_voltage"></select>

      <label>靜置電壓</label>
      <input id="sg_restVoltage" type="number" step="0.1" placeholder="例如 52、71">

      <label>加速最低電壓</label>
      <input id="sg_loadVoltage" type="number" step="0.1" placeholder="例如 48、63">

      <button class="calc-btn" onclick="sg_calculate()">開始檢測</button>

      <div id="sg_errorBox" class="error-box"></div>
      <div id="sg_result" class="result hidden"></div>
    </div>
  </div>

  <div class="footer-copyright">© 祥真一職人｜版權所有</div>
</div>

<script>
function switchTool(type){
  document.getElementById("returnBox").classList.toggle("hidden", type!=="return");
  document.getElementById("healthBox").classList.toggle("hidden", type!=="health");
  document.getElementById("sagBox").classList.toggle("hidden", type!=="sag");

  document.getElementById("tabReturn").classList.toggle("active", type==="return");
  document.getElementById("tabHealth").classList.toggle("active", type==="health");
  document.getElementById("tabSag").classList.toggle("active", type==="sag");
}

function updateSystemTime(){
  const now = new Date();
  const y = now.getFullYear();
  const m = String(now.getMonth()+1).padStart(2,'0');
  const d = String(now.getDate()).padStart(2,'0');
  let h = now.getHours();
  const min = String(now.getMinutes()).padStart(2,'0');
  let p = "上午";

  if(h >= 12){
    p = "下午";
    if(h > 12) h -= 12;
  }
  if(h === 0) h = 12;

  document.getElementById("systemTime").innerText =
    `系統時間：${y}/${m}/${d} ${p} ${h}:${min}`;
}

function getNowTime(){
  const now = new Date();
  const y = now.getFullYear();
  const m = String(now.getMonth()+1).padStart(2,'0');
  const d = String(now.getDate()).padStart(2,'0');
  let h = now.getHours();
  const min = String(now.getMinutes()).padStart(2,'0');
  let p = "上午";

  if(h >= 12){
    p = "下午";
    if(h > 12) h -= 12;
  }
  if(h === 0) h = 12;

  return `${y}/${m}/${d} ${p} ${h}:${min}`;
}

function addUseCount(){
  let count = localStorage.getItem("battery_count");
  count = count ? parseInt(count,10) : 0;
  count++;
  localStorage.setItem("battery_count", count);
  updateUseCountDisplay();
}

function updateUseCountDisplay(){
  let count = localStorage.getItem("battery_count");
  count = count ? parseInt(count,10) : 0;
  document.getElementById("viewCount").innerText =
    `📊 本系統已完成 ${count} 次檢測`;
}

function getActionButtons(){
  return `
    <div class="action-box">
      <div class="action-intro">
        若您對目前車況或電池表現有疑慮，歡迎透過 LINE 詢問，也可直接來電。<br>
        📩 提供此檢測結果截圖，可協助您更快判斷與回覆。
      </div>
      <a class="line-btn" href="https://line.me/R/ti/p/~wujiau" target="_blank">
        💬 LINE快速詢問
      </a>
      <a class="call-btn" href="tel:0927372875">
        📞 直接來電 0927-372-875
      </a>
    </div>
  `;
}

function getScoreBadge(percent){
  if(percent >= 70){
    return "<div class='score-badge score-green'>🟢 狀態良好</div>";
  }
  if(percent >= 50){
    return "<div class='score-badge score-yellow'>🟡 建議留意</div>";
  }
  if(percent >= 35){
    return "<div class='score-badge score-orange'>🟠 建議檢測</div>";
  }
  return "<div class='score-badge score-red'>🔴 建議處理</div>";
}

/* 核心資料 */
const li_lithiumData = {
  58:{full:58.0,minInput:43.0},
  60:{full:71.0,minInput:54.0},
  72:{full:84.0,minInput:63.0},
  76:{full:88.2,minInput:66.0}
};

const li_socCurve = {
  58:[[45.0,5],[46.0,8],[47.0,12],[48.0,18],[49.0,28],[50.0,38],[51.0,48],[52.0,58],[53.0,68],[54.0,78],[55.0,86],[56.0,92],[57.0,96],[58.0,100]],
  60:[[56.0,5],[57.0,8],[58.0,12],[59.0,18],[60.0,25],[61.0,35],[62.0,45],[63.0,55],[64.0,65],[65.0,75],[66.0,82],[67.0,88],[68.0,93],[69.0,96],[70.0,98],[71.0,100]],
  72:[[65.5,5],[66.5,8],[67.5,12],[68.5,18],[69.5,25],[71.0,35],[72.5,45],[74.0,55],[75.5,65],[77.0,75],[78.5,82],[80.0,88],[81.5,93],[82.5,96],[83.5,98],[84.0,100]],
  76:[[68.5,5],[69.5,8],[70.5,12],[71.5,18],[72.5,25],[74.0,35],[75.5,45],[77.0,55],[78.5,65],[80.0,75],[81.5,82],[83.0,88],[84.5,93],[86.0,96],[87.0,98],[88.2,100]]
};

const pb_voltageLimit = {
  48:{min:44,max:52},
  60:{min:55,max:65},
  72:{min:66,max:78}
};

function li_getSOC(voltage,type){
  const table = li_socCurve[type];
  for(let i=0;i<table.length-1;i++){
    const v1 = table[i][0], s1 = table[i][1];
    const v2 = table[i+1][0], s2 = table[i+1][1];
    if(voltage>=v1 && voltage<=v2){
      const ratio = (voltage-v1)/(v2-v1);
      return s1 + (s2-s1)*ratio;
    }
  }
  if(voltage<table[0][0]) return 0;
  if(voltage>table[table.length-1][0]) return 100;
  return 0;
}

function rt_interpolate(v,table){
  for(let i=0;i<table.length-1;i++){
    const v1=table[i][0], s1=table[i][1];
    const v2=table[i+1][0], s2=table[i+1][1];
    if(v>=v1 && v<=v2){
      const r=(v-v1)/(v2-v1);
      return s1+(s2-s1)*r;
    }
  }
  if(v<table[0][0]) return 0;
  if(v>table[table.length-1][0]) return 100;
  return 0;
}

function rt_getLeadSOC(voltage,type){
  const tableMap = {
    48:[[42,0],[44,20],[46,40],[48,60],[50,80],[52,100]],
    60:[[53,0],[56,20],[58,40],[60,60],[62,80],[65,100]],
    72:[[63,0],[67,20],[70,40],[72,60],[75,80],[78,100]]
  };
  return rt_interpolate(voltage, tableMap[type]);
}

function rt_clearError(){
  const box = document.getElementById("rt_errorBox");
  box.style.display = "none";
  box.innerHTML = "";
}

function rt_showError(message){
  const box = document.getElementById("rt_errorBox");
  box.style.display = "block";
  box.innerHTML = "⚠ " + message;
}

function rt_updateConfig(){
  const type = document.getElementById("rt_batteryType").value;
  const voltageSelect = document.getElementById("rt_voltage");
  const ageSelect = document.getElementById("rt_age");

  voltageSelect.innerHTML = "";
  ageSelect.innerHTML = "";

  if(type === "lithium"){
    [
      {value:58, text:"48V"},
      {value:60, text:"60V"},
      {value:72, text:"72V"},
      {value:76, text:"76V"}
    ].forEach(item=>{
      const opt = document.createElement("option");
      opt.value = item.value;
      opt.text = item.text;
      voltageSelect.appendChild(opt);
    });

    [
      {value:1.00, text:"全新"},
      {value:0.97, text:"使用3個月"},
      {value:0.93, text:"使用6個月"},
      {value:0.88, text:"使用約1年"},
      {value:0.82, text:"使用1年6個月"},
      {value:0.75, text:"使用2年以上"}
    ].forEach(item=>{
      const opt = document.createElement("option");
      opt.value = item.value;
      opt.text = item.text;
      ageSelect.appendChild(opt);
    });
  }else{
    [
      {value:48, text:"48V"},
      {value:60, text:"60V"},
      {value:72, text:"72V"}
    ].forEach(item=>{
      const opt = document.createElement("option");
      opt.value = item.value;
      opt.text = item.text;
      voltageSelect.appendChild(opt);
    });

    [
      {value:1.00, text:"全新"},
      {value:0.93, text:"使用3個月"},
      {value:0.88, text:"使用6個月"},
      {value:0.80, text:"使用約1年"},
      {value:0.72, text:"使用1年6個月"},
      {value:0.65, text:"使用2年以上"}
    ].forEach(item=>{
      const opt = document.createElement("option");
      opt.value = item.value;
      opt.text = item.text;
      ageSelect.appendChild(opt);
    });
  }

  rt_updateCapacityOptions();
}

function rt_updateCapacityOptions(){
  const type = document.getElementById("rt_batteryType").value;
  const voltage = parseInt(document.getElementById("rt_voltage").value, 10);
  const capacitySelect = document.getElementById("rt_capacity");
  capacitySelect.innerHTML = "";

  let capacities = [];

  if(type === "lithium"){
    if(voltage === 58) capacities = [12,16,20,30,40,50];
    if(voltage === 60) capacities = [20,30,40,50];
    if(voltage === 72) capacities = [30,40,50];
    if(voltage === 76) capacities = [30,40,50];
  }else{
    if(voltage === 48) capacities = [12,13,15,20,24,30];
    if(voltage === 60) capacities = [20,24,30];
    if(voltage === 72) capacities = [20,24,30];
  }

  capacities.forEach(c=>{
    const opt = document.createElement("option");
    opt.value = c;
    opt.text = c + "Ah";
    capacitySelect.appendChild(opt);
  });
}

function rt_getRideAdvice(type, soc, remainRange){
  if(soc <= 10 || remainRange <= 3){
    return {
      level:"🔴 電量偏低",
      text:"目前電量已接近低區間，續航風險較高，建議立即補電或停止遠行。",
      className:"result-red"
    };
  }
  if(soc <= 25 || remainRange <= 8){
    return {
      level:"🟠 電量偏低",
      text:"目前電量偏低，建議避免遠距離騎乘，並優先安排返程或補電。",
      className:"result-orange"
    };
  }
  if(soc < 70){
    return {
      level:"🟡 電量中等",
      text:"目前電量處於中等區間，仍可騎乘，但建議留意回程電量與使用距離。",
      className:"result-yellow"
    };
  }
  return {
    level:"🟢 電量充足",
    text:"目前電量充足，可安心騎乘日常使用，建議仍預留回程電量。",
    className:"result-green"
  };
}

function rt_getRoadText(value){
  if(value === "1") return "平路通勤";
  if(value === "0.92") return "市區走停";
  if(value === "0.85") return "山路 / 坡道";
  return "一般路況";
}

function rt_getWeightText(value){
  if(value === "1.03") return "單人輕量";
  if(value === "1") return "單人一般";
  if(value === "0.9") return "單人偏重";
  if(value === "0.82") return "雙載 / 載貨";
  return "一般載重";
}

function rt_getBarColor(percent){
  if(percent >= 70) return "linear-gradient(90deg,#22c55e,#84cc16)";
  if(percent >= 40) return "linear-gradient(90deg,#facc15,#f59e0b)";
  return "linear-gradient(90deg,#ef4444,#f97316)";
}

function rt_getDestinationJudge(remainRange, needDistance){
  const safeNeedDistance = needDistance * 1.3;
  const diff = remainRange - safeNeedDistance;
  const ratio = remainRange / safeNeedDistance;

  if(ratio >= 1.15){
    return { title:"🟢 可安全到達", text:"續航餘量較充足，可安心前往目的地。", diff:diff };
  }
  if(ratio >= 1.0){
    return { title:"🟡 可到但需保留電量", text:"理論上可完成行程，但建議避免繞路、重載或激烈騎乘。", diff:diff };
  }
  if(ratio >= 0.85){
    return { title:"🟠 接近續航極限", text:"目前距離已接近安全極限，建議先補電或調整行程安排。", diff:diff };
  }
  return { title:"🔴 不建議前往", text:"以目前條件來看續航不足，途中可能出現電量不足或無力情況。", diff:diff };
}

function rt_calculate(){
  rt_clearError();

  const type = document.getElementById("rt_batteryType").value;
  const voltageType = parseInt(document.getElementById("rt_voltage").value);
  const cap = parseFloat(document.getElementById("rt_capacity").value);
  const ageFactor = parseFloat(document.getElementById("rt_age").value);
  const roadSelect = document.getElementById("rt_road");
  const weightSelect = document.getElementById("rt_weight");
  const roadFactor = parseFloat(roadSelect.value);
  const weightFactor = parseFloat(weightSelect.value);
  const voltage = parseFloat(document.getElementById("rt_nowVoltage").value);
  const targetDistanceText = document.getElementById("rt_targetDistance").value.trim();
  const tripMode = document.getElementById("rt_tripMode").value;

  if(isNaN(voltage)){
    rt_showError("請輸入目前靜置電壓");
    return;
  }

  if(targetDistanceText !== ""){
    const targetDistanceValue = parseFloat(targetDistanceText);
    if(isNaN(targetDistanceValue) || targetDistanceValue <= 0){
      rt_showError("目的地距離請輸入正確的公里數");
      return;
    }
  }

  let soc = 0;
  let minV = 0;
  let maxV = 0;

  if(type==="lithium"){
    soc = li_getSOC(voltage, voltageType);
    minV = li_lithiumData[voltageType].minInput;
    maxV = li_lithiumData[voltageType].full;
  }else{
    soc = rt_getLeadSOC(voltage, voltageType);
    minV = pb_voltageLimit[voltageType].min;
    maxV = pb_voltageLimit[voltageType].max;
  }

  if(voltage < minV || voltage > maxV){
    rt_showError("此規格可輸入電壓範圍為 " + minV + "V ~ " + maxV + "V");
    return;
  }

  addUseCount();

  const rawWh = voltageType * cap;
  const efficiency = type==="lithium" ? 0.90 : 0.78;
  const usableWh = rawWh * efficiency * (soc/100) * ageFactor * roadFactor * weightFactor;

  let consumption = 25;
  if(voltageType===48 || voltageType===58) consumption = 22;
  if(voltageType===60) consumption = 25;
  if(voltageType===72 || voltageType===76) consumption = 30;

  const remainRange = usableWh / consumption;
  const advice = rt_getRideAdvice(type, soc, remainRange);
  const roadText = rt_getRoadText(roadSelect.value);
  const weightText = rt_getWeightText(weightSelect.value);

  const resultBox = document.getElementById("rt_result");
  resultBox.className = "result " + advice.className;
  resultBox.classList.remove("hidden");

  let html =
    "<div class='test-time'>檢測時間：" + getNowTime() + "</div>" +
    getScoreBadge(soc) +
    "<div class='result-title'>🔋 回程續航評估結果</div>" +
    "目前剩餘電量：約 <span class='info-strong'>" + soc.toFixed(1) + "%</span><br>" +
    "<div class='bar'><div class='bar-fill' id='rt_socBar'></div></div>" +
    "預估剩餘續航：約 <span class='info-strong'>" + remainRange.toFixed(1) + " km</span><br>" +
    "騎乘判斷：<span class='info-strong'>" + advice.level + "</span><br>" +
    "建議說明：" + advice.text + "<br>";

  if(targetDistanceText !== ""){
    const targetDistance = parseFloat(targetDistanceText);
    const needDistance = tripMode === "round" ? targetDistance * 2 : targetDistance;
    const tripText = tripMode === "round" ? "來回" : "單程";
    const destJudge = rt_getDestinationJudge(remainRange, needDistance);

    const safeDistance = needDistance * 1.3;
    const diffText = destJudge.diff >= 0
      ? "剩餘 " + destJudge.diff.toFixed(1) + " km"
      : "不足 " + Math.abs(destJudge.diff).toFixed(1) + " km";

    let extraTip = "";
    if(tripMode === "round" && remainRange >= targetDistance && remainRange < safeDistance){
      extraTip = "<br>👉 單程可能仍可到達，但若考量返程與安全餘量，建議先補電再出發。";
    }

    html +=
      "<br><div class='result-title'>📍 目的地可達判斷</div>" +
      "輸入目的地距離：<span class='info-strong'>" + targetDistance.toFixed(1) + " km</span><br>" +
      "行程模式：<span class='info-strong'>" + tripText + "</span><br>" +
      "本次需求距離：<span class='info-strong'>" + needDistance.toFixed(1) + " km</span><br>" +
      "安全建議距離：<span class='info-strong'>" + safeDistance.toFixed(1) + " km</span><br>" +
      "判斷結果：<span class='info-strong'>" + destJudge.title + "</span><br>" +
      "續航差額：<span class='info-strong'>" + diffText + "</span><br>" +
      "目的地建議：" + destJudge.text +
      extraTip +
      "<div class='small-note'>⚠ 本判斷已預留安全係數，若近期常出現「理論可到、實際騎不到」，可能為電池老化、虛電或負載掉壓偏大，建議安排檢測。</div>";
  }

  html +=
    "<br><div class='small-note'>" +
    "本次估算條件：<br>" +
    "騎乘環境：" + roadText + "<br>" +
    "載重類型：" + weightText + "<br><br>" +
    "※ 本系統為快速估算工具，實際續航會因騎乘習慣、路況、胎壓、車況與電池老化有所差異。" +
    "</div>" +
    "<div class='notice-card'>" +
    "<div class='notice-title'>到店檢測提醒</div>" +
    "<div class='notice-text'>若車輛已出現明顯掉速、頓挫、續航縮短，或目的地判斷接近極限，歡迎到店免費檢測。</div>" +
    "<div class='notice-store'>台南永康｜祥真一職人二輪電動車</div>" +
    "</div>" +
    getActionButtons();

  resultBox.innerHTML = html;

  const bar = document.getElementById("rt_socBar");
  if(bar){
    const safeSoc = Math.max(0, Math.min(100, soc));
    bar.style.width = safeSoc + "%";
    bar.style.background = rt_getBarColor(safeSoc);
  }
}

function ht_clearError(){
  const box = document.getElementById("ht_errorBox");
  box.style.display = "none";
  box.innerHTML = "";
}

function ht_showError(message){
  const box = document.getElementById("ht_errorBox");
  box.style.display = "block";
  box.innerHTML = "⚠ " + message;
}

function ht_getHealthLevel(health){
  if(health >= 85){
    return {
      badge:"🟢 健康良好",
      advice:"目前續航表現良好，電池狀況正常。",
      className:"result-green"
    };
  }
  if(health >= 70){
    return {
      badge:"🟡 已有些微衰退",
      advice:"電池已有些微衰退，建議持續觀察使用狀況。",
      className:"result-yellow"
    };
  }
  if(health > 50){
    return {
      badge:"🟠 明顯老化",
      advice:"電池效能已明顯下降，建議安排檢測或評估更換。",
      className:"result-orange"
    };
  }
  return {
    badge:"🔴 建議更換",
    advice:"電池衰退幅度已高，建議儘快檢測或評估更換，以避免續航突然不足。",
    className:"result-red"
  };
}

function ht_calculate(){
  ht_clearError();

  const ideal = parseFloat(document.getElementById("ht_idealRange").value);
  const actual = parseFloat(document.getElementById("ht_actualRange").value);

  if(isNaN(ideal) || ideal <= 0){
    ht_showError("請輸入正確的理論滿電續航里程");
    return;
  }
  if(isNaN(actual) || actual <= 0){
    ht_showError("請輸入正確的實際目前滿電續航里程");
    return;
  }
  if(actual > ideal){
    ht_showError("實際續航不應大於理論續航，請重新確認輸入值");
    return;
  }

  addUseCount();

  const health = (actual / ideal) * 100;
  const level = ht_getHealthLevel(health);

  const resultBox = document.getElementById("ht_result");
  resultBox.className = "result " + level.className;
  resultBox.classList.remove("hidden");

  resultBox.innerHTML =
    "<div class='test-time'>檢測時間：" + getNowTime() + "</div>" +
    getScoreBadge(health) +
    "<div class='result-title'>🔧 電池健康度診斷結果</div>" +
    "理論滿電續航：<span class='info-strong'>" + ideal.toFixed(0) + " km</span><br>" +
    "實際目前續航：<span class='info-strong'>" + actual.toFixed(0) + " km</span><br>" +
    "電池健康度：<span class='info-strong'>" + health.toFixed(1) + "%</span><br>" +
    "<div class='bar'><div class='bar-fill' id='ht_healthBar'></div></div>" +
    "健康判定：<span class='info-strong'>" + level.badge + "</span><br>" +
    "建議說明：" + level.advice +
    "<div class='small-note'>※ 此功能以續航衰退比例做快速估算，實際仍會受路況、載重、胎壓、溫度與騎乘習慣影響。<br>※ 當健康度低於 50%，實際騎乘時續航衰退通常會更明顯。</div>" +
    "<div class='notice-card'>" +
    "<div class='notice-title'>到店檢測提醒</div>" +
    "<div class='notice-text'>若實際續航明顯低於原本表現，歡迎到店免費檢測。</div>" +
    "<div class='notice-store'>台南永康｜祥真一職人二輪電動車</div>" +
    "</div>" +
    getActionButtons();

  const bar = document.getElementById("ht_healthBar");
  if(bar){
    const safeHealth = Math.max(0, Math.min(100, health));
    bar.style.width = safeHealth + "%";
    bar.style.background = rt_getBarColor(safeHealth);
  }
}

function sg_clearError(){
  const box = document.getElementById("sg_errorBox");
  box.style.display = "none";
  box.innerHTML = "";
}

function sg_showError(message){
  const box = document.getElementById("sg_errorBox");
  box.style.display = "block";
  box.innerHTML = "⚠ " + message;
}

function sg_updateVoltageOptions(){
  const type = document.getElementById("sg_batteryType").value;
  const voltageSelect = document.getElementById("sg_voltage");
  voltageSelect.innerHTML = "";

  if(type==="lithium"){
    [
      {value:58,text:"48V"},
      {value:60,text:"60V"},
      {value:72,text:"72V"},
      {value:76,text:"76V"}
    ].forEach(item=>{
      const opt = document.createElement("option");
      opt.value = item.value;
      opt.text = item.text;
      voltageSelect.appendChild(opt);
    });
  }else{
    [
      {value:48,text:"48V"},
      {value:60,text:"60V"},
      {value:72,text:"72V"}
    ].forEach(item=>{
      const opt = document.createElement("option");
      opt.value = item.value;
      opt.text = item.text;
      voltageSelect.appendChild(opt);
    });
  }
}

function sg_getResult(type, sag){
  if(type==="lithium"){
    if(sag <= 3){
      return {
        level:"🟢 正常",
        text:"負載掉壓屬正常範圍，電池輸出表現正常。",
        className:"result-green",
        detail:"目前負載表現正常，暫無明顯異常掉壓現象，可持續觀察日常騎乘狀況。"
      };
    }
    if(sag <= 6){
      return {
        level:"🟡 稍大",
        text:"掉壓略大，建議持續觀察電池狀況與實際續航表現。",
        className:"result-yellow",
        detail:"可能原因：<br>・電池內阻開始上升<br>・電芯初期老化<br>・負載下輸出能力略降<br><br>⚠ 若近期有爬坡無力或起步頓挫感，建議優先檢測電池內阻。"
      };
    }
    if(sag <= 9){
      return {
        level:"🟠 偏大",
        text:"掉壓明顯偏大，可能已有老化、內阻升高或虛電現象。",
        className:"result-orange",
        detail:"可能原因：<br>・電池內阻上升<br>・電芯老化<br>・負載下輸出能力下降<br><br>⚠ 若近期有爬坡無力或起步頓挫感，建議優先檢測電池內阻。"
      };
    }
    return {
      level:"🔴 異常",
      text:"掉壓異常偏大，可能造成無力、頓挫或續航明顯下降，建議安排檢測。",
      className:"result-red",
      detail:"可能原因：<br>・電池內阻明顯升高<br>・電芯老化嚴重<br>・負載下輸出能力不足<br><br>⚠ 若近期有爬坡無力或起步頓挫感，建議盡快安排檢測。"
    };
  }else{
    if(sag <= 4){
      return {
        level:"🟢 正常",
        text:"負載掉壓屬正常範圍，電池輸出尚可。",
        className:"result-green",
        detail:"目前負載表現正常，暫無明顯異常掉壓現象，可持續觀察日常騎乘狀況。"
      };
    }
    if(sag <= 7){
      return {
        level:"🟡 稍大",
        text:"掉壓略大，鉛酸電池可再持續觀察後續續航與爬坡表現。",
        className:"result-yellow",
        detail:"可能原因：<br>・電池內阻開始上升<br>・容量衰退初期<br>・負載表現略降<br><br>⚠ 若近期有爬坡無力或起步頓挫感，建議優先檢測電池內阻。"
      };
    }
    if(sag <= 10){
      return {
        level:"🟠 偏大",
        text:"掉壓偏大，可能已有老化或負載表現不佳情況。",
        className:"result-orange",
        detail:"可能原因：<br>・電池內阻上升<br>・容量衰退<br>・負載下輸出能力下降<br><br>⚠ 若近期有爬坡無力或起步頓挫感，建議優先檢測電池內阻。"
      };
    }
    return {
      level:"🔴 異常",
      text:"掉壓異常偏大，鉛酸電池在負載下可能明顯虛弱，建議安排檢測或評估更換。",
      className:"result-red",
      detail:"可能原因：<br>・電池內阻明顯升高<br>・電池老化嚴重<br>・負載能力不足<br><br>⚠ 若近期有爬坡無力或起步頓挫感，建議盡快安排檢測。"
      };
  }
}

function sg_calculate(){
  sg_clearError();

  const type = document.getElementById("sg_batteryType").value;
  const voltageType = parseInt(document.getElementById("sg_voltage").value);
  const restVoltage = parseFloat(document.getElementById("sg_restVoltage").value);
  const loadVoltage = parseFloat(document.getElementById("sg_loadVoltage").value);

  if(isNaN(restVoltage) || isNaN(loadVoltage)){
    sg_showError("請輸入完整的靜置電壓與加速最低電壓");
    return;
  }
  if(loadVoltage > restVoltage){
    sg_showError("加速最低電壓不應高於靜置電壓，請重新確認輸入值");
    return;
  }

  let minV = 0;
  let maxV = 0;

  if(type==="lithium"){
    minV = li_lithiumData[voltageType].minInput;
    maxV = li_lithiumData[voltageType].full;
  }else{
    minV = pb_voltageLimit[voltageType].min;
    maxV = pb_voltageLimit[voltageType].max;
  }

  if(restVoltage < minV || restVoltage > maxV){
    sg_showError("靜置電壓可輸入範圍為 " + minV + "V ~ " + maxV + "V");
    return;
  }

  addUseCount();

  const sag = restVoltage - loadVoltage;
  const result = sg_getResult(type, sag);

  const resultBox = document.getElementById("sg_result");
  resultBox.className = "result " + result.className;
  resultBox.classList.remove("hidden");

  const scoreValue = type==="lithium"
    ? Math.max(0, 100 - sag * 10)
    : Math.max(0, 100 - sag * 12);

  resultBox.innerHTML =
    "<div class='test-time'>檢測時間：" + getNowTime() + "</div>" +
    getScoreBadge(scoreValue) +
    "<div class='result-title'>📉 負載掉壓檢測結果</div>" +
    "靜置電壓：<span class='info-strong'>" + restVoltage.toFixed(1) + " V</span><br>" +
    "加速最低電壓：<span class='info-strong'>" + loadVoltage.toFixed(1) + " V</span><br>" +
    "掉壓幅度：<span class='info-strong'>" + sag.toFixed(1) + " V</span><br>" +
    "診斷結果：<span class='info-strong'>" + result.level + "</span><br>" +
    "建議說明：" + result.text +
    "<div class='small-note'>" + result.detail + "<br><br>※ 本功能適合現場檢測或車主反映「有電但一催就無力」時作為快速判斷參考。</div>" +
    "<div class='notice-card'>" +
    "<div class='notice-title'>到店檢測提醒</div>" +
    "<div class='notice-text'>若車輛已出現明顯掉速、頓挫或負載掉壓過大，歡迎到店免費檢測。</div>" +
    "<div class='notice-store'>台南永康｜祥真一職人二輪電動車</div>" +
    "</div>" +
    getActionButtons();
}

window.onload = function(){
  rt_updateConfig();
  sg_updateVoltageOptions();
  switchTool("return");
  updateSystemTime();
  updateUseCountDisplay();
  setInterval(updateSystemTime,60000);
};
</script>
</body>
</html>
