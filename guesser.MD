<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Satellite City Guesser</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.css">
<style>
:root{--bg:#10151c;--panel:#18202b;--text:#e8edf3;--muted:#8d9bab;--accent:#4ea1ff;--good:#3ecf8e;--bad:#ff6b6b}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--text);font-family:system-ui,-apple-system,"Segoe UI",sans-serif;display:flex;flex-direction:column;height:100vh}
header{display:flex;justify-content:space-between;align-items:center;padding:10px 16px;background:var(--panel);font-size:15px}
header b{font-size:17px}
#map{flex:1;min-height:200px;background:#000}
#panel{background:var(--panel);padding:14px 16px;display:flex;flex-direction:column;gap:10px}
#msg{min-height:22px;color:var(--muted)}
#msg.good{color:var(--good)}#msg.bad{color:var(--bad)}
.row{display:flex;gap:8px}
input{flex:1;padding:11px;border-radius:8px;border:1px solid #2c3948;background:#0d1218;color:var(--text);font-size:16px}
button{padding:11px 16px;border:0;border-radius:8px;background:var(--accent);color:#06121f;font-weight:600;font-size:15px;cursor:pointer}
button.alt{background:#2c3948;color:var(--text)}
#end{display:none;text-align:center;padding:8px}
#end h2{margin:4px 0}
</style>
</head>
<body>
<header><b>Satellite City Guesser</b><span id="stat"></span></header>
<div id="map"></div>
<div id="panel">
  <div id="msg"></div>
  <div class="row" id="guessRow">
    <input id="inp" list="cities" placeholder="Which US city is this?" autocomplete="off">
    <datalist id="cities"></datalist>
    <button id="go">Guess</button>
    <button class="alt" id="skip">Give up</button>
  </div>
  <div class="row" id="nextRow" style="display:none"><button id="next" style="flex:1">Next city</button></div>
  <div id="end"><h2 id="final"></h2><button id="again">Play again</button></div>
</div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.js"></script>
<script>
// Cities with population over 100k: name, state, lat, lon
const DATA=`New York,NY,40.71,-74.01
Los Angeles,CA,34.05,-118.24
Chicago,IL,41.88,-87.63
Houston,TX,29.76,-95.37
Phoenix,AZ,33.45,-112.07
Philadelphia,PA,39.95,-75.17
San Antonio,TX,29.42,-98.49
San Diego,CA,32.72,-117.16
Dallas,TX,32.78,-96.80
San Jose,CA,37.34,-121.89
Austin,TX,30.27,-97.74
Jacksonville,FL,30.33,-81.66
Fort Worth,TX,32.75,-97.33
Columbus,OH,39.96,-83.00
Charlotte,NC,35.23,-80.84
San Francisco,CA,37.77,-122.42
Indianapolis,IN,39.77,-86.16
Seattle,WA,47.61,-122.33
Denver,CO,39.74,-104.99
Washington,DC,38.91,-77.04
Boston,MA,42.36,-71.06
El Paso,TX,31.76,-106.49
Nashville,TN,36.16,-86.78
Detroit,MI,42.33,-83.05
Oklahoma City,OK,35.47,-97.52
Portland,OR,45.52,-122.68
Las Vegas,NV,36.17,-115.14
Memphis,TN,35.15,-90.05
Louisville,KY,38.25,-85.76
Baltimore,MD,39.29,-76.61
Milwaukee,WI,43.04,-87.91
Albuquerque,NM,35.08,-106.65
Tucson,AZ,32.22,-110.97
Fresno,CA,36.74,-119.79
Sacramento,CA,38.58,-121.49
Kansas City,MO,39.10,-94.58
Atlanta,GA,33.75,-84.39
Omaha,NE,41.26,-95.93
Colorado Springs,CO,38.83,-104.82
Raleigh,NC,35.78,-78.64
Miami,FL,25.76,-80.19
Virginia Beach,VA,36.85,-75.98
Oakland,CA,37.80,-122.27
Minneapolis,MN,44.98,-93.27
Tulsa,OK,36.15,-95.99
Tampa,FL,27.95,-82.46
New Orleans,LA,29.95,-90.07
Wichita,KS,37.69,-97.34
Cleveland,OH,41.50,-81.69
Honolulu,HI,21.31,-157.86
Anchorage,AK,61.22,-149.90
Pittsburgh,PA,40.44,-79.99
Cincinnati,OH,39.10,-84.51
St. Louis,MO,38.63,-90.20
Orlando,FL,28.54,-81.38
Salt Lake City,UT,40.76,-111.89
Buffalo,NY,42.89,-78.88
Boise,ID,43.62,-116.20
Richmond,VA,37.54,-77.44
Spokane,WA,47.66,-117.43
Des Moines,IA,41.59,-93.62
Birmingham,AL,33.52,-86.80
Rochester,NY,43.16,-77.61
Lexington,KY,38.04,-84.50
Reno,NV,39.53,-119.81
Madison,WI,43.07,-89.40
Baton Rouge,LA,30.45,-91.15
Savannah,GA,32.08,-81.09
Providence,RI,41.82,-71.41
Charleston,SC,32.78,-79.93
Knoxville,TN,35.96,-83.92
Little Rock,AR,34.75,-92.29
Jackson,MS,32.30,-90.18
Fargo,ND,46.88,-96.79
Sioux Falls,SD,43.55,-96.73
Lincoln,NE,40.81,-96.70
Salem,OR,44.94,-123.04
Mobile,AL,30.69,-88.04
Huntsville,AL,34.73,-86.59
Chattanooga,TN,35.05,-85.31
Hartford,CT,41.76,-72.67
Lubbock,TX,33.58,-101.86
Corpus Christi,TX,27.80,-97.40
Tacoma,WA,47.25,-122.44
Norfolk,VA,36.85,-76.29
Akron,OH,41.08,-81.52
Durham,NC,35.99,-78.90
Grand Rapids,MI,42.96,-85.67
Springfield,MO,37.21,-93.29
Bakersfield,CA,35.37,-119.02
Stockton,CA,37.96,-121.29
Long Beach,CA,33.77,-118.19
Newark,NJ,40.74,-74.17
Jersey City,NJ,40.73,-74.06
St. Petersburg,FL,27.77,-82.64
Fort Wayne,IN,41.08,-85.14`;
const C=DATA.split("\n").map(l=>{const[n,s,a,o]=l.split(",");return{n,s,lat:+a,lon:+o}});
const TOTAL=10, $=id=>document.getElementById(id);
const norm=s=>s.toLowerCase().replace(/\./g,"").replace(/\bsaint\b/,"st").trim();
$("cities").innerHTML=C.map(c=>`<option value="${c.n}, ${c.s}">`).join("");

const map=L.map("map",{zoomControl:false,dragging:false,scrollWheelZoom:false,doubleClickZoom:false,boxZoom:false,keyboard:false,touchZoom:false});
L.tileLayer("https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}",{maxZoom:17,attribution:"Imagery © Esri"}).addTo(map);

let order,round,score,cur,tries,done,center;
function start(){
  order=[...C].sort(()=>Math.random()-.5).slice(0,TOTAL);round=0;score=0;
  $("end").style.display="none";nextRound();
}
function setMsg(t,k){const m=$("msg");m.textContent=t;m.className=k||""}
function stat(){$("stat").textContent=`Round ${round}/${TOTAL}  ·  Score ${score}`}
function nextRound(){
  if(round>=TOTAL){
    $("guessRow").style.display="none";$("nextRow").style.display="none";
    $("end").style.display="block";
    $("final").textContent=`Final score: ${score} / ${TOTAL*3}`;setMsg("");return;
  }
  cur=order[round++];tries=0;done=false;
  const j=()=>(Math.random()-.5)*.08;
  center=[cur.lat+j(),cur.lon+j()];
  map.setView(center,11,{animate:false});
  $("inp").value="";$("guessRow").style.display="flex";$("nextRow").style.display="none";
  setMsg("Worth 3 points. Wrong guesses reveal hints and lower the score.");
  stat();$("inp").focus();
}
function reveal(pts,won){
  done=true;score+=pts;stat();
  map.setView(center,11,{animate:false});
  setMsg(won?`Correct! It's ${cur.n}, ${cur.s}. +${pts}`:`It was ${cur.n}, ${cur.s}.`,won?"good":"bad");
  $("guessRow").style.display="none";$("nextRow").style.display="flex";
  $("next").textContent=round>=TOTAL?"See results":"Next city";
}
function wrong(){
  tries++;
  if(tries===1){map.setView(center,9,{animate:false});setMsg("Not quite. Zoomed out for you. 2 points left.","bad")}
  else if(tries===2){setMsg(`Not quite. Hint: it's in ${cur.s}. 1 point left.`,"bad")}
  else reveal(0,false);
}
function guess(){
  if(done)return;
  const raw=$("inp").value;if(!raw.trim())return;
  const[parts,st]=raw.split(",").map(x=>x.trim());
  const ok=norm(parts)===norm(cur.n)&&(!st||st.toUpperCase()===cur.s);
  if(ok)reveal(3-tries,true);else{$("inp").value="";wrong()}
}
$("go").onclick=guess;
$("inp").addEventListener("keydown",e=>{if(e.key==="Enter")guess()});
$("skip").onclick=()=>{if(!done)reveal(0,false)};
$("next").onclick=nextRound;
$("again").onclick=()=>{$("guessRow").style.display="flex";start()};
start();
</script>
</body>
</html>
