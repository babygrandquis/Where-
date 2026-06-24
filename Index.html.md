#   
<!DOCTYPE html>  
<html>  
<head>  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>Wealth Warriors Pro</title>  
  
<link rel="manifest" href="manifest.json">  
  
<style>  
body{  
margin:0;  
font-family:Arial;  
background:#0b1220;  
color:white;  
}  
  
.header{  
background:#123a7a;  
padding:15px;  
text-align:center;  
font-weight:bold;  
}  
  
.card{  
background:#111a2e;  
margin:10px;  
padding:12px;  
border-radius:10px;  
}  
  
button{  
width:100%;  
padding:12px;  
margin-top:8px;  
border:none;  
border-radius:8px;  
font-weight:bold;  
cursor:pointer;  
}  
  
.win{background:#39d353;}  
.loss{background:#dc2626;color:white;}  
.reset{background:#f59e0b;}  
.new{background:#2563eb;color:white;}  
</style>  
</head>  
  
<body>  
  
<div class="header">WEALTH WARRIORS PRO</div>  
  
<div class="card">  
Balance: <h2 id="bal">$85.00</h2>  
Next Trade: <h2 id="trd">$2.80</h2>  
Recovery Step: <span id="step">0</span>  
</div>  
  
<div class="card">  
<button class="win" onclick="win()">WIN</button>  
<button class="loss" onclick="loss()">LOSS</button>  
<button class="reset" onclick="reset()">RESET</button>  
<button class="new" onclick="newSession()">NEW SESSION</button>  
</div>  
  
<div class="card">  
Stats:  
<div>Total Trades: <span id="total">0</span></div>  
<div>Wins: <span id="wins">0</span></div>  
<div>Losses: <span id="losses">0</span></div>  
</div>  
  
<script>  
  
let balance=85;  
let trade=2.8;  
let step=0;  
let wins=0;  
let losses=0;  
let total=0;  
  
function update(){  
document.getElementById("bal").innerText="$"+balance.toFixed(2);  
document.getElementById("trd").innerText="$"+trade.toFixed(2);  
document.getElementById("step").innerText=step;  
document.getElementById("wins").innerText=wins;  
document.getElementById("losses").innerText=losses;  
document.getElementById("total").innerText=total;  
}  
  
function win(){  
balance += trade*0.92;  
trade = 2.8;  
step = 0;  
wins++;  
total++;  
update();  
}  
  
function loss(){  
balance -= trade;  
trade *= 1.55;  
step++;  
losses++;  
total++;  
update();  
}  
  
function reset(){  
trade=2.8;  
step=0;  
update();  
}  
  
function newSession(){  
balance=85;  
trade=2.8;  
step=0;  
wins=0;  
losses=0;  
total=0;  
update();  
}  
  
update();  
</script>  
  
</body>  
</html>  
